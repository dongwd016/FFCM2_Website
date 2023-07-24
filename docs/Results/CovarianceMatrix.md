---
layout: default
title: Covariance Matrix
parent: Results
nav_order: 6
---

# Covariance Matrix

The covariance matrix is one of the key results of NN-MUM-PCE analysis. The matrix of the optimized model provides the pairwise joint probability distribition of the normalized rate coefficients. It reduces the uncertain parameter space of the rate coefficients and reduces the model prediction uncertainties of the optimized model.

- Click [here]({{ site.baseurl }}/assets/data/covariance/visualize_covariance.html) to visualize the posterior covariance matrix. The figure shows graphically this matrix where the color code represents the magnitudes of the probability values.
    - the row and column indices are the 258 rate parameters that remain active after freezing, in the order from C<sub>0</sub> to C<sub>4</sub> reactions. They are listed in [Active Parameters]({{ site.baseurl }}/docs/Results/ActiveParameters/).
    - the figure is interactive, one can use the cursor to see the pair of reactions for each entry of the covariance matrix.
- The prior covariance matrix is a diagonal matrix given as $\lambda^{-2} \mathbf{I}$, where $\lambda$ is the regularization factor and $\mathbf{I}$ is the identity matrix. The posterior covariance matrix is obtained using the Bayes' rule with a multivariate Gaussian as prior distribution.
