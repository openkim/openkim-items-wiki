### Background ###

Ganga Purja Pun and Yuri Mishin developed this bond order potential form of silicon. Previous potentials such as the modified embedded-atom method (MEAM) potential [1], Stillinger-Weber (SW) potential [2], and modified Tersoff potential (MOD) [3] have some limitations in computing mechanical and thermal properties for bulk of Silicon (specially at high temperature). The new potential is an extension of the MOD Tersoff-type potential. The developers tested four potentials (MEAM, SW, MOD, and the new potential) with respect to the mechanical and energetic properties of bulk and low-dimensional structures including Si clusters and single and bilayer silicene (a 2D allotrope of Si). The new potential performed better than earlier potential overcoming limitations such as an overestimated thermal expansion (at high temperature) and the volume effect of melting.

### Potential ###

The total energy is given by 

$$E = \frac{1}{2} \sum_{i \ne j}\phi_{ij}(r_{ij})$$,

where $$r_{ij}$$ is the distance between atom i and j and the bond energy $$\phi_{ij}$$ is taken as

$$\phi_{ij}=f_{c}(r_{ij})[A\space exp(-\lambda_{1}r_{ij})-b_{ij}\space B\space exp(-\lambda_{2}r_{ij})+c_0]$$.

The bond order $$b_{ij}$$ is given by 

$$b_{ij} = (1+\xi_{ij}^\eta)^{-\delta}$$,

where 

$$\eta_{ij} = \sum_{k\ne i,j}f_{c}(r_{ij})g(\theta_{ijk})exp[\alpha(r_{ij}-r_{ik})^\beta]$$,

where $$f_{c} (r_{ij})$$ has the form

$$
\begin{align*}
&f_{c}(r) = \left\{\begin{aligned}
&1,\space r \leq  R_1 \\
&\frac{1}{2} + \frac{9}{16}\space cos(\pi\frac{r-R_1}{R_2 - R_1}) - \frac{1}{16} cos(3\pi \frac{r-R_1}{R_2 - R_1}),\space R_1 \lt\space r \lt\space R_2  \\
&0,\space r \geq R_2 \\
\end{aligned}
\right.
\end{align*}
$$.

Here, $$R_1$$ and $$R_2$$ are cutoff radii. The outer cutoff  $$R_2$$  is chosen between the first and second coordination shells of the diamond cubic structure. The angular function $$g(\theta_{ijk})$$ is

$$
g(\theta) = c_1 + \frac{c_2 (h - cos\theta)^2}{c_3 + (h - cos\theta)^2} \times \{ 1 + c_4 exp[-c_5 (h-cos\theta)^2] \} 
$$,

where $$\theta_{ijk}$$ is the angle between bonds i-j and i-k.

### Reference: ###

[1] S. Ryu, C. R. Weinberger, M. I. Baskes, and W. Cai, Improved modified embedded-atom method potentials for gold and silicon, Modell. Simul. Mater. Sci. Eng. 17, 075008 (2009).
[2] F. H. Stillinger and T. A. Weber, Computer simulation of local order in condensed phases of silicon, Phys. Rev. B 31, 5262 (1985).
[3] T. Kumagai, S. Izumi, S. Hara, and S. Sakai, Development of bond-order potentials that can reproduce the elastic constants and melting point of silicon for classical molecular dynamics simulation, Comput. Mater. Sci. 39, 457 (2007).


