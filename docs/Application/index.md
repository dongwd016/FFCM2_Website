---
layout: default
title: Application
nav_order: 11
has_children: true
---

# Application
{: .no_toc }
Application of the optimized and uncertainty-minimized FFCM-2.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

### Hybrid chemistry (HyChem) modeling
The development of foundational fuel chemistry model is not only critical to small hydrocarbons, but relevant to the modeling of real, multicomponent fuel combustion. 

Recently, a physics-based hybrid chemistry (HyChem) modeling approach was developed for modeling combustion chemistry of large hydrocarbons and real, distillate fuels[^WXW2018]$^{,}$[^XWB2018]$^{,}$[^TXW2018]$^{,}$[^WXP2018]$^{,}$[^SWX2020]$^{,}$[^XSL2020]$^{,}$[^XW2021]. The HyChem approach decouples the high-temperature combustion of large hydrocarbons and real, liquid fuels into two stages that are separable in temporal and spatial scales: the fuel first undergoes a rapid decomposition to produce a mixture of smaller intermediate species; these fragments, consisting primarily of foundational fuels, are oxidized to the final combustion products. The fuel decomposition is a fast process, and can be modeled with a few global, lumped reactions. The stoichiometric coefficients and rate constants of the lumped reactions can be determined by solving an inverse problem, using as targets the speciation data of thermal and oxidative pyrolysis experiments conducted in shock tube and flow reactor. The rate limiting step is the oxidation of the fragments, which must be treated with a detailed, foundational fuel chemistry model. 

A major challenge in kinetic modeling of the real, multi-component fuels is to determine the chemical compositions precisely. The HyChem approach treats the real fuel as one single species to resolve this issue. Also, HyChem uses a few global, lumped reactions to decouple the fuel decomposition from the oxidation of foundational fuel mixtures. It avoids compiling a great many reaction pathways and rate constants that cannot be studied by first-principle or experiments. The number of chemical species and reactions in the HyChem models are significantly reduced to the level of foundational fuel chemistry. The model could be further reduced to 40 to 50 species to be applicable to CFD simulations. The HyChem approach has been successfully applied to modeling a series of conventional jet fuels[^WXW2018]$^{,}$[^XWB2018], synthetic jet fuels[^TXW2018], rocket fuels[^XWB2018], gasoline fuels[^XSL2020], sustainable aviation fuels[^WXP2018] and formation of NOx from the Jet A fuel[^SWX2020]. 

An issue identified in the earlier HyChem work is that the uncertainties of HyChem models remain large, due to the uncertainties in the foundational fuel chemistry[^XWB2018]$^{,}$[^WXP2018]. Thus, an accurate and uncertainty-minimized foundational C<sub>0−4</sub> combustion chemistry model is critical to modeling large hydrocarbons and real, distillate fuels.

### List of FFCM-2 based HyChem models

| Fuel    | POSF number | Type & Applications          | Status |
|:--------:|:-------------:|:----------------------------:|:----:|
|  JP-8 | A1, POSF 10264         |Distillate jet fuel        | Working in progress |
|  Jet A      | A2, POSF 10325         |Distillate jet fuel   | [Available]({{ site.url }}{{ site.baseurl }}/docs/Application/Jet A)[^ZDX2023] |
|  JP-5      | A3, POSF 10289         |Distillate jet fuel    | [Available]({{ site.url }}{{ site.baseurl }}/docs/Application/JP-5) |
|  JP-10   | N/A           | Synthetic jet fuel    | [Available]({{ site.url }}{{ site.baseurl }}/docs/Application/JP-10) |
|  RP2-1   | POSF 7688          | Distillate rocket fuel       | [Available]({{ site.url }}{{ site.baseurl }}/docs/Application/RP2-1) |
|  RP2-2   | POSF 5433          | Distillate rocket fuel       | [Available]({{ site.url }}{{ site.baseurl }}/docs/Application/RP2-2) |
|  Shell A | N/A           | Gasoline fuel                |Working in progress |
|  Shell D | N/A           | Gasoline fuel                |Working in progress |
|  Gevo ATJ      | C1, POSF 11498         | Synthetic jet fuel | [Available]({{ site.url }}{{ site.baseurl }}/docs/Application/Gevo ATJ)[^ZDX2023] |
|  Gevo ATJ      | POSF 12394         | Synthetic jet fuel | [Available]({{ site.url }}{{ site.baseurl }}/docs/Application/Gevo ATJ)[^ZDX2023] |
|  C5      | POSF 12345         | Synthetic jet fuel           |Working in progress|
|  n-Dodecane      | N/A         | Pure species           | [Available]({{ site.url }}{{ site.baseurl }}/docs/Application/n-Dodecane) |

