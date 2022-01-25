## Description
This **Model Driver** implements the Stillinger-Weber three-body potential

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

$$ v_3(\mathbf{r}_i ,\mathbf{r}_j, \mathbf{r}_k) = \epsilon f_3(\mathbf{r}_i/\sigma, \mathbf{r}_j/\sigma, \mathbf{r}_k/\sigma) $$

The function $$f_2$$ has the following form:

$$ f_2(r) = \begin{cases}
      A(Br^{-p} - r^{-q})\exp[(r-a)^{-1}] &  \text{if  } r < a\\
     0 & \text{if  }r >=a\\

    \end{cases} $$

The function $$f_3$$ takes the form:

$$ f_3(\mathbf{r}_i, \mathbf{r}_j, \mathbf{r}_k) =  h(r_{ij},r_{ik},\theta_{jik}) + h(r_{ji},r_{jk},\theta_{ijk}) + h(r_{ki},r_{kj},\theta_{ikj}) $$

where

$$  h(r_{ij},r_{ik},\theta_{jik}) = \lambda \exp[\gamma(r_{ij}-a)^{-1} + \gamma(r_{ik}-a)^{-1}](\cos\theta_{jik} + 1/3)^2 $$

 The term $$ (\cos\theta_{jik} + 1/3)^2 $$ is a penalty term which makes $$h$$ vanish for the ideal tetrahedral angle i.e. $$ \cos\theta = -1/3 $$.

