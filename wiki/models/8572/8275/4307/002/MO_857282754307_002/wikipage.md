**Notes:**

Despite the focus of the article by Morris *et al.* cited below being placed on many-body (EAM) extensions of pair potentials which retain their predictions for the cohesive energy and lattice constant while only minimally affecting the bulk modulus they predict, this Model only corresponds to the Modified Johnson pair potential itself.  **It does *not* contain any code which implements many-body contributions.**

The original form of this Fe pair potential was published by Johnson in 1964.  Srolovitz *et al.* noted that Johnson's potential possesses a second derivative which is discontinuous at two points (2.4 Å and 3.44 Å).  Accordingly, they modified Johnson's potential so that derivatives up to second order are continuous for all separations.  The modified form of Johnson's potential due to Srolovitz was later adopted by Morris *et al.*  Because Johnson's potential is not technically defined for r < 1.9 Å, Morris et al. implement a repulsive exponential for this range of the form $$A_0 \exp(-Br)$$ with $$A_0$$ = 8752.934 eV and $$B$$ = 4.572488 Å$$^{-1}$$  (which are chosen such that the potential and its first derivative with respect to separation are continuous at r = 1.9 Å).  It is this final, third form of the potential which is implemented in this KIM Model.

**Data used in fitting:**

The only material properties which were ever used in fitting this potential in any of its three forms (Johnson, Srolovitz *et al.*, and Morris *et al.*) are the elastic constants $$C_{11}$$, $$C_{12}$$, and $$C_{44}$$ of $$\alpha$$-iron (which has a bcc crystal structure).

**Source citation DOI:**

* J. R. Morris, R. S. Aga, V. Levashov and T. Egami, "Many-body effects in bcc metals: An embedded atom model extension of the modified Johnson pair potential for iron."  Phys. Rev. B 77, 174201 (2008).
    - http://dx.doi.org/10.1103/PhysRevB.77.174201
* D. J. Srolovitz, K. Maeda, V. Vitek, and T. Egami, "Structural defects in amorphous solids Statistical analysis of a computer model."  Philos. Mag. A 44, 847 (1981).
    - http://dx.doi.org/10.1080/01418618108239553
* R. A. Johnson, "Interstitials and Vacancies in $$\alpha$ Iron." Phys. Rev. A 134, 1329 (1964).
    - http://dx.doi.org/10.1103/PhysRev.134.A1329
