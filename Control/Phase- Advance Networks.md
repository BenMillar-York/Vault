---
aliases: [PAN, PAN Contol, PAN Controller, PAN Controllers, Phase- Lead Network, Phase-Advance Compensator]
tags: [Control]
---
Phase- Advance Networks are similar to [[Control/PD Controller|PD Controllers]], but have an additional filter pole $p_f$ this means they work much better in reality, as ideal [[Differentiator|Differentiators]], which [[Control/PD Controller|PD Controllers]] rely on do not exist in reality, as the noise from the signal will have a constantly changing gradient.

We can fix this issue by adding a filter just ahead of the controller. This is the equivalent of adding an additional pole $p_f$ to the controller. This will filter the error singnal $E(s)$.

This changes the [[Control/PD Controller|PD controller]] strcuture to
$$H(s)=\frac{K(s+z{pd})}{s+p_f}$$
Where $p_f > z_{pd}$ because the filter pole is chosen to be fast and we do not want it to [[Dominance|dominante]] the response.

This is know known as a Phase- Advance Network.

## Implementation
It is possible to implement a Phase- Advance Network passively as seen below.

![[Phase Advance Network Circuit.svg]]
$$\frac{Vout(s)}{Vin(s)}=(\frac{R_2}{R_1+R_2})(\frac{1+sCR_1}{1+sC\frac{R_1R_2}{R_1+R_2}})$$
## Advantages
- Reduced noise problems when compared with [[Control/PD Controller|PD Controllers]]
- More realistic- tends to work bettwe when implementedd in real systems
- Completely passive implementation (If the required gain K < 1)
## Disadvantages
- Doesn't reduce the excess of poles, so asymptotes are more likely to cross the imaginary axis
- More complex design procedure, as both the pole and the zero must be placed
- Available 'power' [[Angle Crierion|Angle Contribution]] reduced, so some specifications might be achievable for a [[Control/PD Controller]] but not for a [[Phase- Advance Networks|PAN]].

## PAN Design
- The compensator pole and zero are linked.
	- Together they must contribute the correct angle to satify the [[Angle Crierion]] at the desired pole location.
	- If the zero moves to the left, the pole must move to the left, and vice- versa
- Design starts by arbitrarily choosing a zero position
- A good first guess is often to the **place the compensator zero underneath the desired pole location**
- Then, calculatedd the compensator pole to satisfy the [[Angle Crierion]] at the desired [[Closed Loop|closed- loop]] pole location
- Find the gain, [[Closed Loop|close the loop]], check the step response
- If it is not satisfactory, work out why not
- Move the zero to the left or right as necessary, and try again


> [!example]+
> Design a [[Unity Negative Feedback]] control system using a [[Phase- Advance Networks| Phase- Advance Network]]
> for the system
> $$G(s)=\frac{100}{2s^2+5s}$$
> such that the [[Closed Loop|closed- loop]] system has the following characteristics:
> - Less than 10% [[Overshoot]] to a unit step input
> - A [[Settling Time]] $T_s$ < 3 seconds
> 1) Find desired [[Closed Loop|closed- loop]] pole positions 
>    - $\alpha = \frac{4}{3}$. Therefore [[Closed Loop|closed- loop]] poles need to be to the left of $\frac{-4}{3}$
>   - 10% [[Overshoot]] is $\zeta \approx 0.5912$, as $\cos^-1\zeta \approx 53.75\degree$
>   - We know that the phase- advance zero will increase the [[Overshoot]] we get so we should use an value for $\theta < 53.75\degree$
>  - We will therefore set the desired [[Closed Loop|closed- loop]] pole as $-2\pm2j$
> 2) Plot the open- loop poles and zeroes as well as the desired pole and the compensator zero on an [[S-plane Plot]]
> ![[PAN S-Plane.excalidraw.svg]]
> 3) Pole angle contributions are $-135\degree$ and $-76\degree$. Zero angle contribution is $+90\degree$.
>    Total is $-121\degree$, therefore compensator pole must add $-59\degree$.
>  4) Find the compensator pole location using$$\tan59\degree\approx\frac{2}{p-2}$$
>     $$p\approx3.2$$
>  5) Plot this new compensator pole and find the distances between the desired pole and all other poles and zeros.
>  6) Find the [[Monic Form]] gain, using [[Root Locus]] rule 12
>     $$K_m = \frac{\prod \text{finite pole lengths}}{\prod \text{finite zero lengths}}$$
>      $$K_m = \frac{2.83*2.33*2.06}{2}\approx6.8$$
>   7) Find the additional required by dividing $K_m$ by the already present [[Monic Form]] gain on $G(s)$, which in this case is $\frac{100}{2} = 50$
>      $$\frac{6.8}{50}\approx0.136$$
>  8)The controller transfer function will then be given by 
>     $$H(s)=K\frac{s+z_d}{s+p_c}$$
>     $$H(s)=0.136\frac{s+2}{s+3.2}$$



