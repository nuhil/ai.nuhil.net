# P Value

{% hint style="success" %}
P-value tells us how likely it is to get a result like this if the Null Hypothesis is true.
{% endhint %}

{% hint style="info" %}
A neurologist is testing the effect of a drug on response time by injecting 100 rats with a unit dose of the drug, subjecting each to neurological stimulus, and recording its response time. The neurologist knows that the mean response time for rats not injected with the drug is 1.2 seconds. The mean of the 100 injected rats' response time is 1.05 seconds with a sample standard deviation of 0.5 seconds.

Do you think that the drug has an effect on response time?
{% endhint %}

### Hypothesis

**Null Hypothesis:** Drug has no effect. \(Sample mean would also be 1.2 sec ****even with drug\)  
**Alternative Hypothesis:** Drug has an effect. \(Mean is not equal 1.2 sec when drug is given\)

Given,   
$$\sigma_{\overline{x}}=\frac{\sigma}{\sqrt{n}}=\frac{0.5}{10}=0.05$$ \[Best estimation of sample standard deviation\]  
$$z=\frac{1.2-1.05}{0.05}=3$$ \[Z score or how far we are away from the mean\]

That means, the z-score is 3, its `3 SD` away \(i.e., beyond the probability of 99.7% of the normal distribution\), which is `0.3% = 0.003` Therefore, **the p-value is** `0.003` 

> The probability of getting a result more extreme than 1.05 seconds given the Null Hypothesis, is 0.3% and is called the p-value. **This rejects the Null Hypothesis.**

{% hint style="danger" %}
**P-values have different threshold other than 0.05, based on different experimental scenarios!**
{% endhint %}

**Again, the p-value is the probability of observing the data, given the null hypothesis is true.** A large probability means that the H0 or default assumption is likely. A small value, such as below 5% \(0.05\) suggests that it is not likely and that we can reject H0 in favor of H1, or that something is likely to be different \(e.g. a significant result\).

> In this example, we performed a **Parametric Statistical Hypothesis Tests.**
>
> Sometimes, **P** is the probability that two variables are independent \(i.e., Correlation Test\). See More [Use Cases](hypothesis-test.md#reasons-for-hypothesis-tests)

### **T-value**

The larger the absolute value of the t-value, the smaller the p-value, and the greater the evidence against the null hypothesis.  


### References

{% embed url="https://www.youtube.com/watch?v=-FtlH4svqx4" %}

{% embed url="https://towardsdatascience.com/p-values-explained-by-data-scientist-f40a746cfc8?" %}



