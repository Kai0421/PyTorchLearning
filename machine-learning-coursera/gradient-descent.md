---
description: https://www.coursera.org/learn/machine-learning/lecture/2f2PA/gradient-descent
---

# Gradient Descent

To find the min of the value for w and b, we can use gradient decent to systematically find the min value. This doesn't just apply to linear regression cost function.

To find the minimum J(w,b) we can start out as w and b ot be zero, Increment the value of w and b to find the min J(w,b).

$$
W = w - \alpha {\frac d {dw}} J(w,b)
$$

* W - new w value
* w - old w value
* Alpha - learning rate (small positive number between 0-1)
* using the old w value and updating it to a small amount which is on the right expression&#x20;

$$
{\frac d {dw}} J(w,b)
$$

* This is the derivitive term for cost function J. Describe where the gradient descent wants to take the baby step.&#x20;
* With the alpha describe how big of a step to towards the direction.

$$
B = b - \alpha {\frac d {db}} J(w,b)
$$

To find the valley in the graph using gradient descent, repeat the calculation until the 2 points (w,b) converge. during the gradient descent process, it will need to simulataneously update w and b to a new value. **(Correct way)**

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

$$
\
$$

### Gradient Descent Intuition

Look into the derivative of the function of J which is the equation in the box:

$$
W = w - \alpha \boxed{{\frac d {dw}} J(w)}
$$

Is to draw a tangent line, which is a straight line that touches the curve at that point. The **Slope** of this line is the derivative of the **function J** at this point.&#x20;

To get the slope of the tangent, you can draw a line straight down and across to find the slope using pythagorus.&#x20;

<figure><img src="../.gitbook/assets/image (16) (1).png" alt=""><figcaption></figcaption></figure>

* When the tangent is pointing up and to the right, this means that the derivative is positive, so is greater than 0.

$$
W = w -\alpha(positiveNumber)
$$

This will give you a smaller number which in turn move the point to the left towards the lower value of w.

* When the Line is pointing up on the left this means that is has a negative slope.&#x20;

$$
W = w - \alpha(negativeNumber)
$$

This will end up increating the number of the value of w, this will get you closer to the min of of J(w)

### Learning Rate

<figure><img src="../.gitbook/assets/image (7) (2).png" alt=""><figcaption></figcaption></figure>

* Learning is too small, this will take baby steps to get to w. The outcome of the of the J(w), need alot of step to get to minimum.
* Learning rate is too large, this it will missed the minimum of w and move passed to w. It will progressively getting worst result

when gradient decent already reach local minimum. When the cost function have more than 1 local minimum.

<figure><img src="../.gitbook/assets/image (2) (2) (1).png" alt=""><figcaption></figcaption></figure>

When drawing a tangent line at the local minimum the slop will be 0, and therefore the gradient decent becomes:

$$
W = w - \alpha (0)
$$

This means that W = w, the old w is the same as the new W.  Then the gradient will do nothing. As the gradient descent getting closer and closer to the local minimum, each time it is taking smaller and smaller steps **eventhough the learning rate is kept at a fix value.**

## [Gradient descent for Linear Regression](https://www.coursera.org/learn/machine-learning/lecture/lgSMj/gradient-descent-for-linear-regression)

> _Using Gradient descent to minimize the cost function J(w,b) this in turns reduce the value w, b._&#x20;

The derivative of the w looks like this:&#x20;

$$
W = w - \alpha \boxed { {\frac d {dw}} J(w,b)} -> {\frac 1 m} \sum_{i=1}^m(f_{w,b}(x^{(i)}) -y^{(i)})x^{(i)}
$$

$$
B = b - \alpha \boxed { {\frac d {db}} J(w,b)} -> {\frac 1 m} \sum_{i=1}^m(f_{w,b}(x^{(i)}) -y^{(i)})
$$

There are more than 1 local mininum but there can be only 1 global minimum.

> _But turns out that using the squared error cost function there can be only be 1 single global minimum and there cannot have a local minimum. This is called a convex function._

<figure><img src="../.gitbook/assets/image (4) (3).png" alt=""><figcaption></figcaption></figure>

### [Batch Gradient Descent](https://www.coursera.org/learn/machine-learning/lecture/349Ay/running-gradient-descent)

* refers to the fact that on every step of the gradient descent, we're looking at all of the training examples, instead of just a subset of the training data. It uses all the training data.&#x20;

There are other gradient descent that doesnt look into the entire set of the training data.&#x20;

### Gradient Descent With Vectorization

#### Without vectorization example:

$$
w_1 = w_1 -0.1d_1 \\
w_2 = w_2-0.1d_2 \\
...
w_{16} = w_{16}-0.1d_{16}
$$

```python
for j in range(0, 16):
    w[j] = w[j] - 0.1* d[j]
```

#### With Vectorization

$$
\vec{w} = \vec{w} -0.1*\vec{d}
$$

```python
w = w -0.1 * d
```

### Gradient Descent With Multi linear regression

Previously:&#x20;

$$
w_j = w_j - \alpha {\frac \partial {\partial w_j}} J{(w_1,...w_n, b)}
$$

$$
b =b - \alpha {\frac \partial {\partial b}} J{(w_1,...w_n, b)}
$$

Now turns into:

$$
w_j = w_j-\alpha \boxed{{\frac \partial {\partial w_j}} J(\vec{w}, b)}
$$



This box turns into:

