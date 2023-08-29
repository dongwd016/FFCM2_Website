---
layout: default
title: Optimization and Uncertainty Minimization
nav_order: 6
---

# Optimization and Uncertainty Minimization
{: .no_toc }

Algorithm and mathematical formulas for FFCM-2 optimization and uncertainty minimization
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}
The Method of Uncertainty Minimization by Polynomial Chaos Expansion (MUM-PCE) was developed in earlier work for reaction
model optimization and uncertainty minimization[^SW2011]$^{,}$[^WS2015]. FFCM-1 was developed using the MUM-PCE framework. The 
optimal rate parameters were obtained by minimizing the objective function, and the covariance matrix that describes the 
correlation between each pair of rate parameters was updated using the Bayesian theorem[^STW2016]. The current NN-MUM-PCE
approach builds on the MUM-PCE framework with some adaptation. In this page, we explain the algorithms and mathematical 
formulas for NN-MUM-PCE, and highlight the a few unique features.

## Objective function
Similar to MUM-PCE, the NN-MUM-PCE finds the optimal rate parameter assignments $\mathbf x^*$ by solving a
nonlinear least-squares optimization problem 

$$
\begin{align}
    \underset{\mathbf{x}}{\text{minimize}} &\quad \Phi ({\mathbf x}) \\
    \text{subject to } &\quad \mathbf{-1} \leq \mathbf{x} \leq \mathbf{1}
\end{align}
$$

where the objective function $\Phi(\mathbf{x})$ is given as

$$
\begin{equation}
\Phi(\mathbf{x}) = \min_{\mathbf x} \left\{\sum_{m=1}^M \left(\frac{y_m(\mathbf x) - y_{m,obs}}{\sigma_{m,obs}}\right)^2 + \sum_{k=1}^N (\lambda x_k)^2 \right\}
\end{equation}
$$ 

where $M$ is the number of targets considered, $y_m (\mathbf{x})$ and $y_{m,obs}$ are 
the model prediction and the experimental value of the $m^{th}$ target, respectively. $\sigma_{m,obs}$ represents the data uncertainty. 

For the objective function $\Phi(\mathbf{x})$, 
- **the first term** measures the deviation between the model prediction $y_{m}(\mathbf{x})$ and the experimental value $y_{m,obs}$, inversely weighted by the sqaure of the data uncertainty $\sigma_{m,obs}$; 
- **the second term** is the Euclidean norm of the normalized rate parameter $\mathbf{x}$, representing the distances of the optimized rate parameters $$\mathbf{x}^*$$ from the trial assignments $$\mathbf{x} = \mathbf{0}$$.
- $\lambda$ is a regularization coefficient, governing the weight applied to the reaction kinetics relative to combustion property data.

In FFCM-1, an unconstrained optimization problem was solved. Unique to the FFCM-2 work is that the constraints of rate parameters are explicitly applied to the optimization to ensure the physical soundness and interpretability of the optimized rate parameters. 


## Optimization algorithm
In the MUM-PCE approach, the optimization was solved using the Levenberg-Marquardt (LM) algorithm, which works well for low-dimensional, unbounded problems. Also, the constraints on the rate parameters $\mathbf{x}$ was not explicitly imposed. FFCM-2, however, is an exceptionally higher-dimensional, sparse problem. We leveraged the trust region reflective (TRF) algorithm from the SciPy nonlinear least squares optimizer `scipy.optimize.leastsquares`. The TRF algorithm is a robust method that is particularly suitable for large sparse problems with bounds, and it explicitly applies the parameter bounds so that the physical soundness of the optimized rate parameters are ensured. The TRF algorithm requires as input the gradient of $y$ with respect to the optimization variables $\mathbf{x}$, which is available analytically, as discussed before.

## Inconsistent targets
MUM-PCE allows us to evaluates the consistency of reaction model with respect to the experimental data by calculating the $F$ score of a target $m$ as

$$
\begin{equation}
    F_m = \frac{y_{m,obs} - y_{m,opt}}{2\sigma_{m,obs}}
\end{equation}
$$

where $y_{m,opt}$ is the optimized model prediction. A target $m$ is regarded as inconsistent when $\|F_m\| > 1$. That is, the optimized model cannot reconcile the target within its experimental uncertainty by adjusting the rate parameters within the uncertainty limits. The inconsistent targets are removed from the target list and the model is re-optimized. This process is carried out iteratively until all remaining targets are consistent. The inconsistent targets are usually further examined to understand the source of inconsistency. Analysing the inconsistent targets shed light on the refinement of the reation models (e.g., missing reactions, inappropriate rate constant assignments) and the uncertainty/noise in the combustion property data.

