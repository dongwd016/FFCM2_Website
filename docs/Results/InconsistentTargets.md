---
layout: default
title: Inconsistent Targets
parent: Results
nav_order: 5
---

# Summary of Inconsistent Targets
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

The table lists the 34 inconsistent targets excluded from FFCM-2 optimization. Inconsistent target data are not necessarily inaccurate. Some of the targets (e.g., three $i$-C<sub>4</sub>H<sub>8</sub> species profile targets) cannot be accurately predicted without aromatic chemistry, which is currently not considered in FFCM-2.

- Type: The data types are pro (shock-tube speciation), fls (laminar flame speed) and ign (ignition delay).
- $T$: temperature (K)
- $p$: pressure (atm)
- $\phi$: equivalence ratio, where inf indicates thermal pyrolysis experiments (no oxygen)
- Diluent: diluent of the mixture and mole fraction of the diluent
- $\sigma_{exp}$: data uncertainty
- $F$: inconsistency score of a target, calculated by $\dfrac{y_{exp} - y(\mathbf{x})}{2 \sigma_{exp}}$.
- Method: experimental techniques

## List of 34 inconsistent targets in FFCM-2 optimization

### Three inconsistent speciation targets

| Type |  Fuel | $T$ (K)| $p$ (atm)|  $\phi$ |  Diluent  |  $X_{spe}$(ppm) | $\sigma_{exp}$ |   $F$   |             Method             | Reference |
|:----:|:--------:|:----:|:----:|:----:|:---------:|:----:|:-----------:|:-----:|:------------------------------:|:---------:|
|  pro |   IC4H8  | 1430 |   2  |  inf |   98% Ar  | 3471 |     1.21    | -1.24 |     Mole fraction of allene    |  NKP2020[^NKP2020]  |
|  pro |   IC4H8  | 1430 |   2  |  inf |   98% Ar  | 3323 |     1.22    |  1.11 |    Mole fraction of propyne    |  NKP2020[^NKP2020]  |
|  pro |   IC4H8  | 1430 |   2  |  inf |   98% Ar  | 1035 |     1.32    |  1.42 | Mole fraction of 1,3-butadiene |  NKP2020[^NKP2020]  |

### Nine inconsistent laminar flame speed targets

| Type |  Fuel | $T$ (K)| $p$ (atm)|  $\phi$ |  Oxidizer  |  $S_u^o$ (cm/s) | $\sigma_{exp}$ |   $F$   |             Method             | Reference |
|:----:|:--------:|:----:|:----:|:----:|:---------:|:----:|:-----------:|:-----:|:------------------------------:|:---------:|
|  fls |   CH3OH  |  400 |   1  |  1.3 |    air    |  53  |     5.34    |  2.01 |        Spherical (L)       |  LJH2007[^LJH2007]  |
|  fls |   CH3OH  |  373 |   1  |  1.3 |    air    |  47  |     4.67    |  2.15 |        Spherical (L)       |  ZHW2008[^ZHW2008]  |
|  fls |   C2H2   |  300 |   1  |  1.5 | 13%O<sub>2</sub>-87%N<sub>2</sub> |  31  |      2      |  1.4  |       Counterflow (L)      |  EZL1990[^EZL1990]  |
|  fls |   C2H4   |  298 |  0.5 |  1.6 |    air    |  36  |     3.55    |  -1.1 |       Counterflow (L)      |  EZL1990[^EZL1990]  |
|  fls |   C2H4   |  298 |   2  |  1.6 |    air    |  22  |     2.18    | -1.02 |       Counterflow (L)      |  EZL1990[^EZL1990]  |
|  fls |   C2H4   |  300 |   4  |  1.4 |    air    |  35  |     3.5     |  1.28 |        Spherical (L)       |  HAK1998[^HAK1998]  |
|  fls |   C2H4   |  300 |   2  |  1.4 |    air    |  45  |     2.8     |  1.39 |      Spherical (NL)     |  JZZ2005[^JZZ2005]  |
|  fls |   C3H6   |  300 |   2  |  0.8 |    air    |  20  |     2.03    |  1.5  |      Spherical (NL)      |  JZZ2005[^JZZ2005]  |
|  fls |  C2H5OH  |  325 |   1  |  1.3 |    air    |  33  |     3.25    |  1.47 |        Spherical (L)       |   HT2006[^HT2006]  |

### 22 inconsistent shock tube ignition delay targets

