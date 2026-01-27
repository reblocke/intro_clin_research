# Systematic Reviews and Meta-analyses

Narrative review: not structured but on 1 topic

Subset: 
SR: identifies all relevant studies, synthesizes summary findings with a systematic process. (Specified objective, Search/inclusion methods, bias assessment - reproducible.)

Subset: 
MA: systematic quantitative review using statistical methods to combine results of several studies. 

Reasons for MA: 

- decreased bias
- increase statistical power
- explore differences / clinical heterogeneity (did the studies answer different questions) 
- perform subgroup analyses 

Useful when multiple studies on a subject that haven't been summarized. 

##Types of Evidence Synthesis 

Systematic Review: 

- narrative, qualitative
- quantitative (w MA)

Or: 

- scoping = answers what has been done to identify key concepts, gaps. Aka "evidence mapping" or "evidence gap mapping". Generally require search strategy, standardized data extraction, +/- registration. 
- rapid = timely information for decision-making; e.g. health technology assessment re: policy-maker. Timeline < 1 month - 'semi-systematic' review. Acknowledge result will be less rigorous. 
- Network = combine several pairwise meta-analysis to compare multiple interventions
- Umbrella review = panoramic view summarizing all systematic reviews and meta-analyses on a topic to summarize outcomes, gaps, knowledge. 

## Steps to perform a Meta-analysis

Pre-registration of protocols: PROSPERO (free) ; OSF 

### Formulate study question

Define goals: impact (direct patient care vs policy/CPG/formulary; publication)

Good question -> needs good data to support. *this one is hardest to find a new question. 
—> may need to utilize suboptimal evidence; identify gap

Population/Patient
Intervention/Exposure
Comparison
Outcome

### Literature search / retrieval

Key databases: 

- MEDLINE (aka PUBMED)
- EMBASE
- Cochrane Controlled Trials Register

(Minor: International Pharmaceutical Abstract, CINAHL, BIOSIS, AMED, PSYCHINFO, SIGLE)

Highly sensitive searching (using inclusive string: *, synonyms, exploded MeSH); best to include non-English articles

Represent this by a PRISMA Flow (from EQUATOR network for reporting)


Peer Review of Electronic Search Strategies
- PRESS Checklist

https://www.bmj.com/content/358/bmj.j4008 AMSTAR critical appraisal 

PRISMA-A abstract
PRISMA-P protocol
PRISMA-S search strategy
https://www.equator-network.org/?post_type=eq_guidelines&eq_guidelines_study_design=0&eq_guidelines_clinical_specialty=0&eq_guidelines_report_section=0&s=PRISMA+extension&btn_submit=Search+Reporting+Guidelines 


Protocol must be a priori: 

- PICOT
- Inclusions
- Exclusions
- Search Methods
- Data collect
    - Selection
    - Data extraction
    - Quality assessment/risk of bias
    - Data synthesis


Tools: http://systematicreviewtools.com/

Cochrane EPOC = effective practice organization of care

Revman 5.4 free for academic (non-commercial) use. 

Yale MESH analyzer - https://mesh.med.yale.edu/ —> gets you associated mesh terms 

Pubmed PubReMiner - https://hgserver2.amc.nl/cgi-bin/miner/miner2.cgi

Ways to find correct MESH terms 
Exemplar articles -> reminder / mesh analyzer to add more

Databases: 

Medline (via punned) - MESH terms
Embase - EMTREE terms  use ‘ti,ab,kw’
Central (Cochrane Library) 

Start in MESH tree or EMTREE -> then generate search in the advanced options. 

MESH terms

[Subheading:NoExp] would restrict; using just mesh will miss some that using [ti] (or text) would pick up 

There is a “translation document” to go between the search engines. 

NOT (“Animals”[MESH] NOT “Humans”[MESH])

Use Cochrane handbook validated RCT filter. 

ENDNOTE to remove duplications: Use export from pubmed to endnote to get all in end-note. 

Remove duplicates off Author/Year/Title
Edit->preferences-> duplicates (set up which ones to match based on)
Library -> find duplicates. Then double check and delete. 

