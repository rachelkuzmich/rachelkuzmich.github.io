---
layout: post
title: "Advent Day 17: Scale matters"
date: 2025-12-17 10:00:00 +02:00
author: "Rachel Jade Kuzmich"
categories: [blog]
tags: [ecology, remote sensing, scale]
excerpt: "Here’s what remote sensing can do for ecologists. Remote sensing lets ecologists see ecosystems across space and time—but what we see, and what it means, depends critically on scale."
---

Remote sensing makes a contribution to ecology by enabling continuous observation of ecosystems across space and time. Yet the patterns that can be detected and the conclusions drawn from them depend fundamentally on scale. The same landscape can appear stable or dynamic, homogeneous or heterogeneous, resilient or stressed depending on the scale, resolution, frequency, and type of data that is used to observe it. Understanding scale is essential for linking remote sensing data to ecological processes. I spend a lot of time talking about forests as that is my scientific sandbox, but understanding scale is important across ecosystems. [Myers-Smith et al 2020](https://doi.org/10.1038/s41558-019-0688-1) provide an excellent discussion of the challenges to examining and understanding greenness patterns in the Arctic (and lots of great figures, like the one below).

<p align="center">
  <img src="/assets/images/adventday17-MyersSmith2020.png" alt="Image from Myers-Smith et al., 2020" width="700">
</p>

Remote sensing data vary along several key dimensions, each shaping the ecological information that we can detect:
- Spatial scale refers to the area represented by each pixel. Coarse-resolution sensors aggregate spectral data over hundreds of meters and over broad extents, making them well suited for regional phenology or productivity patterns. Fine-resolution data may be able to resolve individual trees, gaps, and microhabitats but typically cover smaller areas.
- Temporal scale describes how often observations are made and over what duration. High-frequency data can capture short-term dynamics such as drought stress or rapid greening, while long time series reveal trends, legacies, and regime shifts.
- Spectral scale reflects the number and placement of wavelength bands measured. Broadband multispectral data capture general vegetation patterns, while hyperspectral data can resolve subtle differences in physiology, chemistry, and stress that may precede visible change.
- Thematic scale refers to the level of ecological abstraction in derived products. Raw spectral values preserve information but are difficult to interpret directly, whereas vegetation indices, land-cover classifications, and model outputs simplify complexity to emphasize specific processes.

Ecological processes themselves operate across nested spatial and temporal scales. Drought responses, for example, can be detected at the level of stomatal conductance or leaf water content over hours to days, propagate to reduced growth or crown dieback at the individual tree level over weeks to months, and ultimately scale up to changes in stand structure or ecosystem organization over years. Remote sensing intersects with these processes at different resolutions, capturing some levels of organization while smoothing or missing others. Coarser spatial data aggregate responses across individuals, masking variability but revealing emergent stand- or landscape-level patterns.

Recognizing which levels of biological organization a given sensor can observe is critical for interpretation. Many apparent contradictions in ecological remote sensing arise from scale mismatch: a forest may appear phenologically stable at regional scales while experiencing strong stress at the individual level. Scale also governs transferability—models trained at one spatial or temporal grain may fail elsewhere not because ecology differs, but because the observation scale does. Rather than choosing a single “best” scale, modern ecological remote sensing increasingly integrates across them. Multi-sensor data fusion, hierarchical models, and time-series approaches allow ecologists to connect fine-scale mechanisms with broad-scale patterns. Remote sensing does not offer a single view of ecosystems—it offers many. Treating scale as a core analytical choice, rather than a technical detail, makes those views far more informative.

--

## References

  Myers-Smith, I. H., Kerby, J. T., Phoenix, G. K., Bjerke, J. W., Epstein, H. E., Assmann, J. J., John, C., Andreu-Hayles, L., Angers-Blondin, S., Beck, P. S. A., Berner, L. T., Bhatt, U. S., Bjorkman, A. D., Blok, D., Bryn, A., Christiansen, C. T., & Cornelissen, J. H. C. (2020). Complexity revealed in the greening of the Arctic. Nature Climate Change., 10(2), 106–117. [https://doi.org/10.1038/s41558-019-0688-1](https://doi.org/10.1038/s41558-019-0688-1)