| Type |  Fuel | $T_5$ (K)| $p_5$ (atm)|  $\phi$ |  Diluent  |  $\tau_{ign} (\mu s)$ | $\sigma_{exp}$ |   $F$   |             Method             | Reference |
|:----:|:--------:|:----:|:----:|:----:|:---------:|:----:|:-----------:|:-----:|:------------------------------:|:---------:|
|  ign |   CH3OH  | 1635 |   2  |   1  |  92.3% Ar |  137 |     1.37    | -1.58 |          Onset of CH*          |  NAB2010[^NAB2010]  |
|  ign |   CH3OH  | 1606 |  2.5 |  0.5 |  90.0% Ar |  24  |     1.28    |  1.45 |          Onset of CH*          |   NB1981[^NB1981]  |
|  ign |   CH3OH  | 1476 |  2.5 |  0.5 |  90.0% Ar |  60  |     1.3     |  1.52 |          Onset of CH*          |   NB1981[^NB1981]  |
|  ign |   CH3OH  | 1561 |  4.5 |  0.5 |  90.0% Ar |  21  |     1.29    |  1.35 |          Onset of CH*          |   NB1981[^NB1981]  |
|  ign |   CH3OH  | 1397 |  4.5 |  0.5 |  90.0% Ar |  55  |     1.3     |  1.9  |          Onset of CH*          |   NB1981[^NB1981]  |
|  ign |   C2H2   | 1314 |  0.8 |   1  |  90.0% Ar |  61  |     1.18    |  1.81 |          Onset of CH*          |  KPK2013[^KPK2013]  |
|  ign |   C2H4   | 1419 |   2  |   3  |  93.0% Ar |  80  |     1.29    |  1.3  |          Onset of CH*          |  SKS2011[^SKS2011]  |
|  ign |   C2H4   | 1428 | 18.6 |   3  |  93.0% Ar |  58  |     1.41    | -1.43 |          Onset of CH*          |  SKS2011[^SKS2011]  |
|  ign |   C2H4   | 1212 |   3  |   1  |  96.0% Ar | 1558 |     1.48    | -1.08 |      Maximum pres rise     |   BS1972[^BS1972]  |
|  ign |   C2H4   | 1655 |   3  |   2  |  97.5% Ar |  144 |     1.28    | -1.29 |      Maximum pres rise     |   BS1972[^BS1972]  |
|  ign |   C2H4   | 1666 |   3  |   2  | 98.75% Ar |  208 |     1.29    | -1.22 |      Maximum pres rise     |   BS1972[^BS1972]  |
|  ign |   C2H6   | 1502 | 7.67 |   1  |  97.3% Ar |  130 |     1.34    | -1.66 |      Maximum pres rise     |  BCS1972[^BCS1972]  |
|  ign |   C2H6   | 1398 | 7.37 |   1  |  97.3% Ar |  290 |     1.38    | -1.34 |      Maximum pres rise     |  BCS1972[^BCS1972]  |
|  ign |   C2H6   | 1555 | 2.15 |   1  |  91.0% Ar |  95  |     1.3     | -1.72 |      Maximum pres rise     |  BCS1972[^BCS1972]  |
|  ign |   C2H6   | 1410 | 2.03 |   1  |  91.0% Ar |  270 |     1.34    | -1.47 |      Maximum pres rise     |  BCS1972[^BCS1972]  |
|  ign |   C3H6   | 1799 | 5.95 |   2  |  94.8% Ar |  92  |     1.52    |  -1.3 |      Maximum pres rise     |   BR1985[^BR1985]  |
|  ign |   C3H8   | 1129 | 67.4 |  0.5 |  91.0% Ar |  650 |     1.28    | -1.29 |      Maximum pres rise     |  LHD2011[^LHD2011]  |
|  ign |   C3H8   | 1061 | 63.8 |  0.5 |  91.0% Ar | 1600 |     1.3     | -1.77 |      Maximum pres rise     |  LHD2011[^LHD2011]  |
|  ign |   C3H8   | 1386 | 2.55 |   1  |  75.0% Ar |  65  |     1.45    |  1.66 |        Maximum CH* rise        |   BT1999[^BT1999]  |
|  ign |   C3H8   | 1778 | 4.14 | 0.72 | 98.47% Ar |  17  |     1.31    | -1.08 |         Onset pres         |   Q1998[^Q1998]   |
|  ign |   PC3H4  | 1311 |   5  |  0.5 |  95.5% Ar |  832 |     1.36    |  1.11 |      Maximum pres rise     |  CSD1996[^CSD1996]  |
|  ign | CH3COCH3 | 1749 | 1.02 |   2  |  92.5% Ar |  110 |     1.3     |  -1.1 |        Maximum CH* rise        |  PBC2009[^PBC2009]  |

