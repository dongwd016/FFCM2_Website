---
layout: default
title: Download
nav_order: 10
---

# Downloads
The current page provides access to the optimized FFCM-2 and the covariance matrix, in both Cantera format and Chemkin format. To obtain the trial FFCM-2, please contact Prof. Hai Wang. 
{: .fs-6 .fw-300 }

## FFCM-2 in Cantera format
[CTI]({{ site.url }}{{ site.baseurl }}/assets/data/optmodel/FFCM2_model.cti){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[YAML]({{ site.url }}{{ site.baseurl }}/assets/data/optmodel/FFCM2_model.yaml){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[CTI (9999 K)]({{ site.url }}{{ site.baseurl }}/assets/data/optmodel/FFCM2_model_NEW_POLY_9999K.cti){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[YAML (9999 K)]({{ site.url }}{{ site.baseurl }}/assets/data/optmodel/FFCM2_model_NEW_POLY_9999K.yaml){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

## FFCM-2 in Chemkin format
[Reactions]({{ site.url }}{{ site.baseurl }}/assets/data/optmodel/FFCM2_reactions.inp.txt){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

[Transport]({{ site.url }}{{ site.baseurl }}/assets/data/optmodel/FFCM2_transport.txt){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

[Thermochemistry]({{ site.url }}{{ site.baseurl }}/assets/data/optmodel/FFCM2_thermo.txt){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Thermochemistry (refit to 9999 K)]({{ site.url }}{{ site.baseurl }}/assets/data/optmodel/thermo_FFCM2_NEW_POLY_9999K.dat){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

{: .note }
The above thermochemical data file is in the seven-coefficient NASA polynomial format.  In some high-speed combustion simulations, local temperature can exceed the upper temperature limit of the polynomial fits.  If the local temperature of your simulation does not exceed 4,000 K, the base thermochemical data file (Thermochemistry) is sufficient for your application.  If the local temperature can exceed 4,000 K, please use the second thermochemistry file (Thermochemistry - extended - to be made available).  The fits are made up to 9,999 K, even though 6,000 K is indicated in the species line.

## Covariance Matrix
[Covariance matrix]({{ site.url }}{{ site.baseurl }}/assets/data/covariance/Covariance_matrix.csv){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Readme]({{ site.url }}{{ site.baseurl }}/assets/data/covariance/README_covariance.csv){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

{: .note }
The covariance matrix $\mathbf{\Sigma_{aa}} \in \mathbb{R}^{258 \times 258}$ describes the correlation among the normalized rate parameters $\mathbf{x_a} \in \mathbb{R}^{258}$ that remain active after parameter freezing. It can be used to sample the optimized model in the posterior parametric space, using multivariate normal distribution centered at $\mathbf{\mu_a} = \mathbf{0}$. The readme file specifies the rate parameter that corresponds to each dimension of the matrix, along with the uncertainty factor $f$. Given the $k^{th}$ sample $\mathbf{x_k}\sim \mathcal{N}(\mathbf{0}, \mathbf{\Sigma_{aa}})$, the multiplier is calculated by $f^{\mathbf{x_{k}}}$. The sampled rate parameters $A_{k}$ is obtained by multiplying the optimized nominal rate parameter $A_{\*}$ by the multiplier $A_{k} = A_{\*} \times f^{\mathbf{x_{k}}}$.



