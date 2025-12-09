---
layout: post
title: "Advent Day 8: Lidar height and diversity"
date: 2025-12-03 10:00:00 +02:00
author: "Rachel Jade Kuzmich"
categories: [blog]
tags: [ecology, remote sensing, advent, lidar]
excerpt: "Here’s what remote sensing can do for ecologists. Today we’re finally talking about spectral bands themselves and the different ecological signalsthat they contain."
---

Over the past week, I’ve talked about vegetation indices, hyperspectral data, and time series. All of these topics circle around one foundational idea: spectral bands. Today we finally focus on them directly. Multispectral sensors capture light into a handful of broad wavelength regions, and each band reveals a different piece of ecological information. Understanding what these bands measure, and why they matter, helps us interpret the signal in the data.

Common multispectral bands and what they tell us:
- Red (≈ 650 nm) light is strongly absorbed by chlorophyll, making it central to plant monitoring. Useful for vegetation health and greenness (it is used to calculate NDVI, and countless indices), mapping vegetation boundaries and bare soil, detecting early senescence and stress, crop monitoring and defoliation assessment
- Green (≈ 550 nm) reflectance is strongly influenced by chlorophyll, which reflects light in the green band. Useful for capturing variations in plant pigments, differentiating vegetation types, estimating biomass or canopy “greenness”
- Blue (≈ 450 nm) light penetrates clear water and interacts strongly with the atmosphere. Useful for mapping shallow coastal or freshwater features, assessing turbidity and suspended sediment, correcting atmospheric effects in other bands
- Near-Infrared (NIR, ≈ 800–900 nm) is highly reflected by healthy vegetation due to cell structure. Useful for mapping biomass and leaf area index, distinguishing vegetation from soil or water, detecting canopy changes like effects of damage or thinning, and building almost every vegetation index (this is the other band used to calculate NDVI)
- Shortwave infrared (SWIR1, ≈ 1.6 µm; SWIR2, ≈ 2.2 µm) interacts with liquid water in leaves and soils. Useful for measuring vegetation water content, mapping drought stress, detecting burn scars and fire severity, examining soil moisture, soil mineralogy, and dryness patterns
- Red Edge (≈ 700–740 nm) marks the sharp jump between red absorption and NIR reflectance. Useful for detecting subtle physiological stress, monitoring early-season growth and late-season decline, differentiating species with distinct leaf traits, precision agriculture and forestry

<p align="center">
  <img src="/assets/images/adventday3-NASABandComparisonTool.png" alt="Image from NASA Band Comparison Tool" width="700">
</p>

This [image](https://science.nasa.gov/mission/landsat/spectral-bands-and-applications/) shows the location of spectral bands for each of the Landsat satellite instruments, showing changes through time as new sensors are developed.

Why multispectral bands matter for ecology 
Multispectral bands are the foundation on which nearly all ecological remote sensing is built. They capture the fundamental ways that vegetation, soil, and water interact with light—information that is surprisingly difficult to measure consistently on the ground, even with a spectroradiometer in hand. These bands condense complex biophysical processes into observable, comparable signals across space and time, giving ecologists a scalable view of ecosystem function. Every spectral index, every trend analysis, and every machine learning model ultimately rests on these core wavelengths—quiet building blocks that make modern ecological insight possible

--

## References

[https://science.nasa.gov/mission/landsat/spectral-bands-and-applications/](https://science.nasa.gov/mission/landsat/spectral-bands-and-applications/)

[https://www.usgs.gov/faqs/what-are-best-landsat-spectral-bands-use-my-research](https://www.usgs.gov/faqs/what-are-best-landsat-spectral-bands-use-my-research)
