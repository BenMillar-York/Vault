### Backwards difference approximation
This approximates the gradient at a point to be the gradient between the current sample point and the previous sample point.

$$\left.\frac{d e(t)}{d t}\right|_{t = nT}\approx\frac{e(nT)-e((n-1)T)}{T}$$
$$=\frac{1}{T}(e_n-e_{n-1})$$
![[1st Approx Differential.svg]]
