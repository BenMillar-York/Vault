---
aliases: [Differentiators]
tags: [Control]
---
In electronics a differentation is a curciut that is designed such that the output of the circut is approximately directly proportional to the rate of change (The [[Derivative]]) of the input.


In the [[Frequency Domain|Laplace Domain]] a differentator is a multiplication by s.

## In a circuit
![[Differentiator.svg|500]]
$$\frac{R}{\frac{1}{sC}}=sCR$$
This is a multiplication by s in the [[Frequency Domain|Laplace Domain]] and therefore Vout is the differential of Vin.

## In reality
In reality an ideal differentiator cannot exist, this is because the gradient of a real signal will always be varying due to noise, a differentation therefore will amplify this noise.