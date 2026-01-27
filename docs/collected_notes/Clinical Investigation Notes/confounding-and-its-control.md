# Confounding and its control

Definitions: 

- Must be related to the likelihood of exposure - either directly or through association with something that is causative. 
- Must be either a cause of the outcome (e.g. smoking and lung ca), associated with an unmeasured cause of the outcome (e.g. race and prostate ca), or related to likelihood of recognition of the outcome (e.g. cervical ca screening in the relationship between OCPs and cervical ca)
- should not be part of the causal pathway for how the exposure causes the outcome.

Note: all these variables and the measures used (e.g. OR, RR, RD) should be specified a prior based on subject matter knowldge.

## Three views of confounding

- C: confounder (not on the path from E to Y)
- E: exposure (yes or no)
- Y: binary outcome

### Comparability view

aka 'classical view'. Can be measured.

C confounds E-Y if: 

1. Distribution of C differed between exposed and unexposed
2. C affects Y in its own right

### Collapsibility view

If the association between E-Y has the same value at each stratum of C, then C is NOT a confounder. 

Note: this requires you to specify a measure (OR, RR, RD) before analysis. It also presupposes no effect modification of E-Y by C.

In comparison to the comparability view: 

1. If E-Y is homogenous across the strata of C - both comparability and collapsibility view apply. 
2. When C has two categories, comparability and collapsibility are the same. 
3. When C has more than two categories, comparability confounders are a superset of collapsibility confounders. However, all confounders by collapsibility are also confounders by comparability. 

Note: this is the view that is implied by seeing if inclusion in multivariable analysis models changes the E-Y exposure or not. 

### Counterfactual view

C is a confounder if the cumulative incidence of the outcome would be the same for each group if they had or hadn't been exposed to the confounder. The difference in the incidence among people if everyone had been exposed to if everyone had not been exposed is the 'average causal effect among the exposed'. Confounding is present if this is not 0 (ie. the incidences are different). 

Since we can't measure what the outcome would have been if exposed (in the unexposed group) or unexposed (in the exposed group), this is usually not measurable. However, 

- shows us that the unexposed group is actually a surrogate for the unobserved counterfactual outcomes of the exposed group (= the assumption they are exchangeable - which is by definition true in an RCT, but not so in observational studies)
- if the putative confounder switched the outcome status of 60 people in 1 direction, and 60 people in the other direction - it would not be considered. a confounder even though it did have some individual impacts. 

The implication of this is that because we don't know exactly who would have "switched" in outcome based on "confounder" exposure, we cannot empirically tell for sure if something is a confounders, whether it's been appropriately controlled, or if it's a confounder at all. Instead, have to rely on subject matter knowledge. 

## Causal Diagrams

Terms: 

- nodes aka vertices, directed edges aka arcs
- adjacent nodes = connected by edge. Arrow goes from parent to child node.
- ancestor = upstream (parents are a special case of an ancestor), descendent = downstream (child are special cases of descendent) 
- path = a way to connect two nodes that IGNORES the direction
- Directed acyclic graphs: 1. all edges are directed 2. no node is a descendant of itself

Causal diagrams are a special type of DAG where

1. Nodes represent variables
2. Arrows/Directed Edges represent direct causal effects (e.g. changing 1, with all other variables constant, would change the other). Thus, parent = cause, child = effect.
3. If any two variables share a common ancestor (cause), that ancestor is included in the causal diagram. If not measured, it is given U

Collider: a node where two arrows along a path both point toward it.

Conditioning on a variable: controlling, aka holding constant (via restriction, stratification, matching, covariate adjustment etc.)

### Reasons for an association between 2 variables: 

1. Chance
2. X causes Y
3. Y causes X 
4. X and Y have a shared ancestor (cause) aka confounding
5. Control for a shared descendant aka collider, berksons bias.

