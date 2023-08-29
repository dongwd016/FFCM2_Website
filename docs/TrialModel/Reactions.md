---
layout: default
title: Reactions & Rate Constants
parent: Trial Model
nav_order: 2
---

# Reactions in FFCM-2
{: .no_toc }
Overview of reaction pathways and rate coefficients in FFCM-2, and their uncertainty factors.
{: .fs-6 .fw-300 }

1. TOC
{:toc}

## Trial model as a searchable table
Click [here]({{ site.url }}{{ site.baseurl }}/assets/data/trialmodel/table.html) for a searchable table that documents the trial model rate coefficients and sources and comments for each individual reaction is available. In the table, one can select reaction for a particular species using the filter option in the Species column.
- No.: index of the reaction in FFCM-2, ranging from 1 to 1054.
- Reaction type: the type of a reaction, one of elementary reaction, three-body reaction, falloff reaction and PLOG reaction.
- Parameter type: the type of rate parameters, e.g., Arrhenius rate coefficient (A-factor), three-body Chaperon efficiency, falloff parameters (high pressure limit, low pressure limit and Troe centering parameter), and PLOG rate coefficient for one given pressure.
- Rate constant
  - A: pre-exponential factor (A-factor), unit given by cm$^3$, mol and s;
  - n: temperature dependency, unitless;
  - Ea: activation energy, unit cal $\cdot$ mol$^{-1}$.
  - Enhancement factor: three-body Chaperon efficiency enhancement factor (relative to N<sub>2</sub> or Ar).
- Uncertainty factor: the uncertainty factor of the rate coefficient assigned for the trial model.
- Source: references considered in deriving the trial rate coefficients and uncertainty factor. Click the abbreviated reference names for details.
- Comment: details of the evaluation of trial rate coefficient and uncertainty factor

In what follows, we provide an overview of the trial rate coefficients evaluation and uncertainty factor estimation.

## Review of key reaction pathways
When evaluating the trial model and its rate coefficients, direct experimental rate constant measurements are preferred for rate assignment. Theoretical calculations of potential surfaces and rate constants play a large role also in evaluating rate expressions, as this is often necessary to give proper extrapolation outside of limited measurement conditions. Reliance on theoretical values for product branching ratios is often needed. In some cases, only theoretical values or estimates made from similar reactions are available. In trial model compilation, several functionally equivalent expressions are often available. We have relied on previous evaluations when available, notably the recent H<sub>2</sub> models by Li et al.[^LZK2004] and Hong et al.[^HDH2011], and the IUPAC combustion kinetics evaluations of Baulch et al.[^BBC2005]. The reviews by Baulch et al.[^BBC2005] is also an important source for the rate uncertainty.

For the model to be valid and consistent over wide temperature and pressure ranges, a proper parameterization of recombination, decomposition, and chemical activation rate constants is vital. We select available Master Equation calculations[^B2001] with appropriate pressure falloff parameterization that best match experimental data. Rate coefficients of multichannel chemical activation reactions often have negative pressure dependency, due to collisional stabilization of the bound intermediate at high pressures. Many such reactions need to be considered for C<sub>3-4</sub> species. FFCM-2 treats the pressure dependency of chemically activated reactions using the ChemKin PLOG format. Note that some error is introduced by this choice because the temperature and pressure dependencies can be functionally more complex than PLOG can describe. We have tried to obtain the best precision at relevant temperatures, so errors may be larger at extremes. Relative efficiencies for different collider gases are often unavailable for many systems. We used collision efficiency values when they are available and consistent, and otherwise employ generic relative values from GRI Mech. When different collider efficiencies or low-pressure limit rate constants are separately optimized, we have placed appropriate bounds on the ranges of relative efficiencies. 

For most rate coefficients, we take values directly from the source without ad hoc tuning, because the model is subject to optimization and the exact best selections are not required. Note that deviations from the trial rate values are considered in the optimization, so there is a penalty for large perturbations on the rate values. 

### C<sub>0-2</sub> chemistry
For the C<sub>0-2</sub> chemistry, a comprehensive list of species and reactions were assembled, with a focus on high-temperature (above 1000 K) combustion. Some highly oxygenated or weakly bound species are omitted. The current model does not include C<sub>2</sub> fuels such as DME and methyl acetate, which could be added and separately optimized. The GRI Mech species HCCOH is assumed to isomerize to CH<sub>2</sub>CO. The decomposition of HOCO and C<sub>2</sub>H<sub>5</sub>O are assumed.

The species and reactions for the C<sub>0-2</sub> chemistry were largely adapted from the earlier FFCM-1 trial model, with necessary addition and update. Kinetics for ethanol oxidation are added. We also added methyl and ethyl peroxide chemistry, which are important at modest temperature and high oxygen concentration. The new species are CH<sub>3</sub>O<sub>2</sub>, CH<sub>3</sub>OOH, C<sub>2</sub>H<sub>5</sub>O<sub>2</sub>, C<sub>2</sub>H<sub>5</sub>OOH, C<sub>2</sub>H<sub>2</sub>OH, C<sub>2</sub>H<sub>3</sub>OH, C<sub>2</sub>H<sub>4</sub>O (ethylene oxide), C<sub>2</sub>H<sub>5</sub>OH, C<sub>2</sub>H<sub>4</sub>OH and CH<sub>3</sub>CHOH. Selected rate coefficients and three-body Chaperon efficiencies were revised upon considering new literature, and sensitive or problem areas identified in the FFCM-1 study. This includes the decomposition of ethylene, methane and carbon dioxide, re-evaluations for the C<sub>2</sub>H<sub>3</sub> + OH and C<sub>2</sub>H<sub>3</sub> + O<sub>2</sub> reactions, and the addition of prompt dissociation channel OH + HCO $\rightleftharpoons$ H + CO + OH. A new, theory-based reaction of CH<sub>3</sub>O<sub>2</sub> + O<sub>2</sub> was added, which is relevant to methane ignition under low temperature and high oxygen conditions. 

