---
layout: post
title: "From points and pixels to processes: Ecological time series with remote sensing"
date: 2025-11-07 10:00:00 +02:00
author: "Rachel Jade Kuzmich"
categories: [blog]
tags: [ecology, remote sensing, time series, workflow, methods]
excerpt: "Ecological time series allow us to detect, model, and understand change in ecosystems through time. This post outlines key approaches and workflows for analyzing these data, from trend detection to linking patterns with ecological processes."
---

## Why ecological time series

Ecological systems are dynamic, and the spatial and temporal resolution of remote sensing time series enable the observation of this dynamism. From seasonal changes to forest succession to responses to exogenous factors, remote sensing time series allow us to see change across space, time and scales. In ecology, time series data have enabled researchers to move from snapshots to stories. A single remote sensing acquisition reveals a pattern; a static snapshot of canopy structure, greenness, or species composition. While a time series helps to tell the story of the processes behind those patterns; enhancing our understanding of the mechanisms and drivers of forest growth, mortality, and regeneration. This shift from pattern to process is critical for interpreting ecosystem function (particularly in the context of a changing climate).

## From imagery to information

The type of information extracted from remote sensing depends on the platform and the sensor. The platform determines spatial and temporal resolution. For instance, uncrewed aerial vehicles (UAVs) provide sub-meter detail ideal for tree-level analyses, airborne systems balance resolution and coverage for stand- to landscape-scale applications, while satellites enable long-term regional and global monitoring. The sensor defines what type of information is observed. Basic RGB cameras offer easily interpretable visual information, while higher spectral resolution sensors like multispectral and hyperspectral allow us quantify canopy greenness, stress, chemistry. Radar and lidar are both used to characterize three-dimensional structural components such as height, gap dynamics, and biomass. Together, platform and sensor choices determine the scale, resolution, frequency, and ecological processes that can be studied.

The key is repeated (ideally consistently!) data acquisitions, forming a time series. Temporal analysis also requires harmonized data. Each data acquisition in the time series needs to be adjusted to make it consistent and comparable across sensors, platforms or dates. Harmonization typically involves resampling images to a common pixel grid, co-registering them spatially, and applying radiometric calibration to correct for sensor and illumination differences. This ensures that apparent differences reflect actual ecological differences, rather than artifacts due to differences in acquisition characteristics. 

Harmonized remote sensing data can be stacked to form ecological time series, linking scales of observation and ecology. Connecting pixel or object analytical units, to tree-, stand-, landscape-, regional- and global level ecological processes.

## Types of change

There are multiple methods for analyzing remote sensing time series, depending on the research goal and data availability. Broadly, approaches can be grouped into several categories.

I like how Verbesselt et al 2010 described the types of time series analyses to characterize change.

- Seasonal change:
Ecosystems vary seasonally as temperature and rainfall influence plant phenology, canopy greenness, and productivity. Time series can capture these cyclic dynamics.

- Gradual change:
Beyond intra-annual seasonal changes, ecosystems experience gradual or directional inter-annual changes, for instance associated with climate variability or forest succession. These changes appear as long-term trends in time series data.

- Abrupt change:
Ecosystems can also undergo sudden, high-magnitude shifts due to disturbances such as forest fire or harvesting. These events are often captured as breakpoints or discontinuities in a time series.

Detecting change through time is not straightforward. Ecological time series may include multiple types of changes, along with noise from factors like sensor differences, atmosphere, and viewing geometry. The challenge is to separate meaningful ecological change from this variability

Alright, you've detected a genuine change, now what?

### **Characterizing change**
Once change is detected, it can be characterized by its size, frequency, severity, how these attributes change through time, and causal agent. Rather than detecting when and where changes occur, characterizing how these attributes evolve through time reveals broader trends in ecosystem processes. For example, Senf and Seidl (2021) used three decades of satellite data to map forest disturbances across Europe, showing that while disturbance frequency has increased, severity has generally decreased, and size patterns have shifted, revealing large-scale transformations in disturbance regimes and forest dynamics. Similarly, Cohen et al. (2016) analyzed Landsat time series across the United States and attributed changing disturbance rates to shifting dominance among causal agents, notably declines in harvest and increases in climate and stress related disturbances.

### **Linking patterns with processes**
From my perspective, the strength of remote sensing time series is not only to detect and characterize changes, but to use these data to understand the processes driving them. This can be accomplished by modelling remote sensing with environmental, ecological or physiological time series. Lidar and multispectral data can link structural and functional responses to climate, while UAV and dendrometer measurements connect tree physiology with stress responses. These integrations allow remote sensing time series to become more than records of change, instead making them invaluable tools for understanding ecosystem function through time. For instance, Chen et al. (2023) used satellite data across Europe to quantify how ecosystems respond to drought onset, duration, and severity. Their results found that some ecosystems, like mixed forests, exhibit slower, buffered responses compared to more vulnerable systems. At the tree level, Cardil et al. (2019) demonstrated how UAV multispectral data can detect and quantify insect-driven defoliation with high accuracy. These data were able to capture physiological stress before it became visible at coarser spatial scales.

Analyzing ecological time series is ultimately about understanding change, not just detecting it. Remote sensing provides a record of how ecosystems vary across space and time and respond to different types of changes from different types of drivers. These data are indispensable for developing time series, but their greatest value lies in linking remote sensing patterns to underlying processes.

This post introduces core concepts for analyzing ecological time series from remote sensing. In upcoming posts, I’ll explore practical workflows for building and analyzing ecological time series, including example methods and code.

---

## References

  Cardil, A., Otsu, K., Pla, M., Silva, C. A., & Brotons, L. (2019). Quantifying pine processionary moth defoliation in a pine-oak mixed forest using unmanned aerial systems and multispectral imagery. PloS One, 14(3), e0213027. https://doi.org/10.1371/journal.pone.0213027

  Chen, Q., Timmermans, J., Wen, W., & van Bodegom, P. M. (2023). Ecosystems threatened by intensified drought with divergent vulnerability. Remote Sensing of Environment, 289. https://doi.org/10.1016/j.rse.2023.113512

  Cohen, W., Yang, Z., Meigs, G., Cohen, W. B., Yang, Z., Stehman, S. V., Schroeder, T. A., Bell, D. M., Masek, J. G., Huang, C., & Meigs, G. W. (2016). Forest disturbance across the conterminous United States from 1985–2012: The emerging dominance of forest decline. Forest Ecology and Management, 360, 242–252. https://doi.org/10.1016/j.foreco.2015.10.042

  Senf, C., & Seidl, R. (2021). Mapping the forest disturbance regimes of Europe. Nature Sustainability, 4(1), 63–70. https://doi.org/10.1038/s41893-020-00609-y

  Verbesselt, J., Hyndman, R., Culvenor, D., Verbesselt, J., Hyndman, R., Newnham, G., & Culvenor, D. (2010). Detecting trend and seasonal changes in satellite image time series. Remote Sensing of Environment, 114(1), 106–115. https://doi.org/10.1016/j.rse.2009.08.014

