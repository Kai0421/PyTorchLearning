# Feature Engineering

Choice of the feature can have a huge impact on your learning algorithm's performance.

\[i.e.] On the housing model.

*   we can have the width and dept of the house of each to be its own feature. $$f_{\vec{w},b}(\vec{x}) = w_1x_1+w_2x_2 + b$$

    Where $$x_1$$-> depth $$x_2$$-> width
*   Instead we can find the area the house. $$area = depth * width$$

    we can then create a _ **new feature**_ call $$x_3 = x_1*x_2$$

    $$f_{\vec{w},b}(\vec{x}) = w_1x_1+w_2x_2+w_3x_3+ b$$
* Feature engineering: using intuition to design _**new feature**_, by _**transforming or combining**_ original feature.

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

## [Polynomial Regression](https://www.coursera.org/learn/machine-learning/lecture/OnGhN/polynomial-regression)

When data don't fits into a straight line but instead a curve such as $$x^2$$or $$x^3$$ function.&#x20;

So that the feature can be:

$$f_{\vec{w},b}(x) = w_1x+w_2x^2+ b$$\
OR\
$$f_{\vec{w},b}(x) = w_1x+w_2x^2+w_3x^3+ b$$

When using squaring or cubing the value feature scaling is much more important. So that the feature is in more comparable range of value.

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

### Choice of Feature

Useful alternative, is to use square root function. this become less steep but never completely flatten out and certainly never come back down.&#x20;

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>
