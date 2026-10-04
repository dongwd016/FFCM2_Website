---
layout: default
title: n-Dodecane
parent: Application
nav_order: 12
---

# n-Dodecane
{: .no_toc }
 
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Model files

### High-T model (detailed)
[CTI]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_highT.cti){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[YAML]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_highT.yaml){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Chemkin]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_highT.zip){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

### High-T model (detailed, refit to 9999 K)
[CTI]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_highT_9999K.cti){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[YAML]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_highT_9999K.yaml){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Chemkin]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_highT_9999K.zip){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

### High-T model (skeletal)
[CTI]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_highT_skeletal.cti){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[YAML]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_highT_skeletal.yaml){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Chemkin]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_highT_skeletal.zip){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

### High-T model (skeletal, refit to 9999 K)
[CTI]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_highT_skeletal_9999K.cti){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[YAML]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_highT_skeletal_9999K.yaml){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Chemkin]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_highT_skeletal_9999K.zip){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

### NTC-enabled model
[CTI]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_NTC.cti){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[YAML]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_NTC.yaml){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Chemkin]({{ site.url }}{{ site.baseurl }}/assets/data/applications/n-dodecane/NC12H26_NTC.zip){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

## How to cite
### APA format
```
W. Dong and H. Wang, 
n-Dodecane model based on Foundational Fuel Chemistry Model Version 2.0 (FFCM-2), https://web.stanford.edu/group/haiwanglab/FFCM2/docs/Application/n-Dodecane, 2024.
```
### Bibtex format
```bibtex
@Misc{DW2024,
  author  = {Dong, Wendi and Wang, Hai},
  title   = {n-Dodecane model based on {Foundational} {Fuel} {Chemistry} {Model} {Version} 2.0 ({FFCM}-2)},
  journal = {FFCM-2 website},
  url     = "https://web.stanford.edu/group/haiwanglab/FFCM2/docs/Application/n-Dodecane",
  year    = {2024},
  }
  
```

## Model performance

### High temperature

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/idt_highT.png" alt="N/A" width="600" height="600">
</p>
<i>Figure 1: n-Dodecane ignition delay time at high temperature. Model predictions contain high-T detailed model, high-T skeletal model, and NTC-enabled model. Experimental measurements are from MRW2020: Mao et al. [^MRW2020], and DHP2011: Davidson et al. [^DHP2011].</i>

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/pro_N12H26_0...10.png" alt="N/A" width="1000" height="600">
</p>
<i>Figure 2: Time history of multiple species from oxidation of n-dodecane. Model predictions contain high-T detailed model, high-T skeletal model, and NTC-enabled model. Shock tube oxidation measurement is from DHP2011: Davidson et al. [^DHP2011]. Initial condition: tempearture and pressure are listed on each subplots, $\phi$=1, $n$-C<sub>12</sub>H<sub>26</sub>/0.75%O<sub>2</sub>/Ar.</i>

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/pro_N12H26_11,12.png" alt="N/A" width="400" height="600">
</p>
<i>Figure 3: Species time history of n-dodecane and ethylene from thermal decomposition of n-dodecane. Model predictions contain high-T detailed model, high-T skeletal model, and NTC-enabled model. Shock tube pyrolysis measurement is from MRZ2013: MacDonald et al. [^MRZ2013]. Initial condition: 1306 K, 17.2 atm, and 0.17%$n$-C<sub>12</sub>H<sub>26</sub>/99.83%Ar.</i>

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/pro_NC12H26_13.png" alt="N/A" width="1000" height="600">
</p>

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/pro_NC12H26_14.png" alt="N/A" width="1000" height="600">
</p>

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/pro_NC12H26_15.png" alt="N/A" width="1000" height="600">
</p>

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/pro_NC12H26_16.png" alt="N/A" width="1000" height="600">
</p>

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/pro_NC12H26_17.png" alt="N/A" width="1000" height="600">
</p>

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/pro_NC12H26_18.png" alt="N/A" width="1000" height="600">
</p>
<i>Figure 4: Yield of multiple species from n-dodecane oxidation and pyrolysis. Model predictions contain high-T detailed model, high-T skeletal model, and NTC-enabled model. Shock tube measurement is from MB2013: Malewicki and Brezinsky [^MB2013].</i>

### NTC

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/idt_NTC.png" alt="N/A" width="1200" height="600">
</p>
<i>Figure 5: n-Dodecane ignition delay time extended to NTC-related temperature. Model predictions are from NTC-enabled model. Experimental measurements are from MRW2020: Vasu [^V2010], Shao et al. [^SCP2019], and Mao et al. [^MRW2020].</i>

### Model reduction

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/ign_43.png" alt="N/A" width="1000" height="600">
</p>
<i>Figure 6: Comparison of detailed and skeletal model predictions of n-dodecane ignition delay time at high temperature. Initial conditions (used as DRG targets): $T_5$ from 1200 to 2000 K, $P_5$ = 0.5, 1, 5, 30 atm, and $\phi$ = 0.5, 1.0, 1.5.</i>

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/psr_43.png" alt="N/A" width="1000" height="600">
</p>
<i>Figure 7: Comparison of detailed and skeletal model predictions of n-dodecane PSR S-curve. Initial conditions (used as DRG targets): $T_{in}$ = 300 K, $P$ = 0.5, 1, 5, 30 atm, and $\phi$ = 0.5, 1.0, 1.5.</i>

<p align="center">
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/hychem/n-dodecane/znd_43.png" alt="N/A" width="400" height="600">
</p>
<i>Figure 8: Comparison of detailed and skeletal model predictions of n-dodecane ZND temperature profile. Post shock conditions (not used as DRG targets, only for testing): $T_0$ = 300 K, $P_0$ = 1, 5, 30 atm, and $\phi$ = 1.0.</i>

## References

[^MRW2020]: Mao, Y., Raza, M., Wu, Z., Zhu, J., Yu, L., Wang, S., Zhu, L. & Lu, X. (2020). An experimental study of n-dodecane and the development of an improved kinetic model. Combustion and Flame, 212, 388-402.

[^DHP2011]: Davidson, D., Hong, Z., Pilla, G., Farooq, A., Cook, R. & Hanson, R. (2011). Multi-species time-history measurements during n-dodecane oxidation behind reflected shock waves. Proceedings of the Combustion Institute, 33 (1), 151-157.

[^MRZ2013]: MacDonald, M., Ren, W., Zhu, Y., Davidson, D. & Hanson, R. (2013). Fuel and ethylene measurements during n-dodecane, methylcyclohexane, and iso-cetane pyrolysis in shock tubes. Fuel, 103, 1060-1068.

[^MB2013]: Malewicki, T. & Brezinsky, K. Experimental and modeling study on the pyrolysis and oxidation of n-decane and n-dodecane. Proceedings of the Combustion Institute, 34 (1), 361-368.

[^V2010]: Vasu, S. (2010). Measurements of ignition times, OH time-histories, and reaction rates in jet fuel and surrogate oxidation systems. Ph.D. Thesis.

[^SCP2019]: Shao, J., Choudhary, R., Peng, Y., Davidson, D. & Hanson, R. (2019). A shock tube study of n-heptane, iso-octane, n-dodecane and iso-octane/n-dodecane blends oxidation at elevated pressures and intermediate temperatures. Fuel, 243, 541-553.
