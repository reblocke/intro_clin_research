# Epistemology of Clinical Investigation and EBM

## Logic

Fundamental error in basing clinical practice on experience: Post hoc propter hoc: after this, therefore because of this. E.g. Contrast associated nephropathy

Induction: inference of a generalized conclusion from particular instances

- often used to conceptualized how theories are formed
- however, replication carries no implication of validity (Hume)

Deduction: inference in which conclusions about particulars follows from general or universal premises

- conceptualized as the 'hypothesis testing' - theories survive until proven false, and then are replaced by new theories.
- however, you can still make errors if your tests of whether the conclusions you deduce are biased, insufficiently powerful, or unlucky.

There is no proof in science

There are for possible reasons for an association: 

1. True causation (or association)
2. observation bias or information bias (systematic error distorting the exposure-outcome relationship)
3. confounding
4. chance

By the disjunctive syllogism (make a list of all possibilities, then disprove all but the one that is correct; a rule of inference. Aka modus Toledo tollens), we try to exclude the others and thus leave only true causation/association. This is the logical construct underlying the scientific paper. 

### Sociologic phenomena that influence likelihood the logic holds

Based on https://fantasticanachronism.com/2021/11/18/how-i-made-10k-predicting-which-papers-will-replicate/

1. Plausibility of the underlying hypothesis - If you view the statistical analysis as a test with a sensitivity of 0.80 and a specificity of 0.95 then it is very clear that the 'prevalence' of true findings in the field will drastically effect the positive predictive value.  Supporting research, plausibility of hypotheses. 

Why most published research findings are false: https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.0020124
Goodman/Greenland Response: https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.0040168
Ioannidis response - https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.0040215

2. Post-hoc changes that may influence the family-wise error rate: lack of pre-registration, researcher degrees of freedman in choosing the analysis (rigidity of field norms, etc.), negative controls/sensitivity, etc. 

3. Outcome measures: high variability metrics, tests for interactions (less power), especially when combined with 2. 

### Paradigms in Science
Paradigm - model/system of ideas that frames both problems and solutions in a particular area for a particular time. 

- Prepositivist Era: Up until Hume - took the stance of a passive observer - learning by observing. No testing
- Positivist Era: Galileo; Kepler; Descarte etc. testing ideas to see if they fit observations, belief in ability of science to find universal expectations. 
- Postpositivist era - naturalist paradigm, limits of science based on limits to generlizability and the nature of reality. 

Paradigm change = scientific revolutions.

### Medical Cosmology

doi:10.1093/ije/dyp180


Sets of axioms, assumptions which guide interests, perceptions, and cognitive processes. First principles -> problem orientation, explanatory strategy, methodology, and acceptable results. Provides an overall definition of the field and it's form.  Not static

Bedside medicine - phenomenological nosology (grouping together experientially related symptoms - diseases defined by their symptoms/presentation) and speculative pathology introduced (making inferences about the causes of disease. Search for single "cures for disease in man". The person was the unit of cause - thus physical, emotional, and spiritual life all felt relevant to development of a disease.).

Hospital medicine (started 1800s) -  sick locus resolved to the level of events (pathology) in organs - diseases come to be defined by disordered organs (structural nosology, localized pathology) rather than symptoms. Thus, physical exam to localize becomes important. Led to the development of histology and physiology as fields of study. This also enabled study outside of personal patient-clinician relationships, and thus led to establishment of journals and professional researchers 

Laboratory medicine (started 1850s) - methods of natural science applied to problem solving in medicine. Cells become the basis of physiology and pathology. Initially dispatched of old therapies, but slow process to build knowledge toward new ones. Diseased defined in terms of physiologic dysfunction, meterialist interpretation of biologic phenomena. Since these events are not perceptible directly by clinicians or patients, science separates out from clinical practice. 

