We can implement [[PID Controller|PID Controllers]] digitally using [[Integration]] and [[Differentiator|Differentiators]] approximations.

The standard parallel- form PID controller is specified as
$$H(s)=\frac{C(s)}{E(s)} = K_p+\frac{K_i}{s}+Kds$$
Then the time- domain PID control law is
$$C(s)=H(s)E(s)$$
$$\mathscr{L}^{-1}\{C(s)\}=c(t)=K_pe(t)+K_i\int_{0}^{t}e(\tau)d\tau+K_d\frac{de(t)}{dt}$$
This means we need to find $e(t)$, the error term, the [[Derivative]] of $e(t)$ and the [[Integration|Integral]] of $e(t)$

## Sampling of $e(t)$
As digital signals must be sampled rather than expressed continuously the error signal must be sampled at regular intervals.

This gives readings of the error signal, $e(t)$ at discrete time intervals $t=nT$, where n is an integer.
The sample rate must be chosen to:
- Be frequent enough to satify [[Nyquist–Shannon sampling theorem|Shannon's sampling theorem]] (Sample rate at least double the highest frequency in the signal).

We will use the notation $e_n$ to represent $e(t) at time $t=nT$.

### Benefits of increasing the sample rate
- The [[Derivative|derivative]] approximation becomes more accurate
- The [[Integration|integration]] approximation becomes more accurate
- Delays are reduced, so the system [[Control/Phase Margin|phase margin]] is eroed less
### Problems with increasing the sample rate
- Increased computational effort
- Greater problems from numerical precision and rouding errors
	- As $T$ becomes very small, the [[dynamic range]] of the computer values will increase
- Greater susceptibility to noise in the [[Derivative|derivative]] calculation
	- As $\frac{1}{T}$ becomes very large, tiny variations can lead to very large derivative estimates

## Differentaial of $e(t)$
The simplest method of finding an approximation for the differential at the point $e(t)$ can be found using the [[Backwards- difference approximation]].
$$d_n = \frac{1}{T}(e_n-e_{n-1})$$

### Integral of $e(t)$
We can approximate the integral from $0$ to a point $t$ of $e(t)$ but using either:
- [[Rectangular approximation]]
- [[Trapezoidal approximation]]
We can then express the integral term as a [[Recurrence Relation]].

For the [[Rectangular approximation]], if 
$$i_n=\sum_{k=0}^ne_kT$$
then
$$i_n-i_{n-1}=e_nT$$
Where $i_0 = 0$

For the [[Trapezoidal approximation]], if
$$i_n = \sum_{k=1}^n(\frac{e_k+e_{k-1}}{2}T)$$
then
$$i_n-i{n-1}=\frac{e_n+e{n-1}}{2}T$$
$$i_n=i{n-1}+\frac{e_n+e{n-1}}{2}T$$
Where $i_0=0$

## Digitial PID control
Putting these terms together gives a simple algorithm for inital [[PID Controller|PID control]]
#### Initialisation:
- Set $e{n-1}=i_{n-1}=0$
#### Every sample:
- Read $e_n$
- Compute the [[Derivative|derivative]] $d_n = \frac{1}{T}(e_n-e_{n-1})$
- Update the [[Integration|integral]] $i_n=i_{n-1} + e_nT$ or $i_n=i_{n-1}+\frac{T}{2}(e_n+e_{n-1})$
- Compute the controller output $c_n=K_pe_n+K_ii_n+K_dd_n$
- Store $i_{n-1}=i_n$ and $e_{n-1}=e_n$ for next iteration

## Other digital controllers
It is possible to implement other stuctures, such as [[Phase- Advance Networks|PANs]] and phase- lag networks, digitially.

### Implementation method
- Start with a controller transfer function
- Express it as the ratio of the controller output $C(s$) to the error signal $E(s)$
- Rearrange to eliminate the fractions
- Multiply out all the brackets
- Substitute sampled signals and suitable derivative approximations
- Rearrange to find recurrence relations

We can do this with [[PI Controler|PI]] and [[PID Controller|PID controllers]], but the integration is effectively always rectangular, so the explicit technique is better.

>[!EXAMPLE]+
>Consider the [[Phase- Advance Networks|phase- advance network]]
>$$H(s)=\frac{C(s)}{E(s)}=10.2\frac{s+5}{s+11.6}$$
>
>1) Eliminate the fractions and expand
>   $$\frac{C(s)}{E(s)}=10.2\frac{s+5}{s+11.6}$$
>   $$(s+11.6).C(s) = 10.2(s+5).E(s)$$
>   $$sC(s) + 11.6C(s) = 10.2sE(s) + 51E(s)$$
> 2) Substitute - This moves form the [[Frequency Domain|Laplace Domain]] to the time domain
>    $$C(s) \to c_n$$
>$$sC(s) \to \frac{1}{T}(c_n-c_{n-1})$$
>$$E(s) \to e_n$$
>$$sE(s) \to \frac{1}{T}(e_n-e_{n-1})$$
> $$\frac{1}{T}(c_n-c_{n-1}) + 11.6c_n = 10.2*\frac{1}{T}(e_n-e_{n-1})+ 51e_n$$
> 3) Rearrange
> $$(11.6+\frac{1}{T})c_n-\frac{1}{T}c_{n-1}=(\frac{10.2}{T}+51)e_n-\frac{10.2}{T}e_{n-1}$$
> $$c_n=(\frac{T}{11.6T+1})(\frac{51T+10.2}{T}e_{n}-\frac{10.2}{T}e_{n-1}+\frac{1}{T}c_{n-1})$$
> $$=(\frac{T}{11.6T+1})((51T+10.2)e_n-10.2e_{n-1}+c_{n-1}$$
> Note that all coefficients are constant are can be pre- calculated
> 4) At 10Hz, $(T=0.1)$
> $$c_n=(\frac{1}{11.6T+1}((51T+10.2)e_n-10.2e_{n-1}+c{n-1}$$
> $$=\frac{1}{2.16}(15.3e_n-10.2e_{n-1}+c_{n-1})$$
> This is a recursive digital filter, and is smple to implement algorithmically
> 




