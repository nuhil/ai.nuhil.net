# Linear Regression

### From Logit to Sigmoid

$$
ln(\frac{p}{1-p}) = b_0+b_1x_1+b_2x_2+b_3x_3\\
\frac{p}{1-p} = e^{b_0+b_1x_1+b_2x_2+b_3x_3}\\
e^{b_0+b_1x_1+b_2x_2+b_3x_3} - p(e^{b_0+b_1x_1+b_2x_2+b_3x_3}) = p\\
p + p(e^{b_0+b_1x_1+b_2x_2+b_3x_3}) = e^{b_0+b_1x_1+b_2x_2+b_3x_3}\\
p(1 + e^{b_0+b_1x_1+b_2x_2+b_3x_3}) = e^{b_0+b_1x_1+b_2x_2+b_3x_3}\\
p = \frac {e^{b_0+b_1x_1+b_2x_2+b_3x_3}}{1 + e^{b_0+b_1x_1+b_2x_2+b_3x_3}}\\
p = \frac {\frac{e^{b_0+b_1x_1+b_2x_2+b_3x_3}}{e^{b_0+b_1x_1+b_2x_2+b_3x_3}}}{\frac{1 + e^{b_0+b_1x_1+b_2x_2+b_3x_3}}{e^{b_0+b_1x_1+b_2x_2+b_3x_3}}}\\
p = \frac {1}{1+\frac{1}{e^{b_0+b_1x_1+b_2x_2+b_3x_3}}}\\
p = \frac {1}{1+e^{-(b_0+b_1x_1+b_2x_2+b_3x_3)}}\\
$$

{% embed url="https://towardsdatascience.com/linear-regression-using-gradient-descent-97a6c8700931" %}



