The Fe-Fe interactions in this potential are based upon those of  [EAM_Dynamo_MendelevHanSrolovitz_2003Potential2_Fe__MO_769582363439_005](https://openkim.org/cite/MO_769582363439_005) and are identical to those of [EAM_Dynamo_BonnyPasianotCastin_2009_FeCuNi__MO_469343973171_005](https://openkim.org/cite/MO_469343973171_005).  However, as Bonny *et al.* point out, there are two transformations in the EAM paradigm that leave the total energy invariant:

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

The values of these constants used by the authors to modify EAM_Dynamo_MendelevHanSrolovitz_2003Potential2_Fe__MO_769582363439_005 to describe interactions in pure Fe are $$C$$ = 0.116093429 and $$S$$ = 0.0380008812.  For pure Ni interactions, the authors modify the Voter--Chen potential [1] using the above transformations with $$C$$ = −24.3575774 and $$S$$ = 2.84007616.  For details on how the cross-interactions (Fe/Ni) were fit, please see the source article.

[1] Voter A F and Chen S P, *Mater. Res. Soc. Symp. Proc.* 82 (1987), pp. 175.
