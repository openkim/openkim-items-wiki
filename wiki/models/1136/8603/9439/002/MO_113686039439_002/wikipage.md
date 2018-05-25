## Parameter Choices in the SW Potential

In the original Stillinger-Weber paper (SW85: PRB 31:5262, 1985) it is stated that in order to obtain the correct “atomization energy” (cohesive energy) the following choice for epsilon must be made (see Eqn. (2.9) in [SW85]):

epsilon = 50 kcal/mol = 3.4723E-12 erg/atom

There are some unit conversion issues related to this data (see <https://openkim.org/cite/MO_405512056662_003>). However, a more fundamental problem is that in [SW85] the potential is fitted to an incorrect value for the cohesive energy of silicon. Using Eqn. (2.8) in [SW85], the cohesive energy corresponding to epsilon = 2.1682 eV (corresponding to 50 kcal/mol) is

E_coh = 2.168205112 eV x 1.999993 = 4.33639505 eV

However, the accepted experimental value for E_coh for silicon in the diamond structure is 4.63 eV. (See for example, B. Farid and R. W. Godby, "Cohesive energies of crystals", Phys. Rev. B, vol 43, 14248-24250, 1991). 

This discrepancy led Balamane, Halicioglu and Tiller in their review article of silicon potentials (H. Balamane, T. Halicioglu and W. A. Tiller, "Comparative study of silicon empirical interatomic potentials", Phys. Rev. B, vol. 46, 2250-2279, 1992) to rescale the SW epsilon parameter to 2.315 eV which reproduces the experimental cohesive energy.

It is important to realize that the rescaled potential is completely different from the original SW potential. It will have different forces, different elastic constants, different activated processes, etc. Only equlibrium structures will be the same. Unfortunately, Balamane et al. did not state in their article that this rescaling was performed which has led to some confusion. (The fact that a rescaling was done was mentioned in an earlier article by the authors, Balamane et al., Phys. Rev. B, vol 40, 9999-10001. See last paragraph on p.9999.)

Balamane et al.'s rescaled SW potential may have merit, but it should not be confused with the original SW potential, which should use epsilon = 2.1682 eV (see <https://openkim.org/cite/MO_405512056662_003>)
