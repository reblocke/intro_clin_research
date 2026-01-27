# Statistical Rethinking Notes

## Bayesian Data Analysis 

Note: Bayesian data analysis not not necessarily defined by the use of Bayes' theorem (as all inferential statistics utilize it - 'bayesian' or not) - it's the fundamental basis is to quantify uncertainty about theoretical entities like parameters and models using Bayes' theorem.

Bayes was formerly called 'inverse probability. General approach: 

- for each possible explanation of the data
- count all the ways that the data can happen (conditional aka assuming that the explanation is true)
- explanations with more ways to produce the data are more plausible.

Things that can happen in more ways are more plausible: basis of applied probability ('probability is calculus for counting'). Thus, the goal is to deduce the possible parameters(?) given a set of assumptions (the model) that could have produced the data. 

Bayesian data analysis is particularly helpful in signal detection problems, defined as: 

1. There is some (binary) state that is hidden from us
2. We observe an imperfect cue of the hidden state
3. We (should) use bayes theorem to logically deduce the impact of the cue on our uncertainty. 

(Medical reasoning - and specifically, the appraisal of medical tests; or the medical literature in general- being a classic example of this) 

Variables: anything that can take a variety of values.
Counts/data: variables describing concrete things in the world
Likelihood: a distribution function of an observed variable
Parameters: variables that are unobservable/theoretical constructs, can be distributions.

Expectation.-an average result of a function over all of the plausible values of its parameter(s). Also called a marginal (as in, Marginal likelihood)

Contrast: Frequentist approach is to define probabilities in connection to the frequencies of events that would occur in a very large number of samples from the population. In this framework, parameters and models cannot have distributions (though measurements can - the sampling distribution) 

Randomness in frequentist statistics: variation upon resampling
Randomness in bayesian statistics: incomplete knowledge (a property of information, not of the world)

Unlike frequentist statistics where the normal distribution requires 'asymptotic' behavior (30+ observations) before the model fits, there is no minimum sample size using bayesian calculations. Instead, you 'pay' for the uncertainty with dependency on the prior. 

Bayesianism: normative description of rational belief in which principles from bayesian data processing are taken as an ideal method for rationally interacting in the world.

Subjective bayesian: priors (at least the initial ones at the start) are taken to be the personal belief of the analyst. Common in philosophy and Econ - not so much in science (where the prior is essentially treated as another part of the model). 

Bayes (provably) optimally uses information to update the model. Thus, whether the model accurately reflects the real world becomes the operative question.

