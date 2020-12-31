---
description: Bayes Theorem
---

# Bayesian Statistics

Bayes’ theorem is so fundamental and ubiquitous that a field called “bayesian statistics” exists. 

{% hint style="success" %}
In bayesian statistics, the probability of an event or hypothesis as evidence comes into play.
{% endhint %}

Therefore, prior probabilities and posterior probabilities differ depending on the evidence.

### Bayes’ Theorem

$$
P(A|B)=\frac{P(B|A) \times P(A)}{P(B)}
$$

P\(A\|B\) 	= Posterior probability of “A” \(the hypothesis\) given the evidence “B”  
P\(B\|A\) 	= Likelihood of the evidence “B” given the hypothesis “A” is true  
P\(A\) 	= Prior probability \(The marginal probability of the event “A”\)  
P\(B\) 	= Prior probability that the evidence itself is true

$$
P(H|E)=\frac{P(E|H) \times P(H)}{P(E)}
$$

### Example

{% hint style="info" %}
Team A and Team B have played each other 10 times, and Team A has won 9 of those times. If the teams are playing each other tonight, and I ask you who you think will win, you’d probably say Team A! **What if I also told you that Team B has bribed tonight’s referees?** Well, then you might guess that Team B will win.
{% endhint %}

{% hint style="success" %}
Bayesian statistics allows you to incorporate this extra information into your calculations, while frequentist statistics focuses solely on the 9 out of 10 win percentage.
{% endhint %}

The conditional probability of H given E, written $$P(H|E)$$, represents the probability of H occurring given that E also occurs \(or has occurred\). In our example, H is the hypothesis that Team B will win, and E is the evidence that I gave you about Team B bribing the referees.

$$P(H)$$ is the frequentist probability, 10%. $$P( E|H)$$ is the probability that what I told you about the bribe is true, given that Team B wins. _\(If Team B wins tonight, would you believe what I told you?\)_

Finally, $$P( E)$$ is the probability that Team B has in fact bribed the referees. Am I a trustworthy source of information? You can see that this approach incorporates more information than just the outcomes of the two teams’ previous 10 match-ups.

### Bayes Theorem to Naive Bayes Classifier

Naive bayes algorithm is structured by combining bayes’ theorem and some naive assumptions. Naive bayes algorithm assumes that features are independent of each other and there is no correlation between features.

The direct application of Bayes Theorem for classification becomes intractable, especially as the number of variables or features \(n\) increases. Instead, we can simplify the calculation and assume that each input variable is independent.

Although dramatic, this simpler calculation often gives very good performance, even when the input variables are highly dependent.

We can implement this from scratch by assuming a probability distribution for each separate input variable and calculating the probability of each specific input value belonging to each class and multiply the results together to give a score used to select the most likely class.

$$
P(yi|x1,x2,...xn) = P(x1|y1)*P(x2|y1)...P(xn|y1)*P(y1)
$$



{% embed url="https://towardsdatascience.com/top-5-statistical-concepts-every-data-scientist-must-know-d4bc8740a55d" %}



