# Observational Study Designs

Aka Epidemiologic study designs (and descriptive ones)

## Case Control

Beware, there are 'case-control' designs to determine the validity of a test - this is somewhat different. Additionally, many 'case-control' designs are mislabeled in the literature.

### Advantages And Disadvantages

Group assignment based on outcome: has the advantage that you 

a.) don't have to be there back when all the exposures happened, shorter 
b.) you don't need to know the exposure status of everyone - just the cases and controls = more efficient, especially for rare outcomes. 

Advantages - particularly helpful for questions of etiology (not for incidence, prognosis)

- more efficient than cohort for rare diseases or outcomes
- can study multiple exposures as risk factors for a given disease
- quicker, easier, less expensive - especially important if there is a long latency to the outcome
- can investigate exposures that cannot easily be manipulated (e.g. genetic, work-related)

Disadvantage 

- key source of selection bias: how is the matched group created? This is difficult to without introducing selection bias (needs to be sampled randomly from the source cohort without knowledge of exposure status)
- you cannot calculate the incidence (because we are not looking at the full cohort). 
- less confidence that the exposure preceded the disease - reverse causation: how can one demonstrate that the association a study finds is not causally backward (e.g. changes leading to lung cancer make people more likely to smoke)
- Information bias - can be difficult to assess the exposure retrospectively; issues around recall biases

### Group assignment and control selection

Matched group (no disease, control) compared to a study group (disease, cases) with respect to their likelihood of having certain exposures (or characteristics). Note: control has a different meaning than in cohort/RCT. In case-control= non-disease; in cohort/RCT = non-exposed.

Think of a case-control study being nested within a cohort, the 'source cohort' = the population that gave rise to the cases, so that you can sample your controls from that same group. Standard approach to generating cases: a random sampling of patients from a source cohort selected WITHOUT knowledge of exposure risk.

Inclusion/Exclusion criteria redefine your source cohort: MUST be the same between cases and controls (or will result in selection bias)

Questions to ensure to ask yourself about this selection process: 

- would a case, if having not developed a disease, had a chance of being sampled as a control?
- would each control, if having developed the disease, had a chance of being captured as a case?

Example strategies: 

- Healthcare system: take patients from hospital/clinics/HMO EHR who don't have the disease
- Population: random sampling (e.g. drivers license or voter registration, random digit-dialing), family members, friends/neighbors (geographic), work

Occasionally, controls are taken to be those who were tested for disease and found not to have it ("test-negative controls"). This is OK if the disease is generally asymptomatic (ie would not be discovered w/o testing). Validity will decrease if these people would be diagnosed soon regardless of testing

Case : Control ratio? Usually 1-4 controls per case (maximizes efficiency, decide on exact ratio based on cost of data extraction and size of available cases) 


### Control selection and Matching

TODO: merge with above section

Goal: estimate the frequency of the exposure in patients without the disease

Must be: 

1. Selected from a population with the same distribution of exposure that the cases are drawn from (to mitigate selection bias)
2. Identical distribution of covariates that influence the likelihood/degree of exposure AND covariates that influence disease risk independent of the exposure (to mitigate confounding)
3. Exposure can be measured accurately and in a way that is the same as in the cases (to mitigate information bias)

Note: the matching done for control selection (as opposed to later, in the post-analysis) is generally performed to increase the study power (e.g. not wasting resources collecting info for patients who will later be less influential to the analysis). However, it is generally NOT sufficient to control for confounding (which additionally needs to be done in the analysis). 

Matching (On control cases, as opposed to in later analysis stages) should be done on covariates that: 

1. Are strongly related to both disease and exposure risk 
2. Information on the variable can be obtained easily (then why not? Increases the efficiency of the study)
3. Information on the exposure status is very difficult to obtain (thus making a lean, well-matched comparison group pays dividends in avoiding collecting exposure information on many patients that contribute less to the comparison)

#### Case selection

Generally, the goal is to enroll incident cases. Said another way: a case becomes a case at the time of occurrence of the event

- though logistically, sometimes prevalent cases must be used because a system to identify new cases as they develop is required to use incidence. Challenging to get a pinpoint time of onset.
- prevalence study - case selection is also influenced by factors that affect the duration of illness such as survival - over-representation of "survivors" or people who stay sick longer (for shorter episode-diseases)

To avoid non-representative selection, cases need to be drawn in an unselected manner related to exposure status, from all eligible cases. Similar for controls. 

For case criteria: specificity of the diagnostic criteria is particularly important because False Positives will rapidly decrease the power of the study. Need consistent and well defined criteria to get a homogenous case group (from an etiologic standpoint; or can create multiple case groups with varying certainty of diagnosis) 

Common ways this is done: 

