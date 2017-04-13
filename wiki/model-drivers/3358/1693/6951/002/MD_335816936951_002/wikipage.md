## Description
This **Model Driver** implements the Stillinger-Weber three-body potential for Si

## Parameters
Symbols:

$$ a, A, B, p, q, \sigma, \lambda, \gamma$$

Corresponding variables in code:
a, A, B,p, q, sigma, lamda, gamma

## Details

The total potential energy function $$ \phi $$ for Si crystal is approximated by a combination of a pair and three-body potential $$v_2$$ and $$v_3$$ respectively. It takes the following form:

$$ \phi =  \sum_{i,j; i<j} v_2(i,j) + \sum_{i,j,k; i<j<k} v_3(i,j,k) $$

Where 

$$ v_2(r_{ij}) = \epsilon f_2(r_{ij}/\sigma) $$

$$ v_3(r_i,r_j,r_k) = \epsilon f_3(r_i/\sigma,r_j/\sigma,r_k/\sigma) $$

The function f_2 belongs to five parameter family and takes the following form:

$$ f_2(r) = \begin{cases}
      A(Br^{-p} - r^{-q})\exp[(r-a)^{-1}] &  \text{if  } r < a\\
     0 & \text{if  }r >=a\\
      
    \end{cases} $$

The graph of function f_2 with the parameter values suggested by Stillinger and Weber is given in Figure 
![](/wimage/MD_335816936951_002/taru4uce/Figure1)

The function f_3 takes the form

$$ f_3(r_i,r_j,r_k) =  h{(r_{ij},r_{ik},\theta_{jik})} + h(r_{ji},r_{jk},\theta_{ijk}) + h(r_{ki},r_{kj},\theta_{ikj}) $$

$$  h(r_{ij},r_{ik},\theta_{jik}) = \lambda exp[\gamma(r_{ij}-a)^{-1} + \gamma(r_{ik}-a)^{-1}]*(\cos\theta_{jik} + 1/3)^2 $$

 The term $$ (\cos\theta_{jik} + 1/3)^2 $$ is a penalty term which makes $$ h $$ vanish for 'ideal' tetrahedral angle i.e. $$ \cos\theta = -1/3 $$

for a constant \theta, the contour plot of the function $$ h $$ with r_{ij} and r_{ik} look like the following Figure

![](/wimage/MD_335816936951_002/taru4uce/Figure2)
