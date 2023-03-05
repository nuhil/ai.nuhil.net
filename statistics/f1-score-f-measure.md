# F1 Score (F Measure)

{% hint style="success" %}
Consider a Binary Classification Model that Predicts Whether or Not a Person Got Diabetic.
{% endhint %}

![](<../.gitbook/assets/Screen Shot 2020-03-30 at 11.08.26 PM.png>)

### Accuracy

How many cases did we correctly label out of all the cases? $$\frac{TP+TN}{TP+FP+TN+FN}$$&#x20;

### Precision

How many of those who we labeled as diabetic are actually diabetic? $$\frac{TP}{TP+FP}$$&#x20;

### Recall/Sensitivity/TPR

Of all the people who are diabetic, how many of those did we correctly predict? $$\frac{TP}{TP+FN}$$&#x20;

### Specificity/FPR(1-Specificity)

Of all the people who are healthy, how many of those did we correctly predict? $$\frac{TN}{TN+FP}$$&#x20;

### F1-score/F-Score/F-Measure

It is the harmonic mean (average) of the precision and recall. $$\frac{2*Precision*Recall}{Precision+Recall}$$&#x20;

Using F1 score as a metric, we are sure that if the F1 score is high, both precision and recall of the classifier indicate good results. This score takes both false positives and false negatives into account. Intuitively it is not as easy to understand as accuracy, but F1 is usually more useful than accuracy, especially if you have an uneven class distribution.



###
