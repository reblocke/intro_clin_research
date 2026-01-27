# Heterogeneity of Treatment Effect

[ ] combine with effect modification page?

BMJ 2018;364:k4245. doi: 10.1136/bmj.k4245

A fundamental problem (mentioned above) with RCTs is that we only learn about average treatment effects for the population under study, but then need to infer/predict the result in an individual based on that result. 

This is particularly challenging when people respond in different ways - which may be partly due to 'random' variability, and partially due to non-random variability based on characteristics of patients (which is called heterogeneity in treatment effects, HTE).

If the universe was entirely stochastic (ie, no random component), then each patient's true risk would be either 0 or 1, and not measurable due to the fundamental problem of causal inference. Thus, even in this case, the best we could do is measure 'similar enough' people - who form the reference class, and estimate an average risk As similar enough varies, this approach is 'model dependent' and we can still not predict in an individual.

'Reference classes' are generally taken to be the RCT trial population in EBM. However, determination of the correct reference class is key - too small (e.g. the individual or just a few similar patients) and you have no power; too large and you may miss important, predictable deviations. 

Conventional subgroup analyses choose the reference class by a single variable (e.g. female or male) do NOT. However, it is a statistical fallacy to say that if one group meets signficance and the other doesn't - then there is heterogeneity. Even if you directly compare, most are false positives (because RCTs are not powered to detect them (weak theory, noisy data -> false positives). 

At a minimum, for subgroups to be useful they need to be defined a prior, limited in number or corrected for multiplicity, well supported by prior reasoning, and pre-specified in direction.

Other options: stratify based on risk (by a logistic regression prognostic modeling that is independently validated - or occasionally internally valid), or risk of harm from the treatment. You can also make prediction models based on treatment-by-covariate interaction terms.

Sidenote: it is controversial whether HTE should only refer to differences on the relative scale (ie different across risk), or either absolute or relative.



e.g. difference in absolute risk reduction that are mediated by baseline absolute risk are not HTI (meaning, that people at higher risk of an outcome will be benefitted more by a treatment with a given relative risk reduction). For HTE to represent a meaningful difference in mechanism, must be on a relative scale.

How much of variation in observed outcomes is due to HTE vs underlying uncertainty in outcomes? If HTE is present, variance in intervention group must be larger than variance in control group (assuming continuous outcome variable.)

refs: 
https://www.fharrell.com/post/hteview/