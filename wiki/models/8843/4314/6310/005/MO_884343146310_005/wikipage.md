**Notes:**

Parameters of this potential are given in Table 5 of the article cited below.  Note that the authors warn that this potential is specifically intended for studying radiation damage and point defects in Fe-rich compounds of FeP, and should not necessarily be expected to be transferable to other scenarios.  Specifically, they note that no properties of pure phosphorus or phosphorus-rich FeP were used in the fitting process.

It is also stated in the article that the Fe-Fe interactions of this potential are taken directly from [M.I. Mendelev, S. Han, D.J. Srolovitz, G.J. Ackland, D.Y. Sun and M. Asta, Phil. Mag. 83, 3977-3994 (2003)](http://dx.doi.org/10.1080/14786430310001613264).  However, the predictions of this potential for properties of pure Fe do not appear to match those of any of the five parametrizations found in this reference.  Therefore, it is not completely clear which properties were used to fit the Fe-Fe interactions.

The following potentials feature identical (or approximately identical) Fe-Fe interactions to this potential:

* [EAM_Dynamo_HepburnAckland_2008_FeC__MO_143977152728_005](https://openkim.org/cite/MO_143977152728_005)
* [EAM_Dynamo_MendelevHanSon_2007_VFe__MO_249706810527_005](https://openkim.org/cite/MO_249706810527_005)
* [EAM_Dynamo_MendelevSrolovitzAckland_2005_AlFe__MO_577453891941_005](https://openkim.org/cite/MO_577453891941_005)

**Data used in fitting:**

This potential was fitted to point defects in iron, their interactions with phosphorus atoms, and hypothetical Fe-rich structures of FeP.  Unless stated explicitly, all results below were computed using GGA DFT.

* Perfect crystals
  * Experimental values of the cohesive energy and elastic constants (C$$_{11}$$, C$$_{12}$$, C$$_{44}$$) of body-centered cubic (bcc) Fe ($$\alpha$$-Fe)
  * A bcc Fe lattice where every fourth (001) plane of atoms is replaced with phosphorus atoms.  The authors refer to this as a "stripe" structure.
  * The Fe$$_2$$P crystal lattice.  Although the authors state has been observed experimentally, they compute its equilibrium geometry, energy, and magnetic moment using GGA DFT.
  * Hypothetical crystal lattices with composition Fe$$_{3}$$P
    * L1$$_{2}$$
      This lattice is formed by replacing the corner atom in a conventional face-centered cubic (fcc) unit cell of iron atoms with a phosphorus atom
    * DO$$_{3}$$
      Imagine assembling a set of eight adjacent conventional bcc unit cells of Fe atoms in a 2 x 2 x 2 configuration.  Among the top four unit cells, select two of them which are opposite one another, i.e. do not share any edges, and replace the Fe atoms in the centers of these cells with phosphorus atoms.  Now proceed to the bottom four unit cells and do the same, but for the two unit cells opposite one another which do not lie beneath the two chosen in the top layer.  See [http://www.geocities.jp/ohba_lab_ob_page/structure2.html](http://www.geocities.jp/ohba_lab_ob_page/structure2.html) for an image.  See also "Intermetallic phases with D0$$_3$$-structure: a statistical-thermodynamic model," Ipser, Semenova, and Krachler. J. Alloys Compd. 338 (1-2), pp.20-25, 2002.
    * DO$$_{32}$$
      Imagine the same set of eight bcc unit cells as in the case of the DO$$_{3}$$ lattice above, this time leaving all of the atoms in the centers of the indivudal conventional unit cells to be Fe.  Instead, replace Fe atoms in the remaining layers of atoms with phosphorus so that when one proceeds along any two edges of the individual conventional bcc unit cells, the species of the atoms encountered alternates between Fe and P.  See [http://www.geocities.jp/ohba_lab_ob_page/structure2.html](http://www.geocities.jp/ohba_lab_ob_page/structure2.html) for an image.

* Vacancies
  * Monovacancy in 16-atom and 32-atom $$\alpha$$-Fe supercells
  * Divacancy in a 16-atom $$\alpha$$-Fe cell where the vacancies are at nearest-neighbor sites of one another
  * Divacancy in a 16-atom $$\alpha$$-Fe cell where the vacancies are at second-nearest-neighbor sites relative to one another

* Substitutional impurities (relaxed under constant-volume constraints)
  * Single substitution of Fe$$\rightarrow$$P in a 16-atom and 54-atom supercells of $$\alpha$$-Fe
  * Pairs of P substitutions on neighboring sites in 16-atom and 54-atom supercells of $$\alpha$$-Fe.  These pairs are located
  The authors indicate that because of the small unit cells used, these quantities are *not* to be interpreted as the energies of isolated defects.

* Combinations of vacancies and substitutional impurities
  * Monovacancy in a 16-atom $$\alpha$$-Fe supercell with a substitutional Fe$$\rightarrow$$P defect placed at the nearest-neighbor site
  * Monovacancy in a 16-atom $$\alpha$$-Fe supercell with a substitutional Fe$$\rightarrow$$P defect placed at the second-nearest-neighbor site
  * Nearest-neighbor divacancy in a 16-atom $$\alpha$$-Fe supercell with a P atom placed midway between one of the vacancy sites and a <111> interstitial site
  * Monovacancy in a 32-atom $$\alpha$$-Fe supercell with a substitutional Fe$$\rightarrow$$P defect placed at the nearest-neighbor site
  * Monovacancy in a 32-atom $$\alpha$$-Fe supercell with a substitutional Fe$$\rightarrow$$P defect placed at the second-nearest-neighbor site
  * Nearest-neighbor divacancy in a 32-atom $$\alpha$$-Fe supercell with a P atom placed midway between one of the vacancy sites and a <100> interstitial site
  * Nearest-neighbor divacancy in a 32-atom $$\alpha$$-Fe supercell with a P atom placed midway between one of the vacancy sites and a <111> interstitial site

* Interstitials
  * Tetrahedral and octahedral self-interstitials in a 16-atom $$\alpha$$-Fe supercell
  * [001], [011], [111] dumbbell self-interstitials in a 16-atom $$\alpha$$-Fe supercell
  * [100], [011], and [111] dumbbell interstitials of P atoms in 16-atom $$\alpha$$-Fe supercell
  * Mixed [001], [011], and [111] dumbbell interstitials in 16-atom $$\alpha$$-Fe supercell
  * Tetrahedral and octahedral P interstitials in a 16-atom $$\alpha$$-Fe supercell

* Surfaces and monolayers
  * The (100) surface energy of $$\alpha$$-iron.  This was computed using a slab containing a total of eight layers of Fe atoms.
  * Seven layers of Fe atoms (in the $$\alpha$$-iron bcc configuration) with one layer of P atoms on top
  * Six layers of Fe atoms followed by one layer of P atoms and another layer of Fe atoms
  Energies of these configurations were recorded at a number of different strains.

* Liquid configurations generated using a simple pair potential

**Cutoffs:**
The pair potentials of this Model (for Fe-Fe, P-P, and Fe-P) all have a cutoff of 5.3 Angstroms.  The three density functions (Fe-Fe, P-P, Fe-P) all have a cutoff of 4.2 Angstroms.  The effective cutoff for all *atomic forces* is thus 9.5 Angstroms.

For the case of pure Fe, the pair potential decays to an absolute value of less than 0.01 eV at approximately 4.5 Angstroms and the electron density decays to a value of 0.01 at approximately 4.0 Angstroms, yielding an effective force range of 8.5 Angstroms.

**Source citation DOI:**

* G.J. Ackland, M.I. Mendelev, D.J. Srolovitz, S. Han and A.V. Barashev, J. Phys.: Condens. Matter 16, S2629-S2642 (2004).
    - http://dx.doi.org/10.1088/0953-8984/16/27/003
