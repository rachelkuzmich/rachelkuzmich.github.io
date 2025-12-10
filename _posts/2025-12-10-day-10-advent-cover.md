---
layout: post
title: "Advent Day 10: Canopy cover"
date: 2025-12-10 10:00:00 +02:00
author: "Rachel Jade Kuzmich"
categories: [blog]
tags: [ecology, remote sensing, DAP, photogrammetry]
excerpt: "Here’s what remote sensing can do for ecologists. Today’s focus is on canopy cover, which regulates light, temperature, moisture, habitat connectivity, and more."
---
Canopy cover, which is the proportion of ground shaded by vegetation, is a deceptively simple but hugely influential ecological variable. It structures how forests function, from the treetops to the soil surface, and how wildlife move through forests. Even small changes in canopy cover can have large effects on ecosystem function and community dynamics. It can be measured on the ground, for instance using hemispherical photographs, but remote sensing enables consistent, scalable estimates across landscapes.

There are multple remote sensing data and methods to model canopy cover reliably across space and time. [Li et al 2020](https://doi.org/10.1016/j.isprsjprs.2023.03.020) provides an excellent review of remote and ground-based methods. Multispectral imagery uses spectral thresholds to identify vegetation and estimate fractional cover. Lidar or DAP measures vertical structure directly using height profiles and penetration ratios. And radar detects canopy density through differences in backscatter. Together, these tools offer scalable, repeatable, and historically comparable measures of a variable that would otherwise require extensive fieldwork to capture. 

Canopy cover matters because it regulates several key ecological processes. 
- Microclimate: buffers temperature extremes, retains moisture, and maintains cooler conditions
- Understory light: controls seedling establishment, species composition, and understory productivity
- Connectivity: influences how species move through habitat patches at local and landscape scales
- Biodiversity: shapes species richness and community structure, as organisms respond to canopy openness or closure
- Regeneration: determines where seedlings can germinate and survive, influencing the composition of future forests

<p align="center">
  <img src="/assets/images/adventday10-Slaton2025.png" alt="Image from Fu et al., 2021" width="700">
</p>

And of course if you have a time series of data, then you can model change through time like this study by {Slaton et al 2025}(https://doi.org/10.1080/01431161.2024.2421943), and figure showing loss through time.

At its core, canopy cover can be used to link structure to ecological process. Remote sensing gives ecologists a way to quantify this structure consistently, repeatedly, and across scales that are difficult to capture from the ground.

--

## References



  Li, L., Mu, X., Jiang, H., Chianucci, F., Hu, R., Song, W., Qi, J., Liu, S., Zhou, J., Chen, L., Huang, H., & Yan, G. (2023). Review of ground and aerial methods for vegetation cover fraction (fCover) and related quantities estimation: definitions, advances, challenges, and future perspectives. ISPRS Journal of Photogrammetry and Remote Sensing, 199, 133–156. [https://doi.org/10.1016/j.isprsjprs.2023.03.020](https://doi.org/10.1016/j.isprsjprs.2023.03.020)

  Slaton, M. R., Koltunov, A., Evans, K., Kohler, T., & Young-Hart, L. (2025). Estimating canopy cover loss with Landsat dense time series: a Mortality Magnitude Index for the Ecosystem Disturbance and Recovery Tracker (eDaRT). International Journal of Remote Sensing, 46(2), 686–703. [https://doi.org/10.1080/01431161.2024.2421943](https://doi.org/10.1080/01431161.2024.2421943)