--> the model's certainty is thus no guarantee that the model is a good one for describing the real world; this has to be empirically tested. Inferences are conditional on the accuracy of the model
--> while the model makes optimal use of the data, even if the model is correct and the updating is maximally efficient, you still may get incorrect inferences based on abnormalities of the sample (ie. Rare events, which the model doesn't exclude - just discounts).

Can take in all the data at once, or can start with a little bit, then add more data and update.

There a three steps to building and refining a statistical model: 

1. Story of how the data might arise (either causal or descriptive)
2. Update the model by feeding data and udpating
3. Evaluate

Bayesian updating: 

- state a causal model for how the observations arise, given each possible explanation
- count ways data could arise for each explanation
- relative plausibility the relative value from step 2

Prior: what we knew about the most plausible explanation before the updating
Posterior: what we knew about the most plausible explanation after the updating (new data added)
Likelihood: the counts that summarize the likelihood of seeing the data, given the model. Used to update the prior into the posterior (multiply by the likelihood, then divide by the normalization constant)

The work of this updating can be thought of 'conditioning' the prior on the data. In order to do this on a broad range of Types of priors (ie. Not restricted in the type of distribution that we can do math on), it's important to use frameworks that are robust: 

1. Grid approximation: 1 way to count plausibilities on a continuous distribution is based on running some large (n=1000 say) options (the grid - will be multi-dimensional if there are multiple parameters) and generating counts for all the ways the data could be seen for each, then normalizing (= multiplying by the likelihood to generate the posterior). Useful for learning, but scales poorly.
2. Quadratic approximation - assume the peak of the posterior is gaussian (called quadratic because the log of the Gaussian distribution is a parabola - described by a quadratic equation) - thus you calculate the 'log posterior', then transform. Works well for linear regression.  Calculated by finding the 'mode' of the posterior via a hill climbing method. Then, estimate the curvature. Performs poorly with small datasets.  If a uniform prior with a large dataset is used, this is equivalent to a maximum likelihood estimator.
3. Markov chain Monte Carlo (MCMC): family of conditioning engines that can handle complex models. Draws samples of the posterior (rather than attempting to calculate it). -> collection of parameter values -> frequency of these = posterior plausibilities.

'Density' - relative plausibility of a proportion 

- There is no minimum sample size (you just end up having a wider distribution)
- Shape embodies the sample size (no comparable role as in frequentist stats)
- There is no "point estimate" - the estimate is the curve. You could summarize with mean or mode if you thought it was justified, but that's an additional assumption (ie. Utility functions). All computations are done on the model, summary measures only happen last.
- Intervals can communicate the shape, but have no intrinsic relation to the distribution. 95% = just convention. Intervals don't do error control as in Neyman Pearson Hypothesis testing.

From posterior (distribution) to prediction: 

- the model depends on the entire posterior
- any inference must be averaged over the entire posterior
- requires integral calculus (most common reason for integrals in calculus is to average over a continuous sample), or sampling from the posterior 

Sampling: a method to turn a calculus problem into a data summary problem (ie. Avoiding integrals). Why do you need to do this? To summarize and interpret the posterior distribution, such as when answering: 

- How much of the distrubution lies below a parameter value, or between two parameter values? (Defined boundary questions)
- What range of parameter values marks the lower 5%, Definedt as the center 95%? (defined probability mass questions. Called a credible interval or a compatibility interval - the range of parameter values that are compatible with the model and data, given the prior)
- What parameter value has the highest posterior? (point estimate questions)

1 issue: if you have a highly skewed posterior distribution, the 'central' 95% (or any interval) will miss the most probable (ie mode). The highest-posterior density interval (HPDI) addresses this by choosing the x% of the possible parameter values that have the highest density. HPDI is similar to standard credible interval if not skewed, and is more computationally intensive and has greater simulation variance (sensitivity to how many samples are drawn from the posterior). 

Credible interval / Compatibility interval: in the 'small-world' (ie, assuming model is accurate and no measurement problems) the true value will be within the range. This is usually what people mean when they use a confidence interval. But, confidence intervals DO NOT mean that there is a x% chance that the true parameter value is within the range (you cannot make probabilistic statements about parameters; instead you make statements about a huge number of repeated trials - 95% of which would contain the value). 

Point estimate questions: loss function = rule that defines the value of any point estimate in relation to the true value, and thus implies an optimal point estimate that should be use. Example you lose points in proportion to the distance from the true value -> implies that the median is the optimal choice. Common choices for loss functions: 

- (d-p)^2 -> posterior mean. ([ ] least squares?)
- (d-p) -> posterior median

A second type of use: simulating prediction

- simulating the implications of chosen priors (by sampling from the prior distribution)
- checking your model to see if it fits observations
- validation of your code
- interrogate research diesign
- forecasting (ie. Applied prediction)

--> likelihoods can be used to generate data that is consistent with the model (as opposed to stating whether real data is consistent with the model) because bayesian models are generative. Simulated data = dummy data

How sampling is done: 

- create a sample of parameter values drawn from the posterior (ie frequency that the parameter value is drawn follows the probability density of the posterior function) 
- then, you can perform descriptive statistics on the sample by counting (ie, how many of the values are below or above a threshold? Etc.)

(Note: this doesn't need to be used with grid approximation, because it has already generated samples for all parameter values.. but for other measures we need to generate)

In contrast to non-bayesian stats, where the sampling distribution on the data is used to directly support inferences, in Bayes it is always sampling of the posterior (which is deduced logically from the prior and likelihood of the data)

Prediction: 

Say you have generated a posterior distribution based on some models and observations, but then want to predict what will come next: you need to account both for uncertainty in the parameter (which can't be observed, only inferred) and Uncertainty from the assumed likelihood function. To do this... 

If you take the sampling distributions Generated form each of the parameter values from the posterior distribution, an average them (weighted for their density in the posterior) - then you get a new distribution called the posterior predictive distribution - which summarizes both uncertainty about the parameter values, and uncertainty about construction of the posterior from the likelihood => represents your uncertainty when predicting. 

## Regression Models

Descriptively accurate, but mechanistically wrong => general method of approximation. They model the mean (as a weighted sum of other variables) and variances of variables. 

ANOVA, ANCOVA, t-test, MANOVA are all special cases of linear regression (ie. General linear models)

Note: uses normal distribution, but the normal distribution remains useful even if the data isn't normal (because it still describes the mean and variances). 

In a linear model, the model tells you where to expect values to be: 

Yi ~ Normal (mui, sigma), Mui (called the expectation) = alpha + betaXi . 

There is scatter around the expectation that is described by the standard deviation (sigma). E(y | x) = Mu

In construction of these models, you'll often need priors. Alpha ~ normal, Beta ~ normal, Sigma ~ Uniform.Sigma (std deviation) is an example of a scale prior which means that it has a positive value. These priors should be constructed such that the prior distribution makes sense from what we know (e.g. if using height, we should start with a distribution fitting expected height.)

Importantly, the decisions about the prior (distributions, plausible values) and the structure of the likelihood function [I think? Structure of the model implies likelihood] are justified by knowledge outside the sample. 

For linear regression, what you are calculating (=posterior distribution) is the joint distribution (alpha, beta, sigma) for all the parameters, conditional on the observed data. 

e.g. Pr (alpha, beta, sigma | W , H)  for an example with weights and heights. 

Grid approximation is expensive for joint distributions because you have to calculate 3 different combinations. All linear regressions optimize these 3 parameters. 
 
Instead, we use quadratic approximation (aka Laplace approximation)

Results: the parameters covary, thus you can't interpret them independently (and effects on prediction are not independent). You need to choose values of all parameters to generate predictions. 

To get predictions:

- plot the sample
- plot the posterior mean
- plot the uncertainty for the mean
- plot uncertainty of predictions (incorporate sigma)

## Model Comparison

Generative models:  can be
- dynamic, where incremental development of the relationship derives from a pattern (ie. A gaussian model results from fluctuations); implies a mechanism
- static: no mechanism implied, but the final state is described accurately from the data


Several models can be created to represent any set of data- how should we choose among them? Generally, by evaluating predictive performance.

Fitting is easy; prediction is har

Techniques: 

### Crossvalidation

### Information Criteria

## Multilevel Models

Aka hierarchical, random effects, varying effects, or mixed effects models. Probably should be the default mode of regression in biomedical research.

What justified a given parameter's value as an input to a model? You could argue that it's a placeholder for another model ("Turtles all the way down") 

Useful when modeling: Generally, when there are clusters of data

- repeat sampling (ie multiple values from 1 person)
- adjusting for imbalances in sampling
- to explore variation between groups in the data
- to avoid averaging that can lead to false confidence.


## Graphical causal models

Sometime models that are causally incorrect make better predictions than those that are causally correct.

DAGs are heuristics that we can use to deduce statistical models. DAGs come from information outside the data (assumptions about how we think the world works)


## Particular Distributions of Note

Binomial distribution: describes that there are two events, independent trials, and in each trial the likelihood is p and 1-p. No other information added (maximum information entropy.)

~ = stochastic; any individual instance is not known, but generated probabilistically

W~ Binomial(N, p); W is the outcome, ~ means 'is distributed', binomial refers to the data distribution (or likelihood function), N is the number of observations aka sample size, p is the proportion of interest. (N, p) together describe the shape of the binomial distribution.

Uniform distribution between a and b: 1 / (b - a). Makes it such that every value between a and b is given the same value, and the integral sums to 1. e.g. p ~ Uniform (0,1)

Normal distribution: 2 arguments for why its important. 

- Generative argument -if a process arises from summing (or multiplying) random fluctuations (ie coin tosses), you approximate a normal distribution. Many more way for the fluctuations cancel each other than not - thus density is near to middle. This is true regardless what distribution the fluctuations come from (though that influences speed of convergence)  
- Statistical argument - for estimating the mean and variance the normal distribution is the least informative (only information needed is a mean and variance) - maximum entropy. Equivalently, if all we are willing to commit to is the mean and variance, then the normal distribution is most consistent (can be realized the most number of ways without any new assumptions)

One downside is that many natural processes have fatter tails than the Gaussian distribution, especially in the long term.   

Exponential family of distributions.  - includes normal/Guassian distribution


Lognormal distribution: if you took the log of each value in the distribution, you'd get lognormal. (Equivalently, if you exponentiate - e^x - each value in the normal distribution, you get the lognormal)