### Reference
[^NKP2020]: Nagaraja, S. S., Kukkadapu, G., Panigrahy, S., Liang, J., Lu, H., Pitz, W. J., & Curran, H. J. (2020). A pyrolysis study of allylic hydrocarbon fuels. International Journal of Chemical Kinetics, 52, 964–978.'
[^LJH2007]: Liao, S. Y., Jiang, D. M., Huang, Z. H., Zeng, K., & Cheng, Q. (2007). Determination of the laminar burning velocities for mixtures of ethanol and air at elevated temperatures. Applied Thermal Engineering, 27, 374–380.'
[^ZHW2008]: Zhang, Zhiyuan, Huang, Z., Wang, X., Xiang, J., Wang, X., & Miao, H. (2008). Measurements of laminar burning velocities and Markstein lengths for methanol--air--nitrogen mixtures at elevated pressures and temperatures. Combustion and Flame, 155, 358–368.'
[^EZL1990]: Egolfopoulos, F. N., Zhu, D. L., & Law, C. K. (1990). Experimental and numerical determination of laminar flame speeds: Mixtures of C2-hydrocarbons with oxygen and nitrogen. Symposium (International) on Combustion, 23, 471–478.'
[^HAK1998]: Hassan, M. I., Aung, K. T., Kwon, O. C., & Faeth, G. M. (1998). Properties of laminar premixed hydrocarbon/air flames at various pressures. Journal of Propulsion and Power, 14, 479–488.'
[^JZZ2005]: Jomaas, G., Zheng, X. L., Zhu, D. L., & Law, C. K. (2005). Experimental determination of counterflow ignition temperatures and laminar flame speeds of C2--C3 hydrocarbons at atmospheric and elevated pressures. Proceedings of the Combustion Institute, 30, 193–200.'
[^HT2006]: Hara, T., & Tanoue, K. (2006). Laminar flame speed of ethanol, n-heptane, iso-octane air mixtures. JSAE Paper, 20068518.'
[^NAB2010]: Noorani, K. E., Akih-Kumgeh, B., & Bergthorson, J. M. (2010). Comparative High Temperature Shock Tube Ignition of C1-C4 Primary Alcohols. Energy & Fuels, 24, 5834–5843.'
[^NB1981]: Natarajan, K., & Bhaskaran, K. A. (1981a). An experimental and analytical study of methanol ignition behind shock waves. Combustion and Flame, 43, 35–49.'
[^KPK2013]: Kosarev, I. N., Pakhomov, A. I., Kindysheva, S. V., & Aleksandrov, N. L. (2013). Ignition of acetylene by high-voltage nanosecond discharge. Technical Physics Letters 2013 39:7, 39, 606–608.'
[^SKS2011]: Saxena, S., Kahandawala, M. S. P., & Sidhu, S. S. (2011). A shock tube study of ignition delay in the combustion of ethylene. Combustion and Flame, 158, 1019–1031.'
[^BS1972]: Baker, J. A., & Skinner, G. B. (1972). Shock-tube studies on the ignition of ethylene-oxygen-argon mixtures. Combustion and Flame, 19, 347–350.'
[^BCS1972]: Burcat, A., Crossley, R. W., Scheller, K., & Skinner, G. B. (1972). Shock tube investigation of ignition in ethane-oxygen-argon mixtures. Combustion and Flame, 18, 115–123.'
[^BR1985]: Burcat, A., & Radhakrishnan, K. (1985). High temperature oxidation of propene. Combustion and Flame, 60, 157–169.'
[^LHD2011]: Lam, K. Y., Hong, Z., Davidson, D. F., & Hanson, R. K. (2011). Shock tube ignition delay time measurements in propane/O2/argon mixtures at near-constant-volume conditions. Proceedings of the Combustion Institute, 33, 251–258.'
[^BT1999]: Brown, C. J., & Thomas, G. O. (1999). Experimental studies of shock-induced ignition and transition to detonation in ethylene and propane mixtures. Combustion and Flame, 117, 861–870.'
[^Q1998]: Qin, Z. (1998). Reaction mechanism of propane oxidation.'
[^CSD1996]: Curran, H., Simmie, J. M., Dagaut, P., Voisin, D., & Cathonnet, M. (1996). The ignition and oxidation of allene and propyne: Experiments and kinetic modeling. Symposium (International) on Combustion, 26, 613–620.'
[^PBC2009]: Pichon, S., Black, G., Chaumeix, N., Yahyaoui, M., Simmie, J. M., Curran, H. J., & Donohue, R. (2009). The combustion chemistry of a fuel tracer: Measured flame speeds and ignition delays and a detailed chemical kinetic model for the oxidation of acetone. Combustion and Flame, 156, 494–504.'