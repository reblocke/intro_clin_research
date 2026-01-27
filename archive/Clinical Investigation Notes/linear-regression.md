# Linear Regression

Linear Regression visual explainer: https://mlu-explain.github.io/linear-regression/

Used to model continuous outcomes (e.g. SBP) - must be an interval scale or a ratio scale.

Yi = a + bXi + ei, where ei (error term aka residuals) is minimized

Note: 

- Prediction equation = doesn't have the error terms but instead terms take hats (best estimate)
- Theoretical equation = has error terms, describes random and deterministic components. 

Residual = aka observed error = observed minus predicted (from prediction equation)

Simple linear regression 

- Least squared estimators = a method that creates estimates that minimizes sum of squared errors  
- (SSE = sum of squared errors) 
- MSE = SSE / DOF

To get to MSx: SSx / Degree of freedom 

Degrees of freedom= Every time you estimate something, you burn a degree of freedom (= n-1 if you estimated 1 parameter, e.g. MSX; n-2 for MSE because you estimate beta0_hat, beta1_hat)

S2_y = total variability in the outcome
MSE = S2_y|x =  after accounting for the deterministic component, how much variability is left. 

Y=B0 + B1X+E; E~normal(0, sigma^2)

Root(MSE) = basis for confidence intervals and test-statistics for hypothesis testing (of whether B1 = 0, for example)

Sigma is a population parameter, thus not knowable. But can estimate using MSE instead

Say we are not able to reject the hypothesis that B1 = 0. Why? 

- for linear relation, x actually isn't predictive of y
- the true relationship is not linear
- the sample size is too small. 

