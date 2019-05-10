### Parameters for the 'new' potential

This parameterization is optimized for tetrahedral structures of silicon (referred to in the paper as the 'new' potential in contrast to an 'old' version published two years earlier more suitable for high-pressure phases of silicon. The parameters for the ‘old’ potential were by fitting the model to structural energies calculated using density functional theory within the local-density approximation (LDA). The method used for determining the parameters for the ‘new’ potential is not mentioned explicitly, so we presume that the authors followed the same framework for both of their models. The influence distance parameter $$D$$ is not reported originally by the authors, here we use a value of 6 angstroms for reasons of speedup. Also the values of parameters $$B_1$$ and $$B_2$$ reported in the original article correspond to half of the values given below. This is because in our model, the summation of three-body potential term is implemented more efficiently in an asymmetric manner, while Biswas and Hamann assumed a symmetric form for the three-body potential in their original article.

### Table of parameters

Parameter &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Value &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Units
-------|-----------|-------------
$$A_1$$ | $$142.2922$$ | $$eV$$
$$A_2$$ | $$-107.0338$$ | $$eV$$
$$B_1$$ | $$26.0598$$ | $$eV$$
$$B_2$$ | $$1.3441478$$ | $$eV$$
$$\lambda_1$$ | $$0.5200836$$ | $$\overset{\circ}{A}^{-2}$$
$$\lambda_2$$ | $$0.4206931$$ | $$\overset{\circ}{A}^{-2}$$
$$\alpha_1$$ | $$0.3034373$$ | $$\overset{\circ}{A}^{-2}$$
$$\alpha_2$$ | $$0.3191903$$ | $$\overset{\circ}{A}^{-2}$$
$$r_c$$ | $$3.9527357$$ | $$\overset{\circ}{A}$$
$$\mu$$ | $$0.3120580$$ | $$\overset{\circ}{A}$$
$$D$$ | $$6.0$$ | $$\overset{\circ}{A}$$


# Representative plots

A plot from the original article depicting the angular variation of the three-body potential for the new classical Si model is shown. The bond lengths were set equal to 2.35 angstroms, which is the equilibrium bond length of Si.

![](/wimage/MO_019616213550_000/dipghosh/plot.png){:height="500px"}
