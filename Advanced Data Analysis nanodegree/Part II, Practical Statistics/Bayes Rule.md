The essence of Bays rule is:

It is some sort of a ```prior```, of which we mean ```the probability before we run a test```,  and then get some evidence from the test itself. 

```Prior probability + Test Evidence ---> Posterior Probability```

----------------------------------------------------------------------------------------------

For this table of cases:

![Capture](https://user-images.githubusercontent.com/91827137/166153875-f7a7e8d9-ce08-41fa-a5fa-62036ca83485.PNG)

If specific cancer occurs in 1% of the population (P(C) = 0.01), and a test for this cancer is with a 90% chance if they have this C (usually called sensitivity), and there is another 90% chance it is negative if we don't have C ( usually called specificity). What do you think is the probability of having that specific type of cancer?

So, we have P(C) = 0.01 
            90% is positive if you have C.
            90% is negative if you don't have C.
     question: Test = Positive, probability of having cancer = ?

Using the probability provided above. What is the probability that there is truly cancer if someone has a positive test P(Cancer|Positive)? choices are: (8% / 1% / 90%)

First, we know that only 1% of people have cancer regardless of the test being positive or negative. Imagine someone has already tested positive, the probability of that person having cancer will be higher than 1%. But how much higher?

From conditional probability theory, we know that:
```P(C | Pos) = P(C & Pos) / P(Pos) = P(C & Pos) / [P(C & Pos) + P(¬C & Pos)]```,
which is the ratio of people who have cancer and also test positive to people who test positive whether they have cancer or not. This ratio will be quite small because the majority (99%) of people don't have cancer, which means the number of people who test positive and have cancer (P(C&Pos)) is relatively small compared to the number of people who test positive but don't have cancer (P(¬C & Pos)). So the ratio could not be as high as 90%.

Based on the estimation and the 3 choices, we can say that P(C|Pos) is higher than 1% and below 90%. So only 8% makes sense. To calculate it mathematically:

![Capture](https://user-images.githubusercontent.com/91827137/166395111-a103e946-89ed-4003-a79b-428eb5aa333e.PNG)

P(¬Cancer|Positive) = 0.99 * 0.1 = 0.099

P(Cancer|Positive) = 0.01 * 0.9 = 0.009

***note*** these two values must add up to 1.

***_Normalizing 1_***

The addition result of the two values is 0.108. This means that there is a 0.108 probability of a positive test result.

***_Normalizing 2_***

![Capture](https://user-images.githubusercontent.com/91827137/166395864-4e7decc0-8944-434e-b98d-8bd7f638a34d.PNG) 

--> So, the postrtior P(C|pos) is = P(C, pos) / [P(C, pos) + P(¬C, pos)] = 0.009 / 0.108 = 0.083

AND P(¬C|pos) = P(¬C, pos) / [P(C, pos) + P(¬C, pos)] = 0.099 / 0.108 = 0.916

--> The total probability for both cases, P(Cancer|Positive) and P(¬Cancer|Positive) = 1

***Table of all cases***

![Capture](https://user-images.githubusercontent.com/91827137/166396385-ae8e2cb4-4abf-49a8-af5e-5b7cffd1872c.PNG)

### Bayes Rule Diagram

![Screenshot (509)](https://user-images.githubusercontent.com/91827137/166862514-ea750c94-8840-4f9d-a50b-d48667d923b3.png)

- Cancer Hypothesis = Prior probability x sensitivity
- No Cancer Hypothesis = Prior probability x (1-sensitivity)
- Normalizer = Cancer Hypothesis + No Cancer Hypothesis

- Posterior Probability (Cancer) = Cancer Hypothesis / Normalizer
- Posterior Probability (No Cancer) = No Cancer Hypothesis / Normalizer

So, for this example:

![Capture](https://user-images.githubusercontent.com/91827137/166865634-8237e469-1dc7-4265-a918-6a56ca7eee09.PNG)

### Another example:

P(C) = 0.1 ; P(POS|C) = 0.9 ; P(NEG|¬C) = 0.5

SO:

P(¬C) = 1 - 0.1 = 0.9

P(NEG|C) = 1 - P(POS|C) = 1 - 0.9 = 0.1

P(POS|¬C) = 1 - P(NEG|¬C) = 1 - 0.5 = 0.5

-----------------------------------------------------------------

For test Neg:

1. The probability of having cancer and receiving a negative test result P(Cancer, Negative) = P(C,NEG) = Cancer Hypothesis = P(C) * P(NEG|C) = 0.1 * 0.1 = 0.01
2. The probability of not having cancer and receiving a negative test result P(¬Cancer, Negative) = P(¬C, NEG) = No cancer hypothesis = P(¬C) * P(NEG|¬C) = 0.9 * 0.5 = 0.45
3. The normalizer P(Negative) based on the probabilities above = P(NEG) = P(C,NEG) + P(¬C, NEG) = 0.01 + 0.45 = 0.46
4. The posterior probabilities of having cancer given a negative test result and not having cancer given a negative test result:

     a. P(C|NEG) = P(C,NEG) / P(NEG) = 0.01 / 0.46 = 0.0217
     b. P(¬C|NEG) = P(¬C, NEG) / P(NEG) = 0.45 / 0.46 = 0.9783
     
5. The posterior probabilities of having cancer given a positive test result and not having cancer given a positive test result:
     a. Cancer Hypothesis = P(C, POS) = P(C) * P(POS|C) = 0.1 * 0.9 = 0.09
     B. No Cancer Hypothesis = P(¬C, POS) = P(¬C) * P(POS|¬C) = 0.9 * 0.5 = 0.45
     c. Normalizer = P(POS) = 0.09 + 0.45 = 0.54
     d. Posterior Probability (cancer) = P(C|POS) = 0.09 / 0.54 = 0.1667
     e. Posterior Probability (no cancer) = P(¬C|POS) = 0.45 / 0.54 = 0.833
     
## Bayes Rule Summary
1. Prior probability – P(C) – Tells us how frequently our variable is true. And the test is characterized by:
    a. Sensitivity – P(Positive|Cancer) – Tells us how often the test is positive when the   variable is true.
    b. Specificity – P(Negative|¬Cancer) – Tells us how often the test is negative when the variable is false.
    
_note_ : The two variables (Cancer hypothesis & No cancer hypothesis for these examples) are also called ```the joint probabilities of two events```
