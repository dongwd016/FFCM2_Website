---
layout: default
title: Download
nav_order: 10
---

# Downloads
The current page provides access to the optimized FFCM-2 and the covariance matrix, in both Cantera format and Chemkin format. To obtain the trial FFCM-2, please contact Prof. Hai Wang. 
{: .fs-6 .fw-300 }

## FFCM-2 in Cantera format
[CTI]({{ site.baseurl }}/assets/data/optmodel/FFCM2_model.cti){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[YAML]({{ site.baseurl }}/assets/data/optmodel/FFCM2_model.cti){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

## FFCM-2 in Chemkin format
[Reactions]({{ site.baseurl }}/assets/data/optmodel/FFCM2_reactions.inp){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

[Transport]({{ site.baseurl }}/assets/data/optmodel/FFCM2_transport.dat){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

[Thermochemistry]({{ site.baseurl }}/assets/data/optmodel/FFCM2_thermo.dat){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Thermochemistry (refit to 6000 K)]({{ site.baseurl }}/assets/data/optmodel/FFCM2_thermo.dat){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

{: .note }
In many high-speed combustion simulations, temperature may be higher than 6000 K. For several species, the NASA polynomials are not fit for over 6000 K. We provide a thermochemistry file that extends the polynomial fits to over 6000 K for all species.

## Covariance Matrix
[Covariance matrix]({{ site.baseurl }}/assets/data/covariance/Covariance_matrix.csv){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Readme]({{ site.baseurl }}/assets/data/covariance/README_covariance.csv){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

{: .note }
The covariance matrix $\mathbf{\Sigma_{aa}} \in \mathbb{R}^{258 \times 258}$ describes the correlation among the normalized rate parameters $\mathbf{x_a} \in \mathbb{R}^{258}$ that remain active after parameter freezing. It can be used to sample the optimized model in the posterior parametric space, using multivariate normal distribution centered at $\mathbf{\mu_a} = \mathbf{0}$. The readme file specifies the rate parameter that corresponds to each dimension of the matrix, along with the uncertainty factor $f$. Given the $k^{th}$ sample $\mathbf{x_k}\sim \mathcal{N}(\mathbf{0}, \mathbf{\Sigma_{aa}})$, the multiplier is calculated by $f^{\mathbf{x_{k}}}$. The sampled rate parameters $A_{k}$ is obtained by multiplying the optimized nominal rate parameter $A_{\*}$ by the multiplier $A_{k} = A_{\*} \times f^{\mathbf{x_{k}}}$.



