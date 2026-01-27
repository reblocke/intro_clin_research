# Logistic Regression

Logistic regression visual explainer: https://mlu-explain.github.io/logistic-regression/

Statquest series: https://statquest.org/statquest-logistic-regression/ 

Used for dichotomous outcomes: why can't you use linear regression? Given it's an interval scale, you can generate the b-coefficients and risk differences. However, the residuals are not normally distributed (why?) - not a huge deal. Also, there's no guarantee that the predicted individual risks will be bounded by 0-1 (not an issue for mean effects or P-value testing). Thus, not often done. 

Logistic function constrains between 0 and 1 (and thus can sensibly represent a proportion or risk)

Simple case:  pi(x) = exp(bo + b1*x) / 1 + exp(bo+b1*x)

This works to bound the possible values [0,1]

Because large number / (1+large number) = near 1
Small number / (1+small number) = near 0

-> sigmoidal shape

Similar to linear regression, attempts to minimize residuals. Uses maximum likelihood estimator as apposed to least-squares. 

Logistic function: f(z) = 1 / (1+e^-z).  

This function was dreamed up for this purpose - has the nice additional property that the shape corresponds to what you might expect when a threshold needs to be passed (say, in terms of number of risk factors) before an event occurs.
z = infinity? 1 / 1+huge =>0
Z = -infiinity? 1/1-0 => 1
0 = 1/(1+e^0)=> 1/2

Z = alpha + beta_1*x_1 + ... beta_k*x_k

f(z) = 1/(1+e^-(alpha + beta_1*x_1 + ... beta_k*x_k)) 

also equals P(dz | x_1, x_2, ...) => predictor equation.