####Collider bias 
aka Collider-stratification bias, M bias, Berkson's Paradox. A bias occurs when a collider (a variable influenced by two others) is conditioned on, leading to a spurious association between the two others. E.g. academic ability and athletic ability have no relation, but among college matriculants, they are negatively correlated (as having lots of ability in 1 allows you to be admitted). This is different from selection bias in that the inference is not valid even for the population studied (as opposed to only being a problem with generalization). https://www.nature.com/articles/s41467-020-19478-2 . Particularly problematic for cohorts where a convenience sample (as opposed to a random sampling of the target population) is used.


### What confounders should be adjusted on?

It is possible to over-adjust - 

1. On a mediator: if you try to adjust (use one of the analysis methods above) on something in the causal pathway, you will end-up inappropriately altering the exposure-outcome relationship (e.g. finding the causal effect independent of the mediator).  Relationships can be found (or not) in the data (ish, see counterfactual framing), but the only way to know if the factor is in the causal pathway is through clinical judgment.   

2. On a collider - and introduce M-bias. 

Using causal diagrams, the following algorithm ('d-separation') will identify what needs to be controlled for (S = the set of factors in need of controlling/conditioning-on): 

1. Set S must not contain any descendants of the exposure or outcome
2. Identify all backdoor paths from the exposure to the outcome; paths are blocked if they are either a non-collider in Set S or a collider that is not in S and has no descendent in S. 
3. The causal effect of exposure on outcome is confounded if, and only if, an unblocked backdoor path exists from exposure to outcome. 

## Measured vs Unmeasured Confounders: 

With the exception of randomization/natural experiment, all of the following methods require that the confounders be anticipated and measured. 

Thus, residual confounding will be present whenever a variable hasn't been measured (or measured accurately), or the variable hasn't been anticipated and recorded. 

The nondifferential mismeasurement of a confounder will lead to exposure-disease associations falsely close to the crude estimate.

How to address the unmeasured confounders / residual confounding?

- Sensitivity analyses
- Computing an e-value (quantify how large a confounder would need to be to explain the relationship)
- create a Causal diagram and see if there is a way to block the backdoor path by conditioning on a variable that is a descendant from key unmeasured confounders. 

## Ways to address confounding

###Design: randomization (or natural experiment)
the only method that deals with unrecognized and unmeasured confounders

Pro: deals with unknown and unknown confounders, Con: generally only feasible with interventions. 

###Design: matching
construct study groups that are comparable in levels of the confounder - e.g. make sure the same distribution of ages are included (though note, this is practically quite difficult).

Pro: efficient once the trial is enrolled, con: inefficient in enrolling, may introduce selection bias.

Note: the matching that occurs in Case-Control studies is not done to control confounding. It is done to increase study efficiency. 

###Design: restriction
study only patients at similar levels of the confounder.

Pro: easy to analyze. Con: generalizability of findings? Inefficient to find patients to enroll.

###Analysis: Standardization

compute summary estimates that manipulate the risk of the confounder across the two populations - e.g. compare mortality among 50s y/o, and separately among 60s y/o, 70s y/o then use that to back-compute "what would the overall rates be if they both had the same distribution of the comparison.". Example for age

1. Calculate the age-specific rate
2. Use info on the distribution of ages in the target population (realistically, any population distribution can be used, so best is one that is easily interpretable in the context of clinical question.)
3. Multiple age-specific rates by their frequency in the target population. 
4. Sum the distributions to get the overall rate.

Pro: weight scheme is explicit, doesn't assume the effect
Con: ??

An example is the "standardized mortality ratio: the expected number of deaths in a population is calculated from the observed rate in the general population, but standardized to the population in question. Then, the ratio of the observed deaths to this expected calculation is taken. 

###Analysis: Stratified analysis
 (separating into groups by their confounder status) on the potential confounder, then analyze each (stratum-specific effect e.g. Odds ratio). Example: birth order and Down syndrome risk appear associated. 

One methodology for combining the stratum-specific effects to an individual summary measure is to use the Mantel-Haenszel estimate -it is a weighted average of status specific measures

Interpretting the individual stratum-specific ORs:

