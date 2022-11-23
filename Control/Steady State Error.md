---
tags: [Control]
---
The steady state error refers to the difference between the desired input and the systems output at infinite time. The stea state error of a system will depend on the type of input (step, ramp, etc.) as well as the [[System Type]] (0, 1, 2, etc.)

## Steady state error for each system type
|Type|Step $\frac{1}{s}$|Ramp $\frac{1}{s^2}$|Parabola $\frac{1}{s^3}$|
|---|---|---|---|
|Type 0|$\frac{1}{1+K_g}$|$\infty$|$\infty$|
|Type 1|$0$|$\frac{1}{K_g}$|$\infty$|
|Type 2|$0$|$0$|$\frac{1}{K_g}$|
|Type 3+|$0$|$0$|$0$|

> [!QUOTE]+ ## Type 0 systems
> An open- loop system with no integrator (m=0) is type 0
> $$G(s)\triangleq\frac{K_g(1+T_as)(1+T_bs)\text{...}}{(1+T_1s)(1+T_2s)\text{...}}$$
> > [!EXAMPLE]+ ### Unit step
> > $$K_p = \lim_{s\to0} G(s)=K_g$$ So $$e(\infty)_{step}=\frac{1}{1+K_p}=\frac{1}{1+K_g}$$
>
> > [!EXAMPLE]+ ### Unit ramp
> > $$K_v = \lim_{s\to0} sG(s)=0$$ So $$e(\infty)_{ramp}=\frac{1}{K_v}=\frac{1}{0}=\infty$$
> 
> > [!EXAMPLE]+ ### Unit parabola
> > $$K_a = \lim_{s\to0} s^2G(s)=0$$ So $$e(\infty)_{parabola}=\frac{1}{K_a}=\frac{1}{0}=\infty$$

> [!QUOTE]+ ## Type 1 systems
> An open- loop system with exactly 1 integrator (m=1) is type 1
> $$G(s)\triangleq\frac{K_g(1+T_as)(1+T_bs)\text{...}}{s(1+T_1s)(1+T_2s)\text{...}}$$
> > [!EXAMPLE]+ ### Unit step
> > $$K_p = \lim_{s\to0} G(s)=\infty$$ So $$e(\infty)_{step}=\frac{1}{1+K_p}=0$$
> 
> > [!EXAMPLE]+ ### Unit ramp
> $$K_v = \lim_{s\to0} sG(s)=K_g$$ So $$e(\infty)_{ramp}=\frac{1}{K_v}=\frac{1}{K_g}$$
> 
> > [!EXAMPLE]+ ### Unit parabola
> $$K_a = \lim_{s\to0} s^2G(s)=0$$ So $$e(\infty)_{parabola}=\frac{1}{K_a}=\frac{1}{0}=\infty$$

> [!QUOTE]+ ## Type 2 systems
> An open- loop system with exactly 2 integrators (m=2) is type 2
> $$G(s)\triangleq\frac{K_g(1+T_as)(1+T_bs)\text{...}}{s(1+T_1s)(1+T_2s)\text{...}}$$
> > [!EXAMPLE]+ ### Unit step
> $$K_p = \lim_{s\to0} G(s)=\infty$$ So $$e(\infty)_{step}=\frac{1}{1+K_p}=0$$
> 
> > [!EXAMPLE]+ ### Unit ramp
> $$K_v = \lim_{s\to0} sG(s)=\infty$$ So $$e(\infty)_{ramp}=\frac{1}{K_v}=0$$
> 
> > [!EXAMPLE]+ ### Unit parabola
> $$K_a = \lim_{s\to0} s^2G(s)=0$$ So $$e(\infty)_{parabola}=\frac{1}{K_a}=\frac{1}{K_g}$$


