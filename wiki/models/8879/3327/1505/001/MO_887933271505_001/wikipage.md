## Description
This **Model** implements the potential developed by R.A. Johnson for fcc metals as described in the reference above (see Source Citations). In particular, this model is applied to copper (Cu).

## Parameters
Symbols (matching the reference):

$$ r_{1e}, \phi_e, \gamma, f_e, \beta, E_c, \alpha, \rho_e.$$

Corresponding variables in code:
JEAM\_R0, JEAM\_PHI0, JEAM\_GAM, JEAM\_G0, JEAM\_BET, JEAM\_EC, JEAM\_ALF, JEAM\_RHO0, 
where the prefix JEAM emphasizes the fact that each variable belongs to the "Johnson Embedded Atom Potential".

## Details

The total potential energy of a system of $$N$$ atoms is assumed to take the form $$E = \sum_{i=1}^N E_i$$, such that

$$E_i= \sum_{i=1}^N \left[F(\rho_i) + \frac{1}{2}\sum_{j=1}^m  \phi(r_{ij})\right]$$,
and
$$\rho_i=\sum_{j=1}^m f(r_{ij})$$,
where $$E_i$$ denotes the energy per atom $$i$$, $$F(\rho_i)$$ is the embedding function contribution, $$\frac{1}{2}\sum_{j=1}^m  \phi(r_{ij})$$ is the two-body contribution to the energy, $$\rho_i$$ stands for the electron density at atom $$i$$, and $$f(r_{ij})$$ is the atomic electron density of atom $$j$$ as a function of the distance from its center $r_{ij}$, while $$j$$ is one of the $$m$$ neighbors of the atom $i$.

The electron density function is given by

$$f(r_{ij})=f_e\: e^{-\beta (r_{ij}/r_e-1)}$$,

while the two-body potential is obtained from

$$\phi(r_{ij})= \phi_e\: e^{-\gamma(r_{ij}/r_e-1)}$$.

In both cases, for particles $$i$$ and $$j$$ such that their distance is below or equal to the cut-off $$r_c$$. 

Finally, the embedding function is given by 

$$F(\rho_{ij})=-E_c\left[1-\frac{\alpha}{\beta}\:\text{ln}\left(\frac{\rho_{ij}}{\rho_e}\right)\right]\left(\frac{\rho_{ij}}{\rho_e}\right)^{\alpha/\beta}-6 \phi_e \left(\frac{\rho_{ij}}{\rho_e}\right)^{\gamma/\beta}$$
