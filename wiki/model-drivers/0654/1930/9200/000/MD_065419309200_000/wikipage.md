# Background
This potential was published by X. G. Gong in Physical Review B in 1993$$^1$$; it was developed to study small clusters of silicon atoms which are not effectively modeled by interatomic potentials developed for bulk silicon crystals. Although the author proposed that *ab initio* molecular dynamics with local-density approximation would be suitable for studying small silicon clusters, such methods were very computationally expensive at the time, so an empirical potential was suggested. Other available potentials such the those by Stillinger \& Weber (SW)$$^2$$ and Tersoff$$^3$$ were effective for bulk silicon and silicon surfaces, but not for silicon clusters with only tens of atoms. The results from the potential were used to analyze the stability of very small ($$\leq$$ 11 atoms) clusters.
# Functional form of the potential
## Pair term:
A plot of the pair potential as a function of the scalar distance is shown in Figure 1.
$$
\begin{align}
\phi^{\rm G}_2(r_{ij}) &= A(B r_{ij}^{-p} - r_{ij}^{-q})f_{\rm 2c}^{\rm G}(r_{ij})\\
f_{\rm 2c}^{\rm G} &= \exp[(r_{ij}-a)^{-1}] 
\end{align}
$$
![Figure1](/wimage/MD_065419309200_000/Schma174/Figure1.png){:height="350 px"}
## Three-body term:
A plot showing the angular component of the three-body term is shown in Figure 2, and a contour plot of the distance-dependent component of the three-body term is shown in Figure 3.
$$
\begin{align}
\phi^{\rm G}_3(r_{ij},r_{ik},r_{jk}) &= h^{\rm G}(r_{ij},r_{ik},\theta_{jik}) + h^{\rm G}(r_{ij},r_{kj},\theta_{ijk}) + h^{\rm G}(r_{ik},r_{kj},\theta_{ikj}) \\
h^{\rm G}(r,s,\theta) &= \lambda_1 (\cos\theta+\tfrac{1}{3})^2 [(\cos\theta+c_0)^2+c_1] f_{\rm 3c}^{\rm G}(r,s)  \\
f_{\rm 3c}^{\rm G}(r,s) &= \exp\{\gamma[(r-a)^{-1}+(s-a)^{-1}]\} 
\end{align}
$$
![Figure2](/wimage/MD_065419309200_000/Schma174/Figure2.png){:height="350 px"} ![Figure3](/wimage/MD_065419309200_000/Schma174/Figure3.png){:height="350 px"}
## Material parameters
$$
A=7.049556277\\
B=0.6022245584\\
p=4\\
q=0\\
a=1.80\\
\gamma=1.20\\
\lambda_1=25\\
c_0=-0.5\\
c_1=0.15\\
\sigma=2.0951\ \unicode{xC5} \\
\epsilon=2.32\ eV\\
$$
Many of the material parameters are taken to be the same as in the SW potential: *A, B, p, q, a* and $$\gamma$$ are the same as in the SW potential. The new parameters, $$\lambda_1$$, $$c_0$$ and $$c_1$$ are fit to data from bulk silicon and silicon clusters and are given in Reference 4. In order to make Figure 2, which matches Figure 1 in Gong 1993, it was realized that $$c_1$$ was **0.15**, not 0.45 as given in the article. The values of all parameters are shown above. In order to be consistent with the experimental cohesive energy of -4.63 eV/atom, the energy unit of the SW potential was scaled from 2.17 to 2.32 eV.
# References
1.) X. G. Gong, Phys. Rev. B **47**, 2329 (1993).
2.) F. H. Stillinger and T. A. Weber, Phys. Rev. B **31**, 5262 (1985).
3.) J. Tersoff, Phys. Rev. B **37**, 6991 (1988).
4.) X. G. Gong, Q. Q. Zheng, and Y.-Z. He, J. Phys.: Condens. Matter **7** 577-584 (1995).
