# Natural Experiments and Quasi Experiments

JCI Series: 
[Paper 1: intro](https://www.sciencedirect.com/science/article/abs/pii/S0895435617307485)
-Quasi-experiments: natural scenarios where the treatment received is "as-good-as random", allowing for confounding free/minimized assessments of an effects and counterfactual

History: 
-Difference-in-difference design (subtract before-after difference in treated group and before-after difference in outcome in an untreated group, aka controlled before-after design): e.g. John snow demonstrating cholera in London via treated and untreated neighborhoods
-Instrumental variable design (a variable - the instrument - predicts the treatment but not the outcome)- e.g. Mendelian randomization
-Regression discontinuity: originally conceived in education research. 

[Paper 2: Uses in health systems research](https://www.sciencedirect.com/science/article/pii/S0895435617302998 ) 

- RCT is gold standard, but operationally difficult, costly, which precludes assessing many long term outcomes and interventions where little equipoise exists. 
- One of several reasons for the evidence to implementation gap is limited external validity of RCT data; quasi-experiments / natural experiments can improve this.

Definition of quasi-experiment: an observational study with an exogenous explanatory varaible that the investigator does not control. (Similar to randomization, this is what the internal validity relies on to balance unmeasured confounders). In comparison, quasi-experiments often have lower internal validity but higher external validity (given they occur during usual care of a broader population of patients))

[Paper 3: Evidence generation for public policy]( )

[Paper 4: Uses and value] ( )
High external and internal validity, usable when experiments are not feasible (e.g. ethical, financial)

[Paper 5: checklist for classification] ( )

[Paper 6: risk of bias assessment] ( )

[Paper 7: Assessing the assumptions ] ( )

[Paper 8: quasi-experiments to inform systematic review] ()

[Paper 9: collecting data from quasi experiments ] ()

[Paper 10: synthesizing evidence] ()

[Paper 11: Supporting syntheses] ()

[Paper 12: Supporting syntheses 2] ()

[Paper 13: funding, data sources, etc] ()

### Regression Discontinuity Designs
[Regression Discontinuity Designs] (https://jamanetwork.com/journals/jama/fullarticle/2768094) - when there is a breakpoint in a continuous variable (e.g. infants <1500g go to NICU, 1500+ don't) you can use this as a natural experiment to compare the effect of the differing care because patients on either side of the breakpoing (e.g. infants 1499g and 1501g) are essentially indistinguishable. In essence, the randomized measurement error of the forcing variable around the threshold creates randomization 


[Regression Discontinuity Designs in Epi](https://pubmed.ncbi.nlm.nih.gov/25061922/)

### Interrupted Time Series by Segmented Regression Analysis

[Interrupted Time Series by Segmented Regression Analysis](https://onlinelibrary.wiley.com/doi/abs/10.1046/j.1365-2710.2002.00430.x?sid=nlm%3Apubmed)
Requires outcome measures at evenly spaced intervals (a time series). Split in to at least two portions at a change point (a time at which behavior changes) - generally 12 data points before and 12 data points after are required, generally a minimum of 100 total observations/events. In a segmented time analysis, each segment has a level (y-intercept) and a trend (slope) - the change in level corresponds to the effect of the intervention. A segmented regression analysis is used to control for confounders and assess the likelihood that chance could explain a drop. 

- Advantages: allows the analysts to control for prior trends and dynamics in the change (e.g. durability) after an intervention. 
- Disadvantages: assume linear trends in each segment, do not allow for individual level covariates (because individuals are aggregated into each time point)


### Difference in Difference Design

[Difference in Difference](https://www.annualreviews.org/doi/full/10.1146/annurev-publhealth-040617-013507)
Quasi-experimental design

### Instrumental Variable Analysis

An instrumental variable with respect to: 

- E = exposure
- Y = outcome
- IV = instrumental variable

The instrumental variable

- must affect E
- must not affect Y in any way other than through E. On a causal graph, Y may be a descendent of IV only through E
- The IV-Y associated must also be un-confounded , meaning no backdoor path from IV to Y

In this case, the instrumental variable can function like randomization for the assignment of study groups. 

In this case, the unconfounded causal effect of the risk difference can be calculated as: 

RD = (r1 - r0) / (p1 - po)

where, 

- r1 = cumulative incidence among those with IV =1
- r0 = cumulative incidence among those with IV = 0
- p1 = proportion of those exposed in group with IV = 1
- p0 = proportion of those exposed in group with IV = 0

This can be applied to randomized trials where non-adherence is present - the randomization result functions as the instrumental variable. 

Strength: the denominator is the STRENGTH of the instrumental variable (ie. the degree to which exposure status is affected by IV). This relates to the efficiency of the study. 

Validity: the validity of the IV is the extent to which you can justify that it means the above 3 criteria - this can not be empirically measured and has to be justified with subject matter knowledge.

