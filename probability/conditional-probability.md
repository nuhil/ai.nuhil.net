# Conditional Probability

{% hint style="success" %}
Conditional probability is the likelihood of an event A to occur given that another event that has a relation with event A has already occurred.
{% endhint %}

Suppose that we have 6 blue balls and 4 yellows placed in two boxes as seen below. I ask you to randomly pick a ball. The probability of getting a blue ball is 6 / 10 = 0,6. What if I ask you to pick a ball from box A? The probability of picking a blue ball clearly decreases. The condition here is to pick from box A which clearly changes the probability of the event \(picking a blue ball\). The probability of event A given that event B has occurred is denoted as p\(A\|B\).

![](../.gitbook/assets/0_r2bplap03m0kbxgz.png)

$$
P(A|B) = \frac {P(A,B)}{P(B)} = \frac {P(A \cap B)}{P(B)}
$$

### Example

{% hint style="info" %}
In a group of 100 sports car buyers, 40 bought alarm systems, 30 purchased bucket seats, and 20 purchased an alarm system and bucket seats. If a car buyer chosen at random bought an alarm system, what is the probability they also bought bucket seats?
{% endhint %}

Here, P\(B\) = Probability of a car buyer chosen at random bought an alarm system, which is 40/100 = 0.4  
P\(A,B\) = Probability of both happening together, which is given 20/100 = 0.2  
So, P\(A\|B\) = 0.2/0.4 = 0.5

