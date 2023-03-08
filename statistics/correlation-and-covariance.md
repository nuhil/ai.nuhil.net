# Correlation and Covariance

### Correlation

* **Positive** correlation exists when larger values of $$x$$ correspond to larger values of $$y$$ and vice versa.
* **Negative** correlation exists when larger values of $$x$$ correspond to smaller values of $$y$$ and vice versa.
* **Weak or no** correlation exists if there is no such apparent relationship.

![](../.gitbook/assets/screen-shot-2020-01-23-at-1.13.59-pm.png)

### Covariance

{% hint style="success" %}
It is a measure that quantifies the strength and direction of a relationship between a pair of variables.
{% endhint %}

$$
cov(x,y)=\frac{1}{n}\sum_i^n(x_i-\overline{x})(y_i-\overline{y})
$$

### Correlation Coefficient

{% hint style="success" %}
The correlation coefficient, or **Pearson** product-moment correlation coefficient is another measure of the correlation between data. You can think of it as a **standardized covariance**.
{% endhint %}

$$
r_{xy}=\frac{cov(x,y)}{\sigma(x)\sigma(y)}=\frac{\sum_i^n(x_i-\overline{x})(y_i-\overline{y})}{\sqrt{\sum_i^n(x_i-\overline{x})^2\sum_i^n(y_i-\overline{y})^2}}
$$

> Make a Scatter Plot, and look at it! You may see a correlation that the calculation does not.
>
> **Correlation Is Not Causation** which says that a correlation does not mean that one thing causes the other.
