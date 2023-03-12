---
description: https://www.coursera.org/learn/machine-learning/lecture/2f2PA/gradient-descent
---

# Gradient Descent

To find the min of the value for w and b, we can use gradient decent to systematically find the min value. This doesn't just apply to linear regression cost function.

To find the min J(w,b) we can start out as w and b ot be zero, Increment the value of w and b to find the min J(w,b).

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

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

$$
\
$$
