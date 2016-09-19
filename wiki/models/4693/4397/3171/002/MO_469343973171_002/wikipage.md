The Fe-Fe interactions in this potential are based upon those of  [EAM_Dynamo_Mendelev_Han_Fe_2__MO_769582363439_002](https://openkim.org/cite/MO_769582363439_002) and are identical to those of [EAM_Dynamo_Bonny_Pasianot_FeNi__MO_267721408934_002](https://openkim.org/cite/MO_267721408934_002).  However, as Bonny *et al.* point out, there are two transformations in the EAM paradigm that leave the total energy invariant:

$$
\begin{align}
\hat{T_1} &= \begin{cases}
                         \varphi(r) \rightarrow S \varphi(r)\\
                         F(\rho) \rightarrow F(\rho/S)
                     \end{cases}\\
\hat{T_2} &= \begin{cases}
                         F(\rho) \rightarrow F(\rho) + C \rho\\
                         V(r) \rightarrow V(r) - 2 C \varphi(r)\\
                     \end{cases}
\end{align}
$$

where $$C$$ and $$S$$ are arbitrary constants.  Therefore, the final EAM functions used by the authors is obtained by the following modifications to arrive at an "effective" set of interactions (denoted with the superscript 'eff'):

$$
\begin{align}
V^\mathrm{eff}(r) &= V(r) - 2 C \varphi(r)\\
\varphi^\mathrm{eff} &= S \varphi(r)\\
F^\mathrm{eff} &= F(\rho/S) + C/S\rho
\end{align}
$$

The values of these constants used by the authors to modify EAM_Dynamo_Mendelev_Han_Fe_2__MO_769582363439_002 to describe interactions in pure Fe are $$C$$ = 0.116093429 and $$S$$ = 0.0380008812.  For pure Ni interactions, the authors modify the Voter--Chen potential [1] using the above transformations with $$C$$ = −24.3575774 and $$S$$ = 2.92527845.  The pure Cu interactions, the authors modify the potential of Mishin *et al.* [2] using $$C$$=-0.00195739344 and $$S$$=0.998555148.  For details on how the cross-interactions (Fe-Cu, Fe-Ni, and Cu-Ni) were fit, please see the source article.

[1] Voter A F and Chen S P, *Mater. Res. Soc. Symp. Proc.* 82 (1987), pp. 175.
[2] Y. Mishin, M.J. Mehl, D.A. Papaconstantopoulos, A.F. Voter and J.D. Kress, Phys. Rev. B 63 (2001) p.224106.

**Source citation DOI:**

* G. Bonny, R.C. Pasianot, N. Castin and L. Malerba, Philos. Mag. 89 (2009) 3531
    - http://dx.doi.org/10.1080/14786430903299824
