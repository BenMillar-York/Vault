---
tags: [Control]
---
The [[Polynomial]] $$G(s)=2s^4+3s^3+2s^2+4s+5$$
Would be entered into a Routh Array as seen below

||||
|---|---|---|---|
|$s^4$|2|2|5|
|$s^3$|3|4|0|
|$s^2$|c1||
|$s^1$|||
|$s^0$|||

The Routh array could then be completed using the following formula
$$\text{new element} = \frac{a_2b_1 - a_1b_2}{b1}$$
Or as in the above example
$$c1=\frac{2*3-2*4}{3}=\frac{6-8}{3}=\frac{-2}{3}$$

## Loci crossing imaginary axis
The Routh array can be found to find the imaginary axis crossing point of a [[Closed Loop]] transfer function
$$T(s)=\frac{Z(K)}{P(K)} \hspace{2cm} \text{This is the form of any closed loop function}$$

1) Entering the transfer function into the Routh Array
2) Setting the $s^1$ row to be equal to 0, by finding the value of K which makes it so
3) Creating an Auxillary [[Polynomial]] by reading the values of the Routh Array along the $s^2$ row, creating a new [[Polynomial]]
4) Solve this Auxillary [[Polynomial]] to find the two points where the loci crosses the imaginary axis.
### Example
$$T(s)=\frac{3K}{s^3+2s^2+s+4+3K}$$
Note: The $s^0$ term in the denominator [[Polynomial]] is 4+3K, as K is a constant.

We first enter the denominator [[Polynomial]] into the Routh Array, as seen below

||||
|---|---|---|
|$s^3$|1|1|0
|$s^2$|2|4+3K
|$s^1$|$\frac{2-(4+3K)}{2}$|0|
|$s^0$|||

We set the $s^1$ row equal to 0
$$0=\frac{2-(4+3K)}{2}$$
$$K=\frac{-2}{3}$$
We then create a new [[Polynomial]] using our value of K
$$2s^2+4+3(\frac{-2}{3})$$
$$=2s^2+2$$
We then solve this [[Polynomial]] to find that the axis crossing points are found at
$$s=\pm\sqrt{-1}$$
$$=\pm j$$
