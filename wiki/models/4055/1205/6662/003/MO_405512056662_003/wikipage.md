## Parameter Choices in the SW Potential

In the original Stillinger-Weber paper (SW85: PRB 31:5262, 1985) it is stated that in order to obtain the correct "atomization energy" (cohesive energy) the following choice for epsilon must be made (see Eqn. (2.9) in [SW85]):

epsilon = 50 kcal/mol = 3.4723E-12 erg/atom

Unfortunately, there appears to be an error in the unit conversion here. (There is also an indeterminacy associated with the "kcal" unit which can mean different things.) The kcal and erg values have led to two different values for epsilon being used in articles that cite [SW85].

(a) If the kcal number is selected (assuming that S&W meant the thermochemical kcal unit), then epsilon = 2.1682 eV. This can be seen from the following conversion (which uses NIST conversion factors):

(50 kcal_th/mol)/(6.02214129 mol^-1) = 8.30269461E-23 kcal_th

8.30269461E-23 kcal_th x 4.184E+03 (J/kcal_th) = 3.47384742E-19 J

3.47384742E-19 J x 6.24150934E+18 (eV/J) = 2.168205112 eV

(b) If the erg number is selected, then epsilon = 2.1672 eV, which follows from:

3.4723E-12 erg x 6.24150934E+11 (eV/erg) = 2.16723929 eV

As noted above, both values have been used in simulations that cite the original [SW85] paper. However, it appears that S&W intended to use the 50 kcal_th/mol value since they refer to this number more than once in the paper. (See for example discussion after Eqn. (8.1) in [SW85].) Therefore we argue that the appropriate choice is

epsilon = 8.30269461E-23 kcal_th

or in eV units (reduced to 5-digit significant digits):

epsilon = 2.1682 eV

Note that in the Si.sw parameterization for this potential distributed with LAMMPS, a value of epsilon=2.1683 is used, which appears to be due to slightly different unit conversion.

Another source of confusion is that in [SW85] the potential is fitted to an incorrect value for the cohesive energy of silicon. This is corrected by Balamane in a 1992 paper. See the KIM Model Three_Body_Stillinger_Weber_Balamane_Si__MO_113686039439 for more details.

## SW Functions

See the Stillinger-Weber Model driver page (linked above) for the definition of the model and its functions. The graphs below are for the Stillinger-Weber parametrization for silicon.

The graph of function $$f_2$$ with the parameter values suggested by Stillinger and Weber ($$A=7.049556277$$, $$B=0.6022245584$$, $$p=4$$, $$q=0$$, $$a=1.80$$) is given in the following Figure:

![](/wimage/MO_405512056662_003/taru4uce/Figure1)

The contour plot of the function $$h$$ in $$f_3$$ for $$\theta=\cos^{-1}(-0.25)=104.48^\circ $$, as a function of $$r_{ij}$$ and $$r_{ik}$$ is given below:

![](/wimage/MO_405512056662_003/taru4uce/Figure2)

