---
description: Expected Value of Random Variable
---

# Expected Value

The expected value of a random variable is the weighted average of all possible values of the variable. The weight here means the probability of the random variable taking a specific value.

### Expected Value of Discrete Random Variable

$$
E[X] = \sum x_i \times P(x_i)
$$

Where $$x_i$$equal to the values that $$X$$takes and $$P(x_i)$$ is the probability that $$X$$ takes the value $$x_i$$ 

### Expected Value of Continuous Random Variable

Since continuous random variables can take uncountably infinitely many values, we cannot talk about a variable taking a specific value. We rather focus on value ranges.

In order to calculate the probability of value ranges, probability density functions \(PDF\) are used. 

{% hint style="danger" %}
PDF is a function that specifies the probability of a random variable taking value within a particular range.
{% endhint %}

$$
E[X] = \int_{x_{min}}^{x_{max}} x \times f(x) dx
$$

Where $$f(x)$$ is the PDF of $$X$$

