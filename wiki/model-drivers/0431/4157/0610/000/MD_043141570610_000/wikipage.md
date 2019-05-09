# Introduction
In an attempt to explore the ability of classical mechanics to replicate quantum-mechanical calculations, R. Biswas and D. R. Hamann came up with a three body cluster potential for Si in 1987. In their article “New classical models for silicon structural energies” (*Physical Review B, 36.12 (1987): 6434*), Biswas and Hamann discuss two different potentials, referred to as ‘old’ and ‘new’ potentials in their original article. To address the shortcomings of their ‘old’ potential, namely it’s inability to capture properties of tetrahedral structure of Si, they introduce their ‘new’ potential, which is attractive for molecular-dynamics simulations given it’s short range. However, as a trade-off, the ‘new’ potential is not as efficient as the ‘old’ model in describing high pressure transitions and bulk metallic Si structures. The authors discuss how their ‘new’ potential is able to model the formation energies of interstitials and vacancies, and can also give reasonable account of thermal properties and melting of Si. Our model driver implements this ‘new’ potential of Biswas and Hamann.


# Functional form
The functional form of the two-body potential is


$$\phi^{\rm BH}_2(r_{ij}) = (A_1 \exp[-\lambda_1 r_{ij}^2] + A_2 \exp[-\lambda_2 r_{ij}^2]) f_{\rm 2c}^{\rm BH}(r_{ij}) $$

$$ f_{\rm 2c}^{\rm BH} = \{1+\exp[(r-r_c)/\mu]\}^{-1} $$

The functional form of the three body potential is 


$$ \phi^{\rm BH}_3(r_{ij},r_{ik},\theta_{jik})  = [B_1 \exp[-\alpha_1 r_{ij}^2] \exp[-\alpha_1 r_{ik}^2] (\cos\theta_{jik}+\tfrac{1}{3})^2 +  B_2 \exp[-\alpha_2 r_{ij}^2] \exp[-\alpha_2 r_{ik}^2] (\cos\theta_{jik}+\tfrac{1}{3})^3] f_{\rm 2c}^{\rm BH}(r_{ij}) f_{\rm 2c}^{\rm BH}(r_{ik})$$


