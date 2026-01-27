# Disease Detection and Screening

## Prediction / Diagnosis Approach

Something can be predictive (through strong association) but not causal (meaning, intervening on the biomarker does not impact the disease presence or course).

Both predictive and causal approaches share certain characteristics: 

- similar designs (cohort, case-control) 
- marker or test-result is generally measured at baseline (or in the past)
- an incidence of outcome is measured later (though RR, OR, statistical significance don't generally apply - we are more interested in discrimination)

Where they differ: 

- treatment of confounding: in a predictive approach, we want to include the confounder as part of the predictive 'value'. Adjustments for other covariates may or may not be appropriate depending on how the marker is anticipated to be used and whether you're interested in whether 'additional value' beyond traditional risk factors is desired. 
- outcome measure: OR are misleading (large OR is not very predictive independent of statistical significance). Instead, we want discrimination metrics (se/sp/ROC).

This graph shows ROC curves at various levels of OR - as you can see, very large OR do not generally discriminate well. 
![alt](https://photos.collectednotes.com/photos/5187/63e15757-e4d0-4b07-8343-3253b683fb60)

From: DOI: 10.1093/aje/kwh101

With prediction: 

- we want to know discrimination between the two groups, with control for all that was otherwise previously known (thus, controlling on those covariates).

[ ] ask question about net reclassification index. 


Discrimination: 

- measured by sensitivity and specificity at various cutoffs -> summarized by the ROC curve (and the area under the receiver operator characteristic curve, aka C-statistics)


Net reclassification index? 


## Screening

Screening: test performed in the absence of symptoms or signs of disease

Diagnostic test: performed in the presence of signs of symptoms intended to diagnosis the disease.

Expected value analysis: 

False positive: unnecesary costs, risks for testing and in some percentage, incorrect diagnosis; inconvenience, anxiety -> Cfp
False negative: delay in diagnosis, false sense of security -> Cfn
True positive: to what extent does this allow intervention that is ultimately beneficial? -> Ctp
True negatives: inconvenience, anxiety while awaiting results, complacency, risk factor modificaiton? -> Ctn

The entire costs of the screening program thus be summarized as: 

C_total = C_test + (C_TP * prev * se) + (C_FP * [1-prev]*[1-spec]) + (C_FN * prev * [1-sens]) + (C_TN * [1-prev] * spec)

Using this framework, it can be summarized that the optimal point on a ROC curve to choose your threshold corresponds to 

[ (1-prev) / prev ] * [ (C_fp - C_tn) / (C_fn - C_tp) ] = slope of tangent line in the location of the optimal cutoff.

In words: prevalence effects frequency of FP and FN - high prevalence = more false negatives, low prevalence = more false positives. So: all else equal high prevalence implies optimal cutoff toward upper right of ROC curve (sensitivity prioritized over specificity). Low prevalence favors an optimal cutoff toward lower left of ROC curve (specificity prioritized over sensitivity)

The relative costliness of FP vs FN. C_fp - C_tn = relative cost of a false positive. So, if false positives (numerator) are costly, slope is steep and lower left (specificity > sensitivity) is favored. If false negatives are relatively costly, slope is flat and upper right (sensitivity > specificity) is favored.

Criteria for screening to be potentially beneficial (WHO): 

1. Condition is an important health problem
2. There is an accepted treatment if disease is found that alters course
3. Facilities for diagnosis and treatment are available
4. There is a recognized latent or early symptomatic stage
5. There is a suitable test for examination
6. The test is acceptable in the target population
7. The natural history of the condition, including development from latent to declared disease, should be adequately understood
8. There should be an agreed policy about which patients will be treated
9. The cost of case-findings should be econimically balanced in relation to possible expenditure on medical care as a whole
10. Case-finding should be continued and not "once and for all".

and (added by others)

11. Has known effective treatment that is more effective when given at the presymptomatic than symptomatic stage
12. Has a high prevalence in the population to be screened.
13. Effectiveness of the program should be demonstrated (e.g. RCT)
14. Should allow for informed consent
15. Overall benefits should outweigh harms.


Assumption is disease progresses as such: 

Health -> biologic onset -> asymptomatic but detectable screening -> symptom onset -> diagnosis -> disability -> death. 

Depending on how long the asymptomatic but detectable screening period lasts and the benefit of intervention in that period, it may be challenging to demonstrate improved outcomes. 


### Methods of studying screening

Same methods of association/discrimination apply to screening as diagnostic testing (se, sp, predictive value, etc.), but a higher discrimination is needed because the pre-test probability is noted. 

Possible outcomes: compliance rates, disease prevalence at initial screening, rate of interval disease, stage distribution of screen detected disease, rate of disease, disease death rate.

Problems in evaluating effectiveness: volunteer bias (different population participates in science than in real life), lead time bias (survival estimates confounded by earlier diagnosis) , length-biased sampling (identify slow growing disease preferentially)