Major consequence shifting from "sick-person" (something about the person as a whole makes them sick- maybe spiritual or social or material things) to "person who is sick" (something has gone awry in the cells/systems of the person). Basically, physics-chemical laws triumphed over personal experience as a cause of disease. 

### Education

Interestingly, there are two types of answers for "why do we do what we do" in medicine: 

1. Physiologic: e.g. we prone patients to decrease ventilator pressures and improve oxygenation
2. Clinical epidemiological / empiric: e.g. we prone patients because it leads to a decrease in mortality

(Explored here https://www.acpjournals.org/doi/10.7326/ACPJC-2004-140-1-A11 ) 

We are taught to understand and think of interventions in terms of the first type of explanation. However, the first type of explanation is a poor surrogate of the second for many reasons (our explanations are limited simplifications/models of true physiology, our understanding of outcomes is limited, many interventions have understandable 1st order effects but unpredictable second order ones.). Thus, we do things either because we know of an empiric benefit or we hypothesize there is one. 

Due to the scientific history (laboratory medicine above) - the physiologic model is given prominence in medical decision-making that it should not based on its track record (examples, CAST trial, hormone replacement in women). 

With widespread EMRs and outcome tracking, clinical epidemiology should be the next medical cosmology for clinical decision-making. Physiologic understanding (laboratory medicine cosmology) should remain the standard for proposing scientific inquiry. 

## Biases

Any systematic error that results in an incorrect estimate between an exposure and disease. Of note, sample size reduces chance (random error), but has no impact on the likelihood of systematic errors (biases). 

1.  Selection bias: errors from who is in the study - either selection into the study (case-control, cohorts) or dropout/follow-up pressures (RCTS, case-control, and cohorts)

Selection into study: (particularly problematic for case-control)

- surveillance bias
- diagnostic bias
- referral bias
- refusal bias

Follow up/Drop-out bias: (of particular concern for cohort and RCTs)

2. Information bias: errors in the information about the subjects - the data items are biased by how they are collected and categorized. 

3. Bias due to uncontrolled confounding - when a confounding factor distorts the exposure, outcome relationship.

1 and 2 are results of how the study is designed (and are more difficult to quantitatively evaluate); 3 is due to something that exists in the real world (external to the study)

### Confounding

1. Confounding exposure (B) is causally, independently associated with exposure of interest (A)

2. Confounding exposure (B) is causally, independently associated with the outcome (X)

3. Confounding exposure is not part of the causal pathway to from A to B: (meaning, B is entirely caused by A, and A has no effect on X without B, then B is not a confounder). Note, this requires knowledge about the subject matter, not statistical analyses, to determine.

Causes of a B to X association?

- This can occur if B causes X (confounding)
- B is an effect of X (not confounding)
- chance (not confounding)
- B influences detection of the disease (introduces a selection bias) 

Note: confounding can cause both types of errors: studies that don't find an association when there is one OR finding an association when there is in fact no association.

Confounding can often be explained by "it's going to look like.." Sentences. E.g. because mothers who are older often have higher parity, it's going to look like parity is associated with Down syndrome even though there is not true causal association

Can bias the result in either direction depending on whether the factor is protective or deleterious, and what the distribution of the confounding variables are in the two groups. 

Note: the issue with confounding is bias, not statistical significance. So: 

1. Larger sample sizes won't fix it. 
2. Each strata doesn't necessarily need to have a statistically significant result - the goal is to demonstrate the trend to support or not support the hypothesis that it is present. 

Dealing with this: see "Confounding and its Control"


### Selection Bias

Selection INTO study - bias can occur whenever selection of participants is related somehow to both the exposure and outcome of interest. 

For cohorts, over-selecting on exposure status is fine, as long as the selection process does not over-represent patients with an outcome (RR will be unchanged). In a 2x2 table, this corresponds to a proportional decrease in the values of a row (which cancel in the RR formula)

For case-control, over-selecting on the disease status is fine as long as the exposure status is not over-represented, because the calculation of the OR will not be effected. In a 2x2 table, this corresponds to a proportional decrease in a column (which cancel in the OR formula).  

The problem comes when both are related to the selection and disease status. e.g. if patients who are both exposed and have the disease (or any individual box) are over-represented, both the RR or the OR calculation will be biased. This corresponds to a proportional decrease (or increase) in a particular single cell of the 2x2 table.

This is particularly problematic for case-control studies and retrospective cohort studies, because the exposure-outcome has already occurred when individuals have been selected into the study. Prospective cohorts are less prone to this as the outcome hasn't occurred (so shouldn't bias inclusion into the study, though follow-up can still be related). Often times selection bias is easier to spot in RCTs, because the point of randomization offers a clear account of who should be included (where this is often lacking in a cohort study)