### Paper selection per protocol

Screening 

#### Title/Abstract Phase

Title/abstract screening

- More inclusive approach; 2-5 papers per minute
- 2 reviewers, with 1 to adjudicate.

Can use EndNote

Importantly: need to keep track of hits and which are screened out. 

Rayyan is a free tool to do this. -https://www.rayyan.ai/memberships/

https://estech.shinyapps.io/prisma_flowdiagram/ is an online tool to generate the flow diagram 

Inclusion/Exclusion: 
PICO + design, context/setting (region, inpatient, etc.), type of publication (e.g. excluding commentaries, systemic reviews), language (generally, avoid language restrictions) 

Broad vs narrow? Depends on # of studies. 

Easiest criteria to filter first. 

- Add search of prior review and SRMA inspection to methods. If used

Generally don’t need to include reasons for exclusion at this stage, though logistically it can be helpful to some have this (if you later iterate back to this) 

PRISMA diagram - https://www.eshackathon.org/software/PRISMA2020.html

#### Full text screening

At this stage, record the reasons for exclusions. 

### Data extraction and quality assessment

Objective and reproducible procedure: use standardized data abstraction form

At least two reviewers need to abstract data from same article; 3rd reviewer to resolve issues. 

(Should trial the form initially to see if it works). 

Needs to include study quality assessment.  (Ie using a metric)

- incomplete data
- discrepant data
- non-numeric data 
Etc. 

### Analysis and interpretation 

3 main issues

- are studies combinable (heterogeneity? If so, sometimes you can identify the source of heterogeneity and remove it)
- combining study (fixed or random-effects models)
- Assessing for publication bias

Presents point estimate and 95% CI of summary measure  

Identification of gaps is a valuable. 


A data extraction phase is needed to obtain the relevant information from each study. A modification of CHARMS (checklist for critical
appraisal and data extraction for systematic reviews of prediction modelling studies)

Purposes: 

* Description of included studies
* Construction of tables and figures
* Facilitate quality assessment
* Enable syntheses and meta-analyses

Must specify all data elements that you are going to collect (for reproducibility); at least 2 people should work on the data abstraction. 
-> best to do a preliminary trial

Data elements: PICOS framework is simplest

—> want to compile which outcome measures are used in the various studies. 

Can be done inside Excel/Google, or specific data systems (such as COVIDENCE) 


Outcomes: need 
If yes/no
R1 = number of patients with event in experimental group
N1 = number of patients with no events in experimental group
R2
N2

If continuous: 
Need to extra: 
Mean, SD in each group before and after 

#### Quality Assessment

Quality Assessment: 
Risk of Bias (how well methodologically done) - Use Cochrane RoB 2.0 tool
Reporting Bias (how well reported) - e.g. CONSORT for RCTs
Certainty (extent that reviewers are confident) - mostly summarized with GRADE

RoB 2.0 categories

Selection bias: allocation (sequence generation, concealment)
Performance bias: blinding
Detection bias: assessment of outcome in whole population.
Attrition bias: incomplete outcome data
Reporting bias: selective reporting

EPOC risk of bias is a health services research specific version 


### Statistical Meta-analysis 

Each study: outcome data -> effect measure

Then, at the time of meta-analysis, you combine the study-level (aka study-level meta-analysis) effect measures to generate a summary effect measure. 
— individual patient data meta-analyses is different; involves 

- Identify pairwise comparisons (unless doing something like pooled prevalence estimate)
- Identify outcome (e.g. AKI) and effect measure (e.g. RR) 
- For each study, extract 2x2 table components
- Pooling: more weight is given to the studies that contribute more information. 
    - Generally: inverse variance method: weight = 1 / variance estimate = 1 / (SE)^2
        - Pooled estimate = sum of (estimates*weight)/sum of weights
        - Note: this is not the same, exactly, as proportional to sample size because it also depends on things like event rate, variability, etc.
- Meta-analysis: does not only increase precision: also gives information about heterogeneity (and it’s source), synthesis of data, etc. 
    - One possible goal: Effect modification, subgroup analysis, statistical interaction, heterogeneity (all synonyms)