- Hospital / Clinic based: from hospitals, outpatient clinics, or physician practices. Challenge w this: who is the source cohort? It is a challenge to know who to select controls from to be representative.  
- Population based: HMO records, disease registries/surveillance, Death certificates. Better ability to define source cohort
- Nested (from a prospective cohort study). Best ability to determine source cohort (since you have their information. 


#### Variations

Nested case-control: (See Essebag American Heart Journal 2003; https://pubmed.ncbi.nlm.nih.gov/14564310/)

- Risk set = all non-cases (therefore, at risk for being a case) at any given time. Whenever an event occurs, a few controls are sample (note, these controls COULD later become cases). 
- this means that exposure status needs to be assessed for cases and controls each time someone is included (e.g. weight needs to be assessed at the time of case-ctrl).
- this makes sense if there is loss to follow-up; or if exposure changes or is cumulative. Additionally, it is better than analyzing the entire cohort if it is expensive to determine exposure status (e.g. thawing a sample, requiring manual chart review)

Note: "nested" was initially coined only to refer to a pre-existing cohort, not to the incidence density sampling / risk set sampling - which can be done outside of a cohort if the records are good enough (e.g. Kaiser - where you can know if someone was eligible or not. You can't do that )


Case-cohort: 

- "control" membership is determined at the time of enrollment: by random sampling. This may include some cases. This is called the sub-cohort 
- survival/cox-proportional hazards can be used but requires some modification
- advantage = you can use the sub-cohort for several different outcomes / case-groups.

Matched Case-control studies: 

- to control for confounding by the matching characteristics at the time of when cases and controls are selected
- in a normal case-control, matching during analysis makes it very inefficient to find controls (ie. In an older stratum, you may have many cases and few controls while in a young stratum you may have many controls and few cases) and thus lead to a loss of statistical power. 
- Frequency matching (preferred, very common) - select controls to have the same distribution of the covariate of interest as the cases. This makes the data analysis easier 
- Individual matching - select EACH control to match the characteristics of each individual case = 'matched analysis'.


### Determining exposure status

Methods: 

interviews/questionaires

- An issue is what time frame to evaluate for the exposure in controls - often the time onset of the cases provides a reference: do you use a time referenced to the date of interview? Or some similar times elapsed as to the determination in the case group? 

Records

- Need to be careful to restrict information to info the preceded the case's diagnosis AND the presence of symptoms that led to ultimate diagnosis - as these are likely over-surveilled while the symptoms being worked up. 
- Similarly, the time periods of assessment must be truncated in the controls. 

Physical/Laboratory measurements

- less likely to be biased based on recall etc. 

### Threats to validity

#### Selection biases:
particularly problematic for case-control, because it occurs whenever selection for inclusion into the study analysis for disease status depends in some way on the exposure status. In general: cases and controls both must be sample from the same source population, with no change in likelihood of inclusion in the analysis that depends on the exposure. 

Example: if cases are drawn from a clinic, must be clear that the controls are selected from the entire (or representative) population of patients who would have received care in that clinic if they had developed the disease

A frequent example: if patients who have the outcome (cases) are more likely to be identified if they are exposed (occurs via a variety of mechanisms), then if the controls are truly representative the estimate will be biased. 

Another cause of selection bias: reason for non-participation in the case group (e.g. death, ill, hard to identify) is often different than reasons for non-participation (e.g. loss to follow-up, lack of interest) in the control group. Since we don't have data on the non-participants, it is hard to know for sure how much of a problem this is.

#### Information biases: 

Measurement Error

Recall bias: cases may recall exposure information differently from controls. Interviewer bias (if using interviewers, you want to blind interviewers to disease status).

Cases may have more information available in records than controls

#### Confounding

Note: matching done at the stage of control generation is usually not enough to control for confounding. 

Thus, cohorts (especially if prospective) are often thought of as stronger, in ability to support inferences


### Data analysis for case control studies

Can't calculate incidences - NO, because case to control ratio is selected by the investigators in deciding how many cases vs controls to study. 

Thus, we need to use the Odds Ratio as an approximation of Relative Risk because: 

OR = odds of exposure in cases / odds of exposure in controls =  (A/C) / (B/D) = (A/B) / (C/D) => mathematically, does not matter what the ratio is because denominators cancel  


Thus: OR is approx RR if the following conditions are met: 

1. Cases are representative (odds of Exposure is equivalent to all cases theoretically eligable for the study)
2. Controls are representative (odds of Exposure is equivalent to all cases theoretically eligable for the study
3. Disease is relatively uncommon in the population


## Cohort Study

Group assignment based on exposure (can be prospective or retrospective)

- the group must be able to be enumerated (in order to differentiate from a population)
- comparison can either be to a lesser degree of exposure, or a matched unexposed group (or, no comparison at all - depending what the study question is)

Note: the disease can be the exposure (e.g. of the people with disease X, we follow them over time to see how many get Y to calculate the incidence). Even if this is compared to a non-diseased group, the disease presence functions as the exposure (not the outcome) and thus it is a cohort study. 

Note2: there are some well known unselected cohorts from the community (e.g. Framingham, Nurses study, NHANES) which are not based on a particular exposure. Exposure statuses are determined after the cohort is defined. 

Analyses are similar to RCT, as the only structural difference between a prospective cohort and an RCT is the method of treatment assignment (and thus the need to control for confounding)

Advantages: the exposure is known to precede the disease, useful for rare exposures, incidence can be directly measured, can study multiple outcomes of the same study. Can be used in some situations where ethics or logistics preclude RCT

Disadvantages: inefficient for rare or delayed outcomes, prospective studies can be expensive and labor-intensive. May be susceptible to health volunteer biases the limit generalization. 

Prospective: more expensive and time-consuming, need to worry about the loss to follow-up. However, can ensure high-quality data. 

Retrospective: access larger number of subjects; missing data and poor quality data; difficult to know about all the patients who may not be included in the dataset. 

Note: there is some debate on the precise difference between a case series and a cohort that has only one group (which most people believe can still be called a cohort, if exposure or membership of a group is the defining characteristic). Often comes down to size.

### Defining the cohort

Requires identifying the: source population of interest, the specific definition, the method to identify the patients and how they are contacted. 

Sampling: does the population you enroll represent the source population of interest? 

- Who do you want to generalize to? (Theoretical population)
- What population can you access? (Source cohort)
- How do you identify and access them? (Sampling Frame)
- Who should be in your study? (Sampled Population)
- Who actually is in your study? (Study population)

Comparisons? 

- best = internal comparison group that is not exposed. However, not feasible if unexposed group is small or outcome of interest is rare.
- external = selection / information bias can be present if this group is different in ways that will effect frequency of events (observed differences can be adjusted for; unobserved cannot). Important to ensure that outcome events have been ascertained in a similar way between groups. Population estimates of the outcome rates can generally be much more precise (but biases in the comparison may hamper usefulness)

Note: it is very important than NO events after the determination of exposure status influence the decision of who is in each group (e.g. if comparing C-section, no info on the eventual time of birth should be used in selecting the comparison group)

### Tracking the cohort

- Return visits to a study clinic
- Periodic mailing or phone calls (also get a change of address notifications if you send birthday cards etc)
- Passive follow-up (e.g. assume alive unless in death index)

Information can be obtained by record linkage (e.g. surveillance databases/registries, medical records) or self-report.

Note: generally, information should be collected immediately after the exposure event, with the exception of a gap that is sometimes left in to ameliorate the health worker / healthy screenee bias, or if it is thought that the disease would likely precede the exposure to be present at the time of diagnosis.

### Statistical measures

Similar to RCT, can use relative risk or risk difference measures.Also, Person-Time / Time-to-failure analysis such as hazard rate ratio (e.g. Kaplan Meier). 

Unlike an RCT, the analysis much consider the reasons why a patient may be exposed vs not - eg. confounding.

In the Childhood Cancer Survivor Study discussed in the lectures, they report a relative risk ratio in the tables. Why is this not a hazard rate ratio? (Since there are varying numbers of patients observed at each time point and they call their analysis a Kaplan-Meier analysis?)

### Bias

Selection biases: Any bias introduced by who is included in the study analysis (either enrollment or analysis)

- occurs whenever selection for inclusion into the study analysis for exposure (or disease status in a case-control) depends in some way on the disease status (or exposure status for case-control)


## Cross-sectional study

Definition: Both exposure and outcome assess simultaneously (different than cohort). Subjects are identified by either exposure or convenience (like a cohort, but different than case-control)

Aka prevalence study - useful for estimating the prevalence of a disease, exposure, or other characteristic.  E.g. NHANES, BRFSS, NHIS

Advantages: 

- conducted relatively quickly or easily. 
- Prevalence itself may be of interest (e.g. descriptive epidemiology) 
- can be helpful for cause-effect relationships to exposure that don't change over time (e.g. genetics) or for which assessment of current exposure is better than recollection of prior exposure (e.g. hard to remember)

Disadvantages: 

- Validity depends on random sampling, which can be difficult to assess because characteristics of non-responders is not known. 
- Generally not used for cause-effect relationships (because we don't have information on the direction of causality, if there is any). 
- Subject to information (current exposure is taken as a surrogate for past exposure) and selection bias (e.g. genetics - if variants don't survive.. survivor bias. Cases with longer duration will be over-represented, if people who have both exposure+disease are more likely to leave the source population the association will be biased "healthy-worker" bias)
- Additionally, you don't know incidence - just prevalence (this is probably why incidence of many diseases are so much harder to find, and prevalence is so easier - despite incidence being more relevant to diagnoses.)

Note: "Cross-sectional" (sample) is also sometimes refer to a method of sampling - from a population without regard to exposure or outcome. This is different, can be ambiguous, and should be clarified.

### Measure Terminology

Aggregate measures: summarize the distribution of individual-level characteristics (e.g mean age, proportion of patients over 65). 

Intrinsically group-level measure aka integral measure - characterizes an entire group as a unit (e.g. size of a city, presence of absence of a particular law). 

Group level measures - whether aggregate or intrinsic - are often termed contextual variables.

### Data analysis

Can calculate a risk ratio (called the prevalence risk ratio) or an odds ratio (called the prevalence odds ratio). The 'prevalence' is used to distinguish from cohort or case-control-derived measures.

## Ecological

Definition: No random assignments; unit of observation (outcomes) is groups of people - no attempt to get individual level information. Similar to Cross-sectional studies, the exposure and measurement occur simultaneously. Subjects are identified by either exposure or convenience (like a cohort or cross-sectional study)

E.g. Per capita fat consumption by country with rates of breast cancer per 100,000 women. 

Example Exposures: population air sulfur dioxide level, amount of alcohol per capita, average educational level

Example Outcomes: hospitalizations due to asthma, infant mortality rates

Sometimes called correlational studies. 

Advantages: 

- efficient in a measure where exposure may be more variable between groups more than between people in a group (e.g. diet)
- if there is a high degree if measurement error or biologic variation at the individual level then an aggregate measure can help smooth this out. 
- if exposures are population level (policy, law) aka studying intrinsically group-level measures
- quick/easy/inexpensive, can generate hypotheses
- can be more powerful with time-trend data, though have to carefully craft arguments that don't have other explanations

Disadvantages: 

- Weakness involves the inference that the 1 chosen characteristic is responsible for the 1 outcome,  when in fact there are many differences between groups of patients / people (confounding by other exposures). 
- Additionally, ecological fallacy = hard to infer individual-level causation from the group-level association. (e.g. group level association may be present, but individual level is not. E.g. Nobel laureates per capita associated with chocolate consumption, but do the actual laureates eat more chocolate? Misclassification of individual exposures)
- Potential for differential misclassification of exposure and outcome (e.g. are the ways the data is collected different between the different areas.

### Ecological Fallacy

Association at the population does not imply individual-level association. A specific case of 'cross-level' bias - association at one level of aggregation does not imply association at another level. 

Happens when any of the following occur: 

1. Group itself meets necessary conditions to be a confounder (associated with both exposure and outcome). This can be if groups differ on distribution of risk factors, something intrinsic to group assignment is a risk factor, or the exposure has effects at the group level beyond its individual effect (e.g. herd immunity).
2. Unequal distribution of an effect modifier across groups
3. Model misspecification (e.g. non-linear relationship modeled with a linear model)

Cannot happen in ecologic studies that are evaluating intrinsically group-level measures

### Ecologic study uses

You can use these methods to study things that occur at the group level (e.g. it is a characteristic of the group, not the individual): Public policies, neighborhood social or physical characteristics (maybe socioeconomic characteristics), environmental contaminants. 

- can also use group-level measurements to supplement case-control or cohort studies (where information on exposure is obtained at the group level, but outcome and other covariates are obtained for individuals). This is called a multi-level epidemiological study

- these multi-level epidemiological studies can help explain why outcomes vary between groups: compositional effects (distribution of individual risk factors differing between groups), and contextual effects (group-level determinants of the outcome vary)

Natural experiments - a situation where a marked changed in the level of an exposure occurs at a given time and effects a large population -> then you can do an ecologic study with a time-axis to attempt to capture the effect of the change. 

- advantage: you sample the same population which reduces influence of confounding factors (less different, though other time trends matter), and reduces the likelihood of information bias due to different measurement of disease (unless that changed too)

### Calculations

At most basic level, correlation coefficients can be presented. However, relative risk and attributable risk are more useful outputs. This can be calculated in the following way: 

1. Apply a regression analysis to the group-level data modeling disease frequency as a function of exposure regression. This can be done with unweighted least squares (assumes linear relationship, requires each population contributes equally), weighted least squares (assumes linear relationship, weights appropriately but can be negative = uninterpretable), Poisson regression (assume linear relation  between log(event rate) and exposure), or Negative binomial regression (similar to poisson)
2. Use the model to predict the event rate in conditions where nobody is exposed (Ro) and everyone is exposed (R1).
3.  Relative risk = R1/Ro, Attributable risk is R1 - Ro