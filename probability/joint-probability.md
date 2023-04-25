# Joint Probability

{% hint style="success" %}
Joint probability is the probability of two events happening together.
{% endhint %}

The two events are usually designated event A and event B. In probability terminology, it can be written as:

$$
P(A \cap B) =P(A,B) = P(A|B)*P(B)
$$

Anyway, if an event A and B are idenpendent then $$P(A|B) = P(A)$$, and therefore, $$P(A \cap B) = P(A,B)$$ become $$P(A) * P(B)$$&#x20;

{% hint style="info" %}
**Example:** The probability that a card is a five and black = p(five and black)&#x20;
{% endhint %}

Here p(five|black) is the conditional probability of drawing a five given that the card is black, and p(black) is the probability of drawing a black card.

The probability of drawing a black card from a standard deck of 52 playing cards is:

p(black) = Number of black cards / Total number of cards

\= 26 / 52

\= 1/2

The probability of drawing a five given that the card is black is:

p(five|black) = Number of black fives / Number of black cards

\= 2 / 26

\= 1/13

Therefore, the joint probability of drawing a five and a black card is:

p(five and black) = p(five|black) \* p(black)

\= (1/13) \* (1/2)

\= 1/26

**Another way**

2/52 = 1/26\
(There are two black fives in a deck of 52 cards, the five of spades and the five of clubs).



### OR Events

$$
P(A \cup B) = P(A)+P(B)-P(A \cap B)
$$
