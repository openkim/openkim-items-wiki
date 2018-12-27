**Data used in fitting:**

The authors found that they could not obtain parameters which reproduced the normalized volume at which the cohesive energy of magnetic bcc becomes lower (and thus more favorable) than magnetic fcc as the normalized volume was increased while simultaneously reproducing the correct energetic ordering of the interstitials they included in the training set: relaxed <100>, <110>, and <111> dumbbell interstitials in ferromagnetic $$\alpha$$-iron (bcc).  Case Study I in the article reproduces the former well, but not the latter.  Conversely, Case Study II in the article does not reproduce the former faithfully, but does reproduce the latter with good accuracy.

This potential corresponds to the parameters found in Case Study II, where the following properties were used:

* Ferromagnetic bcc:
    - lattice constant
    - cohesive energy
    - elastic constants C$$_{11}$$, C$$_{12}$$, and C$$_{44}$$
    - unrelaxed vacancy formation energy
    - relaxed interstitial energies (<100>, <111>, <110> dumbbell interstitials)
* Non-magnetic bcc and magnetic/non-magnetic fcc:
    - lattice constant
    - cohesive energy
    - bulk modulus

**Cutoffs:**
Both the pair potential and the density function of this Finnis-Sinclair-type Model have a cutoff of 4.1 Angstroms.  This means that the effective range for *atomic forces* is 8.2 Angstroms.  In practical terms, the pair potential interactions of this Model decay to an absolute value of less than 0.01 eV at 3.93 Angstroms and the density function decays to an absolute value of less than 0.01 at 2.9 Angstroms, yielding an effective force cutoff of 6.83 Angstroms.