Follow-up / Differential surveillance / drop-out bias: differential retention of diseased/non-diseased patients or exposed/non-exposed patients. 

Unlike confounding, selection bias cannot be controlled by data analysis (because no data is available on the patients not included in the analysis). 

#### Mitigating Selection bias

Design: Describe in writing the study design, the theoretical cohort, the eligibility criteria and exclusions, and the strategy for sampling from a defined eligble population

For prospective cohorts requiring active follow-up, select patients with whom you have a way to keep in touch (e.g. nurses, AARP). Minimize the burden on study participants, offer incentives (rationale - increases validity of the study; just use cash), be politely persistent. 

For Retrospective / Administrative data - consider selection into the database and drop out from the database. For example: if patients with more frequent provider visit is more likely of initially meeting some criteria for inclusion, not being counted as lost to follow-up, and (particularly for case-control) more opportunity for the tests leading to diagnosis to be run and thus being diagnosed as a case.

Person-time denominator is better than a Person denominator for measures of effect (e.g. calculate HR > RR). This decreases the amount of bias that occurs from loss to follow-up

Describing participants and non-participants as best as you can in cohort studies. Note: one advantage of randomization is that you know who the non-participants were. 

Analysis: perform a sensitivity analysis on the missing patients.

Consider competing risks: expose-vs-unexposed status is influenced by some other event. E.g. for OSA to Stroke relationship, death by MVA is a competing risk. Often the relationship is described by "what is the assoc of OSA to stroke continual on being alive and observation"

#### vs Non-representative sample and Confounding by indication

Theseare different than selection bias. 

- Non-representative sample: may affect generalizability to the true population of interest, but the findings are internally valid for the sample studied.
- Selection bias: selection of subjects for analysis effects internal validity by biasing the estimate of effect in the population studied. For the people who don't ultimately get analyzed (selected) we don't know their exposure and outcome status - so we cannot easily adjust for this. 
- Confounding by indication = bias from which treatment is assigned for each patient. This will also affect internal validity, though can be controlled if you measure the factors that led to different treatment analysis. (Patients are in the study either way) 

Note: Non-representative sample is different than selection bias because the study results are valid in the population studied; the issue comes with generalizability to a different cohort. 

### Information bias

What is the data you have on the patients included in the study?  Can be biased if there is either measurement or misclassification. Selection bias is related to who is included in the study, information bias pertains to errors in information about the patient (either exposure status, treatment status, outcome status, or potential confounder status). 

Information bias (e.g. measurement error or missclassification error) is inevitable - operative question is whether our ability to do accurate causal inference on the exposure-outcome relationship is impaired by the error. 

The influence of information bias depends on study design: 

- RCT: generally no measurement error in exposure determination (assigned), direct outcome measures (generally reliable)
- Cohort: exposure assessment is variable but often non differential (esp if prospective). Outcome variable (missing information possible)
- Case-control: retrospective, and thus highest concern for differential misclassification/measurement. 

Note: beyond exposures and outcomes, confounders and effect modifiers are also subject to measurement error which can influence conclusions. 

#### Measurement Error

