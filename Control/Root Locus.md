---
tags: [Control]
---
The Root [[Locus]] is a graphical method for examining how the roots of a [[Closed Loop |closed loop]] transfer function change when controlled by a simple gain, K.

All points on a root [[locus]] meet the [[Angle Crierion]]

# Plotting Rules
1) Loci start at open loop poles $K=0$ and end at open loop zeros $K=\infty$.
2) If the number of open loop poles exceeds the number of open loop zeros, then the excess of poles migrate to zeros at $\infty$ and do so along asymptoes.
3) The [[locus]] lies along the real axis wherever the sum of poles are zeros to the right is doo.
4) The root [[locus]] diagram is symmetrical about the real axis.
5) The loci terminsating at zeroes at $\infty$ tend towards asymptotes having directions acording to $$\theta_a=\frac{(2n+1)180^\degree}{\text{excess of poles}} \hspace{3cm} n = (0,1,2)$$
6) The asymptotes intersect on the real axis at a centre of gravity, given by $$S_cg = \frac{\sum poles - \sum zeros}{\text{excess of poles}}$$
7) Dual (complex) root [[locus]] branches depart from or arrive at the real axis at $\pm90\degree$
8) The break- away/ break-in points for complex branches on the real axis are found by solving for s in the following equation: $$\sum_{i=1}^m \frac{1}{s-z_i}=\sum_{i=1}^n \frac{1}{s-p_i}$$
> [!TIP]+ Addditional technique
> Or, if there are no zeros, setting the differential of the denominator of the open loop gain equal to 0 will also reveal the break- away/ break-in points.
> I.e. $$G(s)=\frac{1}{s^2+3s+4}$$
> Break away/ break in points can be found at
> $$0=\frac{d}{ds}s^2+3s+4$$
> $$=2s+3$$
> $$\therefore s=-\frac{3}{2}$$
9) To find the angle of departure of the [[locus]] from a complex pole, consider the total angle contributions from each open loop zero and the remaining open loop poles as follows: $$\theta_{p1}=\sum\theta_z-\sum\theta_p\pm180\degree$$
10) To find the angle of arrival at a finite complex zero: $$\theta_{z1}=\sum\theta_p-\sum\theta_z\pm180\degree$$
A rule of thumb for remembering these rules is:
$$\sum\text{not like} - \sum{\text{like}}$$
All angles are taken from the positve real axis to the point in question.
11) Imaginary axis crossings are found using the [[Routh Array]] and the Routh- Hurwitz stability criterion.
12) The [[monic form]] gain constant, $K_m$, for any point on the [[locus]] is found using: $$K_m = \frac{\prod\text{finite pole lengths}}{\prod\text{finite zero lengths}}$$
When finding the required additional gain you need to divide $K_m$ by the [[Monic Form]] gain already present on the system.