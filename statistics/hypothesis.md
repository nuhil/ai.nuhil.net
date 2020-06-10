# Hypothesis

**A scientific hypothesis** is a provisional explanation for observations that is falsifiable - meaning that there exists a test whose outcome could mean that the hypothesis is not true. A good hypothesis is testable; it can be either true or false. A good hypothesis fits the evidence and can be used to make predictions about new observations or new situations.

{% hint style="success" %}
**A Statistical Hypothesis** is a probabilistic explanation about the presence of a relationship between observations.
{% endhint %}

{% hint style="info" %}
For example, we may be interested in evaluating the relationship between the means of two samples, e.g. whether the samples were drawn from the same distribution or not, whether there is a difference between them. 
{% endhint %}

One hypothesis is that there is no difference between the population means, based on the data samples. This is a hypothesis of no effect and is called the null hypothesis and we can use the statistical hypothesis test to either reject this hypothesis, or fail to reject \(retain\) it. 

We don’t say “accept” because the outcome is probabilistic and could still be wrong, just with a very low probability. 

If the null hypothesis is rejected, then we assume the alternative hypothesis that there exists some difference between the means. 

**Null Hypothesis \(H0\):** Suggests no effect. 

**Alternate Hypothesis \(H1\):** Suggests some effect.

### Machine Learning Hypothesis

{% hint style="success" %}
It is a candidate model that approximates a target function for mapping inputs to outputs.
{% endhint %}

Learning is a search through the space of possible hypotheses for one that will perform well, even on new examples beyond the training set. The choice of algorithm and algorithm configuration involves choosing a hypothesis space that is believed to contain a hypothesis that is a good or best approximation for the target function.

### Reasons for Hypothesis Tests

1. **Normality Tests** Tests that you can use to check if your data has a Gaussian distribution.
   1. Shapiro-Wilk Test
   2. D’Agostino’s K^2 Test
   3. Anderson-Darling Test 
2. **Correlation Tests**  
   Tests that you can use to check if two samples are related.  
   **H0:** the two samples are independent.

   **H1:** there is a dependency between the samples.

   1. Pearson’s Correlation Coefficient
   2. Spearman’s Rank Correlation
   3. Kendall’s Rank Correlation
   4. Chi-Squared Test 

3. **Stationary Tests** Tests that you can use to check if a time series is stationary or not.
   1. Augmented Dickey-Fuller
   2. Kwiatkowski-Phillips-Schmidt-Shin 
4. **Parametric Statistical Hypothesis Tests**  
   Tests that you can use to compare data samples.  
   **H0:** the means of the samples are equal.

   **H1:** the means of the samples are unequal.

   1. Student’s t-test
   2. Paired Student’s t-test
   3. Analysis of Variance Test \(ANOVA\)
   4. Repeated Measures ANOVA Test 

5. **Nonparametric Statistical Hypothesis Tests**  
   Tests whether the distributions of two independent samples are equal or not.  
   **H0:** the distributions of both samples are equal.

   **H1:** the distributions of both samples are not equal.

   1. Mann-Whitney U Test
   2. Wilcoxon Signed-Rank Test
   3. Kruskal-Wallis H Test
   4. Friedman Test



### References

{% embed url="https://machinelearningmastery.com/what-is-a-hypothesis-in-machine-learning/" %}

{% embed url="https://machinelearningmastery.com/statistical-hypothesis-tests-in-python-cheat-sheet/" %}