Any piece of data = subject to measurement error. Nature of this error depends on the data source (e.g. surveys, medical records, Billing records/ICD codes, study visits, etc.). 

Additionally, factors about the underlying thing being measured might matter - e.g. high variability measures like blood pressure may be incompletely representative of long-term blood pressure exposure. 

Lastly, limited se/sp of measurements introduce error. 

Measurements vary in reliability (little variation, high precision - gives same result when repeated) and validity (accuracy, average is around the true estimate - does it agree with gold standard)  

##### Reliability measures

- categorical: kappa. Again, can't use percent agreement (aka concordance) because will look good by chance if characteristic is common or rare based on chance alone. Kappa compares the agreement beyond chance, with the maximal possible agreement beyond chance. K = (Po - Pe) / (1 - Pe), Po = observed agreement (A+D/n), Pe = expected agreement by chance alone [(A+B)x(A+C)/n + (C+D)x(C+B)/n]/n. Chance = 0, complete agreement = 1.
- continuous: intraclass correlation coefficient (roughly, the fraction of the total variance that is due to within person - ie. Repeat measurement - vs how much is inter-person. Intuitively, high ICC would mean most of the variation comes from between people and not from repeated measures). Numerically: ICC = variance between people / total variance. .
- ordered categorical: weighted kappa

Note: reliability is also sometimes called reproducibility or consistency, and can be assessed at several levels (e.g. inter-observer, intra-observer). Test-retest reliability refers to how often someone will get the same result when re-tested.

Non-contextual Kappa categorizations: >0.80 is almost perfect, 0.61-0.8 is substantial, 0.41-0.60 is moderate, 0.21-0.4 is fair, 0-0.2 is slight, <0.00 poor. 

##### Validity measures