## Uncertainty Minimization
The uncertainty minimization is achieved by deriving the posterior covariance matrix using the Bayesian theorem, assuming the trial rate parameters follow a multivariate log-normal distribution. If we linearize the response surface at the optimal point and express $\mathbf{x^*}$ as 

$$
\begin{equation}
    \mathbf{x^*} = \mathbf{x^{(0)*}} + \mathbf{x^{(1)*}} \xi,
\end{equation}
$$

where $\xi \sim \mathcal{N}(0,1)$ is a standard normal random variable; the optimized rate parameters is represented by the mean $\mathbf{x}^{(0)\*}$. The posterior covariance matrix $\Sigma^*$ is obtained by

$$
\begin{equation}
    \Sigma^*= \mathbf{x^{(1)*}} \mathbf{x^{(1)*{T}}} = \Big( \sum_{m=1}^M \frac{\mathbf{J_m}^T \mathbf{J_m}}{\sigma_{m,obs}^2} + \lambda^2 \mathbf{I}\Big)^{-1},
\end{equation}
$$

where $\textbf{I}$ is the identity matrix, and $\mathbf{J_m}$ is the Jacobian matrix evaluated at $\mathbf{x} = \mathbf{x^{(0)*}}$,

$$
\begin{equation}
    \mathbf{J_m} = \frac{\partial y_m}{\partial \mathbf{x}} \Big|_{\mathbf{x} = \mathbf{x^{(0)*}}}
\end{equation}
$$

The prediction uncertainty of the trial or optimized model $\sigma_m^{*}$ can then be calculated using polynomial chaos expansions, 

$$
\begin{equation}
    \sigma_{m}^* = \|\mathbf{J_m}^T \mathbf{L}\|_2^2 + \frac{1}{2} \|\mathbf{L}^T \mathbf{H_m} \mathbf{L}\|_F^2,
\end{equation}
$$

where $\mathbf{J_m}$ and $\mathbf{H_m}$ are the Jacobian and Hessian matrix at the optimal point, and $\mathbf{L}$ is the Cholesky decomposition of the covariance matrix. For the trial model, the covariance matrix is a diagonal matrix given by $\lambda^{-2}\textbf{I}$. For the optimized model, the posterior covariance matrix $\Sigma^*$ is given by equation above.

## Parameter Freezing
The NN-MUM-PCE framework allows us to freeze unnecessary parameters after optimization. The current NN-RS permits all rate parameters to be optimized. Although we used massive sets of targets, not all rate parameters can be profitably optimized and constrained, due to the effect sparsity of the combustion chemistry models. Many reactions have negligible effect. Thus, we found it useful to freeze unnecessary parameters after optimization. This helps to suppress noise and allows easier interpretation of the optimization results (especially the perturbed rate constants).

### Unnecessary parameters
The $i^{th}$ rate parameter $x_i$ is regarded as unnecessary and should be frozen (not optimized) when,

- $\|A_{i,opt}/A_{i,0} - 1\| < \chi_A$
- $\sigma_{i,opt} > \chi_{2\sigma}$

where $A_{i,opt}$, $A_{i,0}$ are the $A$-factor of the $i^{th}$ rate parameter for the optimized and trial models, respectively. ${\sigma_{i, opt}}$ represents the posterior uncertainty factor of the $i^{th}$ rate parameter. 

$\chi_A$, $\chi_{2\sigma}$ set the threshold for the multiplier $A_{i,opt}/A_{i,0}$ and the posterior uncertainty. A small multiplier after optimization means the parameter does not make significant contribution to improving the model prediction; A large posterior parameter uncertainty means the parameter cannot be constrained by the given target set and thus does not contribute to minimizing the
model prediction uncertainties. From this analysis, we divide the parameters $\mathbf{x}$ to two sets of rate parameters, the optimized set $\mathbf{x_a}$ and the unoptimized set $\mathbf{x_f}$. 

### Conditional normal distribution
The conditional normal distribution is applied to freeze the unoptimized set $\mathbf{x_f}$ back to the trial values $\mathbf{x_f} = \mathbf{0}$. The distribution for the optimized set $\mathbf{x_a}$ are derived analytically, 

