---
tags: [Control]
---
A PID or Proportional Integral Derivative controller is a combination of a [[Control/PD Controller]] and a [[PI Controler]], it consists of an integrator and two zeroes.

$$H(s)=\frac{C(s)}{E(s)} = K_p+\frac{K_i}{s}+Kds$$

The two zeroes are:
- PD zero for transient response
- PI zero near the origin
![[PID Controller Diagram.svg]]
We will use a PD first then a PI Controller.
In the exam the PI zero will be given so we will design the [[Control/PD Controller]] around that.

In general the PI Controller will increase settling time and reduce overshoot because of the addditional slow pole.