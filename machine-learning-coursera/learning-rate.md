# Learning Rate

Choosing appropriate learning rate:

From the learning curve. If you see if the line going up and down in the curve this is a sign that the gradient descent is not working. This could mean that there maybe bug in the code or the learning rate is too large.

Sometimes you see that the learning rate increases through iteration. Due to learning rate too large. Or possible bug in the code.&#x20;

#### Debug tip:

*   With small enough $$\alpha$$, $$J(\vec{w}, b)$$should descrese on every iteration. Set alpha to be very small number to see if J decreases in the graphs but if even if alpha is a very small value the learning rate is still going up that means theres a bug in the code.

    &#x20;

    <figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

When running gradient descent, usually use a range of alpha 0.001, 0,01, 0.1 or 1

Just running it a handful of iteration and look at the learning curve and choose a learning rate that descreases value rapidly and consistently.&#x20;

This helps to find the value that is too small and to large to understand the range. and we can find from that the value that work just right.\


<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>
