---
layout: post
title: "Advent Day 21: From pixels to processes"
date: 2025-12-21 10:00:00 +02:00
author: "Rachel Jade Kuzmich"
categories: [blog]
tags: [ecology, remote sensing, mechanisms, interpretation]
excerpt: "Here’s what remote sensing can do for ecologists. Patterns are easy to map; understanding the processes behind them requires ecological insight."
---

Remote sensing is excellent at revealing patterns, but ecological understanding of those patterns depends on processes. Patterns describe what we observe (spatial distributions, temporal trends, correlations) while processes describe the biological, physical, and ecological mechanisms that generate those patterns. This distinction matters because similar remote sensing signals can arise from very different ecological causes. A decline in NDVI might reflect drought stress, herbivory, disease, phenological shifts or management practices (or some combination of many of these). Without context, the pixel or mapped product alone cannot distinguish among these explanations.

As was the case in yesterday's post on uncertainty, this is not a limitation of remote sensing. This is a reminder of what these data measure. Because remote sensing data are commonly used to characterize environmental conditions driving ecological models, to evaluate whether model outputs are consistent with observed patterns, or to constrain model states and uncertainty (check out [this review](https://doi.org/10.1111/2041-210X.13018) by Pasetto et al., 2018). In all of these roles, sensors record reflected or emitted energy, not physiology, fitness, or demographic rates. Ecological meaning emerges only when remote sensing information is interpreted through theory, field observations, experiments, and prior knowledge of how ecosystems function. Problems arise when pattern is mistaken for mechanism, when correlations are treated as explanations.

Bridging pixels to processes requires thoughtful integration. A useful way to think about how different data and approaches can complement one another is illustrated in this figure by [Thackeray & Hampton 2020](https://doi.org/10.1111/gcb.15045). The figure shows multiple possible modes of integration, ranging from observing the same phenomenon with different tools, to filling causal gaps and extending inference across scales. Remote sensing makes a meaningful contributes to ecological research when it is embedded within a broader ecological framework:
- Field data provide comparative and translational complementarity, linking remotely sensed signals to measured structure, function, or composition on the ground, and constraining what a given spectral or structural pattern can plausibly represent
- Experimental and observational studies support causal complementarity, helping to distinguish among competing mechanisms by revealing how ecosystems respond to stress, disturbance, or management under controlled or well-characterized conditions
- Ecological theory provides contextual complementarity, guiding interpretation by identifying which patterns are expected under particular processes and which may be incidental, scale-dependent, or misleading
- Validation, transferability tests, and model diagnostics enable scaling complementarity, assessing not only predictive accuracy but whether inferred relationships remain ecologically plausible when applied across space, time, or changing environmental conditions

<p align="center">
  <img src="/assets/images/adventday21-ThackerayHampton2020.png" alt="Image from Thackeray & Hampton 2020" width="700">
</p>

Process-based understanding in ecology seeks to explain patterns through mechanisms (things like growth, mortality, competition, stress, disturbance and of course feedback). Remote sensing does not replace this kind of reasoning. Instead, it extends it by providing spatially and temporally extensive evidence of where those mechanisms may be operating. Pixels are not processes, but when embeded in ecological theory and integrated with field observations, they allow process-based hypotheses to be evaluated at scales that extend traditional field based observation. Remote sensing enables hypothesis testing, detection of emergent dynamics, and evaluation of mechanisms across spatial and temporal scales. But, because the same pattern can emerge from multiple and sometimes opposing processes, if remote sensing data are used uncritically, you risk producing pretty maps with weak explanations. 

--

## References

  Pasetto, D., Arenas‐Castro, S., Bustamante, J., Casagrandi, R., Chrysoulakis, N., Cord, A. F., Dittrich, A., Domingo‐Marimon, C., El Serafy, G., Karnieli, A., Kordelas, G. A., Manakos, I., Mari, L., Monteiro, A., Palazzi, E., Poursanidis, D., Rinaldo, A., Terzago, S., Ziemba, A., … Pettorelli, N. (2018). Integration of satellite remote sensing data in ecosystem modelling at local scales: Practices and trends. Methods in Ecology and Evolution, 9(8), 1810–1821. [https://doi.org/10.1111/2041-210X.13018](https://doi.org/10.1111/2041-210X.13018)

  Thackeray, S. J., & Hampton, S. E. (2020). The case for research integration, from genomics to remote sensing, to understand biodiversity change and functional dynamics in the world’s lakes. Global Change Biology, 26(6), 3230–3240. [https://doi.org/10.1111/gcb.15045](https://doi.org/10.1111/gcb.15045)
