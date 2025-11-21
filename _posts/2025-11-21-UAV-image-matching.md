---
layout: post
title: "From points and pixels to processes: Evaluating UAV image matching algorithms"
date: 2025-11-21 10:00:00 +02:00
author: "Rachel Jade Kuzmich"
categories: [blog]
tags: [ecology, remote sensing, time series, UAV, image matching]
excerpt: "High-resolution UAV imagery can transform ecological time series. Choice of image matching algorithm influences radiometric and geometric consistency, affecting change detection and ecological interpretation."
---

## Building reliable ecological time series from UAV imagery

Remote sensing time series are a powerful tool for understanding ecological change. In a previous post, I discussed how repeated observations across space and time allow us to move from detecting patterns in a single image to understanding the processes driving ecosystem dynamics. Time series approaches rely on consistent imagery, because any artificial differences between acquisitions due to differences in illumination, sensor properties, or processing artifacts can be misinterpreted as ecological change.

High-resolution uncrewed aerial vehicle (UAV) imagery offers unprecedented detail, enabling tree- or stand-level analyses. Yet forest environments pose unique challenges: dense canopies create shadows and occlusion, while repetitive foliage patterns can confuse feature detection and image alignment. Time series are particularly difficult in these settings because observed differences may result from real ecological change, variations in lighting, or inconsistencies in image processing, making rigorous algorithm evaluation essential.

Not all orthomosaics are created equal. Even subtle differences in how images are stitched together can introduce radiometric and geometric variability, which could impact subsequent ecological analyses. This post explores how image matching algorithm-induced variability can impact change detection in UAV-derived time series.

---

## Evaluating image matching algorithms in the boreal forest

To explore these issues, I used UAV data collected in the boreal forest in southeast of Norway. Data were collected with a DJI Mavic 3 Multispectral camera, capturing red, near-infrared, red-edge, and green bands over a site that included both forested and cleared areas. Orthomosaics were generated using five feature matching algorithms in OpenDroneMap. Side note, I am a big fan of opensource software like OpenDroneMap for scientific accessibility, reproducibility and transparency. Algorithm performance was assessed using image intrinsic information and a spatially blocked comparison.

---

## What these algorithms do

- SIFT (Scale-Invariant Feature Transform): detects distinctive keypoints (e.g., corners) across multiple image scales and assigns orientations based on local gradients, making them rotation-invariant. Builds descriptors from gradient orientations around each keypoint, capturing local texture and intensity patterns. Robust to changes in scale, rotation, and moderate illumination differences. Performs well in forests with varied tree shapes, shadows, or canopy textures.
- DSPSIFT (Domain-Size Pooled SIFT): extends SIFT by sampling keypoints more densely and computing descriptors across multiple patch sizes. This improves matching in areas with few distinctive features, such as homogeneous canopy sections in UAV forest mosaics. Maintains the same robustness to scale, rotation, and illumination as standard SIFT.
- HAHOG (Hessian-Affine and Histogram of Oriented Gradients): finds blob-like keypoints using the Hessian matrix, capturing sharp intensity changes in multiple directions (e.g., treetops, branches). Keypoints are affine-normalized for geometric robustness. HOG descriptors encode local gradients around keypoints, highlighting edges, tree crowns, shadows, and branching structures, providing a richer structural representation than raw pixel values.
- ORB (Oriented Features from Accelerated Segment Test (FAST) and Rotated Binary Robust Independent Elementary Features (BRIEF)): detects keypoints using FAST (Features from Accelerated Segment Test), which identifies corners or high-contrast pixels quickly by comparing each pixel to its surrounding circle of pixels. Describes keypoints with BRIEF (Binary Robust Independent Elementary Features), a compact binary descriptor based on intensity comparisons between pixel pairs. Orientation is added for rotation invariance, and a multi-scale pyramid provides some scale invariance. Fast and lightweight, suitable for real-time applications, but may miss fine or repetitive textures, such as uniform canopy patches. 
- AKAZE: detects keypoints in nonlinear scale spaces, capturing fine-scale features that linear approaches may miss. Describes keypoints using gradient-based KAZE descriptors, robust to small geometric distortions. Performs well for subtle canopy textures but is more sensitive to shadows and illumination changes. 

While all five methods have the shared purpose of detecting and describing features for image matching, they emphasize different aspects, such as keypoint density, geometric invariance, or radiometric stability. These differences shape how well each algorithm handles complex forest structure in UAV mosaics.

