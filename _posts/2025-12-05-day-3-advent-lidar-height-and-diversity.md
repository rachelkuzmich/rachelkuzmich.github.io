---
layout: post
title: "Advent Day 3: Lidar height and Diversity"
date: 2025-12-03 10:00:00 +02:00
author: "Rachel Jade Kuzmich"
categories: [blog]
tags: [ecology, remote sensing, advent, lidar]
excerpt: "Here’s what remote sensing can do for ecologists. Today’s focus is on lidar and how."
---

Today we shift from spectral data to 3D structure. Lidar (light detection and ranging) tells us how vegetation is arranged in space.

Lidar works by sending out laser pulses and measuring the return time from leaves, branches, and the ground. This generates a dense 3D point cloud, capturing canopy height, vertical layering, gaps, and overall structural complexity. One of the simplest and most widely used derivatives is the canopy height model (CHM) — a raster created by subtracting a ground-surface model from the height of the highest vegetation returns. CHMs provide wall-to-wall maps of maximum canopy height at resolutions fine enough to track individual trees.

But lidar isn’t limited to rasters. The point cloud itself can be used to derive height metrics at specific locations. Ecologists often extract local canopy height, canopy cover, gap fraction, or vertical distribution of returns within a defined radius (much like I did for my PhD work). For example, lidar metrics can be extracted from the 3D point cloud around known bird nest sites to quantify nesting habitat structure.

For ecologists, canopy height and vertical structure relate to:
- successional stage and stand development
- habitat suitability for birds, mammals, and insects
- disturbance intensity and post-disturbance regrowth
- vertical heterogeneity, a key correlate of biodiversity

The importance of vertical structure has deep roots in ecology. Long before lidar, Robert MacArthur introduced foliage height diversity (FHD), showing that bird communities respond strongly to variation in vegetation layering (MacArthur & MacArthur, 1961; one of my favourite papers). Measuring FHD once required labor-intensive field sampling - (imagine doing it this way)[https://doi.org/10.2307/1933693]? 

<p align="center">
  <img src="/assets/images/adventday3-MacArthurMacArthur1961.png" alt="Figure from Cavender-Bares et al., 2022" width="700">
</p>

[This figure](https://doi.org/10.2307/1932254) provides an example of some manual FHD derivations. Lidar captures these same structural gradients directly, consistently, and across entire landscapes.

Field measurements remain valuable for fine-level detail, but lidar extends structural ecology into a truly spatial science; for instance modelling species' habitat, disturbance, and recovery at scales that were previously inaccessible.

---

## References

  
  MacArthur, R. H., & Horn, H. S. (1969). Foliage Profile by Vertical Measurements. Ecology (Durham), 50(5), 802–804. [https://doi.org/10.2307/1933693](https://doi.org/10.2307/1933693)


  MacArthur, R. H., & MacArthur, J. W. (1961). On Bird Species Diversity. Ecology (Durham), 42(3), 594–598. [https://doi.org/10.2307/1932254](https://doi.org/10.2307/1932254)