$$
w_1 = w_1 - \alpha \boxed{\frac 1 m \sum_{i=1}^m(f_{\vec{w},b}(\vec{x}^{(i)}) - y^{(i)})x_1^{(i)}} \\
... \\
... \\
w_n = w_n - \alpha \boxed{\frac 1 m \sum_{i=1}^m(f_{\vec{w},b}(\vec{x}^{(i)}) - y^{(i)})x_n^{(i)}} \\
$$

This is only where j = 1 which mean that this is only for 1 feature within the multiple feature.

$$
b = b -\alpha \boxed{{\frac \partial {\partial b}}J(\vec{w}, b)}
$$

This turns into:

$$
b = b -\alpha {\frac 1 m} \sum_{i=1}^m (f_{\vec{w}, b}(\vec{x}^{(i)}) -y^{(i)})
$$

<figure><img src="../.gitbook/assets/image (2) (2) (2).png" alt=""><figcaption></figcaption></figure>

### Alternative to gradient descent

* Normal equation
  * Only for linear regression to solve for w, b without iterations
* Disadvantage
  * Doesn't generalize to other learning algorithms.
  * Slow when number of feature is large ( > 10,000)
* What you need to know
  * Normal equation method may be used in machine learning libraries that implement linear regression.&#x20;
  * Almost no machine learning practitioners should implement the normal equation method themselves but if youre using a mature machine learning library and call linear regression, Theres a chance tht on the backend it will be using this to solve for w and b.

> _**Gradient descent is the recommended method for finding parameters w, b.**_&#x20;

## [Gradient In Practice](https://www.coursera.org/learn/machine-learning/lecture/KMDV3/feature-scaling-part-1)

Technique that make gradien descent works better:

1. Look at the relationship between the size of the feature that is how ig are the nuber for that feature and the size of it associated parameter.

\[i.e.] \
x1 - size(sure feet) range: 300 - 2000\
x2 - # bedrooms range: 0 - 5

In this case x1 has a large range of value and x2 has a small range of value

When the range of a parameters of the feature is relatively large, a good model is likely that the value for the w to be small. \


The key point is to rescale the x1 and x2 values, so that both are now taking comparable range of alues to each other. and if you run gradient descent on a const function to find on this. rescare x1 and x2 using this transformed data, then the contour graph will look morelike circles less tall and skinny. And gradient descent can find a much more direct path to the global minimum.

### Feature Scaling

One was to feature scale is to min < x1 < max&#x20;

$$
x_{j, scaled} = {\frac {x_j} {max}}
$$

This is one way of doing it to ensure the value are small between 0 to 1 but a better way to do it is to use mean normalization.&#x20;

### Mean normalization

This means that both of the value for x1 and x2 values are now centered around 0. Now they have both negative and positive values that maybe usually between -1 and +1.

* $$\mu_1$$is the average&#x20;

To normalize the value use this equation: $$\boxed{x_1 = \frac {x_1 - \mu_1} {max-min}}$$

Example:

$$
x_1 = \frac {x_1 - \mu_1} {2000 - 300}
$$

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

### Z-Score normalization

To get the z-score normalization you need the standard deviation $$\sigma$$.

$$
x_1 = \frac {x_1 - \mu_1} {\sigma_1}
$$

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

Rule of thumb:

1.  Aim for about $$-1 \le x_j \le 1$$for each feature $$x_j$$. But the -1 and + 1 value can be a bit loose If the value is in the range of:\
    $$-3\le x_j\le3$$

    $$-0.3\le x_j\le0.3$$

    _<mark style="color:yellow;">**This is all an acceptable range.**</mark>_\

2. $$0\le x_1 \le 3$$ Okay, no rescaling
3. $$-2\le x_2 \le 0.5$$ Okay, no rescaling&#x20;
4. $$-100\le x_3\le 100$$ Too large -> rescale so the range is between -1 to 1.
5. $$-0.001\le x_4\le0.001$$Too small -> rescale
6. $$98.6 \le x_5 \le 105$$ -  These Feature is around 100 which is bit too large may cause the gradient descent to work more slowly. Rescaling will help.

## [Checking Gradient Descent for convergence](https://www.coursera.org/learn/machine-learning/lecture/rOTkB/checking-gradient-descent-for-convergence)

To make sure gradient descent works correctly:&#x20;

plot a graph $$J(\vec{w}, b)$$vs number of iteration. This is also called a learning curve.\
This graph help you to see how your cost J changes over iterations gradient descent. If gradient descent is working properly, then the cost J should descrese after every single iteration. If J ever increases after 1 iteration, that means either the alpha is chosen poorly, and it usually mean alpha is too large. Or there could be a bug in the code.&#x20;

If the curve is stagnant and no longer decreasing, that means that the gradient descent is morely has converged.

iterations needed is varies, it maybe 30 or 1,000 or 100,000. That is why important to look at the learning curve to understand if the gradient descent has converged

### Automatic convergence test

Another good way to find out if the gradient descent has converged is to use the automatic convergence test.&#x20;

Lets $$\epsilon$$ "Epsilon" be $$10^{-3} / 0.001$$

If $$J(\vec{w}, b)$$, descreases by $$\le \epsilon$$in one iteration, _**declare convergence.**_

Convergence means hopefully you have found parameters w and b that are close to the minimum possible value of J. But usually find that choosing the right threshold epsilon is pretty difficult. tend to look at the graph like the one on the legt, rather than rely on automatic convergence tests.&#x20;

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>









&#x20;