- Binary: sensitivity and specificity. (Why not percent agreement? Can look good by chance if characteristic is either common or rare). Note: se and sp collectively termed operating characteristics (of a test). Se = Pr (T+ | C+). Sp = Pr (T- | C-). Theoretically, these metrics are independent of prevalence (due to Se only referring to patients who have the characteristic, and specificity only referring to patients who do not)- but the spectrum of disease and the rest of the biochemical mileu have an impact.
- Cutoff of continuous variable: ROC plot - calculates se vs 1-sp at various cutoffs. Area under the curve (AUC, or C -statistic) often used to summarize the ROC curve. Perfect = AUC 1, Uninformative = AUC 0.5.
- Continuous: Pearson (Product-moment) Correlation Coefficient - comparing to goal standard; aka validity coefficient. However, there are problems with the correlation coefficient (https://academic.oup.com/ckj/article/14/11/2332/6262634) - better alternative may be Bland-Altman limits of agreement.
- Ordered categorical: Spearman rank correlation coefficient

Other less common metrics for binary measures: 

- Accuracy: proportion of all test results that agree with the gold standard = weighted average of sensitivity and specificity with weights of prevalence and 1-prevalence, respectively = (a + d) / (a + b + c + d). 
- Youden's index: sensitivity + specificity - 1. (How far the metric is from the 'rule of 100')

##### Differential vs Non-differential classification error

If the measurement leads to over-estimation in 1 cell of diseased vs not / exposed vs not 2x2 diagram (confusion matrix), we will have introduced a bias into our estimate. This is called a differential measurement error.  (If the error leads to balanced changes in the estimate between cells, non-differential)

Non-differential misclassification/measurement error: misclassification of exposure status that is unrelated to disease status OR misclassification of disease status that is unrelated to exposure status => biases estimate toward the null ( Null for difference = 0, Null for ratios = 1). *Usually, if specificity is 100% then there is no decrease in OR in cases where exposure is uncommon. If the exposure is common, sensitivity is more important.

Differential misclassification/measurement error: misclassification of disease status is related to exposure status OR misclassification of exposure status is related to disease status.=> can bias the estimate in either direction (can't predict without assumptions)

However, non-differential classification error of a confounder can lead to bias either toward or away from the null, depending on the confounders relationship to the exposure and outcome. 

#### Misclassification bias

Misclassification refers to errors in measurement in a categorical variable. 

Misclassification of confounders (similar to exposure or outcomes) can also lead to bias, with the direction of possible biases depending on whether it is differential to exposure or outcome (and in what direction of each).

#### Other Examples: 

These lead to measurement of misclassification in various ways: 

- Recall bias: if ultimately developing the condition causes you to remember possible exposures differently.
- Interviewer bias: disease status leads to different questioning of exposure history. 

### Approaches to minimize Information biases

Attempt to get high quality data! (there will always be at least some non-differential misclassification that must be dealt with, want to especially design with respect to avoiding non-differential misclassification.)

- Choice of the study population to encourage participation and complete data collection. And (ideally) at high risk for the outcome to minimize the duration of the study.
- Protocolized collection of data - e.g with a form or instrument, explicit protocol and training,  and blinded to group assignment wherever possible. 
- Consider the data source and use multiple when possible- pre-existing records are best (before outcome), though EHR's are likely to be missing predictable types of information (e.g. lifestyle factors)

Sensitivity analyses to explore the possibility of information bias influencing the results of the study

#### Quantification of the effect of information biases

If non-differential: 

Proportion exposed_measured = sensitivity x (1 - proportion exposed_actual) + (1- specificity)*(1- proportion exposed_actual)	=> can use this to calculated the expected impacts of non-differential misclassification at various Se / Sp / Exposure frequency / True OR.

If differential: 

The disease and non-diseased (outcome) group each have their own se/sp 

When should you actually try to quantify this? 

- comparing results across studies


## Study designs

### Randomized Trials

Fundamentally, randomization functions as an instance of a random sampling of the included population. Thus, statistical concepts related to random sampling can be applied toward comparing the two groups. 

see Clinical trials page

### Observational studies

Descriptive studies: case reports, case series - not testing cause-effect hypotheses.

Analytic studies - testing hypotheses, can be randomized or non-randomized

Experimental? Investigator assigns group. Not observational study.

see observational study designs page

###Counterfactuals

Causal Hypotheses are generally what we're interested in; in an experimental study, you'd adjust exposed vs unexposed while keeping all other conditions constant. 

This is impossible (we can only observe a person under 1 exposure status); but hypothetically if we could both expose someone and then run-it over again - then we'd be able to see the difference. This is the idea of a counterfactual. 

###Biases in observational studies

The classic reason for RCTs is to eliminate (or balance) unmeasured confounders between groups such that they are equal in baseline risk of the outcome of interest. However, a second reason for RCT superiority is in homogenizing certain elements of how the outcomes are counted and analyzed (other biases): 

Immortal Time Bias (aka survivor treatment bias): bias that occurs when a patient's opportunity to receive an intervention depends on their continued survival. 
Checklist at DOI: 10.1164/rccm.202008-3238CP

- cohort entry time is defined for all groups (e.g. at time of meeting sepsis criteria for both groups, as opposed to the time of receiving vitamin C vs time of sepsis) 
- intervention is delivered during a discrete eligibility period (this allows an estimate of the immortal time that has accrued)
- if intervention is given over a time period, report if patients receiving only part of the course are included (they generally should be, because otherwise patients who die/etc. are excluded)
- start of the period which outcomes and censoring events (follow-up period) are well defined for both groups
- if the study design allows for the possibility of immortal time, statistical methods should account for this. e.g. Mantel-Byar Method, or using a cox proportional hazard ratio using intervention as a time-varying factor

Time anchors: determine eligibility (when participant meets criteria to be included in the study), treatment assignment, and start of follow-up.  DOI: 10.1513/AnnalsATS.202009-1163VP

- treatment assignment should not occur after eligibility assessment or start of follow-up
- eligibility should not occur after treatment assignment or start of follow-up
- follow-up starting after a 'gap' from assignment or start of follow-up will often lead to exclusion of folks who had already 'failed' the treatment before then.

Part of the 'target trial' method is ensuring that these time anchors are consistent and reasonable (emulating how it would be done in an RCT, which by definition aligns all of these)

#### Bradford Hill 'Criteria'

Features of associations that make it more likely that the effect is causal. They are not criteria, per se. 

1. Strength of association
2. Consistency of Findings
3. Specificity of the findings (e.g. smoking associated with lung ca, but not other diseases)
4. Temporality (e.g. avoiding reverse causality; challenging for case-control and case series)
5. Biological gradient / e.g. dose-response
6. Plausibility
7. Coherence - across different methodologies
8. Experiment - can you prove some aspect of this
9. Analogy - similar to plausibility

The logical argument behind this: "When you have eliminated the impossible, whatever remains, however improbable, must be the truth" (Disjunctive Syllogism) Sir Arthur Conan Doyle. 

10. No alternative non-causal reason for the association 

#### Myths in causal inference

1. There are direct and indirect causes of diseases and direct causes are more important (def; if not for an exposure the disease would not occur. Thus, a.) labeling as 'direct' may reflect a lack of knowledge of true mechanisms and b.) location in the causal chain is irrelevant)
2. Causes either must be present in every case (necessary causes) or capable of producing the disease on it's own (sufficient causes). E.g. do guns kill people or do people kill people? Irrelevant, if the goal is to establish if evidence gun would that some homicides occurred because of the presence of a gun that otherwise would not. 