$$
\begin{align}
    \mathbf{x} \sim \mathcal{N}(\mathbf{\mu}, \mathbf{\Sigma}) = \mathcal{N}(\begin{bmatrix}
    \mathbf{\mu_a} \\
    \mathbf{\mu_f} 
  \end{bmatrix}, \begin{bmatrix}
    \mathbf{\Sigma_{aa}} & \mathbf{\Sigma_{af}}\\
    \mathbf{\Sigma_{fa}} & \mathbf{\Sigma_{ff}}
  \end{bmatrix}),
\end{align}
$$

where

$$
\begin{equation}
    \mathbf{\mu_a}|_{\mathbf{x_f} = \mu_f} = \mathbf{\mu_a + \Sigma_{aa} \Sigma_{ff}^{-1} (x_f - \mu_f)},
\end{equation}
$$

$$
\begin{equation}
    \mathbf{\Sigma_{a}|_{\mathbf{x_f} = \mu_f} = \Sigma_{aa} - \Sigma_{af} \Sigma_{ff}^{-1} \Sigma_{fa}}.
\end{equation}
$$

The choice of $\chi_A$, $\chi_{2\sigma}$ are determined based on the specific problem settings. A parametric study is provided on the summary results page.

## Joint optimization of $A$-factors and activation energies
In the original MUM-PCE framework, only $A$-factors are considered as optimization parameters. When a large array of targets at different temperatures are considered, they may drive the changes of a particular rate parameter in opposite direactions. This motivates the joint optimization of $A$-factor and activation energy $E$. For example, Varga et al.[^VNO2015] developed a method for co-optimizing all rate parameters. In the framework of MUM-PCE, Sheen et al.[^SRT2013] co-optimized $A$ and $E$, assuming the rate parameters are independently distributed. Tao et al.[^TW2019] extended the MUM-PCE framework to include joint and correlated $A$ and $E$ optimization using a block diagonal covariance matrix. The approach developed by Tao et al.[^TW2019] is implemented in the NN-MUM-PCE framwork.

### Augmented normalized rate parameters
If we consider the $i$-th reaction with a modified Arrhenius expression

$$
\begin{equation}
    k_i = A_i T^{n_i} e^{-E_i/T}
\end{equation}
$$

and define the normalized rate parameter $\mathbf{x}_i$ as

$$
\begin{equation}
    \mathbf{x}_i = [x_{A,i}, x_{E,i}]^T 
\end{equation}
$$

where

$$
\begin{equation}
    x_{A,i} = \frac{\ln(A_i/A_{0,i})}{\ln f_i}, \quad x_{E,i} = \frac{E_i - E_{0,i}}{T_{\text{ref}}\ln f_i},
\end{equation}
$$

where $f_i$ is the temperature-independent uncertainty factor of $k_i$ and $T_{\text{ref}}$ is a reference temperature chosen as 1000 K. Then the augmented normalized rate parameter $x_i$ can be related to $x_{A,i}$ and $x_{E,i}$ as

$$
\begin{equation}
    x_i = \frac{\ln(k_i/k_{0,i})}{\ln f_i} = x_{A, i} - \frac{T_{\text{ref}}}{T} x_{E, i}.
\end{equation}
$$

Herein, we consider the temperature dependency $n_i$ a constant and is not treated as an optimization parameter. Using the aforementioned formulation, a response surface $y_m(\mathbf{x})$ conventionally expressed as a function of $x_i$ can be expanded as a function of $x_{A,i}$ and $x_{E,i}$. The optimization can be applied to the augmented rate parameters for joint $A$ and $E$ optimization.

### Objective function for joint optimization
The objective function for the joint $A$ and $E$ optimization is given as

$$
\begin{align}
    \Phi (\mathbf{X}) &= \Phi_{exp} (\mathbf{X}) + \Phi_{rate} (\mathbf{X})\\
    &= \sum_{m=1}^M \left(\frac{y_m(\mathbf{X}) - y_{m,obs}}{\sigma_{m,obs}}\right)^2 + \sum_{k=1}^N \Phi^{(0)} (\mathbf{x_k})
    % \frac{1}{2} (\lambda x_i)^2_{T=T_{\text{min}}} + \frac{1}{2} (\lambda x_i)^2_{T=T_{\text{max}}}
\end{align}
$$

