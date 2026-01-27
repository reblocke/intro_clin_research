# Bayesian Trial Designs

Prior: distribution of our beliefs about a parameter of interest before doing the study. More informative (meaning, you already have more information) = 'narrower' distribution. Know almost nothing? Very wide distribution.

Posterior: distribution of the possible values of the parameter of interest after taking into account the observed data and the prior information.

Beta distribution: parameters w possible values 0 to 1. Y = number of outcomes, n = sample size (n-y = 'number without outcome). A and b = priors. Then

Prior distribution: Beta (a, b)
Posterior distribution: Beta( y + a, n-y + b) 

a, b = 1 means we know nothing
A, b = 100, 100 => more informative prior, and exert a greater proportion of influence for any y and n.


## Drawbacks to traditional RCTs

Powered on an effect size estimate (single value) - but often we don't know how the operating characteristics of a sample size change if the effect size turns out to be different. 

At interim analysis, there is no way to incorporate subjects who have been enrolled but haven't had outcome observed. 

## Adaptive Designs

Prospectively planned (required) changes to the design and hypotheses based on the data (usually interim data analyses)

 Such as: 

- response adaptive randomizations
- sample size rcalculation
- dropping an arm or subgroup of a study
- interim analyses in a traditional RCT (e.g. stopping or efficacy or futility - example: Obrien Flemming)

E.g. Goldilocks design: adaptive sample size algorithm for Phase 3 trials to select a trial's sample size based on accumulating data. Dichotomous outcome (yes/no) of treatment or placebo (150-250 per mo up to 10k max enrolled). Can't observe outcome until 5 months after enrollment. Assuming 6.4% outcome in control, 4.7% in treatment. W non-informative prior

Way to do this: 

Simulate ~5000 trials to see how many get positive results under various associations to arrive at values of the following the achieve your desired Type 1 and Type 2 error rate.

Calculate Predictive probabilities - 

PPnow = predicted probability of success at the current sample size
PPmax is the predicted probability of trial success at the maximum sample size (taking into the account of the observed pattern thus far)
Sn = stopping boundary for superiority
Fn = stopping boundaries for futility

Then, for each check you have a pre-stated thresh-hold for stopping (either PPnow > Sn or PPmax < Fn). 

Thus, you choose: 

1. Maximum sample size (not 'target sample size')
2. Bayesian concerned with 1 sided probabilities
3. Bayesian RCTs are designed via simulation.. thus when you deviate, you loose the test characteristics. 


Adaptive enrichment design: at each look, if one group is looking better you change the group assignment likelihoods to favor the beneficial group. Similarly, if you start with several versions of an intervention (e.g. how long cooling occurs for post-arrest), you can move people to a group that seems better (e.g. if 48h seeming better, do more of that)

Other adaptations: Enrichments, Responsive Adaptive Randomization, Maximum sample size recalculation, adding/dropping arms, Master protocols (e.g. platform trials, basket trials), seamless phase 2->3 trials, adaptive sample sizes (e.g. Goldilocks)
