# Linear Regression

### 1. Regression Model

In statistics, linear regression is a linear approach to modelling the relationship between a dependent variable and one or more independent variables. Let **X** be the independent variable and **Y** be the dependent variable. We will define a linear relationship between these two variables as follows:

$$
Y = \theta_0+\theta_1\times X
$$

### 2. Define Loss Function

We will use the Mean Squared Error function.

$$
L = \frac{1}{n}\sum_{i=1}^n (y_{true}-y_{predicted})^2
$$

### 3. Utilize the Gradient Descent Algorithm

You might know that the partial derivative of a function at its minimum value is equal to 0. So gradient descent basically uses this concept to estimate the parameters or weights of our model by minimizing the loss function.

1. Initialize the weights, $$\theta_0 = 0$$and $$\theta_1 =0$$ 
2. Calculate the partial derivatives w.r.t. to $$\theta_0$$and $$\theta_1$$  $$d_{\theta_0} = -\frac{2}{n} \sum_{i=1}^n(y_i - \bar{y_i}) \\   d_{\theta_1} = -\frac{2}{n} \sum_{i=1}^n(y_i - \bar{y_i}) \times x_i$$ 
3. Update the weights
4. $$\theta_0 = \theta_0 - l \times d_{\theta_0}  \\ \theta_1 = \theta_1 - l \times d_{\theta_1}$$ 

### Python Implementation

```python
# Importing libraries
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split

# Preparing the dataset
data = pd.DataFrame({'feature' : [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15], 'label' : [2,4,6,8,10,12,14,16,18,20,22,24,26,28,30]})
# Divide the data to training set and test set
X_train, X_test, y_train, y_test = train_test_split(data['feature'], data['label'], test_size=0.30)

# Method to make predictions
def predict(X, theta0, theta1):
    # Here the predict function is: theta0+theta1*x
    return np.array([(theta0 + theta1*x) for x in X])

def linear_regression(X, Y):
    # Initializing variables
    theta0 = 0
    theta1 = 0
    learning_rate = 0.001
    epochs = 300
    n = len(X)

    # Training iteration
    for epoch in range(epochs):
        y_pred = predict(X, theta0, theta1)

        ## Here the loss function is: 1/n*sum(y-y_pred)^2 a.k.a mean squared error (mse)
        # Derivative of loss w.r.t. theta0
        theta0_d = -(2/n) * sum(Y-y_pred)
        # Derivative of loss w.r.t. theta1
        theta1_d = -(2/n) * sum(X*(Y-y_pred))

        theta0 = theta0 - learning_rate * theta0_d
        theta1 = theta1 - learning_rate * theta1_d   

    return theta0, theta1

# Training the model
theta0, theta1 = linear_regression(X_train, y_train)   

# Making predictions
y_pred = predict(X_test, theta0, theta1)

# Evaluating the model
print(list(y_test))
print(y_pred)
```

{% embed url="https://towardsdatascience.com/linear-regression-using-gradient-descent-97a6c8700931" %}



