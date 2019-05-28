## Description

The Stephenson-Radny-Smith potential (SRS1996) is a three-body interatomic potential used to model free surface behavior of silicon. It is a generalized form of the classic Stillinger-Weber potential with four additional parameters to better match experimental observations and ab initio calculations of bond lengths and bond energies on the $7 \times 7$ unit cell of the (111)Si free surface.

## Functional Form

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

where $$r_{ij} = r_{ij}^{*}/\sigma$$ is the dimensionless distance between atoms $$i$$ and $$j$$.  For the pairwise term, the only difference between SRS1996 and Stillinger-Weber is in the numerator of the exponential function, which SRS1996 parameterizes as $$\zeta$$ and Stillinger-Weber uses a value of one.


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

and $$\theta_{ijk}$$ is the angle between the position vectors $$\mathbf{r}_{ji}$$ and $$\mathbf{r}_{jk}$$. This differs from Stillinger-Weber in the use of three additional parameters ($$b$$, $$k$$ and $$c$$) for the angular dependence. (The Stillinger-Weber formulation is obtained by setting $$b = 1$$, $$k = 1/3$$ and $$c = 0$$.) The use of these additional parameters in this model allows more flexibility in tuning the bond angles for modeling the behavior of free surfaces. Specifically the value $$k$$ determines the bond angle with the minimum energy according to

$$
\theta_{\mathrm{min}} = \cos^{-1} \left( -k \right).
$$


## Parameter Values

The model has eleven dimensionless parameters ($$A$$, $$B$$, $$p$$, $$q$$, $$\zeta$$, $$a$$, $$\lambda$$, $$b$$, $$k$$, $$c$$ and $$\gamma$$) and two characteristic dimensional scales ($$\epsilon$$ and $$\sigma$$). The authors chose the dimensional scales to be identical to those used in Stillinger-Weber. (Stillinger-Weber chose $$\epsilon$$ based on the enthalpy of atomization of silicon at $$T = 0 ~ \mathrm{K}$$ and $$\sigma$$ based on the equilibrium lattice spacing of silicon at $$T = 0 ~ \mathrm{K}$$. Note that there has been some variation in the precise value of $$\epsilon$$ from Stillinger-Weber due to a limited number of significant figures in the original parameter value and discrepancies in precise unit conversions. Here we use $$\epsilon = 2.1672 ~ \mathrm{eV}$$, which differs slightly from 2.1682 eV used elsewhere in OpenKIM and 2.1683 used in the LAMMPS model.)

The authors do not precisely state how the eleven dimensionless parameters were chosen, but instead state that they were chosen to fit a combination of bulk lattice dynamic properties, equilibrium geometries of free surfaces, and bond energies on free surfaces with the constraint that the diamond structure is the most stable phase. Upon stating the values of the coefficients, which are tabulated in Table 1 (along with reference values for Stillinger-Weber), the authors then compared computed results for bond lengths and bond energies based on SRS1996 with results from Stillinger-Weber, ab initio calculations \cite{brommer1992ab,vstich1992ab,van1988interaction} and experiments \cite{tong1988low}. These ab initio calculations and experiments presumably were used in the fitting of the parameters for SRS1996, but the method for doing so was not explained.

|-----------------+------------+-----------------+----------------|
| Parameter | SRS1996 | Stillinger-Weber|
|:--------:|:-------:|:--------:|
|$$A$$|6.8932|7.049 556 277|
|$$B$$|0.3535|0.602 224 558 4
|$$p$$|4|4
|$$q$$|0|0
|$$a$$|1.80|1.80
|$$\lambda$$|21.0|21.0
|$$\gamma$$|0.5778|1.20
|$$\zeta$$|0.7872|1
|$$b$$|0.0980|1
|$$k$$|0.0500|1/3
|$$c$$|-0.0324|0
|$$\sigma ~ [\text{Angstrom}]$$|2.0951|2.0951
|$$\epsilon ~ [\mathrm{eV}]$$|2.1672|2.1672


## Two-Body Term



## Three-Body Term




