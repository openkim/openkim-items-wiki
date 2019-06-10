## Description

The [Stephenson-Radny-Smith potential](https://www.sciencedirect.com/science/article/pii/0039602896008011) (SRS1996) is a three-body interatomic potential used to model free surface behavior of silicon. It is a generalized form of the classic [Stillinger-Weber potential](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.31.5262) with four additional parameters to better match experimental observations and ab initio calculations of bond lengths and bond energies on the $$7 \times 7$$ unit cell of the (111)Si free surface.

## Functional Form

This model uses the [Stephenson-Radny-Smith model driver](https://openkim.org/id/ThreeBodyCluster_SRS__MD_814842199451_000).


## Parameter Values

The model has eleven dimensionless parameters ($$A$$, $$B$$, $$p$$, $$q$$, $$\zeta$$, $$a$$, $$\lambda$$, $$b$$, $$k$$, $$c$$ and $$\gamma$$) and two characteristic dimensional scales ($$\epsilon$$ and $$\sigma$$). The authors chose the dimensional scales to be identical to those used in Stillinger-Weber. (Stillinger-Weber chose $$\epsilon$$ based on the enthalpy of atomization of silicon at $$T = 0 ~ \mathrm{K}$$ and $$\sigma$$ based on the equilibrium lattice spacing of silicon at $$T = 0 ~ \mathrm{K}$$. Note that there has been some variation in the precise value of $$\epsilon$$ from Stillinger-Weber due to a limited number of significant figures in the original parameter value and discrepancies in precise unit conversions. Here we use $$\epsilon = 2.1672 ~ \mathrm{eV}$$, which differs slightly from $$\epsilon = 2.1682 ~ \mathrm{eV}$$ used elsewhere in the [OpenKIM model of Stillinger-Weber](https://openkim.org/id/SW_StillingerWeber_1985_Si__MO_405512056662_005) and $$\epsilon = 2.1683 ~ \mathrm{eV}$$ used in the [LAMMPS potential](https://github.com/lammps/lammps/blob/master/potentials/Si.sw).)

The authors do not precisely state how the eleven dimensionless parameters were chosen, but instead state that they were chosen to fit a combination of bulk lattice dynamic properties, equilibrium geometries of free surfaces, and bond energies on free surfaces with the constraint that the diamond structure is the most stable phase. Upon stating the values of the coefficients, which are tabulated in Table 1 (along with reference values for Stillinger-Weber), the authors then compared computed results for bond lengths and bond energies based on SRS1996 with results from Stillinger-Weber, ab initio calculations ([Brommer, et al. 1992](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.68.1355), [Stich, et al. 1992](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.68.1351) and [van den Hoek, et al. 1988](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.38.12508)) and experiments ([Tong, et al. 1987](https://avs.scitation.org/doi/abs/10.1116/1.575179)). These ab initio calculations and experiments presumably were used in the fitting of the parameters for SRS1996, but the method for doing so was not explained.

**Table 1: Parameter values for Stephenson-Radny-Smith and Stillinger-Weber**

|-----------------+------------+----------------|
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

The pairwise potential given by the functional form $$\phi_{2}$$ in conjunction with the parameters in Table 1 is plotted below. Curves for Stillinger-Weber and the Lennard-Jones potential are also plotted for reference. We note that both SRS1996 and Stillinger-Weber have a cutoff radius at $$r_{ij} = a = 1.8$$, but the Lennard-Jones potential has no inherent cutoff radius.

![](/wimage/MO_604248666067_000/bdruecke/pairwise_png)


## Three-Body Term
A contour plot of the three-body potential, $$h(r,s,\theta)$$ with parameter values in Table 1, for the case when $$r = s$$ is shown below. A contour plot for the Stillinger-Weber potential is also shown as a basis for comparison.

![](/wimage/MO_604248666067_000/bdruecke/three_body_png)

Finally, the figure below shows the effect of changing $$r$$ and $$s$$ independently in $$h(r,s,\theta)$$ while the angle is fixed at the tetrahedral angle, $$\theta = \cos^{-1} \left( -1/3 \right)$$. The results for both SRS1996 and Stillinger-Weber as a reference are shown. (Although the three-body potential energy of Stillinger-Weber is identically zero for the tetrahedral angle, $$\theta = \cos^{-1} (-1/3)$$, its contour plot is shown to emphasize the contrast with SRS1996.)

![](/wimage/MO_604248666067_000/bdruecke/three_body_tetrahedral_png)

## Summary

Perhaps the most significant departure of SRS1996 from Stillinger-Weber is the much shallower energy well in the three-body potential term as a function of the bond angle $$\theta$$. This makes sense in light of the fact that SRS1996 attempts to predict surface behavior, which is inherently anisotropic. Although the strong energy well at the tetrahedral angle, $$\theta \approx 109.5^{\circ}$$, makes sense for modeling of bulk phenomena using Stillinger-Weber, near the free surface bond angle energies depend on the orientation of the three atoms relative to the surface, and more flexibility in the changing of the bond angle becomes necessary. This increased flexibility in the rotational component of the three-body potential also explains why SRS1996 is not as good as Stillinger-Weber at predicting bulk phenomena. In short, Stillinger-Weber was fit to bulk crystal data and SRS1996 was fit to surface data (as well as some bulk data), and their respective accuracies for bulk versus surface phenomena reflect this.
