# Statistics

Number of decimals to report: match the original precision of the data. E.g, if age is collected as an integer, descriptive statistics about it should be the same (AMA style says its OK to 1 more decimal place). 

P-values - should be expressed with 2 digits, unless its either: within .01 of.05 OR <.01 (in which case, you can see .002... but never go <.001). Also note, the leading 0 is not required for the P-values.

##Terminology: 

Strong Law of large numbers - as the random sample of a distribution gets larger, the measured mean (and variance) will approach the true mean (and variance)

Central limit theory - the distribution of means from samples randomly taken from some population (with mean mu and variance sigma2) will have an approximate normal distribution with mean=mu and variance=sigma2/n as n increases - even if the underlying distribution is not normal. Tests using this are called asymptotic tests (as n=> infinity)


Descriptions of the entire population: parameters (e.g. population mean, mu)

Descriptions of a sample of the population: statistics (e.g. sample mean, x_bar)

Note: when estimating the variance of the sample, the unbiased estimate devides by n-1, not n. This causes a slightly larger variance.. because the sample will always be a restricted look at the possible values from the population.

Explained here https://www.khanacademy.org/math/ap-statistics/summarizing-quantitative-data-ap/more-standard-deviation/v/review-and-intuition-why-we-divide-by-n-1-for-the-unbiased-sample-variance

##Descriptive Statistics

Skewness: labeled as the direction of the long tail. Left skewed = mean < median < mode; Right skewed = mean > median > mode

Std deviation = sqrt(variance)

Std Error on the mean = std deviation / sqrt(n)


### Standard Error of the Mean

This is the 'sampling' error on estimates of the mean if you were to compute the means of random samples and graph the values. 

When should you use SEM as error bars, and when should you use Std deviation? 

-when you are describing distributions in the population (e.g. Table 1)= summarizing individual observations - use standard deviation
-when you are quantifying uncertainty about the estimates of the mean (e.g. the rest of the results), use standard error of the mean.


## Significance testing

Fundamental tasks: separating signal from noise.  Because of the strong law of large numbers, the signal to noise ratio improves as the sample size increases.  Based on assumptions of the data - the goal is to choose a test statistic that accurately encapsulates the signal in the data (ie. A more powerful test relies on assumptions about the data, which if valid, allow more robust inference). 

P value = prob (observing a sample effect at least this large given that the true means are qual)

Logic = proof by contradiction: Suppose something, then show that if that's true, a contradiction follows.. thus the supposed thing can't be the case. In p-values:

- Assume there is no effect (P-value is large)
- construct the signal-to-noise ratio from data (compute the test statistic)
- compute the probability of observing this test statistic aor a larger one. 
- observe that if seeing this test statistic is unlikely, then there is a contradiction

Note: 95% CI and Significance Testing are not necessarily synonymous: CI of each group can overlap by 25% and still be statistically significant... however, the 95% CI of the mean differences should not overlap with 0 if P < 0.05

Note2: how do you go about investigating correctness of tests or robustness to assumptions? Generally, need to perform simulation testing.

### Types of data

(Dichotomous = Binary, special case of nominal with 2 categories)
Nominal  = unordered categories
Ordinal = ordered categories
Interval scale = ordered, with equal intervals and an arbitrary set point (e.g. temperature in C of F)
Ratio scale = ordered, equal intervals, and an absolute zero point (e.g. temperature in K)

(Interval and ratio often lumped together as 'continuous data') 

Additionally, dichotomous variables can be treated as having an interval scale (ordered, equal interval) for the purposes of a predictor variable in a regression. A dichotomous variable is a "Bernoulli variable" = mean is p and variance is p(1-p) where p is the probability of a 1. 

Interestingly, summing ordinal data (e.g. the individual results on a depression scale) are often treated as interval data in aggregate. If the jumps between each answer are unequal (e.g. lie->sit->std at bed-> play basketball), then Rasch model or similar needed to balance weights. 

This is partly the case because analyzing ordinal scales as interval scales actually does not cause much alpha inflation (2-6 Stoddard)

