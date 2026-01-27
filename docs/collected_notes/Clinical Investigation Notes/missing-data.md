# Missing Data



## Types of Missing Data

Missing completely at random (MCAR): data is missing unrelated to any characteristic of the subject or the value. E.g. accidentally dropped the test tube. Best replacement is to just use the sample median

Missing at random (MAR): data are not randomly missing, but the probability of a missing value can be predicted by other measured characteristics. Ie. If males are less likely to respond to questions on their income generally (but no difference based on what their income actually is) -> then you can replace with, say, sex-specific median

Informative Missing (IM): data may be missing if their true value is higher or lower (e.g. if poor or rich people are less likely to answer the income question). No way to correct in post-processing. 


## Approaches to missing data: Imputation

Definition: substituting values (by some statistical method) for missing values. Makes the assumption that data is either MAR or MCAR.

'Default' = Listwise deletion Aka complete case analysis - excluding all patients with any missing data => leads to potential biases and loss of power (increased imprecision in the model if using a multivariable analysis). 

Coding rules: ie. Assuming that if a comorbidity is not present in a patient chart, then it is not present (a decent rule, but not perfect). 

Replace missing values with a likely value (either mean, median, or mode). Problem: artificially decreases the variance. We need something with more variability / randomness such that it doesn't effect our summary measures.

Missing indicator approach - add a variable that is e.g. missing-male, then you include this as an independent variable in the regression model. Then, you ignore that beta. However, this actually leads to biased results if the independent variables are at all correlated, so it's not recommended. 

Hot-deck imputation: randomly shuffle the deck and replace the missing data (The entire row) with a random one. Works ok in that it preserves the structure of the data. However, this is very inefficient so probably not the best choice. 

Simple imputation: develop a linear multivariable model from the other independent variables to predict the value of the missing variable. For categorical variables: classification trees are method of choice. For continuous variables, ordinary regression 

Multiple Imputation: the state of the art. 

### Multiple Imputation

Multivariate Imputation by Chained Equations (MICE): creates several versions of imputed data (5-10 generally), analyzes each data set separately, then creates summary measures of the parameters in all the models, then the standard errors are calculated via "Rubin's Rules". 

1. Specify posterior predictive density on the basis of the predictor variables, the mechanism of missingness, and the data
2. Draw imputations from this density to create m different complete datasets
3. Perform m complete-data analyses
4. Pool the m analyses into final point estimates and variance estimates. 

How many imputation data sets should be used? as low as 3-5 can work, if the computation is quick (Or missingness is high) you might as well use 40 (if missingness is 50%, 40 imputations will lead to 1% power falloff).

How to combine the imputed datasets? Needs correctly calculate the standard deviation including adding the inter- and intra- imputation variability back into the standard error (this is the unique feature of multiple imputation) -> Rubins rules are 3 equations that calculate this. In broad strokes, what they do is add the variability in each coefficient in each simulation to the between-simulation variability. 



### Issues related to imputation

Myth: you can't impute the outcome variable. As long as the outcome variable is dependent on the independent variables in the model, then sometimes imputing outcomes will improve the performance of your regression model. Implicitly, if you drop all data on the individual with the missing dependent variable, you are implicitly saying for that person, r=0 because it adds no information to the model. However, this is not usually the case, and thus a less biased estimate can occur with imputation of the outcome. 

How much data can be missing and imputation still work? Up to 50%. 

If proportion of missing data is less than 5%, maybe just do a complete case analysis

If between 0.05 - 0.15 missing -> simple imputation is probably OK.

If between 0.15 - 0.5 missing -> multiple imputation required (simple imputation will not add the correct amount of variability back in. Hotdeck might be ok. 

### Imputing different types of data

Instead of linear regression (which is useful for imputing continuous variables), other link functions need to be used: 

(Stata commands)

- Dichotomous variables: using logit (logistic regression)
- Nominal variables: use mlogit (multinomial logistic regression)(
- Ordinal values: use ologit (ordered logistic)
- interval: use regress (linear regression)

### Interaction terms

If an interaction term is expected, imputation should be performed on the imputation term (as opposed to imputing first, then generating the interaction terms). This is because an assumption of the imputation is that the missing data are unrelated (r=0). If there is an interaction, they are related and any imputation would underestimate this interaction. 