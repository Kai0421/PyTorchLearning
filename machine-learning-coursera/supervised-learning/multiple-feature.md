---
description: >-
  https://www.coursera.org/learn/machine-learning/lecture/gFuSx/multiple-features
---

# Multiple Feature

## Multi Feature Variables

For denoting multiple feature we can use x subscript:

$$
X_j = j^{th} feature \\
n = number \cdot of \cdot feature\\
\vec{x^{I}} = feature-of-i^{th}-training-set
$$



* X(i) - in this case is consist of 4 numbers and sometimes this is called a vector. &#x20;

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

### Model:

Previously :&#x20;

$$
f_{w,b}(x) = wx +b
$$

Now:

$$
f_{w,b}(x) = (w_1\cdot x_1)+ (w_2 \cdot x_2) + (w_3 \cdot x_3) + (w_4 \cdot x_4 )+ b
$$

$$
\vec{w} = [w_1 w_2... w_n]
$$

$$
\vec{x} = [x_1x_2...x_n]
$$

* The arrow on top of the w is means vector. And this is a row vector.
* b is a number&#x20;

The Equation above and be rewritten as:&#x20;

$$
f_{(\vec{w}, b)} = \vec{w} \cdot \vec{x} + b
$$

### [Vectorization](https://www.coursera.org/learn/machine-learning/lecture/ismjc/vectorization-part-1)

#### Without vectorization with forloop

$$
f_{(\vec{w}, b)} = (\sum_{j=1}^n  \vec{w_j} \cdot \vec{x_j}) + b
$$

```python
f = 0
for j in range(n):
    f = f + w[j] * x[j]
f = f + b
```

This way is still not very efficient

#### With Vectorization

```python
f = np.dot(w,x)+b
```

This Numpy dot() function is natively built-in to numpy, is a vectorized implemetation of the dot product operation between 2 vectors and espeicially when n is large.&#x20;

> There are 2 distinct benefits using vectors. \
> &#x20; 1\.  It makes your code shorter
>
> 2. Resolving your code to run faster. The reason its able to run faster is because the Numpy dot() function able to use parallel hardware in your computer and this is true whether you're running this on a normal computer that is on a normal computer CPU or if you're using GPU.\
>    This makes it much more efficient than the for loop or the sequential calculation. &#x20;

<figure><img src="../../.gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>

### How do vectorization works

#### Without vectorization

```python
for j in range(0,16):
    f = f + w[j] * x[j]
```

T0:\
&#x20;    f + w\[0] \* x\[0]\
T1:\
&#x20;    f + w\[1] \* x\[1]\
....\
T15:\
&#x20;    f + w\[15] \* x\[15]

&#x20;This goes 1 step at a time at each step until it reaches 15.

#### With Vectorisation

```python
np.dot(w,x)
```

|       |       |     |        |
| ----- | ----- | --- | ------ |
| w\[0] | w\[1] | ... | w\[15] |
| \*    | \*    | \*  | \*     |
| x\[0] | x\[1] | ... | x\[15] |

This is implemented in computer hardware, so there computer can get all the values of the vectors w & x and in one single step, it can multiplies each pair of w & x with each other all at the same time in parallel. And it uses a specialilzed hardware to add all of them together very efficiently, rather than needing to carry out distinct addition one after the other.