Similarly, nominal categories (e.g. gender) can be converted to ordinal categories (male-ness) and interval scales (if scored 0 and 1, male = 1, not male = 0) for the purposes of doing arithmetic. In fact, this is required for regression analysis and calculating Pearson correlation coefficients.

### Types of significance tests

Exact tests aka permutation vs limit tests: permutation based tests (e.g. Fischer's exact test) are slightly less powerful, owing to the discreteness of the output (e.g. larger jumps across the threshold of significance). However, can be used with small n (either total sample, or in some results - see ch 2-4 Stoddard)

Parametric Test - assumes features of the underlying distribution (eg sigma, mu); vs non-parametric tests, which makes the comparisons on the observed sample (which allows it to be used on ordinal data, as well... and example is tests based on ranks -e.g. Wilcoxen-Mann-Whitney)


#### Approach to outliers

Tests (e.g. T-tests) that are parametric may be susceptible to outliers. Rank-based comparisons are robust to outliers. 

Often can sidestep this by adding encoding rules to guard against biologically implausible results (termed the Truncation approach to outliers, less extreme that simply eliminating outliers). 

#### T-test

Due to central limit theory, this is robust to deviation in skewness/non-normality (because the distributions of means will be normal even if the underlying distribution is skewed), though not all that robust to outliers. Technically, also requires homogeneity of variances between the samples (though there is a non-homogeneity version... yet, in practice this is actually not needed as the default is pretty robust to those assumptions)

Generally works well for small sample sizes (classic teaching is to switch to WMW test, but this is incorrect - See Stoddard 2-19)

#### WIlcoxen-Mann-Whitney

Rank (non-parametric) test

##### Drawbacks

- Does not use information from an interval scale (decreases the data to an ordinal scale - ranks) which leads to a loss of power. 
- It performs the best when the distributions have the same distribution but are shifted -> can give too much significance when distributions differ.


### Confidence Intervals

Mean = best point estimate; confidence intervals = an interval estimate that covers the true population effect with some level of confidence (e.g. 95%)

When the mean difference is the parameter of interest, +/- Test Statistic * SEM can be used to calculate this

## Pre-specification of Analysis

Need to allow some flexibility in the approach - such as outliers. Suggestion from E9 - due a blind review of the data and make decisions based on that with a justification for why any changes might be made - then unblind it and see what result you get. 


## Sample Size Calculation

How big does the sample size need to be to adequately increase the signal/noise ratio?

Explanation: imagine a confusion matrix with "test result" = your study, and reference standard is the truth of the hypothesis you are testing. 

Sensitivity = true positive / all those that are true
Specificity = true negative / all those that are false

Thus, 

Test Ho False (finds a difference), Ho false (reject null, really is a diff) = True positive = 1-beta
Test Ho False (finds a difference), Ho true (really no diff) = False positive = beta, aka Type 2 error
Test Ho True (finds no difference), Ho false (really is a diff) = False negative = alpha, aka Type 1 error
Test Ho True (finds no difference), Ho true (really no difference) = True negative = 1 - alpha

Thus sensitivity is ~ 1-beta, specificity ~ 1-alpha

(Note: the relation between se/sp to positive/negative predictive value is analogous to why studies with P<0.05 don't have a <5% chance of being false - that depends on pre-test probability). 

1-alpha = confidence level 

Note: say you have a 95% power and find no effect - have you found evidence for no effect? No! 
Need equivalence testing, or non-inferiority testing (if no worse is goal)  - Chapter 2-15 of Stoddard. All we can conclude is that we did not find sufficient evidence for an effect. 

(My musing:)
Is there an analogy to likelihood ratio?  Perhaps this is bayesian?
LR+ = sensitivity / 1-specifity ~= 1-beta / alpha 
LR- = 1-sensitivity / specificity ~= beta / 1-alpha


### Power
Power = prob(our sample achieves statistical significance if there truly is an effect)

Always increases as sample size increases 

Depends on: 

- minimum size of effect you are trying to detect. (If you say, only shooting for large effect - power is higher) - generally should by MCID (minimally clinical important difference)
- standard deviation of each group in the population (more variable = less power). Often taken from pilot data or prior trial.. or can assume biologically plausible range is 4-6 SDs
- the choice of alpha (smaller alpha -> have to go further out on the tails = less power; conventionally, 0.05)
- whether you are using 1 or 2- sided comparisons: test statistic does not have to be as big for 1 tail test, thus more power (though this is uncommonly proper in practice - near all journals require 2 sided.)
- the sample size (generally increases as sqrt(n) - diminishing returns). 

Generally, want 80% (minimum) or 90%-95% depending on cost-benefit of increasing sample size.

Note: you can tighten up inclusion-exclusion criteria to try to decrease power

#### What to do with proportions? 

E.g. Dichotamous outcome variable

Seems like you'd need the 'std deviation' - however, with proportions: 0-1 variables = Bernoulli variable, thus Std Dev = sqrt(p(1-p))

#### What should be done with very large datasets? 

P-values lose their meaning if you are able to detect findings that are smaller than the MCID; thus, using a CI approach is better in this circumstance as it represents the precision of the estimate on the parameters of interest. - then the reader can easily decide whether that effect size is clinically important. 

See: https://doi.org/10.1287/isre.2013.0480

### Multiplicity

With multiple comparisons, their are more chances that at least 1 of the comparisons will be significant - thus we inflate the type 1 error (calling a difference when there is none). Called the multiple comparison problem. 

Thus, we need to pay attention to the family-wise alpha (or family wise error rate) when considering several pair-wise comparisons where the finding of any comparison rejecting the null would be individually treated as significant. 

Multiplicity problem has 5 ways it can arise: 

1. Multiple treatments
2. Multiple end-points - e.g. if there is an improvement in any of these, it will be assumed the drug 'works'
3. Repeated measurements
4. Subgroup Analyses
5. Interim analyses

If each test is independent (not entirely true in reality): for k comparisons, P(at least 1 significant by chance) = 1 - (1-alpha)^k

For interim analyses, clearly not independent because earlier look data is included in subsequent looks -> inflation occurs much slower.

#### Adjustment Procedures

Bonferroni procedure: most conservative (needlessly so). Divide starting threshold P-value by number of comparisons and use that as the new threshold; e.g. 0.05 / 3 comparisons = 0.0167 significance threshold. (This is generally done by adjusting the P-value, not adjusting the threshold, so that readers don't have to do it in their head)

Holm procedure: sort your p-values, then multiply their order. 

Hommel's procedure (most powerful): and generally used. (Though somewhat more complex, use Stoddard's mcpi command in stata)

All the above maintain the family-wise alpha for independent tests.

For highly correlated (r 0.9) hypothesis aka dependent tests, such as interim analysis: Turkey-Ciminera-Heyse procedure

#### Primary-Secondary hypothesis approach

An alternative approach to multiple comparisons: Make one of your hypotheses your primary outcome, then make other outcomes secondary (which are just exploratory, and thus not considered comparisons to adjust)

### K (more than two) sample comparisons

Two possible approaches: 

1. make each pair-wise comparison, then adjust for multiple comparisons (generally preferred, as it preserves the family-wise error rate and leads to significance more often. In addition, it specifies which comparison is significant - whereas ANOVA only says that there is a difference). 

2. Do a oneway ANOVA and generate one p-value for the set of comparisons (this is generally only useful for table 1 in studies with multiple groups). Of note, the built in multiplicity adjustment of ANOVA Is very conservative, thus significance is not often found)

### False discovery rate

The above framework of multiple comparisons keeps the Family-wise error rate (FWER) below the level of alpha (0.05) - meaning that the chance that any test is considered significant is 0.05 or below. FWER = controls for the chance of ANY false positive.

The false discovery rate (FDR) can be used when each individual comparison is important. Controls for the expected proportion of false positives among all tests. e.g use cases 

1. Multiple end-points (where an end-point being significant may lead to a future separate indication, but does not suggest that the drug is 'overall' effective)
2. Multiple subgroups (when treatment decisions would be made independently - that effectiveness in 1 subgroup would not be interpreted as effectiveness in the others)
3. Screening problems - e.g. testing various chemicals for potential drug development

Benjamin Hochberg procedure is most commonly used. 

### Prespecify the Win Criteria

If you say beforehand how you will interpret the result - then, you can determine whether FWER, FDR, or no multiplicity adjustment is required. 

E.g. 
If three separate questions? Tests are in isolation, no adjustment (as long as any being a win is not sufficient to declare a win for all)
If three tests to answer one questions? (e.g. any of these positive = win) Need to adjust

## Displaying Data

Note, relative measures of effect size (relative risks, relative odds), logarithmic scales should be used. Reason? Because the ability to reduce the effect is constrained on one end (to 0.0) but not in the other (to infinity) 

Similarly, P-values / CI are symmetrical on a log scale

## Measures of Incidence and Association in Cohort and RCTs

Ratio, difference = association (= comparison between exposure and index conditions). 

Thus, for any measure of association, it needs to be explicitly said what the comparison is to (e.g. who makes up the index aka unexposed group)

Io = incidence in unexposed
Ie = incidence in exposed

(Relatedly, Si is the proportion without the event, or surviving, in the index group. Or 1 - Io)

Report absolute or report relative? Depends on your research question or conceptual model. 

Absolute: interpretable in terms of incidence (unit), clear inference to clinical significance
Relative: easily accounts for adjustments for confounders, constant over follow-up time, often more constant over varied baseline risk. 


### Denominator = Count

If follow-up complete, and outcome assessed at one time point

- Counts: Risk, Cumulative Incidence, Incidence proportion 
- Relative: Ie / Io. Risk Ratio, Relative risk, Cumulative Incidence Ratio =  relative measures (Risk in the exposed / Risk in the unexposed). Also has no units; null = 1
- Absolute: Ie - Io.Risk Difference, Cumulative Incidence Difference, (Number Needed to Treat)= absolute measure of association. Retains units, null = 0

NNT = 1 / Risk Difference

If CAUSAL, risk difference can be termed attributable risk. 

Note: this is for cohort studies. If assessing at one time point, prevalence and prevalence ratio or difference is calculated (though the formula is the same)

### Denominator = Person-time

These are more valid with frequent loss to follow-up, outcome assessment at many time points (e.g. deaths, which happen when they happen).

Note: 2x2 table has Exposure as the rows, columns as number w incident disease & person-time at risk

- Rate: Incidence Density, Hazard rate = 'rates'
- Relative: Rate ratio, Incidence Density Ratio, Hazard Rate ratio = relative measures (unit-less, null = 1)
- Absolute: Rate difference = absolute measure of association. (Retains units, null = 0)

Note: risk ratio is appropriately only when either 

1. Outcomes of all subjects are measured at a prespecified point in time
2. All subjects are followed to either failure or a uniform follow-up time

If those conditions aren't met, Hazard Rate / HRR is a better choice

Note: 
"This is Francis's first law of NNTs:
If you need to plot a Kaplan-Meier curve,
It's a bad idea to speak  of  "the"  NNT"
- because in fact, the denominator is person time... and thus, if there is a linear relationship, NNT would be in "person-years", and if the relationship is not linear, it is nonsensical.

#### Hazard Rate and Hazard Rate Ratio

Used widely because it more accurately summarizes than incidence rate ratio because it accounts for the time specific hazard rate, rather than lumping all together.   (e.g. if you think of risk of hospitalization by age... it will vary by age. Thus, the HRR can account for this varying hazard, while a risk ratio cannot)

Hazard rate ratio (comparing hazard rates at each failure time point) is close to the incident rate ratio - and thus is interpreted in the same way that a risk ratio is.. 

Hazard rate function = time specific hazard rate (e.g. at time 0, events per time; at time 1, events per time; etc...) vs Incidence rate (=the whole block is treated as one block of time, events summarized over this whole period). HRR gets used more because it doesn't assume a constant risk throughout the entire summarized time.

Calculation uses the risk set = accounts for censoring because only those at risk at any given point in time are used.

Note: you cannot recreate HRR from the tables; you need all the time data (when the events occurred) 

## Odds Ratio in case-control studies

Needed for case control studies, where cases and controls are selected (and thus do not represent an incidence rate - because you do not know that when calculate the measure).

Incidence = requires knowledge of the proportion of cases, which in a case-control study this is fixed by the investigator.  

Can calculate odds of exposure among cases and odds of exposure among the controls => ratio, is the odds ratio. 

Why does this work? When the incidence is low (meaning, disease is rare in the incidence population), it approximates the risk ratio. A << b, c << , thus a/(a+b) / c/(c+d) = a/b / c/d == a/c / b/d. In the 2+2 contingency table, it means that the calculation no longer depends on the ratio of people in the left column (diseased) vs right column (undiseased)

Terminology: Referent (or reference) category is the 'non-exposed' groups (if unclear, generally take the largest group to maximize statistical power), whether they are cases or controls

Odds ratio = risk ratio (which is the real parameter we are interested in) IF 

- the outcome is rare in the population 
- AND requires that the cases are representative 
- AND the controls are representative of the population they are selected from. 

## Measures of impact

Makes sense only if exposure is causal. Difficult to interpret if the exposure has benefits in some but harms in others. 

Absolute: 

Attributable risk (AR, Ie - Io) = the number of cases that are attributable to the exposure. 
Population Attriutable risk (PAR), all cases (exposed and unexposed) make up the denominator. What proportion of ALL the cases are due to the exposure. I - Io.

Relative: 

- Attributable risk proportion (ARP) 100% * (Ie - Io) / Ie = the percentage of the disease incidence among the exposed that is due to the exposure.
- Population attributable risk proportion (PARP)




## Regression

### Linear regression

Linear regression is a generalization of the T-test (same result if two variable linear regression is run). It's generalized to be able to hold other confounding variables in the model 'constant'

Yi = a + bXi + ei

- A = y intercept, _cons in stata
- b = slope, regression coefficient = the change in the outcome variable for one unit change in the predictor (after controlling for ie holding constant all other variables in the model)
- E = residual (error, vertical distance from each point to the line - the algorithm minimizes the squared distances (E) = aka 'least squares regression')

Which confounders / variables should be included in the model? A good rule of thumb is if it is significantly associated (P < 0.05) or changes the outcome of the model by 10% or more

As you add confounders, you add dimensions to the best fit line (and the intercept becomes the predictor value when all other values are 0). As you add these, the ones which are 'significantly' associated with the outcome are called 'independent predictors', suggesting they do explain some variability (beyond chance) to the outcome variable.

Note: another statistical method to control for confounders in the data is restriction (to make a more homogenous data source). 

- valid in the case where you are trying to test a hypothesis in a specific population. Have to be careful that you generalize the findings to non-represented patients. 

### Pearson r

Pearson product moment correlation coefficient = r, -1 to 1 dimensionless. = to the regression line through X-Y scatter plot when they are first converted to standard aka z scores (z = (X-xbar / SD)) -> thus they explain how much 1 unit change in the std dev of the predictor accounts for the change in std dev in the outcome.

Minus 1 = straight line where they are inversely related
0 = best fit line is flat
1 = straight line where they are directly correlated

Rule of thumb: 0-0.3 (little if any); 0.3-0.5 (low correlation); 0.5-0.7 (moderate correlation); 0.7-0.9 (high correlation); 0.90-1 (very high correlation)

Ordinal scales spearman's rho (takes them to ranks, then uses Pearson on those)

r^2 = coefficient of determination = the proportion of the variability in one variable explained by the other variable.

Multiple R^2 (as opposed to simple r^2) is the variance by all of the variables in the model. 

Coefficients from linear regressions are called beta-weights => gives a standard dimension between different covariates so that you can compare their influence on the outcome variable. 


#### Overfitting

E.g. you fit a line between 2 points... even if they are random, will always be a perfect correlation. Some spurious association persists until about 10 points, usually. 

Similarly, if you fit a plane to 3 points, even if they are random it will be a perfect fit. Same with a hyperplane to 4 points, etc. etc. 

Thus, you get overfitting by adding more predictors to the model, and by rule of thumb you need about 10 data points (outcomes) for each predictor to avoid overfitting (aka spurious correlation). 20 is even better (especially if 1 variable has a narrow range). 

Note: there is a lot that goes in to precisely how many outcomes you need: can vary from 1:5 to 1:40. 