### C<sub>3-4</sub> chemistry
The addition of C<sub>3-4</sub> chemistry to expand and complete FFCM-2 requires the inclusion of many more species and reactions, with fewer available studies to evaluate. The current mechanism is limited in size to the C<sub>3-4</sub> hydrocarbon species and aldehyde-ketone oxidation intermediates. We did not find it necessary to include additional peroxyde or alcohol kinetics. Excluding these kinetics favors manageable model size over comprehensiveness of the model. If one wishes to model the combustion of larger oxygenated bio-fuels, additional species and reactions could be added to the currently optimized model, and the additional reactions could be optimized via a sequential optimization approach. 

To begin the evaluation, we relied on the several existing C<sub>3-4</sub> models such as USC Mech II [^WYJ2007], Aramco Mech 2.0 [^ZLO2016] and LLNL. [^MWC1998] Also, Tsang has provided some reviews, evaluations or estimates. Often theoretical work on these complex systems forms the best (if uncertain) basis for rate choices. Typically there is wider range for optimization of these kinetics to better predict limited target sets. A new path for butene isomerization via methylcyclopropane intermediate based on its decomposition kinetics was added. Some large allylic type radicals are particularly stable and could recombine with other radicals such as methyl to form larger compounds under rich, high pressure, low temperature conditions. This chemistry is not currently included for the current model.

## Uncertainty evaluation
A key element of the rate evaluation is an assessment of the uncertainty factor of the reaction rate constants. These limits are used later in the selection and allowed ranges of the optimization parameters. These values are necessarily subjective estimates. When multiple reliable determinations of a rate constant are available, an uncertainty limit encompassing their range is typically selected (excluding outliers). We generally avoided the sometimes over-optimistic values given for individual measurements. For reactions covered by the Baulch et al.[^BBC2005] reviews, we have typically chosen to use their uncertainties. In cases where we adopted values based on the compilations of Tsang [^T1990]$^{,}$[^T1991], often estimates, his estimated uncertainties were used. Our ranges are intended to allow what we consider all possibly reasonable values to the optimization. Bear in mind that the objective function of the optimization includes terms for rate constant deviations from the evaluated values, so choices near these estimated uncertainty limits are disfavored.

## References

[^LZK2004]: Li J, Zhao Z, Kazakov A, Dryer FL. An updated comprehensive kinetic model of hydrogen combustion. Int J Chem Kinet. 2004;36:566-75.

[^HDH2011]: Hong, Z., Davidson, D. F., & Hanson, R. K. (2011). An improved H2/O2 mechanism based on recent shock tube/laser absorption measurements. Combustion and Flame, 158(4), 633-644.

[^BBC2005]: Baulch, D.L., Bowman, C.T., Cobos, C.J., Cox, R.A., Just, T., Kerr, J.A., Pilling, M.J., Stocker, D., Troe, J., Tsang, W. and Walker, R.W., 2005. Evaluated kinetic data for combustion modeling: supplement II. Journal of physical and chemical reference data, 34(3), pp.757-1397.

[^WYJ2007]: Wang, H., You, X., Joshi, A. V., Davis, S. G., Laskin, A., Egolfopoulos, F., & Law, C. K. (2007). USC Mech Version II. High-temperature combustion reaction model of H2/CO/C1-C4 compounds. URL: http://ignis.usc.edu/USC_Mech_II.htm.

[^ZLO2016]: Zhou, C. W., Li, Y., O'Connor, E., Somers, K. P., Thion, S., Keesee, C., Mathieu, O., Petersen, E. L., DeVerter, T. A., Oehlschlaeger, M. A., Kukkadapu, G., Sung, C. J., Alrefae, M., Khaled, F., Farooq, A., Dirrenberger, P., Glaude, P. A., Battin-Leclerc, F., Santner, J., Ju, Y., Held, T., Haas, F. M., Dryer, F. L. & Curran, H. J. (2016). A comprehensive experimental and modeling study of isobutene oxidation. Combustion and Flame, 167, 353-379.

[^MWC1998]: Marinov, N. M., W. J. Pitz, C. K. Westbrook, A. M. Vincitore, M. J. Castaldi, S. M. Senkan (1998). Aromatic and polycyclic aromatic hydrocarbon formation in a laminar premixed n-Butane flame, Combustion and Flame, 114, 192-213.

[^T1990]: Tsang, W. (1990). Chemical kinetic data base for combustion chemistry Part 4. Isobutane. Journal of physical and chemical reference data, 19(1), 1-68.

[^T1991]: Tsang, W. (1991). Chemical kinetic data base for combustion chemistry Part 5. Propene. Journal of Physical and Chemical Reference Data, 20(2), 221-273.

[^B2001]: Barker, J. R. (2001). Multiple‐Well, multiple‐path unimolecular reaction systems. I. MultiWell computer program suite. International Journal of Chemical Kinetics, 33(4), 232-245.
