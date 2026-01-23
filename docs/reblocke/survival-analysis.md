# Survival Analysis

AKA Event history analysis, time-to-event analysis

Why needed? Relative risks (the ratio of the cumulative incidences in each group, aka risk in each group) requires a time frame to be specified. This is only accurate if each individual has an equal follow-up time (meaning - an equal time they were at risk for being recorded as having the outcome) and an equal time of death. Logistic and linear regression models have this assumption build in. 

Dropping out of being 'at risk' (whether it's death by a competing cause, loss to follow-up, etc.) = censoring. Making it to the end of follow-up => administratively censored.

Better; Incidence rate = number events / (total time group at risk) = #events/(person-time) then calculate an incidence rate ratio aka rate ratio. (Note: can no longer use chi2 statistic; have to swap to binomial probability mid-p exact test for person-time data). However, this still doesn't use the time-at-risk information effectively, because it functional assigns each person a 'mean time at risk', while in reality you could have: Patient 1 is censored day 1, patient 2 dies at day 20, vs patient 3 dies day 1, and Patients 4 censored at day 20.. patient 1-2 have had a better outcome than patients 3-4, despite IRR being the same. The time of death is not considered

Best; Hazard ratio (Cox regression; survival analysis)

Kaplan-meier survival function aka product limit survival function 
Cumulative mortality function is the 1-Survival

This avoids bias due to loss to follow-up (as long as it is tracked) 

Censoring: people can either have 
1. Event occur at a particular time
2. Censoring at a specific time (either lost to follow up at a time, or no event by the end of the study). For people who are censored - you don’t know when the event would happen (if ever), but you do know that it didn’t happen up to the certain timepoints.

‘Right censoring’ = ‘censored’ at the end of the study - if we knew (somehow) when everyone would have the event, it’d be somewhere to the right. 

‘Time’ = study time (since enrollment), not calendar time.

### Assumptions about censoring

Censoring: it can matter why people are censored. 

Missing completely at random -  missingness isn’t related to anything.
Missing at random - missingness doesn’t relate to future risk.  reason for missing is totally unrelated to outcome. Can just analyze complete cases.
Missing not at random - reason why it’s missing is related to the outcome of interest. When this is violated, our estimates are likely to be biased.

Two assumptions: sample represents the population of interest, and censoring is not related to risk of the event happening in the future. (MAR or MCAR)



In total: for Cox Regression: What are the assumptions? Proportional hazards; censoring is at random; representative data



## Operationalization

What data you need?  Patient#, Time, Status (1 if event, 0 if censored), covariates of interest.

### Life Table

Step 1: Generate life table -> contains number of patients starting the time interval, survival probability data, and the # lost to follow-up for each time interval, by group

Track 3 variables: 

Ti = the time that the ith person dies
m(t) number of patients for whom t<ti (event has occurred)
d(t) number of patients for whom ti<= t (event hasn’t occurred)

Survival function = S(t) = probability of surviving passed time t = aka P (ti > t)
Cumulative mortality function D(t) = probability that the event has occurred 

Thus, we need to keep track of how much follow-up someone has, AND whether the censoring occurred due to the event happening or loss to follow-up/end-of-study

Note: this is time to FIRST event - can’t undo the event once it’s occurred. (If you are going to do something with multiple events - you have to do time to NEXT event and restart the clock)
===> without accounting for people who have been lost to follow-up, events at a longer time will be biased

Ni = number of people known to be at risk (hasn’t had the event yet, and their status is observed at that time). To be not at risk, you either have to have died in the past or lost to follow-up in the past.
Di the number of people who died that day

Pi =( ni- di ) / ni   : conditional probability of having the event, given that you’ve survived to this point. 

S(t) = Pt * P(t-1) * P(t-….) 
D(t) = 1-S(t)

This means that when someone is censored, they don’t contribute to the numerator of Pi. Thus, they only contribute to the survival probability by lowering the denominator of the next Pt

Survival table: gives the unconditional probability of remaining event free for someone who beings followup (time-0) - called the survivor function. Contrasted with conditional probabilities (ie. What is the probability of surviving past a certain time-point, given you have survive to now. - this can be calculated for any interval as the cumulative survival at t+1 / cumulative survival at t)

Kaplan-Meier plot is the graph of the cumulative survival curves. You can use either failure curve, or survival curve depending on which highlights the difference and minimizes white space better. 


### Hazard Function

Step 2: from this, the hazard can be calculated for each interval (and for each group). Hazard = interval-specific risk (e.g. per year, or per day - however the data is structured). If using an 'actuarial method' - each death or censorship is assumed to happen in the middle of the interval. In the 'standard Kaplan Meier' method, deaths/censorship are assumed to happen at the end of the interval. With shorter intervals, the difference is minimized.

Hazard Function: lambda(t)
— mirrors the definition of a derivative 
— limit as t goes to 0

Lambda(t) approximates P(patient dies by t+1 | patient alive on day t)
(Or, soon as opposed to t+1)

S(t) = exp(-integral(lambda(t))
===> if you know the hazard function, you can calculate the survival function. And vice/versa. 

### Proportional Hazards 

Hazard rate definition: 'instantaneous incidence rate' - incidence rate as the limit of delta_t -> 0. Chance of something happening in the time [t, t+delta_t]. 

HR = This is equivalent to the  risk ratio at an instantaneous time scale. Can the hazard ratio (ratio of hazard rates) be interpreted as a relative risk? Yes. Relative risk = a measure of risk between two groups - aka risk ratio - and hazard ratio definitely fits that definition. Similarly, acceptable when presented in other terms (cumulative hazard, interval specific survival, cumulative survival, etc)

Note: that if you do an adjusted Kaplan-Meier plot on some confounder (ie using Cox-regression) - mean centering should be used. This makes it so that the estimates are taken with "all other things held equal" at the mean, rather than at 0 (for some reason, this is the default in Stata).

‘Proportional hazards’ assumption = the ratio of two hazards would always equal the same constant. 

Ie. Hazard A is always 40% higher than hazard B

Proportional hazard model: lambda(t) = lambda_o(t) * exp*(beta*Xi)

h(t) = ho(t) * exp( b1x1 + b2x2+ ...bkxk)

- h(t) is the hazard at a particular time
- ho(t) is the baseline hazard for someone w all x-variables = 0
- beta coefficients = increase in the adjusted hazard ratio for 1 unit increase in x

Baseline hazard = ‘nuisance parameter’ (needed, but not of interest) if the proportional hazard assumption holds, because you’ll always be comparing two hazards (to get the ratio) and the baseline hazard will cancel out. lambda_o(t) is a ‘baseline’ hazard function. Looking at x=0 vs x=1, if proportional hazard assumptions holds then the lambdas cancel and you just get a Exp(beta) that doesn’t depend on time, and is called the hazard ratio. Exp(Beta)=HR

Cox hazard = modeling the log of the hazard ratio. 

Betas = model the log (hazard ratios), thus we exponentiate them. So, we generally exponentiate them.  
— stata gives you the exponentiated betas by default. 

Cox regression (and Logistic regression) are multiplicative models and so when a continuous predictor is used, it is assumed that the hazard increases exponentially across the range of the predictor (ie. By OR-fold increase per unit).

[ ] why logs? What does it get you?

[ ] what does the log likelihood in a regression model output refer to?


This is called a semi-parametric model = the baseline hazard can be dependent on anything but the rest of the model depends only on the covariates.

stcox in stata = proportional hazard ratio model.  
Note: you don’t specify the y variable in the command (only independent variables) => because you already did in the sts set command. 

Output: HR=exp(beta), SE, Wald z statistic, p-value, confidence interval


## Hypothesis Testing

How do we compare two groups? 

Log rank test: big picture - calculate a X^2 value for survival at different time points and then sum them.
Sts test

Note: Logrank test = ALMOST the univariable cox regression.  It should be noted, though, that you can't do this to control confounders - and thus it should only be used in the case of randomization, where there is a claim that the confounders are balanced. If there are confounders, Cox regression should be used.


Step 3: Comparisons of each interval specific risk (hazard - essentially, a 2x2 table for each time period) generates the hazard function, which is then used by the regression (Cox regression). If you do a Cochrane-Mantel-Haenzsel aka CMH-Chi2 test on each 2x2 table (for each interval) => this is the Logrank test. CMH-Chi2 is an extension of Pearson's Chi2 that allows to stratify by a third variable (in the case, interval). Additionally, the pooled risk ratios (weighted by n in each interval) is ALMOST identical to the pool hazard ratio in Cox regression (only difference is a slightly different test statistic, called a score test, is used)



### Confidence Intervals

How do you generate your confidence interval? 

You can use Greenwood’s formula.  Or, more frequently - you use log (-log(S(t)) -> moves from 0,1 interval to negative infinity to infinity. 

ln(-ln(S(t)) +/- 1.96 * v(t) => S(t)^(exp +/-1.96 * sqrt(vt) 

Means... S(t), V(t), sqrt(VT), multiply by 1.96 and -1.96, exponentiate that, then take S(t) to that. 


## Interactions


Interaction terms: 

Think about as the difference between categories in either of the two ways: 
1. Ratio between M and F in Agegroup1 / Ratio between M and F in Agegroup 2
2. Ratio between Agegroup1 vs 2 in M / Ratio between Agegroup 1 and 2 I n F

If you were to look at F in Agegroup 2, it would be HR of F (vs M as referent) * HR of Agegroup2 (vs 1 as referent) * interaction

## What if proportional hazards assumption does not hold?


If proportional hazard doesn’t hold: obvious evidence is things like  crossing survival curves 

Or, Testing proportional hazards: 

Kaplan Meier = doesn’t require proportional hazards
Cox regression = does
(Log rank test doesn’t technically, but it has the most power and interpretability when it does)

If you plot the survival curve extrapolated from the cox regression (requiring the assumption) and it is close to the model that doesn’t require it - that is some evidence that the model is OK. 

— happens with crossing curves (obvious violation of proportional hazards)


Log-log plots: log of -log of survival curve => looks like linear regression, but is not particularly interpretable. 
- However, it allows us to test proportional hazard assumption.
- Proportional hazards assumptions MEANS that the ratio of hazards DOES NOT depend on time, and thus log of -log will always be a constant (parallel) - same amount of vertical distance - between the group.


What do you do if proportional hazards don’t hold? 

Stratified hazards ratio: allow different hazard ratios for, say, males and females, but do assume proportional hazards between treated and untreated. Two sets of proportional hazards. This works if within males, proportional hazards holds and within females proportional hazards holds, but it doesn’t hold for all 4. 

This is done with the “strata” option. You lose the interpretation of the hazard of the variable - thus it should be a “nuisance variable” where it’s not of primary interest. 

You could test whether the proportional hazard assumption holds in each strata, you could restrict the data to each stratum and calculate the HR in each group, and see if they are similar. 

Time-dependent covariates

A model that allows 1 HR in 1 part of the time, then a second HR in the other. 
