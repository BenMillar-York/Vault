---
tags: [Control]
---
A PI Controller is a proportional an integral controller. It tries to improve a systems steady state error by increasing the [[System Type]], however, it will also negatively affect the transient response by increasing the [[Settling Time]].

![[PI Controller Diagram.svg]]

## PI Controller Design
1) Find a simple gain using [[root locus]] diagram
2) Place a pole on the origin
3) Place a zero close to it
4) Test [[Closed Loop| closed loop]] system behaviour
5) If slow pole [[Dominance|dominated]], try moving the zero further left
6) Repeat until desired performance is achieved or zero cannot move further