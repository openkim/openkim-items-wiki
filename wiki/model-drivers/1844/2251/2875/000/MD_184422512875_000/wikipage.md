**Author and purpose of this potential**

Ganga Purja Pun and Yuri Mishin developed this potential of silicon. Previous potentials such as MEAM potential [1], SW potential [2], and Tersoff potential [3] have limitations on performing mechanical and thermal properties for the bulk of Silicon (specially at the high temperature). In this paper, four potentials (MEAN, SW, Tersoff, and present) are tested using their properties to predict the mechanical and energy properties of low-dimensional structure such as Si clusters and layer forms (single and double) of silicene (2D allotrope of Si). The potential was improved from previous Tersoff-type potential to overcome limitations such as overestimated thermal expansion (at high temperature) and the volume effect of melting. Therefore, the basic energy equation is the same as the Tersoff potential [3]. 

**Potential**

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

Here, $$R_1$$and $$r_2$$ is are cutoff radius. The outer cutoff  $$R_2$$  is chosen between the first and second coordination shells of the diamond cubic structure. The angular function $$g(\theta_{ijk})$$ has an equation form as

$$
g(\theta) = c_1 + \frac{c_2 (h - cos\theta)^2}{c_3 + (h - cos\theta)^2} \times \{ 1 + c_4 exp[-c_5 (h-cos\theta)^2] \} 
$$,

where $$\theta_{ijk}$$ is the angle between bonds i-j and i-k.

**Plot of each function**

$$\boldsymbol{f_c(r_{ij})}$$
![](/wimage/MD_184422512875_000/MKChoi/plot_of_fc)
$$\boldsymbol{g(\theta)}$$
![](/wimage/MD_184422512875_000/MKChoi/plot_of_g)

$$\boldsymbol{\xi(r_{ij},\theta,r_{ik})}$$
![](/wimage/MD_184422512875_000/MKChoi/plot_of_xi)

$$\boldsymbol{b(r_{ij},\theta,r_{ik})}$$
![](/wimage/MD_184422512875_000/MKChoi/plot_of_xi)

$$\boldsymbol{\phi(r_{ij},\theta,r_{ik})}$$
![](/wimage/MD_184422512875_000/MKChoi/plot_of_E)

**Reference:**

[1] S. Ryu, C. R. Weinberger, M. I. Baskes, and W. Cai, Improved modified embedded-atom method potentials for gold and silicon, Modell. Simul. Mater. Sci. Eng. 17, 075008 (2009).
[2] F. H. Stillinger and T. A. Weber, Computer simulation of local order in condensed phases of silicon, Phys. Rev. B 31, 5262 (1985).
[3] T. Kumagai, S. Izumi, S. Hara, and S. Sakai, Development of bond-order potentials that can reproduce the elastic constants and melting point of silicon for classical molecular dynamics simulation, Comput. Mater. Sci. 39, 457 (2007).