### Natural Experiments / Quasi Experimental Designs

see natural experiments page

## Clinical Practice Guidelines

Proposal for Bayesian methods in assessing evidence of clinical meaningful benefit: https://jamanetwork.com/journals/jamainternalmedicine/article-abstract/1108515

##Terminology

Negative control analyses - a method to provide evidence against spurious associations that might result from biases in study design where a factor known to not influence the outcome is investigated to see if an association exists. 

'Risk Factor' - traditionally has been used for causal factors AND predictors which aren't necessarily causal (e.g. reverse causation, counfounding, or the result of collider bias). The distinction is important if interventions to modify the risk factor are assumed to cause changes in outcome. Explained by Galit Shmueli [here](https://www.stat.berkeley.edu/~aldous/157/Papers/shmueli.pdf)

## Shared Decision Making

[Abbreviated Framework](https://link.springer.com/article/10.1007%2Fs11606-020-06043-2):

1. Produce individual estimate of net absolute benefit (Pre-Visit; Net ARR = (Risk noRx * RRR_rx) - HarmRx
2. Identify preference-sensitive zone (pre-visit)
3. Make rec w magnitute of net benefit and strength of evidence; if not ambiguous, just rec. If preference sensitive - rec then give key factors affecting the decision in less than 30 seconds and ask their thoughts. 

Key point: don't spend time on SDM when there is a clear dominant strategy. When decisions are preference sensitive, explain the considerations then elicit an opinion.

## EBM Theory

[Medical Reversal - The Atlantic](https://www.theatlantic.com/health/archive/2017/02/when-evidence-says-no-but-doctors-say-yes/517368/)

[COVID treatments in absence of evidence - NYTimes](https://www.nytimes.com/2020/08/05/magazine/covid-drug-wars-doctors.html?referringSource=articleShare)

[RCTs are not Enough - Senn](https://www.slideshare.net/StephenSenn1/real-world-modified)

[Why personalized EBM is hard- approaches to HTE](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6889830/)

[Pitfalls of personalized Medicine](https://www.nature.com/articles/d41586-018-07535-2)

[Reference class problem](https://jme.bmj.com/content/30/2/131)

Reasons RCTs are challenging in critical care: 

- time-sensitive eligibility windows
- perceived  ethical concerns relating to equipoise d