---
layout: default
title: Transport Data
parent: Trial Model
nav_order: 4
---

# Transport database in FFCM-2
{: .no_toc }
The table below lists the transport properties for all 96 species in FFCM-2.
{: .fs-6 .fw-300 }

## Table of Contents
{: .no_toc .text-delta }
1. TOC
{:toc}

### Chemkin transport database
The FFCM transport database originates from the Sandia Transport subroutine library [^KDW1986]. The table below lists the parametrization of transport coeffcients used in FFCM-2.

- Geometry: an index indicating the geometrical configuration of the molecule; 0: monatomic atom, 1: linear, 2: nonlinear.
- $\epsilon/k_B$: the Lennard-Jones potential well depth, unit in Kelvins.
- $\sigma$: the Lennard-Jones collision diameter, unit in Angstroms.
- $\mu$: the dipole moment, unit in Debye. A Debye is 10$^{-18}$ cm $^{3/2}$ erg$^{1/2}$.
- $\alpha$: the polarizability, unit in cubic Angstroms.
- $Z_{rot}$: the rotational relaxation collision number at 298K.

| Species | Geometry | $\epsilon/k_B$ | $\sigma$ | $\mu$ | $\alpha$ | $Z_{rot}$ |
|:-----------:|:------------:|:-----------:|:---------:|:------:|:---------:|:--------:|
|      H      |       0      |     145     |    2.05   |    0   |     0     |     0    |
|      H2     |       1      |      38     |    2.92   |    0   |    0.79   |    280   |
|      O      |       0      |      80     |    2.75   |    0   |     0     |     0    |
|      O2     |       1      |    107.4    |   3.458   |    0   |    1.6    |    3.8   |
|      OH     |       1      |      80     |    2.75   |    0   |     0     |     0    |
|     H2O     |       2      |    572.4    |   2.605   |  1.844 |     0     |     4    |
|     HO2     |       2      |    107.4    |   3.458   |    0   |     0     |     1    |
|     H2O2    |       2      |    107.4    |   3.458   |    0   |     0     |    3.8   |
|      HE     |       0      |     10.2    |   2.576   |    0   |     0     |     0    |
|      AR     |       0      |    136.5    |    3.33   |    0   |     0     |     0    |
|      N2     |       1      |    97.53    |   3.621   |    0   |    1.76   |     4    |
|      C      |       0      |     71.4    |   3.298   |    0   |     0     |     0    |
|      CH     |       1      |      80     |    2.75   |    0   |     0     |     1    |
|     CH2     |       2      |     144     |    3.8    |    0   |     0     |     1    |
|    CH2(S)   |       2      |     144     |    3.8    |    0   |     0     |     1    |
|     CH3     |       2      |     144     |    3.8    |    0   |     0     |     1    |
|     CH4     |       2      |    141.4    |   3.746   |    0   |    2.6    |    13    |
|      CO     |       1      |     98.1    |    3.65   |    0   |    1.95   |    1.8   |
|     CO2     |       1      |     244     |   3.763   |    0   |    2.65   |    2.1   |
|     HCO     |       2      |     498     |    3.59   |    0   |     0     |     2    |
|     CH2O    |       2      |     498     |    3.59   |    0   |     0     |     2    |
|    CH2OH    |       2      |     417     |    3.69   |   1.7  |     0     |     2    |
|     CH3O    |       2      |     417     |    3.69   |   1.7  |     0     |     2    |
|    CH3OH    |       2      |    481.8    |   3.626   |    0   |     0     |     1    |
|     C2H     |       1      |     209     |    4.1    |    0   |     0     |    2.5   |
|     C2H2    |       1      |     209     |    4.1    |    0   |     0     |    2.5   |
|     C2H3    |       2      |     209     |    4.1    |    0   |     0     |     1    |
|     C2H4    |       2      |    280.8    |   3.971   |    0   |     0     |    1.5   |
|     C2H5    |       2      |    252.3    |   4.302   |    0   |     0     |    1.5   |
|     C2H6    |       2      |    252.3    |   4.302   |    0   |     0     |    1.5   |
|     HCCO    |       2      |     150     |    2.5    |    0   |     0     |     1    |
|    CH2CO    |       2      |     436     |    3.97   |    0   |     0     |     2    |
|    CH2CHO   |       2      |     436     |    3.97   |    0   |     0     |     2    |
|    CH3CHO   |       2      |     436     |    3.97   |    0   |     0     |     2    |
|    CH3CO    |       2      |     436     |    3.97   |    0   |     0     |     2    |
|     H2CC    |       2      |     209     |    4.1    |    0   |     0     |    2.5   |
|    CH3O2    |       2      |    481.8    |   3.626   |    0   |     0     |     1    |
|    CH3OOH   |       2      |    481.8    |   3.626   |    0   |     0     |     1    |
|    C2H5O2   |       2      |    470.6    |    4.41   |    0   |     0     |    1.5   |
|   C2H5OOH   |       2      |    470.6    |    4.41   |    0   |     0     |    1.5   |
|    C2H2OH   |       2      |    224.7    |   4.162   |    0   |     0     |     1    |
|    C2H3OH   |       2      |     436     |    3.97   |    0   |     0     |     2    |
|    C2H4O    |       2      |     436     |    3.97   |    0   |     0     |     2    |
|    C2H5OH   |       2      |    470.6    |    4.41   |    0   |     0     |    1.5   |
|    C2H4OH   |       2      |    470.6    |    4.41   |    0   |     0     |    1.5   |
|   CH3CHOH   |       2      |    470.6    |    4.41   |    0   |     0     |    1.5   |
|     C3H8    |       2      |    266.8    |   4.982   |    0   |     0     |     1    |
|    NC3H7    |       2      |    266.8    |   4.982   |    0   |     0     |     1    |
|    IC3H7    |       2      |    266.8    |   4.982   |    0   |     0     |     1    |
|     C3H6    |       2      |    298.9    |   4.678   |    0   |     0     |     1    |
|     C3H5    |       2      |     252     |    4.76   |    0   |     0     |     1    |
|   CH3CCH2   |       2      |    266.8    |   4.982   |    0   |     0     |     1    |
|    AC3H4    |       2      |     252     |    4.76   |    0   |     0     |     1    |
|    PC3H4    |       2      |     252     |    4.76   |    0   |     0     |     1    |
|     C3H3    |       2      |     252     |    4.76   |    0   |     0     |     1    |
|   C2H5CHO   |       2      |    435.2    |   4.662   |    0   |     0     |     1    |
|   CH3COCH3  |       2      |    435.5    |    4.86   |    0   |     0     |     1    |
|   CH3COCH2  |       2      |    435.5    |    4.86   |    0   |     0     |     1    |
|   C2H3CHO   |       2      |    428.8    |   4.958   |    0   |     0     |     1    |
|    C3H5OH   |       2      |    481.5    |   4.997   |    0   |     0     |     1    |
|   NC3H7O2   |       2      |    481.5    |   4.997   |    0   |     0     |     1    |
|   NC3H7OOH  |       2      |    481.5    |   4.997   |    0   |     0     |     1    |
|   IC3H7O2   |       2      |    481.5    |   4.997   |    0   |     0     |     1    |
|   IC3H7OOH  |       2      |    481.5    |   4.997   |    0   |     0     |     1    |
|     C4H2    |       1      |     357     |    4.72   |    0   |     0     |     1    |
|    NC4H3    |       2      |     357     |    5.18   |    0   |     0     |     1    |
|    IC4H3    |       2      |     357     |    5.18   |    0   |     0     |     1    |
|     C4H4    |       2      |     357     |    5.18   |    0   |     0     |     1    |
|    NC4H5    |       2      |     357     |    5.18   |    0   |     0     |     1    |
|    IC4H5    |       2      |     357     |    5.18   |    0   |     0     |     1    |
|    C4H5-2   |       2      |     357     |    5.18   |    0   |     0     |     1    |
|     C4H6    |       2      |     357     |    4.72   |    0   |     0     |     1    |
|    C4H612   |       2      |     357     |    5.18   |    0   |     0     |     1    |
|    C4H6-2   |       2      |     357     |    5.18   |    0   |     0     |     1    |
|     C4H7    |       2      |    357.1    |    4.72   |    0   |     0     |     1    |
|    IC4H7    |       2      |     355     |    4.65   |    0   |     0     |     1    |
|   IC4H7-1   |       2      |     357     |   5.176   |    0   |     0     |     1    |
|    C4H81    |       2      |     355     |    4.65   |    0   |     0     |     1    |
|    C4H82    |       2      |     355     |    4.65   |    0   |     0     |     1    |
|    IC4H8    |       2      |     355     |    4.65   |    0   |     0     |     1    |
|    NC4H9    |       2      |     352     |    5.24   |    0   |     0     |     1    |
|    SC4H9    |       2      |     352     |    5.24   |    0   |     0     |     1    |
|    IC4H9    |       2      |     352     |    5.24   |    0   |     0     |     1    |
|    TC4H9    |       2      |     352     |    5.24   |    0   |     0     |     1    |
|    C4H10    |       2      |    350.9    |   5.206   |    0   |     0     |     1    |
|    IC4H10   |       2      |    355.7    |   5.208   |    0   |     0     |     1    |
|    H2C4O    |       2      |     357     |    5.18   |    0   |     0     |     1    |
|  CH2CHCHCHO |       2      |     357     |    5.18   |    0   |     0     |     1    |
|  CH3CHCHCO  |       1      |     357     |    5.18   |    0   |     0     |     1    |
|  CH3CHCHCHO |       1      |     357     |    5.18   |    0   |     0     |     1    |
|   C3H7CHO   |       2      |    464.2    |   5.009   |    0   |     0     |     1    |
|   IC3H7CHO  |       2      |    436.4    |   5.352   |    0   |     0     |     1    |
|  C2H5COCH3  |       2      |     454     |   5.413   |    0   |     0     |     1    |
|  C2H3COCH3  |       2      |     454     |   5.413   |    0   |     0     |     1    |
|     OH*     |       1      |      80     |    2.75   |    0   |     0     |     0    |
|     CH*     |       1      |      80     |    2.75   |    0   |     0     |     0    |
|      H      |       0      |     145     |    2.05   |    0   |     0     |     0    |
|      H2     |       1      |      38     |    2.92   |    0   |    0.79   |    280   |
|      O      |       0      |      80     |    2.75   |    0   |     0     |     0    |
|      O2     |       1      |    107.4    |   3.458   |    0   |    1.6    |    3.8   |
|      OH     |       1      |      80     |    2.75   |    0   |     0     |     0    |
|     H2O     |       2      |    572.4    |   2.605   |  1.844 |     0     |     4    |
|     HO2     |       2      |    107.4    |   3.458   |    0   |     0     |     1    |
|     H2O2    |       2      |    107.4    |   3.458   |    0   |     0     |    3.8   |
|      HE     |       0      |     10.2    |   2.576   |    0   |     0     |     0    |
|      AR     |       0      |    136.5    |    3.33   |    0   |     0     |     0    |
|      N2     |       1      |    97.53    |   3.621   |    0   |    1.76   |     4    |
|      C      |       0      |     71.4    |   3.298   |    0   |     0     |     0    |
|      CH     |       1      |      80     |    2.75   |    0   |     0     |     1    |
|     CH2     |       2      |     144     |    3.8    |    0   |     0     |     1    |
|    CH2(S)   |       2      |     144     |    3.8    |    0   |     0     |     1    |
|     CH3     |       2      |     144     |    3.8    |    0   |     0     |     1    |
|     CH4     |       2      |    141.4    |   3.746   |    0   |    2.6    |    13    |
|      CO     |       1      |     98.1    |    3.65   |    0   |    1.95   |    1.8   |
|     CO2     |       1      |     244     |   3.763   |    0   |    2.65   |    2.1   |
|     HCO     |       2      |     498     |    3.59   |    0   |     0     |     2    |
|     CH2O    |       2      |     498     |    3.59   |    0   |     0     |     2    |
|    CH2OH    |       2      |     417     |    3.69   |   1.7  |     0     |     2    |
|     CH3O    |       2      |     417     |    3.69   |   1.7  |     0     |     2    |
|    CH3OH    |       2      |    481.8    |   3.626   |    0   |     0     |     1    |
|     C2H     |       1      |     209     |    4.1    |    0   |     0     |    2.5   |
|     C2H2    |       1      |     209     |    4.1    |    0   |     0     |    2.5   |
|     C2H3    |       2      |     209     |    4.1    |    0   |     0     |     1    |
|     C2H4    |       2      |    280.8    |   3.971   |    0   |     0     |    1.5   |
|     C2H5    |       2      |    252.3    |   4.302   |    0   |     0     |    1.5   |
|     C2H6    |       2      |    252.3    |   4.302   |    0   |     0     |    1.5   |
|     HCCO    |       2      |     150     |    2.5    |    0   |     0     |     1    |
|    CH2CO    |       2      |     436     |    3.97   |    0   |     0     |     2    |
|    CH2CHO   |       2      |     436     |    3.97   |    0   |     0     |     2    |
|    CH3CHO   |       2      |     436     |    3.97   |    0   |     0     |     2    |
|    CH3CO    |       2      |     436     |    3.97   |    0   |     0     |     2    |
|     H2CC    |       2      |     209     |    4.1    |    0   |     0     |    2.5   |
|    CH3O2    |       2      |    481.8    |   3.626   |    0   |     0     |     1    |
|    CH3OOH   |       2      |    481.8    |   3.626   |    0   |     0     |     1    |
|    C2H5O2   |       2      |    470.6    |    4.41   |    0   |     0     |    1.5   |
|   C2H5OOH   |       2      |    470.6    |    4.41   |    0   |     0     |    1.5   |
|    C2H2OH   |       2      |    224.7    |   4.162   |    0   |     0     |     1    |
|    C2H3OH   |       2      |     436     |    3.97   |    0   |     0     |     2    |
|    C2H4O    |       2      |     436     |    3.97   |    0   |     0     |     2    |
|    C2H5OH   |       2      |    470.6    |    4.41   |    0   |     0     |    1.5   |
|    C2H4OH   |       2      |    470.6    |    4.41   |    0   |     0     |    1.5   |
|   CH3CHOH   |       2      |    470.6    |    4.41   |    0   |     0     |    1.5   |
|     C3H8    |       2      |    266.8    |   4.982   |    0   |     0     |     1    |
|    NC3H7    |       2      |    266.8    |   4.982   |    0   |     0     |     1    |
|    IC3H7    |       2      |    266.8    |   4.982   |    0   |     0     |     1    |
|     C3H6    |       2      |    298.9    |   4.678   |    0   |     0     |     1    |
|     C3H5    |       2      |     252     |    4.76   |    0   |     0     |     1    |
|   CH3CCH2   |       2      |    266.8    |   4.982   |    0   |     0     |     1    |
|    AC3H4    |       2      |     252     |    4.76   |    0   |     0     |     1    |
|    PC3H4    |       2      |     252     |    4.76   |    0   |     0     |     1    |
|     C3H3    |       2      |     252     |    4.76   |    0   |     0     |     1    |
|   C2H5CHO   |       2      |    435.2    |   4.662   |    0   |     0     |     1    |
|   CH3COCH3  |       2      |    435.5    |    4.86   |    0   |     0     |     1    |
|   CH3COCH2  |       2      |    435.5    |    4.86   |    0   |     0     |     1    |
|   C2H3CHO   |       2      |    428.8    |   4.958   |    0   |     0     |     1    |
|    C3H5OH   |       2      |    481.5    |   4.997   |    0   |     0     |     1    |
|   NC3H7O2   |       2      |    481.5    |   4.997   |    0   |     0     |     1    |
|   NC3H7OOH  |       2      |    481.5    |   4.997   |    0   |     0     |     1    |
|   IC3H7O2   |       2      |    481.5    |   4.997   |    0   |     0     |     1    |
|   IC3H7OOH  |       2      |    481.5    |   4.997   |    0   |     0     |     1    |
|     C4H2    |       1      |     357     |    4.72   |    0   |     0     |     1    |
|    NC4H3    |       2      |     357     |    5.18   |    0   |     0     |     1    |
|    IC4H3    |       2      |     357     |    5.18   |    0   |     0     |     1    |
|     C4H4    |       2      |     357     |    5.18   |    0   |     0     |     1    |
|    NC4H5    |       2      |     357     |    5.18   |    0   |     0     |     1    |
|    IC4H5    |       2      |     357     |    5.18   |    0   |     0     |     1    |
|    C4H5-2   |       2      |     357     |    5.18   |    0   |     0     |     1    |
|     C4H6    |       2      |     357     |    4.72   |    0   |     0     |     1    |
|    C4H612   |       2      |     357     |    5.18   |    0   |     0     |     1    |
|    C4H6-2   |       2      |     357     |    5.18   |    0   |     0     |     1    |
|     C4H7    |       2      |    357.1    |    4.72   |    0   |     0     |     1    |
|    IC4H7    |       2      |     355     |    4.65   |    0   |     0     |     1    |
|   IC4H7-1   |       2      |     357     |   5.176   |    0   |     0     |     1    |
|    C4H81    |       2      |     355     |    4.65   |    0   |     0     |     1    |
|    C4H82    |       2      |     355     |    4.65   |    0   |     0     |     1    |
|    IC4H8    |       2      |     355     |    4.65   |    0   |     0     |     1    |
|    NC4H9    |       2      |     352     |    5.24   |    0   |     0     |     1    |
|    SC4H9    |       2      |     352     |    5.24   |    0   |     0     |     1    |
|    IC4H9    |       2      |     352     |    5.24   |    0   |     0     |     1    |
|    TC4H9    |       2      |     352     |    5.24   |    0   |     0     |     1    |
|    C4H10    |       2      |    350.9    |   5.206   |    0   |     0     |     1    |
|    IC4H10   |       2      |    355.7    |   5.208   |    0   |     0     |     1    |
|    H2C4O    |       2      |     357     |    5.18   |    0   |     0     |     1    |
|  CH2CHCHCHO |       2      |     357     |    5.18   |    0   |     0     |     1    |
|  CH3CHCHCO  |       1      |     357     |    5.18   |    0   |     0     |     1    |
|  CH3CHCHCHO |       1      |     357     |    5.18   |    0   |     0     |     1    |
|   C3H7CHO   |       2      |    464.2    |   5.009   |    0   |     0     |     1    |
|   IC3H7CHO  |       2      |    436.4    |   5.352   |    0   |     0     |     1    |
|  C2H5COCH3  |       2      |     454     |   5.413   |    0   |     0     |     1    |
|  C2H3COCH3  |       2      |     454     |   5.413   |    0   |     0     |     1    |
|     OH*     |       1      |      80     |    2.75   |    0   |     0     |     0    |
|     CH*     |       1      |      80     |    2.75   |    0   |     0     |     0    |


