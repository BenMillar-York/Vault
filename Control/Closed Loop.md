---
aliases: [Close the loop, closed- loop, close the loop]
tags: [Control]
---
## In general
$$H(s)=\frac{Z_c(s)}{P_c(s)}$$
$$G(s)=\frac{Z(s)}{P(s)}$$
$$T(s)=\frac{Z_c(s)Z(s)}{P(s)P_c(s)+Z(s)Z_c(s)} $$

## Simple gain
To close the loop of a transfer function with Unity Negative Feedback, and a simple gain $H(s) = K$ simply multiply the numerator by the controller $H(s)$ and add the resulting numerator to the denominator.
### Open Loop gain
$$G(s)=\frac{3}{s^2+4s+2}$$
### Closed loop with H(s) = K
$$T(s)=\frac{3K}{s^2+4s+2+3K}$$
Remember that since K is a constant we can write $T(s)$ as
$$T(s)=\frac{3K}{s^2+4s+(2+3K)}$$

