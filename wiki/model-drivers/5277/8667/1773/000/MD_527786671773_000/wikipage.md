This potential was developed by Efthimios Kaxiras and K. C. Pandey and published in December 1988.  It was developed for calculating the energy of realistic atomic processes in Si, particularly for simulating processes in the diamond lattice as opposed to high-energy bulk structures of Si.  It is difficult to construct a potential that accurately describes both high-energy crystal structures and local distortions of the diamond lattice.  This potential is meant to accurately reproduce energy costs for various local distortions from the tetrahedral coordination, including the breaking and formation of bonds, cohesive energy, and bulk modulus of the diamond lattice, which is the lowest-energy crystal structure for Si.  This potential encompasses most of the low-energy, physically accessible configurations.  Previous attempts at constructing Si potentials relied on quantum-mechanical calculations for high-coordination bulk structures of Si, which has been proven to be insufficient.  For instance, previous classical potentials exhibited unrealistic structure, incorrect curvature, and an inability to reproduce activation energy for the concerted exchange (CE) phase-space path for Si, when compared to reliable quantum-mechanical local-density-functional calculations.  To construct the potential, Kaxiras and Pandey utilized the energy surface of atomic exchange, which is a large quantum-mechanical data base.  The potential has a simple, transparent functional form, and it uses a small set of parameters, namely seven.  It reproduces the CE path within an accuracy of $$ 0.1\ eV $$, which is a significant improvement over previous potentials.  

The Kaxiras and Pandey potential is a three-body potential.  The two-body term is the difference of two Gaussians and is as follows:

$$ V_{ij}=A_1\exp(-\alpha_1r_{ij}^2\ )-A_2\exp(-\alpha_2r_{ij}^2\ ) $$

where $$ r_{ij} $$ is the distance between atoms $$ i $$ and $$ j $$.  The full three-body term is a symmetrized sum over all atom triplets, as shown below:

$$ V_3=V_{ijk}+V_{jki}+V_{kij} $$

$$ V_{ijk}=\exp[-\beta(r_{ij}^2+r_{ik}^2\ )] [Bg^2 (θ)+Dg^4 (θ)] $$

$$ g(\theta)=(cos\theta+1/3) $$

where $$ \theta $$ is the angle at the $$ i $$ vertex of the $$ ijk $$ triangle, subtended by the bonds $$ r_{ij} $$ and $$ r_{ik} $$.  The radial dependence of the three-body term is a Gaussian, and the angular dependence is of the generalized Keating-form.  The two-body and three-body terms both vanish at $$ r_c = 5.5\ Å. $$  
