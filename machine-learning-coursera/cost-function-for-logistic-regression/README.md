---
description: >-
  https://www.coursera.org/learn/machine-learning/lecture/0hpr8/cost-function-for-logistic-regression
---

# Cost function for Logistic regression

Previously for linear regression we use Squared error cost function to the min $$f_{\vec{w}, b}(\vec{x})$$, for linear regression is workst because that it creates a convex graph when gradient decent was applied but for logistics regression this creates a non-convex graph, which contain lot of local minima which gradient decent will have a hard time getting out of.&#x20;

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

There will be a different the functionw ill make it convex again.&#x20;

$$
J_{\vec{w}, b} = \frac 1 m \sum_{i=1}^m \boxed{\frac 1 2 (f_{\vec{w}, b}(\vec{x^{(i)}}) - y^{(i)})^2}
$$

$$
L(f_{\vec{w}, b}(\vec{x^{(i)}}), y^{(i)}))
$$

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### Logistic loss function

$$
L(f_{\vec{w}, b}(\vec{x^{(i)}}), y^{(i)})) = \begin{cases} -log(f_{\vec{w}, b}(\vec{x^{(i)}})) &\text{ if } y^{(i)} = 1 \\

-log(1 - f_{\vec{w}, b}(\vec{x^{(i)}})) &\text{ if } y^{(i)} = 0 

\end{cases}
$$

<figure><img src="../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

*   Loss is lowest when $$f_{\vec{x},b}(\vec{x}^{(i)})$$predicts close to true label $$y^{(i)}$$



<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

* So When $$f_{\vec{x},b}(\vec{x}^{(i)})$$-> 0 or close to 0 then the loss -> 0
* But when $$f_{\vec{x},b}(\vec{x}^{(i)})$$-> 1 or close to 1, then it penalize the model to the lose will be ->$$\infin$$
*   The further prediction $$f_{\vec{x},b}(\vec{x}^{(i)})$$is from the target $$y^{(i)}$$, the higher the loss.



Using this loss function to create a convex graph, this will allow you to use gradient descent.&#x20;

### Simplify Loss function

&#x20;

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

$$
L(f_{\vec{w}, b}(\vec{x^{(i)}}), y^{(i)}) = -y^{(i)}log((f_{\vec{w}, b}(\vec{x^{(i)}})) - (1 - y^{(i)} )log(1 - (f_{\vec{w}, b}(\vec{x^{(i)}}))
$$

$$
J(\vec{w}, b) = \frac 1 m \sum_{i = 1}^m [L(f_{\vec{w}, b}(\vec{x^{(i)}}), y^{(i)})]
$$

$$
J(\vec{w}, b) = \frac 1 m \sum_{i = 1}^m [-y^{(i)}log((f_{\vec{w}, b}(\vec{x^{(i)}})) - (1 - y^{(i)} )log(1 - (f_{\vec{w}, b}(\vec{x^{(i)}}))]
$$

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>



