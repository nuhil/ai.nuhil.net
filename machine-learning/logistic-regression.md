# Logistic Regression

### 1. Logistic Model

Consider a model with features x1, x2, x3 … xn. Let the binary output be denoted by Y, that can take the values 0 or 1. Let p be the probability of Y = 1, we can denote it as p = P\(Y=1\). The mathematical relationship between these variables can be denoted as:

$$
ln(\frac{p}{1-p}) = b_0+b_1x_1+b_2x_2+b_3x_3\\
$$

Here the term p/\(1−p\) is known as the odds and denotes the likelihood of the event taking place. Thus ln\(p/\(1−p\)\) is known as the log odds and is simply used to map the probability that lies between 0 and 1 to a range between \(−∞,+∞\). The terms b0, b1, b2… are parameters \(or weights\) that we will estimate during training.

#### It is Actually Sigmoid

From Logit to Sigmoid



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
S(x)=\frac{1}{1+e^{-x}}
$$

Now we will be using the above equation to make our predictions. Before that we will train our model to obtain the values of our parameters b0, b1, b2… that result in least error.

### 2. Define the Loss Function

[L2 Loss function](l1-and-l2-loss-function.md) is okay.

$$
L = \sum_{i=1}^n (y_{true}-y_{predicted})^2
$$

### 3. Utilize the Gradient Descent Algorithm

You might know that the partial derivative of a function at its minimum value is equal to 0. So gradient descent basically uses this concept to estimate the parameters or weights of our model by minimizing the loss function.

1. **Initialize the weights,** $$b_0=0$$ and $$b_1=0$$ .
2. **Calculate the partial derivative** with respect to b\_0 and b\_1$$d_{b_0} = -2 \sum_{i=1}^n(y_i - \bar{y_i}) \times \bar{y_i} \times (1 - \bar{y_i})\\  d_{b_1} = -2 \sum_{i=1}^n(y_i - \bar{y_i}) \times \bar{y_i} \times (1 - \bar{y_i}) \times x_i$$ 
3. **Update the weights** - values of $$b_0$$ and $$b_1$$  $$b_0 = b_0 - L \times d_{b_0} \\ b_1 = b_1 - L \times d_{b_1}$$ 



### Python Implementation

```python
# Importing libraries
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from math import exp

# Preparing the dataset
data = pd.DataFrame({'feature' : [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15], 'label' : [0,0,0,0,0,0,0,1,1,1,1,1,1,1,1]})
# Divide the data to training set and test set
X_train, X_test, y_train, y_test = train_test_split(data['feature'], data['label'], test_size=0.30)

## Logistic Regression Model
# Helper function to normalize data
def normalize(X):
    return X - X.mean()

# Method to make predictions
def predict(X, theta0, theta1):
    # Here the predict function is: 1/(1+e^(-x))
    return np.array([1 / (1 + exp(-(theta0 + theta1*x))) for x in X])

# Method to train the model
def logistic_regression(X, Y):
    # Normalizing the data
    X = normalize(X)

    # Initializing variables
    theta0 = 0
    theta1 = 0
    learning_rate = 0.001
    epochs = 300

    # Training iteration
    for epoch in range(epochs):
        y_pred = predict(X, theta0, theta1)

        ## Here the loss function is: sum(y-y_pred)^2 a.k.a least squared error (LSE)
        # Derivative of loss w.r.t. theta0
        theta0_d = -2 * sum((Y - y_pred) * y_pred * (1 - y_pred))
        # Derivative of loss w.r.t. theta1
        theta1_d = -2 * sum(X * (Y - y_pred) * y_pred * (1 - y_pred))

        theta0 = theta0 - learning_rate * theta0_d
        theta1 = theta1 - learning_rate * theta1_d
    
    return theta0, theta1

# Training the model
theta0, theta1 = logistic_regression(X_train, y_train)   

# Making predictions
X_test_norm = normalize(X_test)
y_pred = predict(X_test_norm, theta0, theta1)
y_pred = [1 if p >= 0.5 else 0 for p in y_pred]

# Evaluating the model
print(list(y_test))
print(y_pred)
```

{% embed url="https://towardsdatascience.com/logistic-regression-explained-and-implemented-in-python-880955306060" %}