- If ORcrude = weighted avg (ORc=0, ORc=1), then no confounding exists
- If ORcrude > or < than weighted avg (ORc=0, ORc=1), then confounding is present
- if ORc=0 and ORc=1 are substantially different, this is effect modification. 

Pro:  estimates can be interpreted within levels of confounders.
Con: can handle only a limited number of confounders. 

###Analysis: Pooling

???

###Analysis: Multivariable regression
 adjust by multivariable regression modeling that includes (potential) confounders as covariates. Can address multiple confounders at once, which is an advantage. This can be done either using the individual confounders or a propensity score. 

Pro: multiple confounders, easily handles continuous variables
Con: choice of the model and it's assumptions influence your results; can make results across papers hard.

See page on Multivariable analysis

###Analysis: matched analysis
Only compare individuals from the two groups that have a comparable (with respect to the confounder) partner in the other group. 

Pro: similar to restriction or matching in design, but can be done after. 
Con: loss of statistical power; possible introduction of bias.


### Advanced analysis techniques: Propensity Score, Inverse probability weighting

Extensions of matching and stratified analyses. 
E.g. for Propensity Score Analysis: In a database with good completeness, you select patients for you treatment groups by modeling the likelihood of each patient getting each treatment (the propensity score), then either weight or restrict patients such that you can analyze patients with similar propensity.

Pro: can incorporate many potential confounders; the adjustment is more parsimonious (just on the propensity score for example)
Con: takes a large database


### Propensity Score

the probability of an exposure, conditional on a set of covariate values) 

If the propensity score is properly developed (?criteria), with large n - the number of patients who differ by exposure status but have the same propensity score will be roughly matched. In this case, controlling for the propensity score also controls for confounding on all of the covariates. 

An inclusive choice of covariates (to the propensity score) is advocated (esp if dataset is large) - but the goal is to control confounding, not maximize the accuracy of the propensity score. Thus, include variables that are weakly associated with exposure but strongly associated with outcome. The converse situation (strongly associated with exposure, weakly associated with outcome) will make the propensity score more accurate, but sacrifice precision in the final model. 

Proposensity-score methods are ideal for cohort studies involving relatively rare outcomes. If ratio of covariates to outcomes is < 1:8, propensity score will outperform multivariable modeling of the outcome

### Disease Risk scores

the probability of an outcome condition on being unexposed and having a given set of covariate values

Estimate the subjects disease risk if unexposed.  The disease risk is then calculated for both the exposed (whose potential unexposed outcome is actually unobserved) and the unexposed group (who's actual outcome is observed). The disease risk score is then treated as a confounder in the final analysis, similar to propensity scoring. 

Similar to propensity scores - among unexposed subjects the coviarites will be similarly distributed among cases and non-cases (though this can only be confirmed in the unexposed group)

This is a good choice for cohorts where the exposure is rare but the outcome event is common among unexposed persons (e.g. with a new treatment for a common disease). Also, the same risk score can be used for several exposures. 

### Inverse Probability Weighting

calculating a cumulative incidence for each exposure group where the subjects weight is the inverse of his/her probability of being in the exposure group (conditional on covariates, e.g. w a propensity score)

This is a way to accommodate more variables into a direct adjustment. It is equivalent to creating a psuedopopulation in which confounding by the adjustment factors is gone (cumulative incidence among exposed persons in the pseudopopulation equals the adjusted cumulative incidence of the exposed group and unexposed group) 


### Time-dependent confounding
This occurs when a confounder may be the result of treatment at one 

Value changes over time and affects both the outcome of interest and subsequent exposure status.  Often also affected by past exposure status. 

One approach to this is marginal structural models: 

- Marginal = estimates population-averaged outcomes that would have been observed under alternative exposure histories (not individual-level causal effects of the exposure)
- Structural = models potential outcomes rather than observed outcomes.

Uses IPW to address confounding at each time point that the exposure status could change. 

Still relies on the assumption that there are no unmeasured confounders. 







