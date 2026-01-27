# Clinical trials

Fundamental logic: 

- randomized controlled trials estimate the average treatment effect for a population under study, not for an individual patient (this cannot be done due to the fundamental problem of causal inference). 
- however, RCTs can still guide clinical practice. Instead of hypothesis tests of causality (their initial intent), they are repurposed as tools of prediction through reference class forecasting (Kahneman and Tversky)

Def: prospective, contain a control group, evaluate an intervention

Prospective - in RCTs, have to be followed forward, though it is possible to collect information (e.g. covariates) after randomization

Main purpose of a trial is to test a hypotheses (Logic of significance testing ),not to estimate an effect size, which is not perfectly reliable due to choices of statistical model, non adherence, missing data, etc

Efficacy: the treatment effect in the laboratory or ideal setting
Effectiveness: the treatment effect in the real world (non-adherence, etc.)
Effectiveness < Efficacy effect size (patient selection; adherence; experience/environment)

Control arm: can be head-to-head; placebo (if ethical - note: the role of this is to PRESERVE BLINDING. Presence of a true 'placebo effect' is controversial - https://twitter.com/statsepi/status/1442207389483163649?s=20); none (if ethical)

Study question components: 

- study population
- the intervention
- primary question
- secondary questions
- subgroup questions
- safety questions

## History

From Chalmers 2001

- 1935: Fisher developed methodology in agriculture
- 1948: MRC (Medical Research Council) on streptomycin on Pulm Tb
- 1950s: increasing using, culminating in Salk polio vaccine trial (1.8 million)
- 1962: FDA requires efficacy evidence from RCT for drug approval. 
- 1970s-80s: DM, CV, Oncology trial groups start
- 1990s - Cochrane Collaboration, CONSORT diagram
- 2004 - trial preregistration required

## Types of trials

#### Phase 1
dose finding, healthy volunteers (if the medications is nontoxic) or patients who have failed conventional treatments (if the treatment is toxic, such as chemotherapy). Give dose to n=3. If tolerated, 3 more. Then increase the dose. Maximally tolerated dose = 33% show toxicity. Often, involves 10-30 patients.

####Phase 2
biological effect. Pre-post, historical control, or concurrent control (randomization is becoming more problem). Often, several intervention groups at various doses. Outcome= biomarkers . Narrower inclusions than phase 3. Often 20-400 patients. Often will include an interim analysis - such as Simon 2-stage design. Can do something like ‘r/o it works in less than 20% of patients’

####Pilot studies 
(eg to uncover problems that may be encountered in larger studies) 

Distinct from phase 2

- to assess feasibility of trial interventions, entry criteria, randomization, data collection, or other study procedures. 
- assess for quality control issues
- estimate the std. deviation of continuous outcomes
- estimate correlations within clusters over time

HOWEVER, you CANNOT estimate the effect size for power calculations OR declare that the intervention works if you get a positive result (because then it is basically just an underpowered phase 3 study). 

Mathemetically, if R is ratio of true effects to null effects tested by a research program, PPV of a study is: 

PPV = (Power * R ) / ([Power * R]+ alpha)

![alt](https://photos.collectednotes.com/photos/5187/dda65b64-fb6f-4a70-a324-16274e2c16c1)

####Phase 3/4 
Definitive trial with broader inclusion criteria and clinically important than points.

Phase 3 Therapeutic efficacy, confirmatory. Entry criteria less restrictive than Phase 1 and 2 (want as inclusive a population as possible). 

Phase 4 Therapeutic use / effectiveness - long term surveillance, ‘post-approval’

#### Group structure
Traditional design: 2 group parallel design. Simple, easy to arrive at enrolment criteria, but can only answer limited questions. 

- may use a run-in period: idea is to improve efficiency, but can cause problems with generalizability. 

Multi group parallel design: can include either 2 interventions (or doses of 1 intervention) or 2 placebo groups. In comparison to a factorial design (e.g. A vs B vs placebo in comparison to Factorial design of A vs placebo and B vs placebo) it requires 60% larger sample but avoided worry about interactions and you can do a direct A vs B comparison.

Factorial design: e.g. 2x2. Two studies for the price of 1. HOWEVER, you have to assume no interactions between the interventions or else you lose assumptions of randomziation. It generally takes more power to test this hypothesis than to test the primary hypothesis (usually roughly 4x the sample). More difficult logistically, and patients must meet entry criteria for both interventions. 

#### Pragmatic vs Explanatory
Pragmatic trial: larger trial with broader inclusion, less complete ascertainment in outcomes where the upshot is to try to use the additional power and generalizability offset losses from incomplete data. The assumption is that subgroups will generally have similar effects, losses will be non-informative. Must have easily administered intervention and easily ascertained outcomes to make sense.  The upshot is they can uncover modest effect benefits that are not findable in efficacy trials.

(As compared to an explanatory trial - which seeks to more rigorously test the hypothesis in ideal conditions (ideal patients, strictly enforced intervention and adherence monitoring). There is a whole spectrum between. 

Explanatory: to test theory, sharply defined groups maximizing difference between treatments, groups are select for chance of adherence and benefit, variable chosen to be most sensitive to effects predicted by the theory

Pragmatic: to show practical use in real-world settings, usual care, broad sample to represent target population, outcome chosen to be patient/policy important. 

#### Superior vs Noninferiority trial

Noninferiority trial: tests the hypothesis that an intervention is not worse than (by the margin of indifference, delta) the comparator. The comparator must have been shown to be superior to placebo in the population under consideration for the hypothesis to make sense. New treatment also must have some other feature (e.g. less toxicity, greater convenience, less cause) for the question to make sense. 

Deciding the margin of non-inferiority (Delta) is generally tough - often the minimally clinically important difference (MCID) can't be achieved with a realistic sample size; also there is an inherent tension between severe, rare adverse effects.  

Example of this tension: medications are successes if they are 20-25% better than placebo, but then anything within 40-50% effectiveness of the therapy would be non-inferior - which seems illogical. However, going from a 40%->20% non-inferiority margin would take a fourfold increase in sample size. 

![alt](https://photos.collectednotes.com/photos/5187/3789eeac-b155-4d4c-b230-c9ea63be9546)

Another challenge is that poor execution (e.g. high nonadherence) often favors non-inferiority. 

#### Cross-over designs

Cross-over trials - each patient receives each intervention for a period, with a gap between (washout). 

Advantage: increases the power (2-4 fold smaller sample needed because each patient is included twice, and you take out some patient-patient variability). Controls for period effects. Easier to enroll (all patients get the "new" treatment)

Disadvantages: carry-over effects take more power to test for than is usually available in the study - thus have to be taken to be absent based on assumption.  Cannot use for acute disease, cannot use for "time-to-event" outcomes such as mortality, can be more logistically complex. 

Simplest: 2-treatment, 2-period design. Though more can be added. 

#### N of 1 trials

RCT of single individual - as an example: the study timeframe is broken up in to 5 segments, and each patient is randomized to placebo vs treatment for each segment. 

Only doable if therapy under investigation produces effects quickly, and those effects stop when medication is stopped.

#### Withdrawal study

Randomize de-prescribing interventions. (note, one barrier to generalization is that people must have been benefiting before)

#### Delayed intervention 

When it is not practical to forego the experimental treatment altogether, or, conversely, if there are not enough resources to do everyone at once.

#### Cluster Randomized Trials

Randomization occurs at a unit larger than the individual (the cluster) - such as a medical unit or institution. 

Can have: 

- parallel cluster randomized (groups randomized to intervention vs not - stay that way)
- stepped wedge (all groups receive control initially, then sites cross over at different time points, order is randomized). 

###### Stepped Wedge

Advantages to this:

- can do even if there is no equipoise because everyone will get the intervention eventually.
- Can be done if resources limit the ability to do everywhere at once. 
- Can be more powerful than parallel (depending on inter-cluster correlation - how much do outcomes of subjects at the same cluster differ? Analogy: if both eyes treat the same -> no added information; if both eyes respond independently, then n=double.). 

Want to choose the order with a randomization algorithm that avoids severe imbalance in cluster size order (so that all the big cluster are at the beginning or end -> reduced statistical power). This could be done with other factors.

Contamination => if the intervention bleeds over into other groups that haven't yet been randomized to swap. Will bias the result to the null. To avoid this, often randomize at the level of the hospital (or group level between which contamination is unlikely to occur). Also, want to keep the time when a site is going to swap private (so that they behavior naturally)

Power: generally use a mixed linear model (random hospital effect / fixed, categorical time period effect). Can build in a transition period (e.g. 'incomplete'), though this decreases power ('fuzzier threshold'). Things that influence: 

- Design-pattern matrix (# of centers, number of transition periods, presence of a gap)
- Subjects per hospital
- Effect size (baseline rate and postulated post-intervention rate)
- Intra-cluster correlation (ICC, 0-1 where 1 is total concordance and 0 is total independence. Generally 1-10%. 0% makes it so that parallel cluster design is best )

Analysis gets done with a generalized linear mixed model (GLMM) / Logistic regression. With covariates: treatment-control, hospital, fixed effects (PICU vs CICU, 6 mo age or not, physiology derangement, time since trial start for temporal trend)

## Study population

Two components: 

1. What were the eligibility criteria? (Inclusion, exclusion. Needs to be precisely defined to avoid ambiguity)
2. A description of who was actually enrolled

Reasons: to allow replication, to assess generalizability. 

Population at large -> (exclude population w/o condition) + Population with condition -> (exclude patients with condition but ineligible) + Study population -> (exclude patients who were eligible but not enrolled) + Study Sample

Last step is summarized by a consort diagram / flow-chart. 

Determinants of generalizability / external validity: 

1. Trial setting
2. Selection of participants
3. Characteristics of randomized participants
4. Difference between the trial protocol and clinical practice
5. Outcomes measures and follow-up
6. Adverse effects of treatment

Note; internal validity refers to the validity of results for participants meeting entry criteria (ie. The study population). 

Criteria to develop selection criteria): Include people who have... 

1. Potential to benefit (based on knowledge of MOA; if more uncertainty about subgroup responses, better to choose a broader criteria. Homogeneity of the population increases likelihood of finding an effect, but may miss relevant subgroup effects)
2. High likelihood of showing benefit (maximizes the power with limited time/population, choose patients at high risk of the outcome- aka enriched population - to increase event rate)
3. Low risk for adverse effects - to favor risks vs benefit (e.g. exclude recent GIB from NSAID), though of course if patients develop these characteristics during the study they can't be excluded.
4. Little Competing risk - exclude patients who have a reason you wouldn't be able to ascertain the final outcome. (e.g. are going to die for a reason unrelated to the trial)
5. Avoid poor adherers - bias effect toward the null. Run in periods can increase (though will limit generalizability some). Similarly, people who are difficult to consent. 
6. Favorable Pharmacogenetics - can characterize participants. 

Restrictive vs unrestrictive enrollment criteria: 

Homogenous = well-defined, useful if the mechanism is known, generates less noise (smaller sample size needed, but recruitment harder) but generates more specific inference
Heterogenous = less well-defined criteria, works better if you don't know if patients will all respond similarly, easier to recruit subjects, and easier to generalize. 

Multicenter trials = should be representative of current practice (e.g. not all rural vs urban, academic vs not). NIH favors more diverse centers. Downside of this is more variability => translates to more statistical noise. 

#### Baseline assessment

Purpose: describe trial participants to help readers assess the target population / external validity, reassurance vs failure of randomization, to perform the basis of subgroup analyses

-- to ensure comparability of groups is listed, but - this seems perhaps problematic? Unless we think there was a problem with randomization, chance imbalances are captured in the uncertainty of the final estimate?

Important: characteristics from the population excluded are needed to assess external validity. This should be accompanied by the reason for exclusion (e.g. CONSORT diagram)

Problem: if likelihood of enrollment is related to degree if deviation of a characteristic from a population mean (whether explicitly through inclusion criteria, or implicitly through patient behavior e.g. decision to undergo a procedure at times when the symptoms are worst) - then subsequent measurements will, on average, return to the mean ("regression to the mean")

- this is most problematic in measures with high variability
- it will create the impression of a quick improvement that occurs in both the control and intervention group
- it is NOT the placebo effect.
- this may cause the power of the study to show an effect to decrease from what is expected (if the initial values are actually less deranged than they might appear, then there is less to improve upon)

Approaches to address this: use a more stringent cutoff to ensure adequate power; average several measurements over a period of time to determine a baseline.


#### Sample size

CONSORT suggests all RCTs should provide a rationale for their chosen sample size. 

How to estimate the effect size? (After all, this is the point of the trial)

Using an effect size that was seen in a prior study (or pilot study) is fraught - if that estimate were reliable, the study would not be needed. And, given that only follow-up studies with a promising effect are followed up on, we are likely differentially taking the over-estimates (and thus, under-estimating the power needed to evaluate a more realistic effect). Lastly, control groups often do better than general population (selection, attention, secular trends, Hawthorne effect being main reasons), making a difference harder to find (lower base rate). All these argue that conservative estimates should be used (as it is better to stop a trial early than to have insufficient power lead to inaccurate conclusions. However, this is harder to justify for funding). 

- consider this not as a prediction of what WILL happen, but as judgement about either 1.) what the smallest effect that would confirm or refute the theory in an explanatory trial or 2.) the smallest improvement in the outcome that would justify the treatments use for a pragmatic trial. 
- In some circumstances, the sample size isn't entirely under control. In this case, it is acceptable to re-arrange to solve for power, and to see if the power is high enough to justify doing the study. (How about keeping power the same and solving for delta?)

##### Power calculation

Determinants of power (1-type 2 error rate, aka how often you will correctly find an effect if one is there): 
- what effect would you find at that rate? (Every study is powered to ~90% for SOME effect)
- what is the type 1 error rate? (Alpha) Chance of incorrectly rejecting the null hypothesis

Step 1: decide on primary response variable (aka outcome): 

- Dichotomous: event rates Pi and Pc compared. Ho: Pc - Pi = 0
- Continuous: expected mean level in intervention and control groups compared (Mui and Muc)
- Time to failure: Hazard rate of the two groups used.
- Dichotomous or Continuous variables that are paired (removing intra-individual variability) can also be analyzed with higher power for the same sample size.

of note, the calculations are based on the 'true' event rate for the populations, which we never know (we only calculate the sample event rates)

Probability of type 1 Error (false positive) = Alpha
Probability of type 2 Error (false negative) = Beta = 1-Power. Depends on alpha. 

Memory trick: 
Type 1 error occurs when Ho is true and you make an error (a la specificity)
Type 2 error occurs when Ha is true and you make an error (a la sensitivity)

Determinants: 

- what is the minimum effect we want to find (delta - or the absolute difference in outcome between the groups... thus, depends on base rate and relative reduction)
- How much information does each piece of data provide? (Variability = sigma.. relates to standard error = sigma/sqrt(n). If variability = 0 then you only need 1 observation. As variability increases, each information piece decreases per datum)
- What is the acceptable risk of false positive? (Alpha, type 1 error rate)
- What is the acceptable risk of an inconclusive trial? (Beta, type 2 error rate)
- What is the budget? (Meaning, how much can you spend on mitigating each of these risks)
- and what the test statistic is (1 sided vs 2 sided, choice of statistic)

Delta: sometimes, Cohen's D effect size is a measure of small vs medium vs large effect sizes (basically, Z-score for the difference.. mean difference over the pooled standard deviation). Then, 0.2 = small effect, 0.4 = mod effect, and 0.6 = large effect

This can be modified to specify the width of confidence interval (in lieu of alpha)

Lakin adjustment for non-adherence: N* = N / (1-Ro -Ri)^2

N* = adjusted sample size
N = initial sample size
Ro = rate of intervention->control
Ri = rate of control->intervention
 
Note: separate approaches exist for multiple measures (usually involving some model, such as representing response as a function of time and trying to find a difference in slope of the responses); time-to-event measures. 

Non-inferiority power: it is NEVER possible to power a study to show that delta = 0 - thus instead some delta (margin) is chosen that is good enough to demonstrate non-(important)-inferiority. Statistically, this means that the 100(1-alpha)% CI does not include delta, with a probability of 1-beta. Then, power can be calculated as; 

2N = 4p(1-p)(Z_alpha + Z_beta)^2 / delta^2

P = event rates that are assumed if interventions are equivalent
Z_alpha, Z_beta: z-scores that correspond to the alpha, beta error
Delta = difference. 

Cluster randomization power: additionally requires estimate of between-cluster variance and within-cluster variance for continuous variables: summarized by the intraclass correlation coefficient ICC = between_var^2 / (between_var^2 + within_var^2).  Then, 

N* = Nm * m = N[1+ (m-1) * ICC]

where

N* = total n
Nm = n per group
M = number of groups

Thus, if ICC = 0 then N* = N (what it would be in a normal trial). If ICC is high, sample size must be much higher. If ICC = 1 (total correlation), then the unit of randomization is essentially m.

Kappa is the equivalent of ICC for binary responses. 

How should estimates for the parameters needed to calculate power / sample size be determined? external pilot = using smaller preliminary studies. Necessarily somewhat fraught due to small sample size. Generally, event rates and variability are overestimated (due to selection of hypotheses to test, optimism, etc.). Alternatively, an 'internal' pilot study can be undertaken with the goal of enrolling some small portion of the ultimate sample size, then using that info to calculate the needed sample size. Have to be careful not to use treatment efficacy estimates or else power drops / significance level needs to change. Lastly, can use a fully adaptive design. 


##### Interim Analyses

'Official' look at the accumulating data at some point before the scheduled end of the trial. At each look, there must be a possibility of stopping or modifying the trial (or else it wouldn't make sense to look) 

Rationale: 

- ethical requirement to only allow harms for the potential of actionable knowledge gained
- economic benefit (don't waste money doing a study that is mostly futile) 
- scientific (there may be an opportunity to improve the trial) 

Done by DSMB - must be independent of the trial. Usually exclude people who are affiliated with participating institutions. Should include a bio stats, bioethicist/lawyer. Odd number of members. 

Charter should pre-specify whether efficacy/protocol adherence/data quality, or only safety, will be reviewed. Also specifies how many analyses, what information will be reviewed, and proposed statistical monitoring. 

[ ] independent of statistical analysis plan proposed by the sponsor?

Possible analyses: 

- superiority (discussed below - issues center around preserving the family-wise error rate despite multiple comparisons. In general, more looks spends more power and thus requires larger sample) 

- futility: More important with longer latency outcomes. Can do this either pre-specified (e.g. using Obrien Flemming, described below), Conditional Power (explained here), or Bayesian methods. Deterministic curtailed sampling = the outcome already determined (or probabilistically, is very unlikely to change - which can be calculated by condition power.) involves conditional power based on what is already known AND an assumption about what the remaining data would look like (often the assumed delta for the original study). If the condition power drops below some threshold defined by the sponsor (<10%) may opt to discontinue. These correspond to 'beta spending' (=chance of false negative). Also increases required sample to some degree (depending on the degree of beta spending). Often will do conditional power calc for 0, currently observed, and original delta assumed effects. Requires unblinding of the DSMB (which is sometimes the default, sometimes not). Note: in general futility scenario is often not symmetric because it is not worth demonstrating definitive evidence of harm, if just evidence of non-benefit is sufficient for it to not be used. 

- safety concerns (generally not requiring a bar of statistical significance) / Adverse events. Some trials will have AE of special concern prespecified (e.g. SE of a drug that are known). MEDDRA is the standard way to do this (classify and report AEs), especially for drug trials.   

- data quality concerns that can't be remedied

- loss of equipoise due to other trial results. 

Arguments against starting early: 

- some centers will recruit feelier than others (say, faster IRB approval) - thus some of the benefit that comes from multicenter trials will be lost
- full sample size gives more information about other end-points beyond the primary (powered) one
- Early, large effects have not held up as well, practically. The effect estimate may not be useful. 

##### Early Termination (or extension)

Specifically with regards to efficacy, there are issues with multiple comparisons (introduced by interim analyses) and how to do 'alpha-spending'.  Harder to do with longer-latency outcomes.

Classical sequential methods: require paired participants. As the paired participants have outcome, the trial is either continued and stopped depending on whether an effectiveness or futility threshold is met - essentially re-analyzed after each pair (inefficient, thus not used).  Comparison's generally made using a log-rank statistic.

E.g. Z score approach: 
- if 1 look, Z score (which is normally distributed) 1.96 is threshold that corresponds to 2 sided p-value of <0.05
- if 5 looks, could do Z score 2.413 at each of 5 looks (p<0.016, roughly)  (Pocock's result) 

Group sequential methods: n = number of patients per group, K = number of looks, 2 groups -> 2nk = total sample size. After 2n patients enrolled, an analysis performed on them. The Z-score required to declare significance is more stringent, and determined in a way so that the overall type 1 error rate stays below 0.05. Ends up that the critical Z-score is about 2.2x more extreme at the first analysis then the last if there are 5 equally spaced looks. One popular method of calculating Z threshold is the Obrien Flemming method (which 'spends' alpha in proportion to how many patients have enrolled). Downsides: have to pre-specify the number of analyses and their needs to be an even number enrolled between each analysis. 

Peto approach - make Z score very extreme in the first several looks, and preserve almost the same alpha for the final comparison. Idea: only stop if something bizarre and unexpected happens, otherwise finish the trial. 


Flexible group sequential procedures (alpha spending functions e.g. Lan-Demets method): remedy those limitations with traditional Obrien-Flemming where your planned meetings might not correspond to the amount of information gathered at the time. Separates "date time" from "information fraction" = the proportion of all the information anticipated that is available. The alpha spending function determines how alpha is spent at a given information fraction. Thus, whenever an analysis is performed the appropriate alpha level is chosen (corresponding to the information fraction available)

Of note: if you calculate point estimates and confidence intervals of the treatment effects at the interim analyses, these may be misleading (meaning, not included the true value 95% of the time) - called the naive calculation; various formulas for adjusting exist, such as the "repeated confidence intervals" method

Sample size adjustments have traditionally been made based on the control group outcome rate (ie. To increase the sample size if event rate is lower than expected in order to preserve power). However, there are methods that allow adjustment based on event rate that do not inflate alpha (but you have to be careful that an investigator wouldn't reverse engineer the trend based on a sample size trend)

Other issues include how to handle primary vs secondary end-points, whether to allow composites to meet criteria or to require individual outcomes, and whether the need for longer term safety/outcome data are paramount. 

Costs in terms of sample size for each of these: 

- Pocock: 2 looks = 1.11x, 3 looks 1.16x, 5 looks 1.229
- Obrien Flemming: 2 looks = 1.008x, 3 looks = 1.017x, 5 looks = 1.028x. If the delta estimate is right on, with OF your actually most likely to stop the trial on the 4th look. 
- Pete: 2 looks 1.003x, 3 looks = 1.010x, 5 looks = 1.014x 

#### Second Generation P-values (SGPV)

A method of adaptive monitoring to ensure adequate sample size

A region of trivial effects surrounds the null (delta_T). How much does the confidence interval overlap with those trivial results? 

- If there is no overlap, then the SGPV is 0
- If the CI is entirely within the trivial range, then SGPV it is 1 (unlike standard hypothesis testing, you CAN accept the null that the effect is within the trivial range)
- If it's somewhat, but not entirely overlapping, then 0 < SGPV < 1

Similarly, if you define a range that is clearly clinically relevant, then you can set the trial such that you continue until:

- interval width stabilizes
- alert when either trivial effects have been ruled out, or relevant trivial effects are ruled out
- stop when the conclusions don't change with some number (n) of additional patients. ( to avoid chance aberrations )

This is analogous to bayesian monitoring with posterior probabilities

#### Subgroups

Note: subgroup definition should ONLY rely on baseline data (except in circumstances where the characteristic cannot be modified, such as age), or else bias is potentially introduced.

Is the treatment effect equally effective in subpopulations? 

e.g. Male/Female, Tumor type, duration of symptoms, meeting gold std definition e.g. cultures vs not, location of event e.g. in vs out of hospital arrest. 

Usual approach: =no strong suspicion, then enroll everyone and then assess the consistency across the subgroups, and then do an interaction test across the subgroups (not just the treatment effect in each group). These usually have very low statistical power 

The problem: 

Do a huge trial, that shows no effect. However, some subgroup seems to have an effect. This is cherry-picking, and you are likely to pick up noise. 

Said differently, chance findings in some subgroups are expected (multiple comparisons) and under-powered (assuming trial was powered for the primary variable). Thus "significant" subgroup effects do not usually represent true HTE. The combination of noisy data and no strong a priori theory makes false positives very likely.

(Vice-versa - dexamethasone no effect in patients not on oxygen)

If you have a strong suspicion for the subgroup responding differently (e.g. heterogeneity of treatment effect) - you have to power for the interaction test, which often takes 4 times larger trial than just looking for the overall effect. Thus, this is rarely done. 

Interaction test: first do an 'omnibus' test to see if adding striatum categories significantly improves the prediction of a statistical model in predicting response or not. Then, only if positive, proceed to examine treatment effects within the strata.

A different approach: enroll everyone, do an interim analysis, then do adaptive enrichment (enroll patients preferentialy into the groups that seem to be doing better). Can increase the power if there truly is a difference in treatment effect. 

OR

Just study the separate subgroups in different trials, or pick one. (Simultaneous trials can have some efficiency from sharing operations).


##### Heterogeneity in treatment effects
https://collectednotes.com/reblocke/heterogeneity-of-treatment-effect

## Intervention

Issues: 

- does it reflect clinical practice? Does the control group get std of care? 
- stability over time? 
- blinding? (Is it possible?)
- degree of burden to patients / centers
- need consensus between sites. 

Timing of trials: 
-often difficult to perform the trial once engrained in practice (equipoise, participation)
-also difficult to do a trial before information is known: need to know why it works, develop expertise in the intervention; intervention needs to be stable.

## Response Variables

-Binary: don't provide much statistical info so larger sample size. Easy to interpret
-Ordered categorical
-Continuous: gives more statistical info, except in the case of clustering at a few thresholds.
-Longitudinal: usually continuous, at several time points. Lots of info, but hard to compare
-Survival/Failure time: event indicator and time - gives more information than binary alone and can handle differing follow-up durations.

If the outcome of interest can be appropriately defined with a continuous variable, sample size can be reduced. 

Chosen to answer the primary question - "co-primary" outcomes can only be justified if the investigator cannot decide which variable best answers the question (though this should be rare). 

Pre-specified secondary endpoints do not entirely side-step the multiple comparison problem

Related, events can be combined (though if a person has multiple events, it should only be counted once) into a composite outcome. It is important that this composite share some mechanism or treatment if the result is to be interpretable.

In general, patients are censored once the primary response variable has occurred; though they are still tracked for important secondary variables (e.g. death). Patients are not censored after a secondary response variable event occurs because they are still at risk of the primary happening. 

Blinded assessment > impartial assessment (e.g. third party) > non-blinded assessment by the trialists in terms of risk of misclassification. More important the more subjective the end-point/response variable. 

Why end-point vs response variable? 

Reasons to change a primary end-point: slow recruitment, lower than expected event rate. Should generally be discouraged and always accompanied by a rationale. 


Intermediate outcomes: a marker on the proposed causal pathway between the treatment and the clinically important outcome. Usually a biomarker or physical sign/measurement. These allow for A.) testing the proposed mechanism of treatment effect, B.) in certain circumstances providing a "surrogate end-point". 

#### Surrogates

Barriers to trials: very expensive, and related to sample size. Sample size can be minimized by choice of end-point type (e.g. continuous) and the outcome itself. 

Surrogates: can be used to decrease trial size and duration; however will mislead if the surrogate is not causally/strongly related to outcome of interest, does not capture the full relevant action of the intervention, and can be assessed reliably and accurately.  The fundamental problem is that in order to ensure the surrogate predicts the end-point, a trial definitive enough to demonstrate the effect on the clinically-important end-point is needed.

Conversely, surrogates will also not be representative if they do not capture the full effect of the intervention on the clinically important outcome (ie. Then it is possible to make type 2 errors)

#### Composites

Another way to limit the size and cost - combine rare end-points. 

Avoids competing-risk problems (e.g. if you are dead, you can't have a heart attack), increases power, can get around difficulty classifying (e.g. was the death from HF or from MI?)

Makes it so that you can't separate them later. 

Mortality should always be included, and if a nonfatal event is included, all related events of greater severity should also be included (because you wouldn't want more severe events to look better). The most mild event should have justification including a treatment effect. 

## Safety 

-Rare events will have low power
-Short term vs long term -unlikely to be able to determine long term issues. (e.g. Vioxx)

Thus, safety information often requires other study designs to definitively know. 

DSMB - NIH appoints if funded through them; review all adverse events and interim monitoring (want the chance to stop early or futility)

## Why Randomize

Purpose: to establish if there is a causal relationship between an intervention and outcome.

Fundamentally, to provide a casual basis for inference. (See validity) 

- not: balance a baseline covariates (though this sometimes happens, not required for causal inference)
- not: estimate the treatment effect. Why? Issues around the coherence of the definition of 'treatment effect' and summarizing the results with 1 number

"randomization allows us to do is make probabilistic statements about the likely similarity of the two groups, with respect to the outcome." (https://statsepi.substack.com/p/out-of-balance) Note: this is different than saying the covariates will be equally distributed - if there IS a chance imbalance of 1 covariate, it does NOT change the distribution of likelihood for the outcome of interest.

"Usual rationale"  - not entirely accurate (these are side-effects of randomization, but don't actually result in the ability to use statistics for causal inference)

- Treatment groups are - as a group - generalized balanced with respect to both measured and unmeasured confounders.
- Allows for interpretable statistical testing, even in situations where the groups (by chance) are not balanced. Randomization distribution = the possible permutations of randomization / treatment assignments. On average, the treatment groups will be similar. But for any given randomization, there may be chance imbalances (=/= 'randomization did not work'; statistical tests are still valid because the randomization distribution is accounted for in the testing). Especially for small sample sizes (decrease follows an exponential decay - note, subgroups are basically small n samples). 

Consider: you do 3 hypothetical versions of the same randomized trial; 1 with no covariates measures, 1 with some, 1 with all that are relevant to risk of the outcome. You will generate THE SAME statistical confidence measures in your result regardless how many are measured. If more are measured, there will be more chance 'imbalances' in baseline covariates.

(Covariates balance may increase the efficiency of the inference - more similar / less variable groups (or equivalently, more of the outcome being due to the treatment under evaluation - leads to a smaller required trial)

##### Consider minimization: 

deterministic algorithm that minimizes difference between the aggregate risk factors in two groups. Ie. Give the next patient to whichever group will minimize group differences. What happens? 

- groups will be more balanced for covariates that we are balancing upon - however, you will NOT necessarily balance risk for the outcome  {unless the outcome is entirely dependent on the covariates of itnerest?}
- you will increase efficiency (though not as much as you would be incorporating the baseline information into the analysis stage, instead of allocation, so that the information can be used to increase power and not alpha)

What about the fundamental causal effect? Probably maintained - because there is some degree of randomization that occurs by order of presentation. (Thought of as similar to an instrumental variable)

Practically, this works better for small trails than large ones.

###Assumptions for randomizations to be valid: 

- everyone is adherent 
- information is available on all randomized patients. ( would still be valid, though less precise, if data were missing at random; however this can usually not be verified )

Note: that if there is a difference in rate of the outcome between patients who are missing and the rest of the trial, the type 1 error rate will increase as the sample size increases!

Trials powered for small reductions in risk (RR > 0.8), missing ness as low as 5% can dramatically increase type 1 error rate.

### Logistics

Can randomize at the level of the individual, or group (e.g. cluster, stepped wedge)
(See randomization using excel, 3-7 in Stoddard course)

Keeping the randomization sequence separate from the people enrolling patients is critical for maintaining the blind. Now, usually an internet-based approach (to reduce subversion)

Note: in general, randomization should be 1:1 (to maximize power), reflecting equipoise between the groups. Reasons to 2:1 or 3:2 randomize include gaining more information about toxicity/SE in the treatment (though you lose power), or less information is needed about the control group. Note: the loss of power is parabolic, so as long as the allocation is not severely imbalanced, the power reduction is not likely to be large

#### Strategies of Randomization to avoid chance imbalances

Note: that this is NOT to preserve validity, but instead to preserve power. Even if there are chance imbalances, validity is preserved. 

Chance imbalances lead to decreased statistical power, more difficult to interpret.

Reduce the chance of allocation and chronologic imbalances

- (Permuted) Block randomization - blocks of varying sizes = permuted. Guards against breaking the blind. Most straightforward, viable strategy.
- Biased coin randomization (move threshold so that probability goes to an under-allocated group; less reliable than permuted blocks, though more than coin flip)

##### Random permuted blocks

You mix up the order (randomly) of a block size number of patients at a time, with the total number of each group assignment balanced in each block. This is done to keep the balance in group sizes as the study progresses (in case there is a time varying effect, or the study stops early, or there is an interim analysis)

Friedman LM, Furberg CD, DeMets DL. Fundamentals of Clinical Trials, 3rd ed., New York, Springer, 1998, pp.64-66.

Example: if the block size is two, each set of two patients will be randomized to either AB or BA. If block size is four, it could be AABB, ABAB, ABBA, BBAA, BABA, BAAB

##### Random permuted blocks with random block size

Same as above, but this time the blocks are of random size. This keeps the study coordinator from realizing the block size an inferring a treatment assignment (because they wouldn't know the block size). 

#### Baseline adaptive randomization 

Reducing the chance of key baseline factor (covariate) imbalance

- Minimization - assign patients so as to minimize the imbalance among patients already assigned. Treatment assignment can be more predictable and you may not balance unmeasured confounders.
- Stratified randomization - randomize within each subgroup. the number of strata increases quickly with features, too many strata can increase the overall imbalance of the randomization. 
- Matched Randomization - refined stratification. 

#### Response Adaptive Randomization

Use information on participant response (requires this to occur quickly). Idea is that more people will receive better treatment (though some loss of power means that the study will need to be larger)

- Play the Winner
- Two armed bandit

### Reporting

CONSORT suggests that each report needs to include: 

- method of sequence generation (e.g. any restriction such as blocking/block size)
- allocation concealment
- implementation (who generated the sequence, who enrolled participants, who assigned participants to treatments)

### Alternative: Use natural experiments, observational data with confounding controls, etc. 

See page on confounding

## Validity 

A valid trial establishes, up to a predetermined level of statistical certainty, whether an experimental treatment is superior (or non-inferior) to a control treatment

Goal: you're left only with the statistical noise (non-systemic, random variation). All other sources of uncertainty are controlled.

Note: statistics (by itself) can't tell us about causation; it can only tell us about correlations. It is study design and/or assumptions about how we think the world works that supports inferences of causality.

- Descriptive statistics: no attempt to draw conclusions beyond the sample at hand. Example: correlational or predictive inference. 
- Statistical inference: goal is to gain knowledge about the universe/population from which the sample is drawn. Example: causal inference. "Are the two groups different?"
- Scientific inference: describing and drawing conclusions about how the world works. "Is the difference due to an effect of the treatment"

A valid trial aligns the statistical test (Reject Ho: Beta=0) and the scientific hypothesis (Ho: treatments are equally effective).

### Internal Validity

Aka Confidence in trial results; Internal validity = the ability of the estimate to accurately summarize the causal effect in the sample.

Causal framework: What would be the outcomes if a patient were to have received treatment A versus treatment B. Then, any difference in the outcome is ONLY due to the treatment (everything else is equal). Fundamental problem is that we can't observe both outcomes in any individual. 

Solution: Compare average treatment effect (ATE) between two comparable groups. (ATE = mean of treatment A - mean of treatment B). Inference will be valid if the two groups are balanced between influential factors impacting the likelihood of the study outcome.

Anything that makes group A and group B unequal with respect to risk of the outcome lowers internal validity.

Considerations for defining the control group to maximize internal validity: 

- Subject retention
- data quality 
- compliance w study intervention (e.g. run in phase requirement)

#### Terminology: 

Estimand: the true effect of an intervention, it is the quantity that the trial aspires to measure. Often, a difference in mean outcomes (e.g. ATE by some metric). Good estimates compare outcomes that capture the main benefits of risks and benefits in the target population. 

Estimate: trial data provides an estimate of the estimated (due to sampling, limitations in trial execution, and inability to directly measure counterfactuals)

Estimator: the formula or algorithm used to estimate the target quantity (e.g. the difference in sample means between 2 treatment groups, Kaplan Meier estimator of a survival curve). Good estimators should summarize the causal effects of treatments among the sample and be unbiased (e.g. Blinded RCT ITT analysis as gold standard)

In order to perform causal inference, you need an estimator and a measure of precision (hypothesis tests, confidence intervals, or posterior credible intervals are often used)

##### Adherence

We have no valid way to answer the question "if you take your medicine, will it work?" Without either assumptions or forcing people to take meds.

If we were omniscient, we could no if a patient would adhere to group A and whether they would adhere in group B. In that case, we would be able to differentiate the causal effect of 'assignment' and the causal effect of 'receipt'. 

e.g. If patient 1 is an A-adherer, B-non-adherer, then perhaps the a real effect of B would be mitigated if A is placebo. In that case, we'd have no actual way for us to know the effect in patient 1 if they had been an adherer. Conversely, if they were assigned to group A, there is no difference. 

Because there is no way to know what the effect would have been in a non-adherer (short of forcing them, which is not possible/not ethical), we are left only estimating the 'assignment' effect. 

Non-adherence = any participant who didn't follow the protocol. May be SE, not informed, crossover, life issues. Risk factors for this: 

- long studies
- intervention out of PI's control
- complicated/demanding regimens
- multiple interventions
- changing habit. 

Excluding subjects at risk for non-adherence can increase power but at the cost of generalizability.  The Run-in period is another strategy with the same risks/benefits.  Patient engagement helps (compensation, family participation, education, reminder cards). 

Monitor with pill counts (expensive/biased), electronic monitors, lab/level tests, diary.

##### Effect on power

IF the non adherence is random, then: 

If 25% of patients are not able to tolerate the drug, then up to 25% of the drug-arm will have the same outcome as the comparator group. This would take a hypothetical 10% effect to 7.5%. This means that power required to find a given effect size increases by the square of % non-adherence. (e.g 20% more adherence -> more than 50% more sample required)

However, when non-adherence is non-random. Some common reasons for non-random non-adherence are: 

1. Non-efficacy - they perceive no benefit, and thus drop out. May make difference appear smaller than it actually is (if there is an effect). If there is no effect, it won't matter. 

2. Side effect 

3. Poor prognosis 


#### Intention to treat

Preserves causal interpretation of the trial: however, the actual question being answered is what is the causal effect of assignment (not receipt) of the intervention. 

Excluding patients from the primary analysis based on adherence, outcome, or response can lead to bias in either direction that is hard to predict (Because the people in each of those groups may be different from the rest). Thus, 'on-treatment' analysis should always be secondary (e.g. Compliance Average Treatment Effect). 

ITT = study analyzed such that only the result of randomization effects treatment group. EVERYONE, who is randomized is analyzed (meaning, missing data is a threat to ITT). Not a method of analysis, but a principle. (e.g. as an analysis of the policy of telling the patient to take that treatment)

- substandard treatment compliance
- withdrawal 
- crossover
- enrollment of non-eligible patients. 
- randomization errors

If there is a lot of cross-over - sometimes it makes sense to do a transition analysis (ie. When patients cross-over is taken into account). 

Modified intention-to-treat is not a thing and should be viewed skeptically - either everyone who is randomized analyzed according to the group they were assigned to... or not. 

What to do with missing data? Can be useful to do sensitivity analysis (e.g. assume worst case, best case, imputed data)

High non-adherence and ITT will bias toward finding equivalence, which is problematic. However, an on-treatment analysis may be balanced in unknown directions. Thus, the best policy is to design a trial to have minimal nonadherence and use ITT.

Note: a typical but incorrect justification for ITT is that it shows the effect of a treatment strategy rather than the biologic effect of the treatment. (Not true as it also gives a more valid benefit estimate). Another incorrect justification is that it provides effectiveness information not efficacy information (incorrect because it also gives a more valid estimate of the efficacy). Is the direction of bias from a complete adherence estimate known? Not necessarily - there is no guarantee of the direction (though this can often be inferred by what the biologic response might be... you can imagine if the dose of the medication were over-shot, that partial adherence might be BETTER)

The real reason is that it is the only analytic approach that relies SOLELY on randomization to give a causal interpretation. All other analyses rely on assumptions in addition to randomization. 

Strict ITT: absolutely everyone who is randomized is analyzed. 

- If you find out later that they are ineligible? (e.g. female only study accidentally enrolls a male..) don't give them the treatment.. but you should probably still include them (on the off chance that eligibility assessment was somehow related to treatment group).  
- If they didn't receive treatment? modified ITT is supposed to refer to inclusion of all patients who received at least 1 dose of the study drug/placebo. Requires double blind/secure blinding such that you can ensure that missing data is unrelated to treatment. This is OK (essentially, considers randomization to be the process up to the first dose); but the term is often used to situations outside of this. 
- Randomization errors? (e.g. transcription error). If you keep the supposed assignment, then it's somewhat like an adherence error. However, if you're sure that the error is random (e.g. independent of treatment assignment - would have occurred equally likely in either group) then you can include them in the group they got (but requires the assumption)
- Bad batch of drugs? 2 options are: leave everyone in the analysis, OR throw out everyone who COULD have been randomized to the bad batch (as long as the blinding is secure). Then, you might need to enroll more to preserve power. 

(Note: it is often shady where investigators will not collect data on people who 'drop out' and then call it intention to treat on the data that they do have). 

#### Per protocol analysis

Only includes full adherers. However, this no longer preserves the causal relationship - there is missing data that is caused by us. You have to exclude some 'pairs' of outcomes, and then you have to make assumptions about what that data might have been. 

A better strategy is to try to get as much data as you can, even for these people.  (Withdrawal from treatment =/= withdrawal from data collection - which should be very rare)

In this case, you do not actually recover the 'if everyone was adherent' treatment effect, because the people that you exclude might be different than the ones you didn't (in fact, you likely would, because there is a reason they were not-adherent). 

Thus, IF there are reasons for non-adherence (side effects, lack of treatment effect, etc.) you will get unpredictably biased results. 

#### Other alternatives to ITT and related issues

How to address death in a patient reported outcome or some other symptom-based measure? Often, can rank death as the lowest / worst possible result. Another strategy is the impute what the outcome would have been based on other covariates. (See below)

ICH E9 R1 Addendum covers the idea of alternative estimands (alternative to ITT) - generally the reason not to use ITT is missing data/loss to follow-up vs study withdrawal vs intercurrent events leading to discontinuation or change in treatment strategy. 

Intercurrent event (ICE) - post-randomization event that change treatment regimen or effect ability to measure outcomes (and thus, interfere with ability to establish causal links). Example ICEs: 

- use of alternative treatment
- discontinuation of treatment
- treatment switching
- terminal events (e.g. death)
- loss to follow-up

Strategies to handle: if you create a composite that brings in some of these ICE measures as part of the outcome. 

Components of a given estimand (the quantity that the trial seeks to measure) that should be 

- treatment (definition is specific: when they take the drug, what alternatives they could switch to, etc.)
- population (explicit definition from inclusion/exclusion criteria)
- variable of interest
- intercurrent event handling - (see below)
- summary measure 

Examples for how to handle intercurrent events: 

- Treatment policy: intention to treat analysis - regardless of the intercurrent events, value of interest are what is observed at the end of study
- While on treatment: seeks to quantify the response to treatment prior to the occurrence of the intercurrent event
- Hypothetical: an approach where you attempt to infer what would have happened if there hd not been intercurrent events. Requires some sort of imputation method. 
- Composite: considers the occurrence of the intercurrent event as providing information about the treatment effect of interest - and thus it is considered in the endpoint definition. 

Idea: if you pre-specify all of these factors, then you preserve some of the ability to handle missing data and preserve/target the analysis toward your question whereas just 'intention to treat' might be not feasible. This approach attempts to avoid end-of-study conflicts where there is a disagreement with how the data ought to be analyzed. 

Once the estimand has been defined, then estimators (often a primary estimator, as well as sensitivity estimator(s) with alternative assumptions about missing data).

General workflow for creating a study design and analysis plan: 

- define objective (with stokeholds ie FDA)
- define estimand (identify ICEs, define treatment regimens, then create definition)
- plan assessments (what data is useful for estimand, how should patients be retained)
- plan the analysis (main estimator, sensitivity estimators based on alternative assumptions bout missing data)


#### contamination adjusted intention to treat 

An IV for the RCT: using instrumental variables to adjust for treatment contamination in randomised controlled trials - https://www.bmj.com/content/340/bmj.c2073.full.pdf+html

Use the likelihood of receiving treatment as a weight. ￼ gives an estimate of the effect that one would get if they received the treatment that is more accurate than intention to treat or per protocol – or at least the assumptions are more plausible￼￼

#### Biases

RCTs can still have issues with selection bias: particularly regarding loss to follow-up. "If you randomize, you analyze"

Selection into study: worse with fuzzy inclusion criteria, researcher chooses who to enroll, consent is required. 

#### Influence of Missing information

Subverts the randomization. Becomes problematic at even just 10-15% rate of missing ness (when trials are powered to detect small effects such as RRR > 0.8). 

If the likelihood of missing information is related to either: which treatment was received, or on likelihood of outcome. 

Treatment independent missing ness (no relation to treatment, but may be related to likelihood of outcome)

Missing completely at random =
Missing at random = no information in 
Missing not at random = introduces bias and subverts randomization; sample size cannot fix this (and in fact makes it worse, by giving false confidence - type 1 error rate actually increases as sample size increases)

##### How to deal with Missingness

Nothing can restore the causal interpretation  because the rely on assumptions that cannot be tested.  Missingness subverts randomization 

Complete case analysis - only include people who have all of the information. 
Imputation - filling in missing values based on some methodology that makes assumptions about what the outcome would have been if you observed it. Examples of how to go about this: 

- Last observation carried forward  (a type of single imputation)- only works if patients are missing at random. Otherwise, not necessarily conservative and does not give a bound on uncertainty - no causal basis. 
- Single imputation - e.g. replace by the mean observation. However, this amounts to a falsely increased sample size in comparison to the complete case analysis. 
- Multiple imputation - better than alternatives. Generate several simulations with random data missing. This still makes assumption that important information (with regard to outcome and missing ness) is present in the model
- Principle Stratification: identify groups of trial participants - ones that would go missing in either A or B, though who would complete only if A, only if B, or regardless which treatment. Then, analyze the ones that would only complete in both groups. This would restore causal inference IF you could do it (ie predict who would go missing). 
- Joint modeling outcome of missing indicator - use the outcome and an indicator variable (to represent missing vs not) then estimate the joint distribution to complete the analysis.
- Inverse probability weighting - model Likelihood of missing data based on baseline data, then weight the data as the inverse of there. Example: if a patient was very likely to go missing, but was in fact complete - that data gets more weight to account for the others that were gone. 

Can do sensitivity analyses to test what happens to the analysis under different assumptions of the difference (e.g. best case and worse case, does the conclusion flip? Or more practically, some intermediate Ratio of missingness-outcome association: Ra and Rb - at what level does the conclusion flip?). 

Note: per-protocol analysis (or other deviations from intention to treat) are INDUCED missing data. 

### External validity 

External validity = ability to establish causal effect of a treatment for the target population (ie. Who would receive the treatment in practice) based on the trial estimate.

Generalizability of trial results

The main threat to external validity to effect modification (degree to which treatment effects vary by characteristics).

1 strategy to assess for effect modification is to compare average treatment effects across many subgroups - if consistent, argues that effect modification is small. 

## Closeout, Reporting, and Uses for Data

Patient care transitions and closeout - unblind

### Reporting

CONSORT guidelines - http://www.consort-statement.org/

Particular issues: 

- state target sample size and how it was derived. Especially if it is different than the ultimate sample size.  ? "could have been unpowered"?
- specify how frequently interim analyses were performed and how decisions to stop accrual were made (if applicable)
- number of patients randomized absolutely must be reported. Relatedly, the withdrawals (treatment, follow-up, or both) and reasons (when possible) should be reported. 
- per protocol is probably better termed "as treated" to differentiate from "pre-specified in the protocol".  To be called intention to treat, everyone randomized has to be analyzed. (Ie. Missing data is a problem for ITT)
- often times, a secondary methods publication or supplement required to give adequate detail to reconstruct but still meet word limits. In this case, still need to give enough overview to let the causal reader know what's been done.

Mandatory figures: 

- CONSORT flow diagram
- if survival end-point, Kaplan Meier Kurves
- if subgroup analysis, Forest Plot of each group.

### Data Release

"Locking the database" = no further updates. Need to plan for data archiving

Data (including protocol, operation manuals, data forms, edited/final data plan, statistical analysis plan, DMC and steering committee minutes) should always be saved: 

- verifications
- secondary analysis - though note that these are often essentially cohort studies (since randomization isn't done with respect to the hypothesis.. that said, good data collection)
- public use data sets (PUDS) - NIH requires that the data be made public.  

### Clinical Trials dot gov

Pre-registration required for trials that will be used to support FDA approval

Studies by topic, studies by map 
