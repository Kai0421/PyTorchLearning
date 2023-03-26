---
description: https://www.coursera.org/learn/machine-learning/lecture/aoMt6/motivations
---

# Motivations

Classification - Logistics regression

**Binary classification**\
&#x20;means that there can only be yes and no or true or false

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

We can use Linear regression for it for binary classification because we cane have a malignant threshold to determined if the tumor is either malignant or benign. The linear regression can draw a straight line from the dataset.&#x20;

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

But if there is a data that is way across this will shift the line to shown in green, and a new threshold for determind if its malignant is not is also shifted. There for this makes the previous data that suppose to be as malignant and now it is no longer the case. This isnt want we want because the data should still be the same, it should change the previous result.&#x20;

Vertical Line - Decision Boundary.

### Classification / Logistics Regression

Sigmoid function or logistic function outputs between 0 and 1.&#x20;

$$
g(z) = \frac 1 {1 + \mathrm{e}^{-z}}
$$

When the _**z**_ value is large then the function _g(z)_ is going to be very close to 1. Example: \
1\. Where z = 100 $$g(z) \approx \frac 1 1$$\
2\. Where z = -100 $$g(z) \approx \frac 1 {bigValue} \approx 0$$

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

When z = 0 then $$g(z) = \frac 1 {1 + 1} = 0.5$$ That is why the sigmoid line crosses the y axis at 0.5.

### Build Logistic regression

$$
f_{\vec{w}, b} (\vec{x}) = z = \vec{w} \cdot \vec{x} + b
$$

$$
g(z) = \frac 1 {1 + \mathrm{e}^{-z}}
$$

$$
f_{\vec{w}, b}(\vec{x}) = g(\vec{w} \cdot \vec{x} + b) = \frac 1 {1 + \mathrm{e}^{-(\vec{w} \cdot \vec{x} + b)}}
$$

This equation thinking of calculating the probability of the class is 1.

Sometimes in research paper you will see this equation:&#x20;

$$
f_{\vec{w}, b}(\vec{x}) = P(y = 1 \mid \vec{x}; \vec{w}, b)
$$

This means that the the probability of y = 1 where given input feature x and with the parameters w and b. The semicolon denotes that w and b are parameters that affect this computation of what is the probability of y being equals to 1 given the feature input x.&#x20;

### Decision Boundary

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Example:&#x20;

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

$$Decision Boundary = z = \vec{w} \cdot \vec{x} +b$$

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

This is more a simple decision boundary where the boundary is linear where is splits between malignant tumor and non-malignant tumor.

#### Non-linear Decision Boundary&#x20;

using polynomial we can use that in here.&#x20;

$$
f_{\vec{w}, b}(\vec{x}) = g(z)=g(\overbrace{w_1x_1^2 +w_2x_2^2 + b}^z)
$$

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

using square and cube to get more complex decision boundary.&#x20;

