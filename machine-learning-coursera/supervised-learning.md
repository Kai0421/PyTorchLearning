# Supervised Learning

Refers to where an input value is mapped to an output label during training phased, and learn what is the right answer.&#x20;

* Regression Algorithm - task to predict number. \[i.e] housing price vs sqre feet
* Classification Algorithm - task to predict category/classes \[i.e] Cancer with class or malignant or benign. Classification predicts category in a small number of possible output and no anything in between

## Linear Regression Model

![](<../.gitbook/assets/image (11).png>)

From the all the data in the scatter graph plot, drew a straight line that best matches the data set. From the line it predicts the value of the \[i.e] housing price.

### Notation for the data (Terminology)

![](../.gitbook/assets/image.png)\
\
x = "input" variable feature. In this case it will be size in feet square which is the size of the house. \
\
y = "output" variable/ "target variable". This is the value the model will predict, which is the price of the house.\
\
m = number of training example\
\
(x,y) = single training example. For a single training example is a row from the table of the training data. where x (size in feet square), and y (price of the house)

$$
(x^{(i)}, y^{(i)})
$$

ith training example. Training set includes training features and targets.&#x20;

### Training model

![](<../.gitbook/assets/image (7).png>)\
Training set will feeds into the learning algorithm. Then the supervised learning algorithm will produce a function (f).\
\
x - refers to the training set.\
f -  refers to the function/ hypothesis (Model) to create predictions.\
ŷ (y-hat) - refers to the predicted value\
y - is refers to the true value, targets y

### How to represents f?

$$
f_w,_b(x) = wx+b => f(x) = wx +b
$$

This equation mean that the function takes the value, depends on the value w and b, f will output some value of prediction (ŷ)\
\
w,b can be remove and just mention f(x). And this can also be known as the line equation \[y = mx + c]. &#x20;

For this housing price problem example with 1 variable which is the size in feet square, this also know as linear regression with one variable / single feature or also know as **univariate linear regression**.

## Cost function formula

* w, b is called parameters. Parameters in machine learning is variable that can be adjusted when training the model.&#x20;
  * w - weight
  * b - bias

![](<../.gitbook/assets/image (2).png>)\
Think of **w** is the slope of the line and **b** is where the line starts.\
\
As is shown on the image above on the 3rd graph, where b = 1, the line value n the Y axis begins at 1.\
\
On the 1st graph it shows where **w** (slope) is 0, therefore the line is constant depends on what the **b**(y axis) value is.

### How to find the value for w,b?

#### Squared Error Cost function

$$
{m \atop \sum_{\substack{i = 1}}} ( ŷ^{(i)}  - y{(i)})^2
$$

Use this error function by using ŷ - y to be squared.\
&#x20;\- m : number of training data

But when the training size gets bigger, so does the cost function. To prevent this happening, we can compute the average sqre error instead of the total. But by convention we can divided by 2m to make the calculation abit neater.&#x20;

$$
J_{(w,b)}={\frac 1 {2m}}{m \atop \sum_{\substack{i = 1}}} ( ŷ^{(i)}  - y{(i)})^2
$$

But it will still work regardless if you divided by m or 2m.\
\
This square error cost function is by far the most commonly use for linear regression.&#x20;

$$
ŷ = f_{w,b}(x^{(i)})
$$

Therefore we can convert rewrite the equation to be:

$$
J_{(w,b)}={\frac 1 {2m}}{m \atop \sum_{\substack{i = 1}}} ( f_{w,b}(x^{(i)})  - y{(i)})^2
$$

## [Cost function intuition](https://www.coursera.org/learn/machine-learning/lecture/FthLz/cost-function-intuition)

![](<../.gitbook/assets/image (13).png>)\
we want to minimizeJ(w,b). To simplify the equation we can set b to be 0 and rewrite it to be :

$$
J_{(w)}={\frac 1 {2m}}{m \atop \sum_{\substack{i = 1}}} ( f_{w}(x^{(i)})  - y{(i)})^2
$$

![](<../.gitbook/assets/image (3).png>)\
Since b = 0, there for the graph is going through the origin when x = 0. \
\
This will just the adjust slope of the line.\
\
![](<../.gitbook/assets/image (9).png>)\
Image above shows that when the cost function is plot against (ŷ - y) the difference between the predicted value for (1,1) is 1-1=0 the sum of sqre(0) for 3 plot in the graph will show :

$$
= {\frac 1 {2m}}(0^2+0^2+0^2) = {\frac 1 {2m} * 0^2} = {\frac 1 {2(3)}*0^2} = {\frac1 6} * 0 = 0
$$

If w value is 0.5 \
![](<../.gitbook/assets/image (1).png>)\
\
By plugging in a different value for w this show a plot of J(w).\
![](<../.gitbook/assets/image (10).png>)\
\
This show on the graph on the right, just like a positive quadratic equation graph. \
\
How do u choose the J(w), by choosing the smallest y value, where the w is 1. Thats why when running the linear regression where u run the cost function to find the value of w that minimised J&#x20;

### [Visualizing the cost function](https://www.coursera.org/learn/machine-learning/lecture/QI1h6/visualizing-the-cost-function)

In the previous example where we set b value to 0, it shows in a shape of parabola. A U shape of the graph but when value of b is not 0 it will show a paraboloid shape image shown below.\
\
![](<../.gitbook/assets/image (8).png>)

