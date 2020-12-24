# Matrix

### Matrix Multiplication

{% hint style="info" %}
Hadamard Product/Multiplication is simply the elementwise multiplication of two Matrix. Usually, in programming, the notation of this operation is a star \(\*\).  
{% endhint %}

### Multiplying a Matrix by Another Matrix

Need to do the "dot product" of rows and columns.

![](../.gitbook/assets/screen-shot-2020-12-22-at-9.21.31-pm.png)

![](../.gitbook/assets/screen-shot-2020-12-22-at-9.21.50-pm.png)

![](../.gitbook/assets/screen-shot-2020-12-22-at-9.22.24-pm.png)

## Dividing a Matrix by Another Matrix

We don't do that. Rather we make the inverse of the denominator matrix and then multiply it with the numerator matrix.

**However**, the elementwise division is obviously possible.

## Inverse of a Matrix

**2x2 Matrix.** The inverse of a 2x2 is easy compared to larger matrices \(such as a 3x3, 4x4, etc\). For those larger matrices there are other methods to work out the inverse.

![](../.gitbook/assets/screen-shot-2020-12-22-at-9.28.45-pm.png)

Very much helpful if we want to get an unknown matrix such as X where,$$XA = B$$ by $$X = BA^{-1}$$ 

## Determinant of a Matrix

The determinant of a matrix is a special number that can be calculated from a square matrix. The determinant helps us find the inverse of a matrix, tells us things about the matrix that are useful in systems of linear equations, calculus and more.

**Calculating the Determinant - For a 2×2 Matrix**

![](../.gitbook/assets/screen-shot-2020-12-22-at-9.32.53-pm.png)

$$
|A| = ad - bc
$$

## Identity Matrix

It is the matrix equivalent of the number "1". It is "square" \(has same number of rows as columns\), It has 1s on the diagonal and 0s everywhere else.

$$
A \times A^{-1} = A^{-1} \times A = I
$$

{% embed url="https://www.mathsisfun.com/algebra/matrix-multiplying.html" %}

{% embed url="https://www.mathsisfun.com/algebra/matrix-inverse.html" %}



