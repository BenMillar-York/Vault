---
aliases: [PC Control, PD Controllers]
tags: [Control]
---
A proportional derivate controller adds a pole at a desired location given by $\alpha$ for the required [[Settling Time]] and $\zeta$ for the [[Damping Ratio]].

The PD controller is used to improve the [[transient response]] of a system, make it respond quicker and have less [[overshoot]], however, it may introduce steady state error.

![[PD Controller Diagram.svg]]
$K_p$ is the Proportional Gain
$K_d$ is the [[Differentiator|Differential]] gain

## PD Controller Design
1) Plot open loop poles and zeros on an [[S-plane Plot]]
2) Establish desired [[closed loop]] pole position
3) Place on [[S-plane Plot]]
4) Draw lines from one desired pole position to all system poles and zeros
5) Establish angles and distances from known poles and zeros
 ![[PD Controller.svg]]
> [!TIP]+
> Angles should be taken from the real axis and can be found using
> $$\theta=\tan^{-1}(\frac{\text{opposite}}{\text{adjacent}})$$
> Or, if the angle is greater than $90\degree$ 
> $$\theta=180-\tan^{-1}(\frac{\text{opposite}}{\text{adjacent}})$$
> Lengths can be found by [[Pythagoras' Theorem]] 
> $$\text{length}=\sqrt{(x_2-x_1)^2+(y_2-y_1)^2}$$


6) Use [[Angle Crierion]] to establish controller the required controller zero angle to enable this desired pole location.
> [!INFO]+
> The angle criterion is defined as
> $$\sum\theta_z - \sum\theta_p = (2n+1)180\degree$$
> However, this often results in 
> $$\theta_z = \sum\theta_p-180\degree$$
![[PD Controller with Zero.svg]]
7) Establish controller zero position
   > [!TIP]+
   > This can be found using
   > $$\tan{\theta} = \frac{\text{opposite}}{\text{adjacent}}$$
   > Using the above example
   > $$\tan{\theta_z} = \frac{\text{2}}{\text{z-5}}$$
   > $$z = \frac{\text{2}}{\tan{\theta_z}}+5$$
8) Use gain rule [[Root Locus]] rule 12 to establish controller gain
9) Test [[closed loop| closed loop]] system behaviour