- Can you find particular groups (or other questions you couldn’t answer from the original trials) 


IPD - allows you to fix some of the methodological / reporting issues that you can’t for

Are the studies combinable? Depends on the amount of heterogeneity. Are they estimating the same treatment effect? 
- Clinical heterogeneity: treatment reg (intensity, duration, delivery, components, experience of providers), control, patients (condition, age, gender, location, eligibility criteria), settings, design, outcome measures (time, method of assessment, cutoffs). One way to classify
    - Clinical diversity = variation in the PICO question
    - Methodological diversity = variation in how the studies were done THAT INFLUENCES THE EFFECT ESTIMATE
- Statistical heterogeneity: is observed variability greater than expected by chance alone. 

Methods to identify heterogeneity IN THE OUTCOME (may be the result of differences in other design choices, but heterogeneity describe variation specific to the OUTCOME): 
- I^2 - is the difference more than what we expected? 
    - I^2 is percentage of total variation across study that is due to heterogeneity rather than chance. 
    - I^2 = 100% * (Q-df) / Q
- Forrest Plot - 
- Q-test / chi2 (actually Q Cochrane Mentel Haeszel) - note: if low power (few studies, mostly low weights)), fail to reject null is weak evidence for homogeneity 
    - Q = sum ( weight * (est_i - est_pool)^2
    - Q test compares this to Chi2(df)  

Note: random-effects meta-analysis is not a solution to heterogeneity, but a way to incorporate unexplained heterogeneity in a valid way

Best to pre-specify expected sources of heterogeneity. 
- Subgroups to look for that
- What is the result if you remove that heterogeneity. 

Meta-regression is a way to explore heterogeneity: evaluates the gradient of effect according to 1 or more study features. 
- Association b/w patient char and outcome, but keep in mind it is average effect of each study (thus may be subject to actually the ecological fallacy/aggregation bias
- Need larger number of studies to power- thus often univariate or 2 independent variables.  
    - Note: point is not to adjust, it is to confirm whether independent variable is a source of heterogeneity and how

- Meta regression is a weighted regression; can be done with fixed or random effects meta-analysis. 
    - [ ] risk of false positives - check citation 21: https://pubmed.ncbi.nlm.nih.gov/15160401/

{Comment, this is meta-regression - which is a weighted regression, with weight loss as the predictor variable}
[ ] linearity assumption difficult to assess in practice: [ ] citation 24. - https://pubmed.ncbi.nlm.nih.gov/9595615/

A subtype of meta-regression is component network meta-analysis - where features of the intervention are coded and used as inputs to a meta-regression to evaluate the portion of variance explained. 

With high hetergeneity, it is unlikely that 1 factor explains it - however, in OSA weight-loss, there is an underlying rationale for why it may be a strong predictor. 

Sensitivity Analysis: change the analysis decisions and see if the analysis is robust. 
- e.g. include only studies with low risk of bias
- e.g. try other effect measures (e.g. OR, RR; absolute vs relative)
- Random vs Fixed effect. 
- Include only larger (e.g. > 200) sample size studies (small study effect = may have more publication bias). 

Lastly - an analysis of the variance of the control group to the intervention group provides a method of evaluating the likelihood of effect modification with patient characteristics. `
https://journals.lww.com/epidem/Fulltext/2021/11000/Detecting_Heterogeneity_of_Intervention_Effects.11.aspx 

L’abbe Plot: Control Group event rate vs Intervention event rate. 
Allows visualization of…?

Statistical Model: 

Two Models: differ in weight used in pooling, concept of pooling, assumption used in the model
- Fixed-effects model - less common now. However, Cochrane would say use fixed effect if you don’t find heterogeneity. 
    - Assumes a single common treatment effect (ie. all studies are estimating the same value), and thus random error explains variation around the truth.
    - All studies weighted by inverse of each study’s variance (within-study variance) 
    - “Did the treatment produce benefit on average in the studies at hand?”
- Random-effects model
    - There are actually a range of treatment effects, thus variation will be due both to difference in the quantity measured, and to random error
    - Weights: inverse of the sum of variances (within study variance AND between study variance which is shared between studies)
        - When shared between study variance is small, it approaches the weighting of the fixed-effect model.
    - Studies are a random sample of a hypothetical population of studies. 
    - Wider CI
    - “Will the tretatment produce benefit on average in studies from the hypothetical population of studies?”
    - Common method for pooling: A DerSimonian and Laird random effects meta-analysis model was used for<outcome> to combine weighted mean differences
    - DerSimonian R, Kacker R. Random-effects model for meta-analysis of clinical trials: an update. Contemp Clin Trials 2007; 28: 105–114.


Analyzing Dichotomous Outcomes
	Ratio (either Odds or Risk) vs Differences (when looking to derive absolute effect sizes) 
	need 2x2 tables to calculate them

For data collection: 

-Effect measure: Point estimate with 95% CI is sufficient. You can also back calculate based on P-value if you make some assumptions)
-Proportions: need both numerator and denominotor

Continuous 
- Weighted Mean Difference: same scale
- Standardized mean difference used when there is no single unit to be pooled. If different scale, they must be conceptual measuring the same thing for this to be valid.

For data collection: 
Need mean value and measure of variation (dispersion)- SD, SE. IQR ok but you need to make assumptions. 


Prediction interval: 

- Usual output interval estimates the range of means from the group of studies. 
- Prediction interval estimates the range of values (ie. studies) that are expected based on the data. 
    - Ie. This predicts what the range of the next study would be, and thus is similar to to the inferences that come from standard studies. 
    - Does this by incorporating both uncertainty in the mean (as usual) plus uncertainty of the true treatment effect.

These haven’t historically, but likely will be more in the future. 


Conceptual problem in meta-analysis: utility to individual patient decision-making: do the patients on which the meta-analysis is based resemble the patient about whom decisions are being made. 
—> Meta-analysis as currently performed may be more acceptable for policy decisions
(Ie. Is a trial with closer characteristics to the decision a better reference class).
—> Yet, Stein’s paradox notes that actually the estimate that includes information of other ‘reference groups’ is actually, on average, more accurate. Due to the statistical concept of ‘shrinkage’ and that estimates that deviate from the hypothetical (and measured) mean are more likely to be spurious.  [ ] read more about Stein’s paradox


### In cases where you can't do meta-analyses: 

Approaches include: 

- qualitative comparative analysis (QCA) 
- qualitative evidence synthesis (QES)

#### Reporting Bias aka Non-reporting Bias

Note: do not include any duplicates (violates independence assumptions.

Funnel Plot- asymmetry is caused by…Publication bias OR heterogeneity OR poor methods/small study effect. NOT just publication bias.

Also note: some effect estimates (e.g. odds ratios and standardized mean differences) are naturally correlated with their standard errors, and this can produce spurious asymmetry in a funnel plot

Contour enhanced Funnel Plot - Helps to differentiate publication bias vs other sources of heterogeneity. Publication bias is suspected when the smaller studies are missing from the NONsignificant regions preferentially; if studies are missing from the significant regions preferentially, it suggests that another source of heterogeneity is likely (because it would be weird if significant results were being suppressed. 

Tests: (for “small study effects”)
- Begg-rank: is there any association between treatment effect and variance? Corresponds to testing if funnel plot is symmetric
- Egger weighted regression model - tests whether treatment effect and variance are related.  This is most commonly done. 
    - There are other new versions… Harbord, Peters

Limitations: 
- Need at least 10 studies to detect bias reliably. 
- Funnel plot symmetry can’t be assessed if all standard errors are the same. 

Trim and Fill method (=fill the publication bias spot - requires many assumptions)

Cumulative meta-analysis: summarizes the amount of data that was known as you added each study (generally done chronologically)

### Network Meta-analysis 

Borrow information from common comparators to allow either indirect comparison (no direct evidence comparing option B to C) or mixed treatment comparison (many RCTs of A-C, A-B , and maybe only 1 of B-C but you want to use the information from the other studies to improve the B-C estimate. )

Two types: 

- Indirect treatment comparison: open loops on comparison diagram

Means: transitive property allows calculation of means. Variances sum.

- Mixed treatment comparison: has closed loops on comparison diagram; both direct and indirect evidence can be used.  

Contrast estimate: the estimate in question. All loops will contribute. Can use Cinema to generate the evidence network graph (https://cinema.ispm.unibe.ch/). Can also do in stata via 'mvmeta' command package. 

There is a connection of the statistics to dummy variables for regression analyses... somehow, not sure yet. Uses multiple imputation (?) 



Heterogeneity (the true treatment effect varies with different population/patient characteristics, study characteristics, or treatment characteristics) is caused by variation in measured and unmeasured effect modifiers. 

--> imbalance of effect modifiers in different studies make it so that the indirect comparison will be less accurate (transitivity will not hold). This is prone to occur when the studies are of different severity of disease in the sample. 
--> now, you need to assess transitivity: look for effect modifiers and how they are distributed across studies. If the distribution of effect modifiers in each pairwise comparison 

Thus, becomes very important to summarize distribution of effect modifiers in each study (if they are different, transitivity assumption is less likely to hold). 


Transitivity = Exchangeable (synonyms): means that the indirect evidence via a common comparison is valid. Often need to justify this assumption (by distribution of effect modifiers among all studies included in the evidence network)
-----



For multi-component interventions, network meta-analysis can be used to split out the effectiveness of each component (if you make the assumption that their is no synergy) by creating a 'network' of evidence around each component of the information. 

### Umbrella Review

Umbrella review: aka of review of review; summary of systematic reviews. 

Unit of analysis: systematic review +/- meta-analysis	
rank the convincingness of answers on various questions. 

Best use: when you are interested in evidence in a subject that already has SRMAs

Use a systematic search strategy: epistemonikos (most exhaustive) and CDSR (Cochrane Database), & all the usual databases. 

How to assess quality of the systematic review: AMSTAR 2 is the most commonly used tool (evaluating the quality of SRMA). ROBIS & JBI

When there are multiple analyses looking at the same study question, you can only include 1: 

- choose the 1 that integrates the most information
- if tied, most patients or most representative population. 

Also note that 1 meta-analysis answers several unique questions (for example, by subgroup analyses or meta-analyses looking at alternative outcomes) 



### GRADE

High / Moderate /Low / Very low based on:

- Design of primary studies
- Quality of primary studies (risk of bias) 
- Inconsistency
- Indirectness
- Imprecision 
- Others (publication bias, large effect, dose-response gradient, prediction interval doesn't include the null, plausible confounding?)

https://bestpractice.bmj.com/info/us/toolkit/learn-ebm/what-is-grade/ overview

Tool: https://www.gradepro.org/
will generate diagram.


For obeservational studies: Ioannidis: from nonsignificant to convincing (requires 1000+ cases, p< 1x1000^-6, I2 50%, no small study effects, and no excess significant bias)
--> generally, this requires recalculating the meta-analysis based on the raw data.

What is excess significance bias - test whether there is a relative excess significant findings. 

- step 1: identify the power of each study (power twoproportions...need to all the 2x2 info basically) to find the pooled effect (or best trial) 
- step 2: sum the power = expected number of studies with significant findings. 
- step 3: compare Observed number with Xi squared. 
--> if E > O, not excess
--> chi2 w DF = (studies-1), generally use significance level of 0.1

Credibility Ceiling test: tests the robustness of the MA estimate considering the limitations of observation data. 

Probability (C) = p(calculated effect is not in the direction of the true effect)

Inflate CI by 10% -> if it is still signficant, the ceiling has passed. 


### Credibility assessment


## Publication tips: 


At U of U, CTSI has SRMA core (survey design core, bioinformatics core, etc.) https://ctsi.utah.edu/cores-and-services/triad/systematic-review 


Search->submission must be less than 6 months. (If longer, may need to repeat/update)