---

## How OpenDroneMap processes UAV images (very briefly)

OpenDroneMap automates the conversion of overlapping UAV images into orthomosaics:  

1. Load & prepare the dataset: validate images, extract metadata, and split as needed into overlapping submodels for parallel processing
2. Structure from Motion: detect and match keypoints across images, use matches to estimate camera positions and build a sparse 3D point cloud via bundle adjustment (this is where all those algorithms that we are talking about in this post come in)
3. Generate a dense point cloud: sparse reconstruction is expanded into a dense 3D point cloud using multi-view stereo across overlapping images
4. Filter the 3D point cloud: remove noise and outlier points to create a cleaner point cloud suitable for downstream modelling
5. Create a 3D mesh & apply texture: a mesh surface is built from the filtered point cloud, and textures from the original images are projected to produce a detailed 3D model
6. Georeference the reconstruction: the model is transformed into real-world coordinates using image GPS data or ground control points (GCPs)
7. Generate DEMs & orthomosaics: compute DSMs and DTMs, then produce a high-resolution orthomosaic by stitching and orthorectifying all images
8. Reporting & final processing: the system outputs a summary report and completes any optional cleanup or merging of submodels

---

## A block-wise approach for radiometric consistency

So, once all of my orthomosaics were generated in OpenDroneMap using the different algorithms, I then imported these into R and implemented a block-wise workflow to compare their radiometric agreement:

1. Standardize mosaics: crop all orthomosaics to a common extent and resample them to a shared pixel grid
2. Divide the scene into blocks: generate 10-m blocks across the study area and compute block-level metrics (mean, SD, correlation, RMSE, MAE) for each algorithm pair
3. Summarize radiometric differences: aggregate block-wise results to the algorithm level and normalize RMSE/MAE by the reflectance IQR to express algorithm-induced differences relative to typical scene variability, providing a scene-specific benchmark.

---

## Results: OpenDroneMap reconstruction results

Across the five mosaics, OpenDroneMap’s internal reports showed clear differences in reconstruction quality.

- SIFT, DSPSIFT, and HAHOG consistently produced the strongest geometric solutions: all images were used, reprojection errors were low, and the resulting orthomosaics appeared smooth with minimal seam lines. These algorithms captured canopy structure well and maintained stable brightness patterns across the scene.
- AKAZE successfully reconstructed the full dataset but introduced more pixel-level noise and subtle brightness shifts, especially in shadowed areas.
- ORB struggled the most. Several images failed to align, and the mosaic showed visible blockiness and tonal discontinuities—symptoms of unstable feature matching in the forest canopy.

---
## Results: Block-wise comparisons in R

To examine these differences using only the orthomosaics themselves, I compared each algorithm pair block by block. In this context, “RMSE” is simply the root-mean-square difference between two orthomosaics, not error. The patterns closely matched the ODM results:

- SIFT, DSPSIFT, and HAHOG showed strong mutual agreement, with similar reflectance patterns across blocks and high correlations. Their radiometric differences were small relative to the natural variation present in the scene.
- AKAZE agreed less consistently, with higher block-level differences that approached the scale of real spectral changes.
- ORB deviated most strongly from all others, with algorithm-induced differences large enough to obscure subtle ecological signals.

When differences were normalized by the scene’s reflectance IQR, the same trend emerged. HAHOG and the SIFT-family algorithms were similar, AKAZE diverged moderately, and ORB stood apart.

---

## Implications for ecological time series

High-resolution UAV time series can detect subtle changes in forest structure, canopy stress, or defoliation. But the choice of image matching algorithm can influence the magnitude and spatial distribution of these signals. Radiometric instability can propagate into indices like NDVI, canopy structure models, or change detection analyses.

By quantifying algorithm-induced variability relative to typical scene variation (RMSE/IQR), ecologists can:

- Choose algorithms that minimize artificial noise
- Interpret detected change with greater confidence  
- Build time series that reflect true ecosystem dynamics, not artifacts

Ensuring consistent radiometry across time is just as important as capturing high-resolution imagery. Properly validated UAV mosaics become a reliable foundation for connecting pixels to ecological processes. With careful algorithm selection and rigorous validation, UAV time series can transform our understanding of ecosystem dynamics and change.

---

## Looking ahead

Future posts will explore ecological time series. I will continue to explore workflows for building and analyzing ecological time series, including methods and code.
