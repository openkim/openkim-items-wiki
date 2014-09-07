## Description
This **Model Driver** implements the original Stillinger-Weber potential of Bazant and Kaxiras (used for silicon in its seminal publication).

## Parameters
Symbols:

$$ a, A, B, \rho, \sigma, \lambda, \gamma, b, c, \mu, Q_0, \eta, \beta, \alpha, u_1, u_2, u_3, u_4$$

Corresponding variables in code:
a, A, B, rh, sig, lam, gam, b, c, mu, Qo, eta, bet, alp, u1, u2, u3, u4

## Details

The total potential energy of a system of $$N$$ atoms is assumed to take the form $$ E = \sum_{i=1}^N E_i $$, where the contribution to the energy of atom $$ i $$ is given by

$$ E_i = \sum_{j \neq i} V_2(R_{ij},Z_i) + \sum_{j \neq i} \sum_{k \neq i, k > j} V_3 (\vec{R}_{ij},\vec{R}_{ik},Z_i) .$$

The "environmental dependence" of the energy (and, consequently, its derivatives) is introduced through the coordination $$Z$$, which takes the form

$$ Z_i = \sum_{m \neq i} f(R_{im}) $$

where 

$$ f(r) = \begin{cases}
      1 &  \text{if  } r < c\\
      \exp{\left(\dfrac{\alpha}{1-x^{-3}}\right)} & \text{if  } c < r < a\\
      0 & \text{if  } r > a
    \end{cases} $$

and $$ x = \dfrac{( r-c )}{(a-c)} $$.
The two-body term $$V_2$$ of the energy includes an attractive part and a repulsive part:

$$ V_2(r,Z) = A \left[ \left(\dfrac{B}{r}\right)^{\rho} - p(Z) \right]\exp\left(\dfrac{\sigma}{r-a}\right)$$

with the bond-order function taking the form $$p(Z) = e^{-\beta Z^2}$$.

The three-body contribution $$V_3$$ to the energy consists of a product of radial and angular functions:

$$ V_3(\vec{R}_{ij}, \vec{R}_{ik}, Z_{i}) = g(R_{ij})g(R_{ik}) h(l_{ijk},Z_i) $$

where the bond angle of triplet $$ijk$$ is contained in $$l_{ijk} = \cos \theta_{ijk} = \vec{R}_{ij} \cdot \vec{R}_{ik} / R_{ij} R_{ik}$$.  The radial contribution is given by the function $$g(r) = \exp\left(\dfrac{\gamma}{r-a}\right)$$.  The angular contribution to $$V_3$$ is given by 

$$ h(l,Z) = \lambda \left[ \left( 1 - e^{-Q(Z)(l+\tau(Z))^2)}\right)  + \eta Q(Z)\left(l+\tau(Z)\right)^2\right]$$

with the sensitivity of the three-body energy to coordination controlled by the function $$Q(Z) = Q_0 e^{-\mu Z}$$.  The function $$\tau(Z)$$, which controls the equilibrium angle of the three-body interaction, is chosen heuristically to have the form

$$ \tau(Z) = u_1 + u_2 \left( u_3 e^{-u_4 Z} - e^{-2 u_4 Z} \right).$$