### Binary transport database

In the current FFCM-2 release, the binary transport coefficients are not considered. In FFCM-1, however, the transport library is appended with selected pairs of diffusion coefficients from [^2]$^{,}$[^3]$^{,}$[^4]$^{,}$[^5]$^{,}$[^6]$^{,}$[^7]. These are mostly pairs involving light species (H and H<sub>2</sub>). For these species, the repulsive part of the Lennard-Jones (L-J) 12-6 potential function is known to be too stiff to accurately model diffusion coefficients at high temperatures [^8]. For this reason, the diffusion coefficients of relevant, key pairs should be directly modeled without resorting to the use of tabulated L-J 12-6 collision integrals, as discussed in [^2]${,}$[^3]. Selected pairs of diffusion coefficients in the form of polynomial coefficients are adopted. These coefficients are obtained from the potential functions directly calculated from high-level quantum chemistry and quantum scattering calculations. The temperature dependence of binary diffusion coefficients at 1 atm is parameterized as

$$
\begin{equation}
    \ln D_{ij}=d_0+d_1\ln T+d_2(\ln T)^2+d_3(\ln T)^3
\end{equation}
$$

where $d_k$ (k=0,1,2,3) is the polynomial coefficients. For the mixture-averaged transport formulation, the above polynomial is sufficient for simulations. The multi-component transport formulation as well as the computation of thermal diffusion ratio in both transport formulations, however, requires the input of the ratios of collision integrals[^KDW1986]:

