# Logistic Regression

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
S(x)=\frac{1}{1+e^{-x}}
$$

### Python Implementation

```python
# Creating the logistic regression model

# Helper function to normalize data
def normalize(X):
    return X - X.mean()

# Method to make predictions
def predict(X, b0, b1):
    return np.array([1 / (1 + exp(-1*b0 + -1*b1*x)) for x in X])

# Method to train the model
def logistic_regression(X, Y):

    X = normalize(X)

    # Initializing variables
    b0 = 0
    b1 = 0
    L = 0.001
    epochs = 300

    for epoch in range(epochs):
        y_pred = predict(X, b0, b1)
        D_b0 = -2 * sum((Y - y_pred) * y_pred * (1 - y_pred))  # Derivative of loss wrt b0
        D_b1 = -2 * sum(X * (Y - y_pred) * y_pred * (1 - y_pred))  # Derivative of loss wrt b1
        b0 = b0 - L * D_b0
        b1 = b1 - L * D_b1
    
    return b0, b1
```

```python
# Training the model
b0, b1 = logistic_regression(X_train, y_train)

# Making predictions
# X_test = X_test.sort_values()  # Sorting values is optional only to see the line graph
X_test_norm = normalize(X_test)
y_pred = predict(X_test_norm, b0, b1)
y_pred = [1 if p >= 0.5 else 0 for p in y_pred]

plt.clf()
plt.scatter(X_test, y_test)
plt.scatter(X_test, y_pred, c="red")
# plt.plot(X_test, y_pred, c="red", linestyle='-', marker='o') # Only if values are sorted
plt.show()

# The accuracy
accuracy = 0
for i in range(len(y_pred)):
    if y_pred[i] == y_test.iloc[i]:
        accuracy += 1
print(f"Accuracy = {accuracy / len(y_pred)}")
```

{% embed url="https://towardsdatascience.com/logistic-regression-explained-and-implemented-in-python-880955306060" %}