If you reject: it means there is some relationship (though it doesn't necessarily accurately reflect)

Note: since we've assumed normality - we can use the T test statistic to generate a p-value. Or, conversely, we can use a critical value of the test statistic and then calculate the range of beta_hats that are within

==> Inferences about the regression line itself (differs from estimates about particular parameters) 
Implication = creates a confidence "band" around the line. Allows you to make inference about the range of values. 

For a particular subject prediction: interested in the parameter

For a population estimate: band is much narrower than a prediction band for an individual person. 

Why Least Squares? Because there is a mathematical solution. [ ] anything else? Vs maximum likelihood?

Simple linear regression: Pearson (r, 'rho' is the population parameter that r estimates): b_hat * (Sx / Sy) correcting for variability of the the SS's. Note: this is mathematically equivalent to testing b_hat = 0 because of 1 to 1 relationship.  

Multiple R-squared = coefficient of determination: The proportion of variability in one variable explained by the other. (Or, the proportion of variability in the dependent variable/outcome that is explained by the set of indepdendent variables/predictors) 

r^2 = 1 - (var of residuals)^2/(var of outcome)^2

![alt text](https://photos.collectednotes.com/photos/5187/cbfea56f-bd2c-4656-9b3c-e02bfce7b537)

If the regression line doesn't hit the observation exactly (ie, residual =/= 0), then something about the observation is not explained by the model. Exactly how much is what the above formula calculates.

Note: If you have 1 predictor (independent variable), then the sqrt( multiple R-squared) -> Pearson Correlation Coefficient aka r

Compare:

- Regression coefficient is a measure of - 1 unit change in the predictor variables leads to r change in the outcome
- Correlation Coefficient is a measure of - how well the independent variable(s) predict the dependent variable.

Why does 1 category always get left out? Intuitively, what the model is calculating is "what proportion of the variability remains if this predictor is held constant?  - if you removed all of the predictors, only the constant (which has no variability) is left. Instead, the last predictor is lumped together with the constant. 

If a quadratic function is used instead, it's a 'curvilinear regression' (refers to all non-linear). Done in stata by generating a square term as a second independent variable.

- quadratic: y_hat = b+ b1x + b2x^2 
- cubic: y_hat = b + b1x + b2x^2 + b3x^3
- inverse: Y_hat = b + b1(1/x)
- logarithmic: y_hat = b + b1*log(x)

Takeaway: look at the data before you regress on it

##### ANOVA 

ANOVA = actually an analysis of means, but the reasons its called analysis of variance, decomposed into a component from the model and a component that is unexplained

"ANOVA Table" - upper left of STATA regression output. 

Total unexplained variation = variation from regression + unexplained residual variation. 

SSY = total variation = sum (y-y_bar)^2 . Fixed for any data set. 

SSE = variation in residual = sum (y - y_hat)^2 . For some models, this will be smaller (if better) 

SSR = variation in  'model' = sum (y_hat - y_bar)^2 . This would make up the remainder. You 'want' this to be bigger (= more accurate model)

SSY = SSE + SSR

R squared
R2 = 1 SSE / SSY = SSR / SSY

Model: DF = # predictors (k), sum of squares = (SSY - SSE), MSR = (SSY - SSE) / DOF.

Error: DF = n- (# predictors (k) - 1). Sum of squares = SSE. MSE = aka S^2 Y|X = SSE / DF. 

Total: DF = n-1, sum of squares Y. 

F value = MSR / MSE => in words, if this mean squared regression is much bigger than mean squared error, then the model explains more than chance of the data and the F value statistic is likely to be small. 

F distribution: r-skewed, non-negative. Average is close to 1. In the specific case where there is 1 independent predictor, then the T statistic squared = F distribution, and thus linear regression is equivalent to ANOVA.

Note: adding variables will increase R^2 - thus, will need an adjustment in order to be comparable between models with different numbers of predictors. 

##### Multiple linear regression 

Types of statistical testing: 

1. Overall test: 'do any of the predictor matter?' F-test = sigma_hat_o^2 / sigma_hat^2  (where sigma_hat_predictor is true). Comparison = MSR / MSE = SSR/k / SSE(n-k-1) = only intercept vs full model (does the additional of all the predictors add any prediction ability beyond chance; equivalent = beta1.. betak all = 0).  
2. Test of adding an individual predictors: Partial F-test = compare a model with all but 1 to the complete model. If testing just 1 model at a time, this is the same as a T test. SSR (x1, x2) = SSR(x1) + SSR(x1 | x2). Tells you how many standard errors you are away from Bi = 0. 
3. Tests of adding a group of predictors: multiple partial F-test = test a subset of predictors as a group. As above. SSR (full model) = SSR (partial model) + SSR (full model | partial model). Tests whether anything other than the partial model matters. = SSR (Full model) - SSR (partial model) = SSE (Partial model) - SSE (Full model). F statistic = [ SSR (Full Model) - SSR (partial Model)]/k  / MSE(Full Model)

Model terminology: 

- Full model: including all the predictors.
- Reduced model: the nested, special case of the full model. Restrictions added (perhaps by removing predictors)

There are 4 types of sums of squares, but what we use (Type 3) = what is the change by adding the variable to the rest of the model (ie. How much is explained that was not already explained by the other variables in the model). 

##### Assumptions (For linear regression)


All assumptions about the distribution are. About the response variable- NOT the independent variables. 

And that is true about all regression methods. 


Same between ANOVA ( which is a special case of..) / linear regression

- Homogeneity of variance aka homoscedasticity. (ANOVA: each category has same variance on outcome; linear with continuous predictor: variance around regression line is the same at every point on the abscissa. However, linear regression is relatively robust to this.   (Otherwise, you need to do a weighted least squares regression)
- Normality of residual error ( predicted - actual has normal distribution). In actuality, this is the least important. Additionally, note that it is the RESIDUALS, not the predictor variables, that need to be normally distributed. If data are somewhat symmetric you are probably fine, even if skewed.
- Statistical independence of residual errors - no pattern to errors. Practically, this means no clustering effects (would imply that you need a multi-level model). No 'test' to determine this. 
- Linearity of model. Y= a + bX + error is a reasonable model ('expectation' of the value is linear; alternatively, the deterministic component is linear). 

(These are required for valid MSE estimates)

Transforming data can address homogeneity of variance or normality of residual error issues.

T-test (which is a special case of ANOVA, with two categories), ANOVA, and linear regression are robust to assumptions of homogeneity of variance - thus if this is violated, the impact probably is not all that big. 

Levine's test can be used to assess this, though it's not entirely clear how to interpret the result of that test into recommendations (to transform or not?)

Shapiro-Wilkes test can be used to test normality of residuals. 

However, transformations can usually be avoided because of the robustness to violations (though they are sometimes done to increase statistical precision).


Evaluating the assumptions of linear regressions: 

Prior to doing any regressions - ensure data quality: 

- Look at 5 largest and smallest values of each variable to make sure they make sense
- Compute descriptive statistics (mean/std, freq)
- Create scatter plots and histograms
- Compute pairwise correlations.

After doing regressions: 

- Standardized residual: zi = Ei/s (= normalize the errors to the amount of variability in the y) - should have mean error of 0 and a normal distribution. Thus, if outside 2 or 3, suspicious
- Jackknife residual [ ] fill this in
- Evaluate high leverage subjects (far from mean observation). High leverage on its own is not a problem, but high leverage combined with a high residual suggests the outlier is influencing the model. 
- Cook's D: looks at how much the model changes if you leave out the observation. Cook's D > 1 is problematic.

Order of operations: 

- clean data
- do regression
- evaluate Cook'd > 1, leverage, and Std/Jackknife residuals - if there are considerable deviations where the same observation is high on multiple parameters -> double check the coding of these ones. 


##### Transformations

Transformation: Even though robustness of linear regression means that it is still valid in non-normal/skewed data, you can improve statistical efficiency. 

Why does this work? In a way, the scale of the original measurement is arbitrary. Thus, if transforming to a new scale gives better statistical properties (such as normality), then that should be done. 

3 reasons to do a transformation: 

1. Ensure linearity
2. Achieve normality of residduals
3. Stabilize the variance of the residuals

Tukey's ladder of powers (stata: ladders command) can be used to search a list of powers (ie. 1/2, -1/2, ln) for a transformation that converts it to a normally distributed variable.


Downsides to transformations: 

1. You lose intuitive meaning of the regression coefficients. 
2. You can't do predicted or adjusted means (because the back-transformation does not work - [a+b]^k =/= a^k + b^k)

Exception: the log transformation is different and DOES have intuitive meaning and back transformation works. Why? Because it transforms that model from a multiplicative model into an additive one. (Model is linear in log(y) but exponential in y)

If you do a log transformation of the outcome variable, then the regression coefficients also need to be transformed: 

- 100 (e^beta - 1): regression coefficients are the percentage increase in the average outcome in the outcome per 1 unit change in the predictor
-  beta * ln (1.01): average change in the outcome for 1% increase in the predictor. (1.05 could be used for 5%, etc.)

Note: these means are GEOMETRIC means, not arithmetic means (at least, assuming you use the usual ordinary linear regression)

Ordinary linear regression with log transform of outcome -> back transform gives geometric mean
Generalized linear model with log transform of outcome -> back transform gives arithmetic mean. (Why?)

If log transformation is desired but the value of the outcome can be 0, sometimes a log(y+1) transform is used. Often the difference is small enough it can be ignored. If not ignored, can just subtract 1 after the back transformation.  With means, still a good idea to subtract 1 after the back transformation it's not perfect, but close (or use glm instead).



#### ANOVA and ANCOVA

-ANOVA = linear regression with categorical predictor variables (called factors). (Note: a T-test is a special case of ANOVA with 2 categories comparing means)

-'One-way ANOVA' = linear regression with 1 (categorical) predictor variable. 
-the P-value associated with this tests the hypothesis that the means of all categorical predictor variable groups are equal - if the p-value is low, it tells you that at least 1 is different from at least 1 other, but doesn't tell you which. 

The top part of the STATA output is the ANOVA table - clarifies how much of the variance (‘analysis of variance’) the model explains. The ANOVA test = is the amount explained more than chance? 

-ANCOVA = linear regression with categorical and continuous variables  (called factors and covariates)


Dummy variables: 
-burn a degree of freedom every category
- N-1 dummy variables (where n is number of categories) 


###Heteroscedasticity

non-homogenous residuals. Greater variance in residuals is a violation of this; or non-normality. 

Variances can be tested using Levene's test. If less than 0.001 do a transformation; if greater than 0.01 definitely don't transform. Grey area between. 

For normality - can use shapiro-wilks test of residuals. However, it is often better to just use an eyeball test of the residual graph, because in large samples you may get a 'statistically signficant', but trivial deviation from normality (that doesn't matter because of the central limit theorem / law of large numbers) and for small samples you may have insufficient power even if the deviation is important. This can be done with a quantile-normal plot (qnorm) in stata


## Interaction terms 

Interaction between 2 continuous variables gets very hard. Thus, generally it is better for 1 to be a categorical variable. (Unless you are primarily interested in prediction rather than explanation)

Interaction terms vs confounding: 

Interaction term = quantifies effect modification (strength of moderation) - how much different the effect of interest is between groups. 

Frequently: the interaction term is the PURPOSE of the paper. Often, if the question is “does A work better in a certain group”? Then the idea is to model with an interaction term. 
