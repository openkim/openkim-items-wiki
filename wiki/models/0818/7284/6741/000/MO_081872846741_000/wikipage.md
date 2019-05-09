## Parametrization

There are a total of 14 parameters in the Wang-Rockett potential. The first ten parameter values (first ten in the table below) were directly
taken from the Tersoff Potential . To make the cut-off function smooth, $$R$$ and $$D$$ were modified. The value of $$R$$ was chosen as $$0.385$$ $$nm$$
and $$D$$ as $$0.015$$ $$nm$$. $$R_a$$  and  $$D_a$$  are the two new parameters introduced in the modified Tersoff potential, and their values were determined by interpolating the repulsive term to an angle dependent screened form.  
The first ten parameters were obtained by Tersoff in 1988 by fitting the cohesive energies of hypothetical and real bulk polytypes of silicon as
well as bulk modulus and bond length in diamond cubic structure. The fitting technique used to parametrize the potential was not reported.  
Other parameterizations for the modified Tersoff potential are not reported in the literature .


|     Parameter     |    Value   |    Units   |
|:-----------------:|:----------:|:----------:|
| $$\lambda_1$$  |   2.4799   | 1/Å |
|  $$\lambda_2$$   |   1.7322   | 1/Å |
|  $$\lambda_3$$   |   1.7322   | 1/Å |
|        $$A$$       |   1830.8   |   $$eV$$   |
|        $$B$$        |   471.18   |   $$eV$$   |
|        $$\beta$$      | 1.0999E-06 |            |
|        $$n$$        |   0.78734  |            |
|        $$c$$       |  100390.00 |            |
|        $$d$$        |   16.218   |            |
|        $$h$$       |  -0.59826  |            |
|        $$R$$        |    0.385   |   $$nm$$   |
|        $$D$$        |    0.015   |   $$nm$$   |
| $$R_a$$ |    0.325   |   $$nm$$   |
| $$D_a$$ |    0.02    |   $$nm$$   |


<br/>
## Verification

The modifications were tested by examining the behavior of atoms in bulk Si and of an adatom on the Si(001) 2 X 1 surface for which
substantial experimental data are available. Zero temperature properties are studied using the molecular statics method. The modifications were
tested in four parts:

The modifications were tested in four parts:

##### 1. Evaluating the behaviour of Tersoff and modified Tersoff potential for small atom clusters. 
This was necessary to gain an insight into the radial and angular behaviour of the potential functions. As described earlier, because of the abrupt cutoff of the Tersoff potential, atoms feel a sudden increase in the attractive force at $$r=0.285$$ $$nm$$. However, the modified Tersoff potential adresses this problem by extending the cutoff radius to $$R=0.385$$ $$nm$$. The angular dependence of the two potential functions was quite similar.

##### 2. Bulk lattice simulations
The results show that the new modified potential reproduced the structural and energetic properties of the bulk Si very well and matched with that of the original Tersoff potential.

##### 3. Flat surface calculations, with and without reconstruction 
Both the potentials predict nearly identical reconstruction geometries. In the original Tersoff potential, only the top two surface layers stay close to each other. However, due to weak long ranges interactions, in modified the Tersoff potential even the third layer atoms are close to the surface layer. This behaviour of modified Tersoff potential is supported by other theoretical and computational studies.  
##### 4. Surface mapping
The influence of cutoff function on surface diffusion was also studied for both the potentials. The energy barriers to motion from one equilibrium state to another were calculated. 
<br/>
# Plots

<br/>
![Figure1](/wimage/MD_817691861922_000/ramanish/fc.png){:height="350 px"}
<br/>


![Figure1](/wimage/MD_817691861922_000/ramanish/g.png){:height="350 px"}

<br/>

![Figure1](/wimage/MD_817691861922_000/ramanish/Aij.png){:height="350 px"}
<br/>


![Figure1](/wimage/MD_817691861922_000/ramanish/r.png){:height="350 px"}

<br/>
 The atomic energy of an atom was calculated by simulating an environment of five Si atoms in tetrahedral geometry. The bond length was kept equal for all the four bonds and it was varied to find the bond length with least energy (using Tersoff potential). The minima was found to be at $$r$$= $$2.3$$ Å.
<br/>

![Figure1](/wimage/MD_817691861922_000/ramanish/angle.png){:height="350 px"}

<br/>
To find out the optimum geometry, a system of five Si atoms in tetrahedral geometry was distorted to see the variation of energy. The central atom was rotated by an angle $$\theta $$ with one of the atoms as the hinge. It is observed that energy is minimum for $$\theta=0$$ (i.e. tetrahedral geometry). 



<br/>

# References
1.)   J. Tersoff, “Empirical interatomic potential for silicon with improved elastic properties,”Phys. Rev. B,vol. 38, pp. 9902–9905, Nov 1988.
2.) J.  Wang  and  A.  Rockett,  “Simulating  diffusion  on  si(001)  21  surfaces  using  a  modified  interatomicpotential,”Phys. Rev. B, vol. 43, pp. 12571–12579, May 1991.
3.) S. R. M. Macucci and A. Correia, “Report on multiscale approaches to modelling for nanotechnology,”ed. Phantoms Foundation, 2008.
