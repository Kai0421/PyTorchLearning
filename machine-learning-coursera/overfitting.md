# Overfitting

## Regularization

This is a technique helps to minimise overfitting.

Generalization - generally you want the model generalize well.&#x20;

&#x20;

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

* Under fit  / high bias
* Just right/ Generalisation
* Overfit/ high variance

### How address overfit models

* _**Collect more training data**_&#x20;
* _**Use fewer features**_ - if theres alot of features but insufficient data will over fits the model. Use your intuition to find which features you need to use.&#x20;
* _**Regularization**_ - What regularization does is encourage the learning algorithm to shrink the values of the parameters without necessarily demanding that the parameter is set to exactly 0.

## Regularization

Modify the cost function adding a large number to $$1000w_3^2 + 1000w_4^2$$, with this the model basically penalize the model when the $$w_3^2$$and $$w_4^2$$is large. So when minimize this function, you're going to end up witth w3 and w4 close to 0. So we are effectively nearly cancelling out the effect off the feature execute and exttra power of 4 and getting rid of these two terms over here.

#### How to implemented

Is to penalize all the $$w_j$$features, shrink them by a bit using this equation.

$$
J_{(\vec{w}, b)} = \frac 1 {2m} \sum_{i = 1}^m (f_{\vec{w}, b}(\vec{x^{(i)}}) - y^{(i)})^2 + \
\overbrace{\frac \lambda {2m} \sum_{j=1}^n w_j^2 }^{\text{Regularization term}}
+ \underbrace{\frac \lambda {2m}b^2}_{\text{ can be include or exclude}}
$$

The reason why we have $$\frac \lambda {2m}$$is because we want to scale the same as . When we scale it the same way its easier to choose the value for lambda.

* $$\lambda$$ is the regularization parameter $$\lambda > 0$$
* If you set lambda to 0 then you're not using the regularization at all. Which then cause the model to _**overfit**_ when theres too many features or not enough sample data.
* But you set the lambda value to to be some large number, the you're place in alot of heavy weight on to the regularization function. Thus f(x) becomes b then makes your model _**under fits.**_

## [Regularization linear regression](https://www.coursera.org/learn/machine-learning/lecture/WRULa/regularized-linear-regression)

$$
J_{(\vec{w}, b)} = \frac 1 {2m} \sum_{i = 1}^m (f_{\vec{w}, b}(\vec{x^{(i)}}) - y^{(i)})^2 + \
\overbrace{\frac \lambda {2m} \sum_{j=1}^n w_j^2 }^{\text{Regularization term}}
$$

So when we are using the regularization to calculate the cost of J. we also need to update the way we calculate gradient descent.&#x20;

### Gradient Descent

$$
W = w - \alpha \boxed { {\frac d {dw}} J(w,b)} -> {\frac 1 m} \sum_{i=1}^m[(f_{w,b}(x^{(i)}) -y^{(i)})x^{(i)}] + \frac \lambda m w_j
$$

* Using $$\frac \lambda m w_j$$this will minimize the value for $$w_j$$

$$
B= b - \alpha \boxed { {\frac d {db}} J(w,b)} -> {\frac 1 m} \sum_{i=1}^m(f_{w,b}(x^{(i)}) -y^{(i)})
$$

* We don't modify the gradient descent calculation for b because we dont want to minimize the value b.

Rearranging the equation for minimizing W

$$
W_j = w_j (1 - \alpha \frac \lambda m) - \alpha \frac 1 m \sum_{i =1^m} (f_{\vec{w}, b}(\vec{x^{(i)}}) - y^{(i)})x_j^{(i)}
$$

### Regularize Logistics Regression

$$
J(\vec{w}, b) = - \frac 1 m \sum_{i =1 }^m[y^{(i)}log(f_{\vec{w}, b}(\vec{x})) + (1 - y^{(i)})log(1 - f_{\vec{w}, b}(\vec{x^{(i)}}))] + \frac \lambda {2m}\sum_{j=1}^n w_j^2
$$

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

In the gradient descent, formular is the same for the linear regression is just the f(x) is different.&#x20;
