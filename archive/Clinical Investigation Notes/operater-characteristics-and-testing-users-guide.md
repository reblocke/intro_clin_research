# Operater Characteristics and Testing Users Guide

Fundamental teaching point: 

- all diagnostic tasks are not created equal: some are harder than others, or more consequential than others (see, threshold approach to decision-making)
- all diagnostic tests are not created equal: some give very strong evidence and some do not give very much
- as such, not all diagnostic tests are useful for all sorts of diagnostic situations. Knowing when a test can be applied is the goal of the Testing Users Guide

Why is this important to preclinical students? As practicing clinicians, we would do horribly at Step 1. Why? We don't use that at all. We should be focusing on this stuff: it pertains to how medicine is actually practiced. 


## Definitions: 

Operating characteristics = the diagnostic properties of the test

Receiver operating characteristic curve = the receive part comes from the initial application in radio signals toward interpreting signals. [ ] bedside rounds link.

## Sensitivity and Specificity to Likelihood ratios

- Sensitivity: in people who have the disease, what proportion of the time does the test get it right?
- Specificity: in people who do not have the disease, what proportion of the time does the test get it right? 

However, because we don't know if the patient has the disease or not (hence, the test), this is of limited direct clinical application. 

Better would be: 

- Positive predictive value: in people who test positive, what proportion have the disease?
- Negative predictive value: in people who test negative, what proportion do not have the disease? 

However, this is only applicable to a patient with an average similar risk to the population. We generally want greater resolution. Hence, likelihood ratios: 

- True positive fraction = sensitivity
- False positive fraction = 1 - specificity
- Positive likelihood ratio = True positive fraction / False positive fraction
- Negative likelihood ratio = False negative fraction / True negative fraction

### Bayes
Bayes factor: the marginal likelihood of two competing hypotheses... likelihood of observation given H1 / likelihood of observation given Ho.

- Bayes theorem: P (A | B) = P(A) * P (B | A) / P (B)
- Definition of a conditional probability: P (A | B) = P (A and B) / P (B) 
- combined: P (A and B) / p (B) = P(A) * (P (A and B) / P(A)) / P(B) 
- cancel: P (A and B) / P (B) = P (A and B) / P (B) -> thus bayes theorem is alway true unlesss P(B) or P(A) = 0.

Odds formulation Bayes theorem:  

Find the likelihood of the hypothesis over the likelihood of the negation of the hypothesis (= the odds)

P(H1 | A) / P(H0 | A) = [P(H1) / P(A|H1) ] / [ P(H0) / P(A|Ho)].  This is just plugging in bayes, and the P(A) denominator drops out. 

If H1 = 1-Ho (meaning, 1 of the two hypotheses are true.. as is the case in diagnosis. Mutually exclusive and collectively exhaustive), then by substituting H1 = 1-Ho we get

- Odds (H1 | A) = odds (A) * P (A|H1) / P(A|Ho)
- aka Post-test = Pretest * Bayes Factor.

Thus, a likelihood ratio of a test is a specific case of a Bayes factor where H1 = patient has the disease, Ho is that they do not. Using Bayes Rule, this can be applied to give individualized estimates of the influence of a test:

Pretest Odds of disease being present * Likelihood ratio = Posttest odds of disease being present

Last step.. how are odds calculated? P = probability; then, Odds = p / (1-p)

This is why likelihood ratios are so powerful.. in a sense, it is a generalization for how predictive power resolves to an individual level.

Good references for this: 

The quick proof of Bayes Theorem: https://www.youtube.com/watch?v=U_85TaXbeIo

Note: P(A and B) = P(A) * P(B) ONLY if A and B are independent; if their likelihoods are related, you need bayes formulation: P( A and B) = P(A) * P(B|A) -- note, that if independent, P(B|A) = P(B) by definition

-- thus, Bayes formula, is useful precisely WHEN events are not independent - it allows that to be quantified.

Bayes theorem geometry of changing beliefs: https://m.youtube.com/watch?v=HZGCoVF3YvM

Medical test paradox: https://www.youtube.com/watch?app=desktop&v=lG4VkPoG3ko

## Utility of this? 

The Bayes factor corresponds to the strength with which one should update information on the basis of a result. 1 is no information added at all. Near 0 is very strong evidence against, near infinity is very strong evidence for. 

### Coin flip 

Imagine I said that flipping a coin can help diagnose pneumonia. Heads = you have pneumonia.

- Sensitivity = "in people who have the disease, what proportion of the time does the test get it right?" = 50% (just by chance)
- Specificity = "in people who do not have the disease, what proportion of the time does the test get it right?" = 50%

In actuality we know that P(PNa | heads) = P(PNa | tails), because they are totally unrelated.  Although you can imagine we run a big study and prove it. 

Thus, the likelihood ratio is: 50% / 50% => 1. No information added.

### Biased Coin Flip

What's wrong with SpIN and SnOUT?

Imagine a hypothetical test with 85% sensitivity and 15% specificity. Pretty good test to exclude people if it's negative? (Rules out?)

- +LR = sensitivity / (1 - specificity) = 85% / (1-15%) = 1
- -LR = (1-sensitivity) / specificity = (1-85%) / 15% = 1

No information added! In essence, this is just a biased coin.. totally unrelated to the outcome, but more frequently comes up on heads. This is the derivation of the rule of 100 - if sensitivity and specificity sum to 100, then the test is no better than chance. 

### Information Added

And conversely, if sensitivity and specificity are much above 100, that's a better test.. as described:

(LR = OR in this case) 

![alt text](https://photos.collectednotes.com/photos/5187/63e15757-e4d0-4b07-8343-3253b683fb60)

This illustrates that smoking history can be a useful (for epidemiologists) clue to etiology, and can be part of an overall physician assessment - but is NOT sufficient to diagnose lung cancer. More testing is needed. 


### Bayes aside

Aside: If we are talking about a binary variable... 

P(B) = (P(B|~A) x P(~A)) + (P(B|A) x P(A)); ~A = not A. Since A is binary, the probability of A and ~A is 1 (it has to be either A or not A). Thus, the total probability of B is the probability of the likelihoods of B with each possible status of A.

Plugging that substitution in to Bayes: 

P(A|B) = P(B|A) x P(A) / ([P(B|~A) x P(~A)] x [P(B|A) x P(A)]

(This is the pie charts of diagnostic reasoning) 

## Conditional probability formulations

All of the above operating characteristics can be formulated as conditional probabilities

T+ = test positive, T- = test negative

C+ = characteristic actually present, C- characteristic actually not present

- Prevalence: P(C+)
- Sensitivity: P(T+ | C+)
- Specificity: P(T- | C-)
- PPV: P(C+|T+)
- NPV: P(C-|T-)
- TPF: P(T+|C+) 
- FPF: P(T+|C-)
- +LR: P(T+|C+)/P(T+|C-)
- -LR: P(T-|C+)/p(T-|C-)

With area the conditional 'given' reframes what probability-space is under consideration. 


## Applications

- Testing with various test operating characteristics and various prevalences/pre-test probabilties and how this influences the likelihood of true positive vs false positive? 



## Disease Definitions

Disease definitions are not 'true or not', but 'useful or not' - which begs the question of 'useful to who and for what purpose'?

see: p 391 of Koespell and Weiss for a recounting of William Farr and the imitation of categorization of disease. 

Also: Bedside rounds http://bedside-rounds.org/episode-64-a-vicious-circle/ and http://bedside-rounds.org/episode-63-signals/ re: the probabilistic basis of diagnosis.
