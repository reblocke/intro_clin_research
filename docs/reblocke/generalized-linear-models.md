# Generalized Linear Models



Linear regression is the only one where variance is independent from the mean 

--> thus, we don't rely on residuals. 


Exponential family : any equation that can fit in the following equation format: 

GLMs are members of the exponential family, which can be expressed by a certain form (complex looking equation) 

Meaning of coefficients? 

- Additive models: linear, logit, log hazard, exponentiation of binomial
-  Multiplicative models: logistic, hazard, GLMs

Hypothesis testing = when the nuance parameters come in to play. For determining the relationships when adjusting the variables, they do not influence. 

### Binomial Distribution

Values: between 0 and n (n= number of times the event occurs; p = probability of each event) 

Mean: np

Variance: np (1-p)

### Poisson distribution 

Values: integer values 0 or greater

mean and variance are the same. Useful if the data is not particularly right skewed. 
-- if it is right skewed, then negative binomial is the best approach. 
--  contrast with negative binomial - variance is allowed to be something else: better for right skewed data. 


Use: categorical outcome where mean and variance are the same

### Exponential Distribution 

Lambda is a rate

Values: continuous values greater than 0

mean: 1/lambda

variance 1/lambda^2


### Negative binomial

values: integers greater than or equal to 0
mean: pr / 1-p
variance: pr / (1-p)^2

use: categorical outcome where mean and variance are not the same


### Gamma distribution
utility - mean and variance are related, but assumptions of normality can be violated - thus, this can be used with with continuous outcomes when normality assumptions don't hold . 

To do the actual molding, use the log link (not inverse, even though inverse is it's natural link) - if log link used, it's similar to poisson or negative binomial interpretation. 
-- this gets used often with things like laboratory values: skew, but don't need negatives. 

values: continuous values over 0

omega = the scale
mean: k*omega
variance: k*omega^2

##Model fit: 

- 1/deviance, 1/pearson = theoretically you want to be close to 1 if you choose the right model. 
- AIC and BIC (can compare this between models to see which one fits best). Note: if difference is greater than 2, it's significant. BIC favors more parsimonious option than AIC, but you can use either. 
- Lastly, you can look at the amount of variance in the y and see if which is best

The tests for poisson, negative binomial (analogous to Hosmer Lemshow) aren't all that good in practice, so not used. 

Catorigcal predictor: use testparm to see: is this generally important? (Any categories?)