# Bayesian statistics

Bayesian statistics do well when you have reason to believe that your data may not be a good representation of what you expect to observe in the future.

{% hint style="success" %}
This allows you to incorporate your own knowledge into your calculations, rather than solely relying on your sample.
{% endhint %}

It also allows you to update your thoughts about the future after new data come in.

{% hint style="info" %}
**Example:** Team A and Team B have played each other 10 times, and Team A has won 9 of those times. If the teams are playing each other tonight, and I ask you who you think will win, you’d probably say Team A! **What if I also told you that Team B has bribed tonight’s referees?** Well, then you might guess that Team B will win.
{% endhint %}

{% hint style="success" %}
Bayesian statistics allows you to incorporate this extra information into your calculations, while frequentist statistics focuses solely on the 9 out of 10 win percentage.
{% endhint %}

### Bayes’ Theorem

$$
P(H|E)=\frac{P(E|H) \times P(H)}{P(E)}
$$

The conditional probability of H given E, written $$P(H|E)$$, represents the probability of H occurring given that E also occurs \(or has occurred\). In our example, H is the hypothesis that Team B will win, and E is the evidence that I gave you about Team B bribing the referees.

$$P(H)$$ is the frequentist probability, 10%. $$P( E|H)$$ is the probability that what I told you about the bribe is true, given that Team B wins. _\(If Team B wins tonight, would you believe what I told you?\)_

Finally, $$P( E)$$ is the probability that Team B has in fact bribed the referees. Am I a trustworthy source of information? You can see that this approach incorporates more information than just the outcomes of the two teams’ previous 10 match-ups.

{% embed url="https://towardsdatascience.com/top-5-statistical-concepts-every-data-scientist-must-know-d4bc8740a55d" %}



