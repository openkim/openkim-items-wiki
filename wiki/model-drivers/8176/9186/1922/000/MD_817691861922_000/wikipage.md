## Background 

Simulating diffusion on Silicon surfaces has application in Microelectronics-device development. To carry out Molecular Dynamics simulations for adatom deposition on the Si(001) surface, an interatomic potential function is needed. The Tersoff potential , which predicts the
bulk properties of Si quite well, does not give satisfactory results for surface diffusion. Hence, to address this need for a potential to be
used for simulations of surface processes, a modified Tersoff potential was proposed by Jun Wang and A. Rockett in 1991 

<br/>
## Drawbacks of the original Tersoff Potential

Since the Tersoff potential is a covalent potential, it has a short interaction range and a soft angular dependence. This causes problems
when it is applied to determine surface behavior because the atoms and adatoms on the surface have lower symmetry as compared to the atoms in the bulk.  
Moreover, the Tersoff cutoff functions leads to a steep (positive) slope at $$r$$ = $$0.285$$ $$nm$$. This means that an atom moving away will feel a sudden attractive force at $$r$$ = $$0.285$$ $$nm$$. This leads to anomalous behavior of atoms on surfaces when there are large distortions during surface diffusion processes.
<br/>
## The modified Tersoff Potential

The modified potential takes into account both the metallic and directional (covalent) contributions to the bonding. It interpolates between screened long range and short range covalent bonding in surface Si atoms. For long range interactions, modified Morse potential is used and for short range interactions, the Tersoff potential is used. A screened Morse potential tail is added to the bulk Tersoff potential to predict the behavior of atoms when tetrahedral geometry is disrupted. Also, both the repulsive and attractive part have an angle dependent screening term.
<br/>
## Mathematical Description

\begin{equation}
V_{ij}=f_{c}(r_{ij})(A_{ij}e^{-\lambda_{1}r_{ij}}-BB_{ij}e^{-\lambda_{2}r_{ij}})
\end{equation}
  
  \begin{equation}
f_{c}(r_{ij}) =
\begin{cases}
1 & r < R-D \\
\tfrac{1}{2} - \tfrac{1}{2}\sin[\tfrac{\pi}{2}(r-R)/D] & R-D < r < R+D \\
0 & r > R + D
\end{cases}
\end{equation}

  \begin{equation}
B_{ij}=[1+(\beta\zeta_{ij})^{n}]^{-1/2n}
\end{equation}

 \begin{equation}
\zeta_{ij} = \sum_{k (\neq i,j) } g(\theta_{ijk})\exp\{[\lambda_3(r_{ij}-r_{ik})]^3\}
f_{c}(r_{ik}) 
\end{equation}

 \begin{equation}
g^{}(cos\theta_{ijk}) = 1 + \left(\frac{c}{d}\right)^2 - \frac{c^2}{d^2 + (h-\cos\theta_{ijk})^2}
\end{equation}

\begin{equation}
A_{ij} =A
\begin{cases}
1 & r < R_a-D_a \\
B_{ij}+(1-B_{ij})\{\tfrac{1}{2} - \tfrac{1}{2}\sin[\tfrac{\pi}{2}(r-R_a)/D_a]\} & R_a-D_a < r < R_a+D_a \\
B_{ij} & r > R_a + D_a
\end{cases}
\end{equation}

<br/>