## References
[^WXW2018]: Wang, H., Xu, R., Wang, K., Bowman, C. T., Hanson, R. K., Davidson, D. F., Brezinsky, K. & Egolfopoulos, F. N. (2018). A physics-based approach to modeling real-fuel combustion chemistry-I. Evidence from experiments, and thermodynamic, chemical kinetic and statistical considerations. Combustion and Flame, 193, 502-519.

[^XWB2018]: Xu, R., Wang, K., Banerjee, S., Shao, J., Parise, T., Zhu, Y., Wang, S., Movaghar, A., Lee, D., Zhao, R., Han, X., Gao, Y., Lu, T., Brezinsky, K., Egolfopoulos, F., Davidson, D., Hanson, R., Bowman, C. T. & Wang, H. (2018). A physics-based approach to modeling real-fuel combustion chemistry–II. Reaction kinetic models of jet and rocket fuels. Combustion and Flame, 193, 520-537.

[^TXW2018]: Tao, Y., Xu, R., Wang, K., Shao, J., Johnson, S., Movaghar, A., Han, X., Park, J. W., Lu, T., Brezinsky, K., Egolfopoulos, F., Davidson, D., Hanson, R., Bowman, C. T. & Wang, H. (2018). A Physics-based approach to modeling real-fuel combustion chemistry–III. Reaction kinetic model of JP10. Combustion and Flame, 198, 466-476.

[^WXP2018]: Wang, K., Xu, R., Parise, T., Shao, J., Movaghar, A., Lee, D., Park, J. W., Gao, Y., Lu, T., Egolfopoulos, F., Davidson, D., Hanson, R., Bowman, C. T. & Wang, H. (2018). A physics-based approach to modeling real-fuel combustion chemistry–IV. HyChem modeling of combustion kinetics of a bio-derived jet fuel and its blends with a conventional Jet A. Combustion and Flame, 198, 477-489.

[^SWX2020]: Saggese, C., Wan, K., Xu, R., Tao, Y., Bowman, C. T., Park, J. W., Lu, T. & Wang, H. (2020). A physics-based approach to modeling real-fuel combustion chemistry–V. NOx formation from a typical Jet A. Combustion and Flame, 212, 270-278.

[^XSL2020]: Xu, R., Saggese, C., Lawson, R., Movaghar, A., Parise, T., Shao, J., Choudhary, R., Park, J. W., Lu, T., Hanson, R. K., Davidson, D. F., Egolfopoulos, F. N., Aradi, A., Prakash, A., Mohan, V. R. R., Cracknell, R. & Wang, H. (2020). A physics-based approach to modeling real-fuel combustion chemistry–VI. Predictive kinetic models of gasoline fuels. Combustion and Flame, 220, 475-487.

[^XW2021]: Xu, R., & Wang, H. (2021). A physics-based approach to modeling real-fuel combustion chemistry–VII. Relationship between speciation measurement and reaction model accuracy. Combustion and Flame, 224, 126-135.

[^ZDX2023]: Zhang, Y., Dong, W., Vandewalle, L. A., Xu, R., Smith, G. P. & Wang, H. (2023). Foundational Fuel Chemistry Model 2 - iso-Butene chemistry and application in modeling alcohol-to-jet fuel combustion. Combustion and Flame, submitted.