where $\Phi_i^{(0)} (x_{A,i}, x_{E,i})$ is the prior joint probability distribution function of $x_{A, i}$ and $x_{E, i}$, defined as

$$
\begin{equation}
    \Phi_i^{(0)} (x_{A,i}, x_{E,i}) = \frac{1}{2} (\lambda x_i)^2_{T=T_{\text{min}}} + \frac{1}{2} (\lambda x_i)^2_{T=T_{\text{max}}}
\end{equation}
$$

and the inverse of the covariance matrix $\Sigma_i^{(0) -1}$ is a block diagonal matrix, expressed as

$$
\begin{equation}
    \Sigma_{i}^{(0) -1} = \frac{\lambda^2}{2} \begin{bmatrix} 2 & -T_{\text{ref}}(T^{-1}_{\text{min}} + T^{-1}_{\text{max}}) \\ -T_{\text{ref}}(T^{-1}_{\text{min}} + T^{-1}_{\text{max}}) & T_{\text{ref}}^2 (T^{-2}_{\text{min}} + T^{-2}_{\text{max}}) \end{bmatrix}
\end{equation}
$$

Here, we choose $T_{\text{min}} = 300$ K and $T_{\text{max}} = 2500$ K. 

### Torque calculation
Considering the first term in the objective function (Equation 1), we express it as a "potential" function $\Phi_t(X)$ and the force can be derived by taking the derivative,

$$
\begin{equation}
    \Phi_t(X) = \sum_{m=1}^{M} \Big(\frac{y_m(\mathbf{x}) - y_m^{\text{obs}}}{\sigma_m^{\text{obs}}}\Big)^2 = \sum_{m=1}^{M} \frac{1}{(\sigma_m^{\text{obs}})^2} \Big( \sum_{i=1}^I a_{m,i} x_i - \Delta y_m({\mathbf{0}}) \Big)^2,
\end{equation}
$$

$$
\begin{equation}
    \Delta y_m({\mathbf{0}}) = y_{m}^{obs} - y_m ({\mathbf{0}}),
\end{equation}
$$

$$
\begin{equation}
    F_{m,i} = -\frac{\partial \Phi_{t,m} (\mathbf{X})}{\partial x_i} = 2 \frac{a_{m,i}}{(\sigma_{m}^{obs})^2} \Delta y_m(\mathbf{X}),
\end{equation}
$$

$$
\begin{equation}
    \tau_i = \sum_{m=1}^M F_{m,i} \Big( \frac{1000}{T_{\text{eff} ,m,i}} - 1 \Big).
\end{equation}
$$

A reaction with large torque values indicate that its A-factor and activation energy may need to be optimized jointly.


## References
[^ZDV2023a]: Zhang, Y., Dong, W., Vandewalle, L. A., Xu, R., Smith, G. P., & Wang, H. (2023). Neural network approach to response surface development for reaction model optimization and uncertainty minimization. Combustion and Flame, 251, 112679.

[^SW2011]: Sheen, D. A., & Wang, H. (2011). The method of uncertainty quantification and minimization using polynomial chaos expansions. Combustion and Flame, 158(12), 2358-2374.

[^STW2016]: G.P. Smith, Y. Tao, and H. Wang, Foundational Fuel Chemistry Model Version 1.0 (FFCM-1), http://nanoenergy.stanford.edu/ffcm1, 2016.

[^WS2015]: Wang, H., & Sheen, D. A. (2015). Combustion kinetic model uncertainty quantification, propagation and minimization. Progress in Energy and Combustion Science, 47, 1-31.

[^TW2019]: Tao, Y., & Wang, H. (2019). Joint probability distribution of Arrhenius parameters in reaction model optimization and uncertainty minimization. Proceedings of the Combustion Institute, 37(1), 817-824.

[^SRT2013]: Sheen, D. A., Rosado-Reyes, C. M., & Tsang, W. (2013). Kinetics of H atom attack on unsaturated hydrocarbons using spectral uncertainty propagation and minimization techniques. Proceedings of the Combustion Institute, 34(1), 527-536.

[^VNO2015]: Varga, T., Nagy, T., Olm, C., Zsély, I. G., Pálvölgyi, R., Valkó, É., Vincze, G., Cserháti, M., Curran, H. J. & Turányi, T. (2015). Optimization of a hydrogen combustion mechanism using both direct and indirect measurements. Proceedings of the Combustion Institute, 35(1), 589-596.
