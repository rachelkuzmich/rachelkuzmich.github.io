---
layout: post
title: "Advent Day 9: Digital Aerial Photogrammetry: When Spectral Data Becomes 3D"
date: 2025-12-09 10:00:00 +02:00
author: "Rachel Jade Kuzmich"
categories: [blog]
tags: [ecology, remote sensing, DAP, photogrammetry]
excerpt: "Here’s what remote sensing can do for ecologists. Today’s focus is on photogrammetry, it's lidar-like but estimated from spectral data."
---

I’ve talked a lot about spectral data and information, but spectral data can do more than tell us about reflectance curves. When images are collected with the right overlap and geometry, they can be transformed into full 3D structure. This is the foundation of digital aerial photogrammetry (DAP).

It's the same RGB data you're already familiar with, just used in a different way to obtain spectral and structural information. DAP uses overlapping 2D images (traditionally from aircraft and now commonly from uncrewed aerial vehicles: UAVs) and computer vision algorithms to reconstruct a detailed 3D surface. With sufficient overlap and accurate camera positions, these algorithms reverse engineer scene geometry, estimating where each pixel must sit in three-dimensional space. The workflow produces a dense point cloud along with orthomosaics, digital surface models, and canopy-height models. Although the core idea dates back to early stereo photography (check your local museum for fun retro examples!), modern DAP relies on techniques like bundle adjustment and dense image matching, yielding outputs that look surprisingly lidar-like. 

And because they are lidar-like, they are good for examining structural aspects of forests and changes through time when multi-temporal data are available. Just like [Fu et al (2021)](https://doi.org/10.1016/j.rse.2021.112300), who compared height, density, canopy and other metrics for two tree species (dawn redwood and poplar) using DAP data from three years apart. The figure speaks for itself, and overall the DAP data showed growth through time.

<p align="center">
  <img src="/assets/images/adventday9-Fu2021.png" alt="Image from Fu et al., 2021" width="700">
</p>

Why ecologists use DAP
- Joint spectral and structural information from the same data
- High-resolution canopy surfaces and height models (centimeter-scale with UAVs)
- Frequent, inexpensive repeat surveys (great for growth, disturbance, and recovery)
- A practical alternative in places where lidar is too expensive or unavailable
 
Compared to lidar, DAP can’t see through dense forest canopy (without supplementary data). But in open to moderately open forests, it does pretty good!

DAP sits at the intersection of spectral and structural information. Spectral data can be more than just pictures. With the right planning and methods, spectral images are 3D models waiting to be extracted.

--

## References


Fu, X., Zhang, Z., Cao, L., Coops, N. C., Goodbody, T. R., Liu, H., Shen, X., & Wu, X. (2021). Assessment of approaches for monitoring forest structure dynamics using bi-temporal digital aerial photogrammetry point clouds. Remote Sensing of Environment, 255. [https://doi.org/10.1016/j.rse.2021.112300](https://doi.org/10.1016/j.rse.2021.112300)
