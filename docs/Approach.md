---
layout: default
title: Approach Overview
nav_order: 2
---

# Approach Overview
{: .no_toc }
The workflow of FFCM-2 development is outlined in the diagram below, followed by discussion of each key element of the framework.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

<p align="center">
<img src="{{ site.baseurl }}/assets/images/FFCMApproach.png" alt="NN-MUM-PCE approach" width="1000" height="1000">
<br>
<i>The overall workflow of FFCM-2 development</i>
</p>

### Trial Model and Rate Constant Evaluation 
A trial reaction model is compiled along with its associated thermochemical and transport data, fronm an extensive literature review of exisiting kinetic knowledge. The evaluation of reaction rate constants relies on experimental measurements, ab initio theoretical calculations, or estimation based on analogous reactions. In addition to the nominal rate constant expression, the uncertainty factor of each reaction is estimated. 

### Experimental data collection and evaluation
Extensive literature review was carried out to compile the **Stanford Fundamental Combustion Property Database (SFCPD)**. Currently **SFCPD** contains 1192 sets of legacy combustion data dating back to 1937. Relevant properties include the global combustion responses (laminar flame speeds and shock tube ignition delay measurements) and detailed time-history profiles of species in shock tubes. Selected flow reactor and low pressure burner flame measurements are also considered. 

Targets for model optimization and validation were selected from **SFCPD**. Uncertainty analysis is performed for each of these targets, taking into consideration the statistical consistency and the generic uncertainties (e.g., uncertainty in the temperature behind reflected shock $T_5$ and due to impurity). Specific target conditions and target values are chosen to best represent the thermodynamic condition range of each data set for a given target fuel/species.

### Preliminary Test
The trial model is subject to extensive, pre-optimization tests against selected targets. Sensitivity analyses were performed to identify certain problems in the trial model. For example, after an initial screening test, it was determined that the model uncertainty for the laminar flame speed of H<sub>2</sub>/air mixtures can be significantly reduced if the uncertainty in the rate coefficient of the reaction

$$
\begin{equation}
    \text{H}_2 + \text{OH} \rightleftharpoons \text{H}_{2}\text{O} + \text{H}
\end{equation}    
$$

is reduced to the $\pm 20\%$ level. Prof. Han's group at Stanford subsequently made the measurement to reduce the $2\sigma$ rate uncertainty to $\pm 17\%$ [^LDH2013]. The measurement suggests that the higher end values within the uncertainty band of the measured H<sub>2</sub>/air laminar flame speed are probably more accurate than the lower values. Preliminary tests also include forward uncertainty quantification (**UQ**). The quality of the current kinetic rate knowledge is accessed in its predictive precision against the selected target. 

### Optimization and Uncertainty Minimization
The Method of Uncertainty Minimization using Polynomial Chaos Expansion [^SW2011]$^{,}$[^WS2015] (**MUM-PCE**) was developed earlier for the optimization and uncertainty minimization of combustion chemistry reaction models. In the FFCM-2 effort, we extended the MUM-PCE framework to **NN-MUM-PCE** [^ZDV2023a], using neural networks as response surfaces to overcome difficulties of high parameter dimensionality.  

The following steps are taken: 
- Develop neural network (NN) response surfaces for each optimization target.
- Solve a globally constrainted optimization problem against a collection of targets. 
- Perform optimization iteratively and remove inconsistent targets in each iteration, until all remaining targets are consistent.
- Obtain the posterior mean and covariance matrix of the optimization variables, using the Bayesian theory with a Gaussian prior. The posterior covariance matrix describes the joint probability distribution function of the rate parameters. It reduces the parameter uncertainty space and minimizes the model prediction uncertainties.
- Identify rate parameters that do not contribute to improving the models. These unconstrained parameters are frozen using the conditional multivariate Gaussian formula to suppress noises and produce optimization results that are easier to interpret. 

### Validation and Test
We distinguish model validation from model test.[^WS2015] Validation refers to tests against experimental data in which the model prediction uncertainty is also given; whereas a test involves only an "agree-disagree" comparison of a model prediction against its underlying data. A test serves the purpose of showing the model capture the essential physics and quantitatively, it shows that the model is not "wrong."  A validation test is more stringent as it not only compares the nominal prediction against its underlying data, it also provides a quantitative assessment of the model uncertainty against the experimental data uncertainty. In our study, the posterior model is **validated** against the set of experimental data from which the optimization targets are selected. Tests are made for a wider range of combustion data not considered in the target set.

### Further Analysis
Further analyses of the model and the target data are made to reveal key uncertainty in several aspects of the problems, including the rate coefficient and reaction pathways, and the combustion property data. Recommendations are made and documented on the basis of these analyses.

### References
[^ZDV2023a]: Zhang, Y., Dong, W., Vandewalle, L. A., Xu, R., Smith, G. P., & Wang, H. (2023). Neural network approach to response surface development for reaction model optimization and uncertainty minimization. Combustion and Flame, 251, 112679.

[^SW2011]: Sheen, D. A., & Wang, H. (2011). The method of uncertainty quantification and minimization using polynomial chaos expansions. Combustion and Flame, 158(12), 2358-2374.

[^LDH2013]: Lam, K. Y., Davidson, D. F., & Hanson, R. K. (2013). A shock tube study of H2+ OH -> H2O+ H using OH laser absorption. International Journal of Chemical Kinetics, 45(6), 363-373.

[^WS2015]: Wang, H., & Sheen, D. A. (2015). Combustion kinetic model uncertainty quantification, propagation and minimization. Progress in Energy and Combustion Science, 47, 1-31.