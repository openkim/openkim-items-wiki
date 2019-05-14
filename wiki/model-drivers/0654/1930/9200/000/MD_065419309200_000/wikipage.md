### Background
This potential was published by X. G. Gong in *Physical Review B* in 1993$$^1$$; it was developed to study small clusters of silicon atoms which are not effectively modeled by interatomic potentials developed for bulk silicon crystals. Although the author proposed that *ab initio* molecular dynamics with local-density approximation would be suitable for studying small silicon clusters, such methods were very computationally expensive at the time, so an empirical potential was suggested. Other available potentials such the those by Stillinger & Weber (SW)$$^2$$ and Tersoff$$^3$$ were effective for bulk silicon and silicon surfaces, but not for silicon clusters with only tens of atoms. The results from the potential were used to analyze the stability of very small ($$\leq$$ 11 atoms) clusters.

### Functional form of the potential
#### Pair term:
$$
\begin{align}
\phi^{\rm G}_2(r_{ij}) &= A(B r_{ij}^{-p} - r_{ij}^{-q})f_{\rm 2c}^{\rm G}(r_{ij})\\
f_{\rm 2c}^{\rm G} &= \exp[(r_{ij}-a)^{-1}] 
\end{align}
$$
#### Three-body term:
$$
\begin{align}
\phi^{\rm G}_3(r_{ij},r_{ik},r_{jk}) &= h^{\rm G}(r_{ij},r_{ik},\theta_{jik}) + h^{\rm G}(r_{ij},r_{kj},\theta_{ijk}) + h^{\rm G}(r_{ik},r_{kj},\theta_{ikj}) \\
h^{\rm G}(r,s,\theta) &= \lambda_1 (\cos\theta+\tfrac{1}{3})^2 [(\cos\theta+c_0)^2+c_1] f_{\rm 3c}^{\rm G}(r,s)  \\
f_{\rm 3c}^{\rm G}(r,s) &= \exp\{\gamma[(r-a)^{-1}+(s-a)^{-1}]\} 
\end{align}
$$

### References
1.) X. G. Gong, Phys. Rev. B **47**, 2329 (1993).
2.) F. H. Stillinger and T. A. Weber, Phys. Rev. B **31**, 5262 (1985).
3.) J. Tersoff, Phys. Rev. B **37**, 6991 (1988).