$$
\begin{align}
    A_{ij}^* &= \Omega_{ij}^{(2,2)}/(2\Omega_{ij}^{(1,1)}) \\
    B_{ij}^* &= (5\Omega_{ij}^{(1,2)}-\Omega_{ij}^{(1,3)})/(3\Omega_{ij}^{(1,1)}) \\
    C_{ij}^* &= \Omega_{ij}^{(1,2)}/(3\Omega_{ij}^{(1,1)})
\end{align}
$$

The above ratios are also parameterized as

$$
\begin{align}
    A_{ij}^* &= a_0+a_1\ln T_{ij}^*+a_2(\ln T_{ij}^*)^2+a_3(\ln T_{ij}^*)^3 \\
    B_{ij}^* &= b_0+a_1\ln T_{ij}^*+b_2(\ln T_{ij}^*)^2+b_3(\ln T_{ij}^*)^3 \\
    C_{ij}^* &= c_0+c_1\ln T_{ij}^*+c_2(\ln T_{ij}^*)^2+c_3(\ln T_{ij}^*)^3
\end{align}
$$

where $a_k$, $b_k$, and $c_k$ (k=0, 3) are the polynomial coefficients whose values are found also in Table 1, $T_{ij}^{\*}$ is the reduced temperature $T_{ij}^{\*} =kT/\varepsilon_{ij}$ and $\varepsilon_{ij}$ is the well depth. When implementing non-L-J potentials for the key pairs, however, $T_{ij}^{\*}$ is undefined. Therefore, the tabulated coefficients for $A_{ij}^{\*}$, $B_{ij}^{\*}$, and $C_{ij}^{\*}$ were calculated for the actual temperature $T_{ij}$ instead, and special handling was added for these coefficients in the transport data interpreter code. These polynomials can be implemented to both Cantera codes and ChemKin PREMIX codes. For example, the [set_binary_diff_coeffs_polynomial](https://cantera.org/documentation/dev/sphinx/html/cython/transport.html#cantera.Transport.set_binary_diff_coeffs_polynomial) and [set_collision_integral_polynomial](https://cantera.org/documentation/dev/sphinx/html/cython/transport.html#cantera.Transport.set_collision_integral_polynomial) subroutines in the latest version of Cantera (version 2.6.0) are useful.

## References

[^KDW1986]: Kee R, Dixon-Lewis G, Warnatz J, Coltrin M, Miller J. Sandia report SAND86-8246. Sandia National Laboratories, New Mexico. 1986.

[^2]:  Middha P, Yang B, Wang H. A first-principle calculation of the binary diffusion coefficients pertinent to kinetic modeling of hydrogen/oxygen/helium flames. Proc Combust Inst. 2002;29:1361-9.

[^3]:  Middha P, Wang H. First-principle calculation for the high-temperature diffusion coefficients of small pairs: The H-Ar case. Combust Theor Model. 2005;9:353-63.

[^4]:  Stallcop JR, Partridge H, Levin E. Effective potential energies and transport cross sections for atom-molecule interactions of nitrogen and oxygen. Phys Rev A. 2001;64:042722.

[^5]:  Stallcop JR, Partridge H, Walch SP, Levin E. H–N2 interaction energies, transport cross sections, and collision integrals. J Chem Phys. 1992;97:3431-6.

[^6]:  Stallcop JR, Partridge H, Levin E. Effective potential energies and transport cross sections for interactions of hydrogen and nitrogen. Phys Rev A. 2000;62:062709.

[^7]:  Stallcop JR, Levin E, Partridge H. Transport properties of hydrogen. J Thermophys Heat Transfer. 1998;12:514-9.

[^8]:  Paul P, Warnatz J. A re-evaluation of the means used to calculate transport properties of reacting flows. Symp (Int) Combust. 1998;27:495-504.

