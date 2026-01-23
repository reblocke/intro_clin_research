# Causal Inference Strategies with Regression Modeling


Conditional Independence: 
- If decision to treat is conditionally independent of the potential outcomes given the value of the covariates
- We account for all confounders (correctly - ie if they are linear we treat it linearly - ie. This is direct model specification) in estimating effect 

Overlap aka the positivity assumption: groups can’t be so different (even with confounders) that it’s hard to predict using the covariates what would happen in the counterfactual condition 

ATT = average treatment effect on the treated - requires only the positivity assumption on those who received treatment (ie. That they could have not been treated)

vs ACE = if you could know the counterfactual outcomes (and the factual outcomes) for all patients under study, the difference of the means (e.g. if all had been treated compared to if all had not been treated), that's the average causal effect.


### Marginal and Conditional Effects

Conditional effect = assuming the value for one or more of the variables.  --> generally useful to think about the implication of something to an individual (i.e. conditional on their unique pattern of covariates). 

Marginal = multiply the conditional effect (e.g, assuming Female=1), by the population likelihood of the patient having that conditional value (e.g. what is the P(Female==1)? * conditional value.  --> generally useful to think about the implication of a policy to the population

In linear regression - marginal values are the same as conditional because there is a the assumption of linearity (ie the curves aka lines are parallel), and thus as you change the value doesn’t change the conditional probability.  Essentially, the model builds the marginal effects to be the same. However, this is NOT the case in logistic regression.

Logistic regression: should we be talking about conditional effects. Or marginal effects? 
—  Marginal effects: public health claims (.e.g if everyone did this we’d get this)
— Conditional effects: individual patient decisions (e.g. if this 1 person does a thing, what will happen?)

Conditional and marginal effects will differ by more when their are stronger confounders


##  Mediation analysis: 
Two models - 1 attempting to model the mediator and it’s effect on the outcome (indirect path), 1 modeling the direct path (controls for it as a covariate)





Propensity Scores: 
Logistic Regression created to predict the likelihood of receiving the treatment of interest


Overlap of the propensity score and the propensity (ie. Who actually gets the treatment) is a good sign that it means that you are relying less on the assumptions.

Inverse Probability of Treatment Weighting: 
Weight: if treated? 1/propensity
Weight if untreated? 1/(1-propensity)
—> patients who get treatments that seem like they are less prone to get are weighted more highly = a way to approximate what it would be like if people were equally likely to receive either treatment. 

One reasonable approach is to truncate the range of weights to avoid outliers or very “unlikely” propensities

 Propensity Score Matching: allows for more matches than directly matching on the covariates themselves. Downside = don’t use all the info. Upside = not susceptible to outlier propensities, could use K to 1 matching if imbalanced data. 

Other options: quintile adjustment (analyze by stratum of propensity) or use it as an independent on a 