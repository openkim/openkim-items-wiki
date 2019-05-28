## Description

The Stephenson-Radny-Smith potential (SRS1996) is a three-body interatomic potential originally developed to model free surface behavior of silicon. It is a generalized form of the classic Stillinger-Weber potential (SW1985) with four additional parameters to allow for better tuning of free surface behavior. It was originally created to better match experimental observations and ab initio calculations of bond lengths and bond energies on the $$7 \times 7$$ unit cell of the (111)Si free surface.

## Parameters
The model has eleven dimensionless parameters ($$A$$, $$B$$, $$p$$, $$q$$, $$a$$, $$\lambda$$, $$\gamma$$, $$\zeta$$, $$b$$, $$k$$ and $$c$$) and two characteristic scales ($$\sigma$$ the characteristic interatomic spacing, and $$\epsilon$$ the characteristic energy).

## Function
The generic model of potential energy for a three-body potential composed of $$N$$ atoms is

$$\mathcal{V}_{(N)}^{\mathrm{int}} = \epsilon \phi_{0} + \frac{1}{2!}\sum_{\begin{array}{c}i,j\\i\neq j\end{array}}^{N}{\epsilon \phi_{2} \left( \frac{r_{ij}^{*}}{\sigma} \right)}
+ \frac{1}{3!}\sum_{\begin{array}{c}i,j,k\\i\neq j \neq k\end{array}}^{N}{\epsilon \phi_{3} \left( \frac{r_{ij}^{*}}{\sigma}, \frac{r_{jk}^{*}}{\sigma}, \frac{r_{ki}^{*}}{\sigma} \right)}$$

where $$\phi_{0}$$ accounts for the number of particles in the system but is independent of their positions, $$\phi_{2}$$ is the pairwise potential and $$\phi_{3}$$ the three-body potential. The dimensional lengths, $$r_{ij}^{*}$$, are non-dimensionalized with the charactersitic interatomic spacing $$\sigma$$, and the energies are non-dimensionalized with the characteristic bond energy $$\epsilon$$.

For SRS1996 (as well as the classic Stillinger-Weber potential), the pairwise term is

$$
\phi_{2}(r_{ij}) = \left\{
\begin{array}{lr}
\displaystyle
A \left( \frac{B}{r_{ij}^{p}} - \frac{1}{r_{ij}^{q}} \right) \exp \left( \frac{\zeta}{r_{ij} - a} \right), & r_{ij} \le a
\\
0,& \mathrm{otherwise}
\end{array}
\right.
$$

where $$r_{ij} = r_{ij}^{*}/\sigma$$ is the dimensionless distance between atoms $$i$$ and $$j$$.  The only difference between SRS1996 and Stillinger-Weber is in the numerator of the exponential function, which SRS1996 parameterizes as $$\zeta$$ and Stillinger-Weber uses a value of one.


The functional form of the three-body potential for SRS1996 is

$$
\phi_{3}(r_{ij},r_{jk},r_{ki}) = h\left(r_{ij},r_{ik},\theta_{jik} \right)
+ h\left(r_{ij},r_{kj},\theta_{ijk} \right)
+ h\left(r_{ik},r_{kj},\theta_{ikj} \right)
$$

where

$$
h(r,s,\theta) = \left\{ \begin{array}{lr}
\displaystyle
\lambda \left( b \left( \cos \theta + k \right)^{2} - c \right) \exp \left( \gamma \left( \frac{1}{r - a} + \frac{1}{s-a} \right) \right),
&r ~ \mathrm{and} ~ s \le a
\\
0,&  \mathrm{otherwise}
\end{array} \right.
$$

and $$\theta_{ijk}$$ is the angle between the position vectors $$\mathbf{r}_{ji}$$ and $$\mathbf{r}_{jk}$$. This differs from Stillinger-Weber in the use of three additional parameters ($$b$$, $$k$$ and $$c$$) for the angular dependence. (The Stillinger-Weber formulation is obtained by setting $$b = 1$$, $$c = 0$$ and $$k = 1/3$$.) The use of these additional parameters in this model allows more flexibility in tuning the bond angles for modeling the behavior of free surfaces. Specifically the value $$k$$ determines the bond angle with the minimum energy according to

$$
\theta_{\mathrm{min}} = \cos^{-1} \left( -k \right).
$$
