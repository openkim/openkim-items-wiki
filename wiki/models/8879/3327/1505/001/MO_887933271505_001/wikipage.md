## Description
This **Model** implements the potential developed by R.A. Johnson for fcc metals as described in the reference above (see Source Citations). In particular, this model is applied to copper (Cu).

## Parameters
Symbols (matching the reference):

$$ r_{e}, \phi_e, \gamma, f_e, \beta, E_c, \alpha, \rho_e.$$

Corresponding variables in code:
JEAM\_R0, JEAM\_PHI0, JEAM\_GAM, JEAM\_G0, JEAM\_BET, JEAM\_EC, JEAM\_ALF, JEAM\_RHO0, 
where the prefix JEAM emphasizes the fact that each variable corresponds to the "Johnson Embedded Atom Potential".

Warning: The model uses other parameters DIM, SPECCODE and MODEL_CUTOFF denoting the dimensionality of the space (3 by default), the number of species (1, by default) and the cut-off radius (3.5 Angstrom by default), respectively. Default values have been hardcoded and, in principle, they should not be modified.

## Details

The total potential energy of a system of $$N$$ atoms is assumed to take the form $$E = \sum_{i=1}^N E_i$$, such that

$$E_i= \sum_{i=1}^N \left[F(\rho_i) + \frac{1}{2}\sum_{j=1}^m  \phi(r_{ij})\right],$$

and

$$\rho_i=\sum_{j=1}^m f(r_{ij}),$$

where $$E_i$$ denotes the energy per atom $$i$$, $$F(\rho_i)$$ is the embedding function contribution, $$\frac{1}{2}\sum_{j=1}^m  \phi(r_{ij})$$ is the two-body contribution to the energy, $$\rho_i$$ stands for the electron density at atom $$i$$, and $$f(r_{ij})$$ is the atomic electron density of atom $$j$$ as a function of the distance from its center $$r_{ij}$$, while $$j$$ is one of the $$m$$ neighbors of the atom $$i$$.

The electron density function is given by

$$f(r_{ij})=f_e\: e^{-\beta (r_{ij}/r_e-1)},$$

while the two-body potential is obtained from

$$\phi(r_{ij})= \phi_e\: e^{-\gamma(r_{ij}/r_e-1)}.$$

In both equations above, the distance between particles $$i$$ and $$j$$ must be smaller or equal to the cut-off (MODEL_CUTOFF). 

Finally, the embedding function is given by 

$$F(\rho_{ij})=-E_c\left[1-\frac{\alpha}{\beta}\:\text{ln}\left(\frac{\rho_{ij}}{\rho_e}\right)\right]\left(\frac{\rho_{ij}}{\rho_e}\right)^{\alpha/\beta}-6 \phi_e \left(\frac{\rho_{ij}}{\rho_e}\right)^{\gamma/\beta}.$$

Below we present plots for the functions electron density $$f(r_{ij})$$, potential $$\phi(r_{ij})$$ and the embedding function $$F(\rho)$$.  The parameters employed in these plots are:  $$\rho_e=2.556$$ [Angstrom], $$\phi_e =0.59$$ [eV], $$\gamma =8.00$$, $$F_e =0.30$$ [eV],
$$\beta =5.85$$, $$E_c=3.54$$ [eV/atom], $$\alpha =5.09$$, $$\rho_e =3.60$$ [eV] (i.e. $$\rho_0 =12*f_e$$).

![](/wimage/MO_887933271505_001/ibarr041/Electron_density_f_vs_radius)

![](/wimage/MO_887933271505_001/ibarr041/Potential_phi_vs_radius-v2)

![](/wimage/MO_887933271505_001/ibarr041/Embedding_function_F_vs_radius)

