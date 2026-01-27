# Effect Modification

Effect of one risk factor on the outcome changes in the presence of another risk factor

Aka interaction, effect measure modification (emphasizes dependence on the model chosen, e.g. additive vs multiplicative), heterogeneity of effect (statistical term)

Example: 

- Alcohol consumption alone = not much risk of MVA
- Alcohol consumption AND driving a care = much higher risk. 

Another example: immunization and measles exposure modify risk for getting measles.

Fundamental questions about causal mechanisms: clearly, some things only have a causal effect under certain conditions. For example, only 10% of heavy smokers will get lung cancer. Thus, in the majority of heavy smokers, there will be no causal effect of smoking on lung cancer. What explains this difference? Presumably, some effect modification with respect to other predisposing factors or underlying biology.

## Biologic Interaction

Sufficient / component cause model:Two measurable risk factors (A and B) and 1 unmeasurable or unknown (U). Consider 4 different possible causal models for (sufficient) development of the disease

1. A, B, and U required (both A and B will be present, but not everyone with A and B will get the disease)
2. A and B required (both A and B will be present, and when present everyone will get the disease)
3. A and U required (A required, but not everyone with A will get the disease. B may or may not be present at the background rate of B)
4. U required (A and B will both be present at the background rate)

There is no direct way to know which model applies in any given individual, but we can indirectly guess at which model is accurate by measuring the presence of A, B, and disease across populations.

Rab = risk of disease in those exposed to a and b; Ra = just exposed to a, Rb = just exposed to b.

All these must be assumed to be un-influenced by confounders. 

If Rab = Ra + Rb - Ru, then there is no interaction and causes (A and B's impact on the development of disease) are independent (if present).

Importantly, biologic interaction is present when the 'additive model' is used (though this is not modeling, but describing how the universe works)

Note: when considering 'preventative factors', it is often simpler mathematically to consider 'lack of the preventative factor' to be causal in development of the disease.

## Assessment of Effect Modification

2 methods: stratified analysis, joint analysis. Both will lead to the same conclusion (about whether effect modification is present or absent) - the decision depends on which method will more clearly explain what you are trying to say. Stratified is commonly easier to explain.

There are two models: additive (risk difference) or multiplicative (relative risk). Additive is useful for explaining impact (e.g. attributable difference) while multiplicative is easier to model (and seems to me to have more impact on mechanism). 

### Stratified Analysis

Is the effect of exposure A consistent across levels of exposure B (across strata)?

E.g. lung cancer and asbestos exposure on risk of lung cancer mortality: 

- No asbestos and non-smokers: 11.3 / 100k
- Asbestos and non-smokers: 58.4 / 100k
- No asbestos and smoker: 122.6 / 100k
- Asbestos and smoker: 601.6 / 100k

Risk difference: nonsmokers = 47 per 100k; smokers = 479 per 100k (= attributable risk)

Risk Ratio: nonsmokers = 5.2; smokers = 4.9 

Does this count as effect modification? Yes in additive model, no in multiplicative. 

One could make an argument to use a logarithmic (or square root) scale for many outcome measures, which again would change the model and whether effect modification is apparently present (essentially changes additive to multiplicative or vice versa). 

An analogous definitional problem (whether to use additive or multiplicative) also exists for the question of statistical interaction generally.  Importantly, statistical interaction is ambiguous (in terms of definition) while biologic interaction (a mechanistic interaction that is either present or not) is not.

Essential interactions: interactions where no change in scale will change the presence of this (ie. Swapping between additive and multiplicative). This might occur if the effect is of different direction (ie helpful with another risk factor present, unhelpful without it) or with a very large interaction (almost trivial without another risk factor present, hugely important with it)


### Joint Effects

Answers the effect of combined exposure to A and B

A contingency table with both exposures on the two axes: 

Outcome: incidence of pneumonia

No influenza exposure and age less than 65: Io
Influenza exposure and age less than 65: Io + effect of influenza
No influenza exposure and age greater than 65: Io + effect of age
Influenza exposure and age greater than 65: the joint effect of both

(Could do this with a multiplicative model by replacing + with *)

Calculating each measures of association relative to the dual-unexposed group (as opposed to calculating it for each stratum in the stratified analysis). 

### Testing for significance of effect modification

Magnitude often more important that statistical significance.

Stratified analysis = subgroup analysis, thus statistical problems occur with lack of power, multiple comparisons, and post-hoc analysis. These apply to effect modification. 

Solution: tests for significant interaction aka tests for heterogeneity of effects. 

Test of heterogeneity of the OR or RR: 

- test the null hypothesis that the OR or RR is the same in the different stratum. (Homogeneity)
- Mantel-hansel approach (a chi2 approach)
- tests for interaction in a regression by looking at an 'interaction term' in a regression model that represents the effect of the combination of the exposures beyond the independent effect of the exposures.
- power issues: depends on effect size, number of observations, and proportion exposed (by strata?). Thus, as a rule of thumb HTE often requires 4x as many observations to adequately evaluate an interaction test as compared to evaluate the main effect. (Seems like maybe needs meta-analyses)

### Contrast with confounding

Both can be assessed using stratified analysis. 

Recall: confounding is 'guilt by association' while effect modification is 'a conspiracy' (increased effect together). 

Confounding: are the stratum specific estimates of association (which can be combined into a mantel-hanses weighted summary measure - if uniform) different than the crude estimate? If so, then the variable defining the strata is a confounder

Effect modification: are the stratum specific estimates different from each other? If so, then effect modification is present.

Study design differs with respect to each: 

- to control confounding, we want to control (or eliminate) it's effect
- for effect modification, we want to describe it to gain insight into causal mechanisms or to identify susceptible groups

What about if Crude is different from both Stratum 1 and Stratum 2? Is this both? No, it means that there is effect modification... confounding is irrelevant because it appears that there is a causal effect modification (and stratum specific results need to be presented).