The other very nice feature of using 1/(1+e^-(alpha + beta_1*x_1 + ... beta_k*x_k)) is that if you do the math and substitute 1/(1+e^-(alpha + beta_1*x_1 + ... beta_k*x_k)) for P(X), then calculate the odds (P(X)/(1-P(X)) -> log (P(x)/(1-P(X)) = alpha + beta_1*x_1 + ... beta_k*x_k


## Probability, Binomial Distribution, Bernoulli Distributions


Imagine each individual has an underlying pi (probability of event), but you only get to observe 1 outcome. Then, if you have a group: From yesses and no’s (a group of bournulli’s) you get a distribution (the binomial distribution) 

In binomial (probability density) distribution (describing a group with a shared underlying probability of the event), there is no independence between mean and variance: 
Mean:  n * pi
Variance: n * pi * (1-pi)


Binomial distribution formula:  [ ] 


What we’re interested in is the likelihood (instead of the probability density function): P (pi | data) instead of P (data | pi)

Based on covariates (x), each individual will have different pi_hats. 

##  Assumptions: 

- Linearity of log odds
- Independence
- Categorical outcome

### Testing assumptions

Hosmer- Lemeshow Chi2 test: 
Groups people (eg. By quantiles of expected probability) and evaluates their expected outcome rate
“Observed” - “expected” rate for each group 
The P-value gives you evidence for a lack of fit

e.g. a large P-value is good ( you can’t prove that it’s a bad fit… but it’s not possible to prove it is a good fit)

If you have a significant p-value, it suggests: 

—maybe interactions?
—maybe non-linear logit assumption violation?
—maybe not that problematic if the sample size is huge (ie is test 'over-powered') - could sample 1000 random patients and see if the assumptions hold. 

ROC curves:  C-statistic (concordance statistic) aka AUROC is often used analogously to R^2 for logistic regression. 


Testing goodness of fit:  (does the model fit well? Do predictors matter?)

Full vs reduced model (= made some restriction that made the model simpler to see if the restricted element matters). Likelihood ratio test aka change in deviance test.  You can use this to test multiple predictors at once. 

Say you have logistic regression with 3 predictors, each binary. You have 2x2x2 combos that can each be thought of as a cell.
Chi2 statistic = sum of the difference between predicted and observed in each square 

Large chi2 = there is a problem with the model. Null hypothesis = model is ok. Large chi2 -> small p value -> model is not OK.  —> only with few binary variables because you need several for each. Hosmer-Lemedhsow test which gets around this issue by grouping patients. 




## Logit 

This is the logit form of logistic regression. "Logit" = Log odds. Thus, the log odds is the outcome variable for a regression on the alpha + betas. -> intercept = log of the baseline odds, beta coefficients are the change in that unit that result in 1 unit change in the logit. (linear predictor)

Odds: p / 1-p

Odds of Pi(x) = exp(bo + b1*x) / 1 + exp(bo+b1*x) / 1+ exp(bo + b1*x) / 1 + exp(bo+b1*x) = exp(bo+b1*x)

Log odds Pix = logit pix = b0 + b1*x

Note: pi = probability of an event.. that is what we’re modeling (not 0s or 1s, which are what you are modeling). 

B1 = additive increase in log odds
exp(b1) = multiplicative increase in odds.

Thus, when ‘, or’ option is specified in STATA - exponentiates all the beta.

To get odds ratios: odds(x1) / odds(x2) = e^-(alpha + beta_1*x_1 + ... beta_k*x_k) / e^-(alpha + beta_1*x_1 + ... beta_k*x_k)

Given identify e^a / e^b = e^(a-b), it reduces to OR = e^(sum(b(x1_i - xo_i)) = general exponential formula of logistic regression.

1 unit increase in the independent variables thus leads to a beta-fold increase in the odds. Why -fold (multiplicative)? e^(a+b) = e^a * e^b. (You have to exponentiate to go back to the logit, linear predictor form)

Logit: linear predictor
Odds Ratio: exponential predictor

In sum: 

Logit = additive beta coefficients on log odds scale
Logit, or (or logistic) = multiplicative beta coefficient on odds scale (ie. Odds ratio) 

### Odds Ratio and Case Control 

Case-control: 

Odds ratios - > power is that you can enrich the sample (ie. Control the rates of cases and controls) 
Therefore, you can enrich the sample
Why would you do this? 
SE = SQRT (1/n+1/n….) so cells with low n=> very large SE. It gives you precision

Also used to obtain adjusted odds ratios (of any design), especially useful for case-control study where you a risk difference isn't valid.

Beta coefficients correspond to the odds ratio for exposure conditional on the remaining x-variables (being held constant)

In general, the bigger the referent group (more n), the more powerful the model will be. Sample size: need 10 events and 10 nonevents per predictor as a rough estimate. 

### Interactions 

Whenever you have a categorical variable with more than 1 betas (ie, more than 2 categories), use the ‘testparm i._var_)’ command to test the overall significance. Note, this command takes account of everything that was in the prior logit command. 

Interactions in logistic regression = X1X2 (multiplicative). 1st check for parallelism w interaction: testparm c._x_ # i._y_    -> is it needed at all? 

(At least, this is the way if you are building an exploratory model. If you goal was to test the interaction, then keep it in the model so that you can accept or reject your hypothesis)

### Multinomial Logistic Regression

meaning, when there are more than 2 outcomes: 

Ordinal = has natural progression => proportional odds regression or baseline category model
Nominal = has no natural progression => baseline category model

(Note, multinomial logistic regression = nominal case… technically ordinal is too, but usually is just called ordinal) 

Proportional odds for ordinal outcomes - consider grades.  (Or likert scale responses)

Compare A’s with nonA’s - draw the cut point at a variety of places. 

Then repeat for each cut point (if 5 categories, 4 split points)

‘Proportional odds” refers to the fact that you have individual cut points, but that all the betas are equal (ie. Slope of log odds, which is assumed to be linear, Is the same regardless where the outpoint is) — not when you transform this from log odds -exp-> odds -> 1/1-q-> probability, this will no longer be linear. 

Baseline category model -> pairwise comparisons to same reference group. Ie. Model stage 1 vs 2. 1 vs 3, 2 vs 3. This allows for different slopes (beta) for each predictor -> no proportional odds assumption. 


### Mantel Haenszel estimate

 a method to control a logistic regression across a 3rd confounder variable by taking a  weighted odds ratio. The weight comes from the off diagonal * sample size at each strata of the 3rd variable. 
==> create a 2x2 table at each strata and combine them all using the weight. 
Only makes sense if the weight lead to a different overall estimate -> test of homogeneity (is odds ratio similar enough in each stratum to allow combination?) can evaluate this
—> if you reject this, it suggests there is an interaction on the third variable (ie. Would need an interaction term). 

In sum - you can get the same answer using logistic regression: 
1 predictor = crude MH odds ratio
Multiple predictor but test of homogeneity not rejected = logistic regression with multiple predictors
MH but test of homogeneity rejected = logistic regression with interaction terms. 


#### Maximum likelihood estimation

This is how logistic regression is fit: MLE of the logit. (Vs, least squares in linear regression)

L = P ( data | parameters ) - it iterates but some algorithm until finding a maximum probability of seeing the data 

Plugging in to logistic formula - assuming the events are independent: Maximize ( product of the probability of having the event in all subjects that had the event * product of probability of not having the event in all the patients that did not have the event )

0 cells have problems with maximum likelihood estimators because there are lots of orders of magnitude that are close to 0….  -> large standard errors, difficulty with inference. Even if there is lots of data in the other cells. 

If you have cells that have 0, you have to account for this in your modeling. 
workarounds: 
- Collapse categories
- Or use FIRTHS logistic regression (add +1 to all cells) - small about of bias. 

Maximum likelihood estimation (e.g. in Logistic regression) fails in 3 circumstances: 

1. Data are sparse such as few outcome events
2. Number events divided by the number of predictor variables in the model is small (overfitting) 
3. Outcomes are perfectly or near-perfectly separated by the predictor category. 

Exact logistic regression can get around these 3 issues.

#### Exact Logistic Regression

What if one of your outcomes has no events? 1 problem is that the log of 0 is undefined, so if a category has 0 events the odds ratio can't be calculated. 

When data are sparse (below 5 predicted per cell) -> need to use exact fisher instead of chi2 because chi2 is an asymptotic test. Similarly, a univariate logistic regression is equivalent to a Chi2 when there is an infinitely large sample (technically, called a Wald test) - and suffers from the same limitation: MLE estimators are less reliable when <10 outcomes per predictor (more if data are largely collinear or there is little variation in the dependent variable).

Occurs when there is complete or quasi-complete separation: if there is a line/plane/hyperplane that separates (or nearly separates) the groups, MLE will fail and a logistic regression model can't be fit to it. -> but exact logistic can, because it uses a median unbiased estimate (MUE) instead of the (conditional) MLE.  

Instead, use exact logistic regression (stata: exlogistic- though this does lose some power). 


#### Alternatives to logistic regression with binary outcome

Why? Readers are likely to get confused by odds ratios (and interpret them as if they were risk ratios)

Poisson regression for binary outcomes, with a robust standard error. "poisson y x, robust irr" in stata

"a log-binomial regression, we use Stata’s generalized linear model command, glm, with a log link (log transformation of outcome variable) and a binomial family (variance of a binomial probability distribution", "glm y x , fam(bin) link(log) eform"


### Log-binomial regression

Typically used to obtain adjusted risk ratios in cohort studies involving closed populations (crucial to not use OR/logistic regression if outcome is common)

Note: it is possible get RR over 1.0 for very high y - which can't be interpreted. 

### Poisson Regression

Similar to log-binomial regression, but does not have the problem of possibly getting RR over 1.0

3 use cases: 

1. Modeling rare events. In stata, using "irr" option exponentiates the regression coefficients -> converts to a ratio between two means (ie. Cases in 1 vs cases in group 2) [ ] why is this needed?

2. Modeling rate: cases / person-time. In stata, "irr exposure(var)" is used -> glm with poisson distribution, log link and an offset of log(exposure). [ ] why does this work? For this, Log (Person-time at risk) is moved to the R side ("offset term")  - mathematically stating the assumption that all other things equal, the expected number of cases is assumed to be proportional to the person-time at risk. 

3. Modeling incidence proportion (or prevalence-ratio in cross-sectional design): cases / number-at-risk. Aka modified Poisson regression (= a replacement to the role of logistic regression). E.g. "proportion of people having an event (= 0 or 1). Gives conservative p-value for binomial distributed data -> remedied by robust variance estimator. This works because incidence proportion is a special case of rate where "at-risk time" is the same for all subjects.

Note: an alternative approach to generate relative risks and risk difference => do logistic regression, followed by margins command to do marginal effect estimation. ("If your study design is a cohort study design, the risk ratios are truely risk ratios.  If your study design is a cross-sectional study design, however, the risk ratios will actually represent prevalence ratios. ")

