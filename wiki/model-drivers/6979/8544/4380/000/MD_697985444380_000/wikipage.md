In 1984, G.C. Abell noted that the bond energies of a particular structure can be expressed using pairwise interactions which are modified to suitably incorporate the effect of the local environment. Tersoff introduced a Morse-like potential which utilized this concept. This potential was known to be quite successful in reproducing surface reconstruction energies but was inaccurate in some cases such as the Pandey defect reconstruction, i.e. cases wherein $$\pi$$ bonding was important. Furthermore, it wrongly predicted the bcc phase to be more stable than the diamond structure and was inapplicable to the graphitic structure of silicon. Dodsen, in 1987, tried to improve this potential by adding another parameter, but the results were insufficient. Also, the equilibrium atomic distance found from Dodsen's potential function was within 5 percent agreement with the density functional results given by Yin and Cohen. 

Khor and Das Sarma based on the work of Abell and identified a linear relationship between ln(De/Z) and the equilibrium distance, re, and as well as between re and ln(Z), where De is the cohesive energy at equilibrium and Z is the coordination number. Based on this concept they derived a bond-order potential function, consisting of ten parameters, that worked well in the case of C, Si, Ge and likewise also for tetrahedrally bonded semiconductors. The potential function has the following form:-

Energy of system = Cohesive Energy = 0.5 $$ (\sum_{ij} \phi^{\rm KDS}(r_{ij})) $$

$$
\begin{align*}
  \phi^{\rm KDS}(r_{ij}) &= A \left\{\exp[-\theta r_{ij}] - b^{\rm KDS}_{ij} \exp[-\lambda r_{ij}]\right\}
\end{align*}
$$

$$
\begin{align*}

b^{\rm KDS}_{ij} &= \frac{B_0}{(Z^{\rm KDS}_i)^\alpha}
[ 1+\sum_k g^{\rm KDS}(\theta_{jik}) ]

\end{align*}
$$

$$
\begin{align*}

g^{\rm KDS}(\theta_{jik})&= \cos\eta(\theta_{jik}-\theta_\circ)-1

\end{align*}
$$

$$
\begin{align*}

f_{\rm c}^{\rm KDS}(r_{ij}) &= \exp[-\beta(r_{ij}-R)^\gamma]

\end{align*}
$$

$$
\begin{align*}

Z^{\rm KDS}_i &= \sum_j \exp[-\beta(r_{ij}-R)^\gamma]

\end{align*}
$$

Here R is the nearest neighbor distance in the lattice structure, for instance, R is equal to $$ a\sqrt{3}/4 $$ where a is the equilibrium lattice parameter. $$r_{ij}$$ is the distance between atoms, $$\theta_{jik}$$ is the angle between the bond between i, j and i, k atoms, $$\theta_{\circ}$$ is the equilibrium bond angle and $$Z_i$$ is the coordination number of the atom. All the summations in the above set of equations are carried over the nearest neighbors of atom i. In the above set of equations, only a simple angular factor has been introduced for simplicity. 

$$\beta$$ and $$\gamma$$ were evaluated to give the correct coordination number of bcc and $$\beta$$ tin structures. $$\eta$$ was fitted to the bond bending force constant of the diamond structure. Furthermore, the rest of the parameters were evaluated by fitting to the slopes and intercepts of the graphs of De vs re and re vs ln(Z) and the bulk modulus. The technique used to fit the parameters was not mentioned in the research paper.

The table below gives the values of the parameters for C, Si, and Ge.

![](/wimage/MD_697985444380_000/Anshul/FTABLE.png){:height="110px"}

Following are the equilibrium properties of the C, Si, and Ge lattices with diamond structure:

![](/wimage/MD_697985444380_000/Anshul/STABLE.png){:height="110px"}

