## Description
This **Model Driver** utilizes the Tersoff potential, originally used for Silicon in its seminal publication by Tersoff in 1988. It can be used for both the T2 and T3 bond order models, which are simply different parameter sets for the form given below.

## Parameters
Symbols used in the model (taking into account $$\alpha_{ij}$$ is set to zero for this implementation of the model, and the modifications given in the note at the bottom of this documentation):

$$ m, \gamma_{ijk}, \lambda_3, c, d, cos\theta_0, n, \beta, \lambda_2, B, R, D, \lambda_1, A $$

These correspond to the following variables in the code:


$$ \text{m, gamma, lambda3 (1/distance units), c, d, costheta0 (must be a valid value between -1 & 1), n,  beta, lambda2 (1/distance units), B (energy units), Rc (distance units), Dc (distance units), lambda1 (1/distance units), & A (energy units).}  $$


The parameters n, beta, lambda2, B, lambda1, & A are used for two-body interactions, while m, gamma, lambda3, c, d, costheta0 are only used for three-body interactions.

Additionally, the code requires three other variables to determine the elements being used:

$$ \text{Element 1}: \text{The center atom in a 3-body interaction} $$

$$ \text{Element 2}: \text{The atom bonded to the center atom} $$

$$ \text{Element 3}: \text{The atom influencing the 1-2 bond in a bond-order sense} $$

## Details
The interatomic potential is given as:

$$ E = \sum_i E_i =  {1 \over 2}{\sum_{i \neq j}V_{ij}}$$

Where $$E$$ is the total energy of the system, decomposed into site energy, $$E_i$$, and bond energy, $$V_{ij}$$. The indices $$i$$ and $$j$$ run through all atoms in the system, and $$r_{ij}$$ is the distance from atom $$i$$ to atom $$j$$.

$$V_{ij}$$ has the form:

$$ V_{ij} =  f_c(r_{ij})[a_{ij}f_R(r_{ij})+b_{ij}f_A(r_{ij})] $$

The functions $$f_A$$ and $$f_R$$ are the respective attractive and repulsive pair potentials:

$$ f_A = Ae^{-\lambda_1r} $$

$$ f_R = -Be^{-\lambda_2r} $$

Moreover, $$f_c$$ is the cutoff function with the form:

$$ f_c(r) = \begin{cases}
      1 &  \text{if  } r < R-D\\
      {1 \over 2}-{1 \over 2}sin[{\pi \over 2}{(r-R) \over D}]& \text{if  } R-D < r < R+D\\
      0 & \text{if  } r > R+D
    \end{cases} $$

The bond-order function, $$b_{ij}$$, is given as:

$$b_{ij} = (1+\beta^n\zeta^n_{ij})^{-1 / 2n} $$

Where $$\zeta_{ij}$$ is the coordination function, which gives the bond coordination of the environment:

$$ \zeta_{ij} = \sum_{k \neq i,j}f_c(r_{ik})g(\theta_{ijk})\exp[\lambda_3^3(r_{ij}-r_{ik})^3] $$

$$g(\theta_{ijk})$$ is as follows:

$$ g(\theta_{ijk}) =  1+ {c^2 \over d^2}- {c^2 \over [d^2+(h -cos\theta)^2]} $$

where $$\theta_{ijk}$$ is the bond angle between bonds $$i-j$$ and $$j-k$$.


Additionally, $$ a_{ij} $$ is given by the following expression:

$$ a_{ij} = (1+\alpha^n\eta^n_{ij})^{-1/2n} $$

where $$\eta_{ij}$$ is:

$$ \eta_{ij} = \sum_{k \neq i,j} f_c(r_{ik})exp[\lambda_3^3(r_{ij}-r_{ik})^3] $$


$$\alpha$$ is generally small enough such that $$a_{ij} \simeq 1$$; however, for most of the work presented in the paper by Tersoff in 1988, as well as this model, $$\alpha=0$$ such that $$a_{ij}=1$$, and thus $$V_{ij}$$ reduces to the form:

$$ V_{ij} =  f_c(r_{ij})[f_R(r_{ij})+b_{ij}f_A(r_{ij})]. $$

### **Note:** 
This model driver is ported from LAMMPS, which uses a few function modifications to allow for commonly used variants of the Tersoff potential (as documented [here](http://lammps.sandia.gov/doc/pair_tersoff.html)). The differences are as follows:

$$\zeta_{ij}$$ is modified to use the factor m:

$$ \zeta_{ij} = \sum_{k \neq i,j}f_c(r_{ik})g(\theta_{ijk})exp[\lambda_3^m(r_{ij}-r_{ik})^m] $$

Additionally, $$g(\theta)$$ used in this model driver is modified by the factor $$\gamma_{ijk}$$:

$$ g(\theta) = \gamma_{ijk}({1+ {c^2 \over d^2}- {c^2 \over [d^2+(cos\theta -cos\theta_0)^2]}}) $$

It can be noted that setting $$m = 3$$ and $$\gamma_{ijk} = 1$$ gives the original Tersoff form (from the 1988 papers) shown above.
