**Notes:**

The Fe-Fe interactions in this potential are approximately identical to those of the following potentials (although seem to vary slightly due to the specific tabulation which was performed):

* [EAM_Dynamo_AcklandMendelevSrolovitz_2004_FeP__MO_884343146310_005](https://openkim.org/cite/MO_884343146310_005)
* [EAM_Dynamo_HepburnAckland_2008_FeC__MO_143977152728_005](https://openkim.org/cite/MO_143977152728_005)
* [EAM_Dynamo_MendelevHanSon_2007_VFe__MO_249706810527_005](https://openkim.org/cite/MO_249706810527_005)

**Data used in fitting:**

* Al-Al
   The following properties, summarized in Table I of Mendelev, Kramer, Becker and Asta (see citations below), were used to fit Al-Al interactions:
    * Zero-temperature
        * Lattice constant, cohesive energy, and elastic constants (C$$_{11}$$, C$$_{12}$$, C$$_{44}$$) of fcc Al
        * Unrelaxed monovacancy formation energy in fcc Al
        * <100> self-interstitial formation energy in fcc Al
        * Lattice constant of bcc Al
        * Difference between cohesive energies of bcc and fcc Al
        * Lattice constants of hcp Al
        * Difference between cohesive energies of fcc and hcp Al
        * Atomic forces (calculated using DFT) of a model liquid configuration generated using a simple pair potential
    * Finite temperature
        * Melting temperature (taken to have a value of 933 K)
        * Latent heat of fusion
        * Change in volume upon melting
        * Liquid density at melting temperature

    Table I of this article also includes the predictions of this potential for surface energies and other liquid properties.  The authors specifically note that this potential predicts values for the (100), (110), and (111) fcc surface energies which are of considerably smaller magnitude than those calculated from DFT.

* Fe-Fe
The Fe-Fe interactions were fitted to a variety of properties of $$\alpha$$-iron, including cohesive energy and elastic constants, interstitial and vacancy formation energies, and surface energies.  Atomic forces present in a liquid configuration (generated using a pair potential) were also used in fitting.  Please see the wiki entry of [EAM_Dynamo_AcklandMendelevSrolovitz_2004_FeP__MO_884343146310_005](https://openkim.org/cite/MO_884343146310_005) for further details.

* Al-Fe
The Al-Fe interactions of this potential were generated iteratively.  In each step of the iteration, a liquid configuration is produced with the current parameter set.  The L1$$_{2}$$ and DO$$_{3}$$ crystal structures, both of which have composition Al$$_{3}$$Fe, are also formed (See description of these structures below.  Furthermore, note that the L1$$_{2}$$ and DO$$_{3}$$ structures were also used in the fitting of [EAM_Dynamo_AcklandMendelevSrolovitz_2004_FeP__MO_884343146310_005](https://openkim.org/cite/MO_884343146310_005).).  Computing the energies and forces of these configurations using GGA-DFT and comparing them to the predictions of the current potential, its parameters are adjusted.  Next, the interaction energy of an Al monovacancy with an Fe interstitial (sitting at a nearest-neighbor site relative to the vacancy) is computed with the potential and using DFT.  The two-body interaction of the potential, separate from the embedding density and energy, is then refitted using all of the previous properties and the entire procedure is iterated to convergence.

    * L1$$_{2}$$
      This lattice is formed by replacing the corner atom in a conventional face-centered cubic (fcc) unit cell of aluminum atoms with an iron atom
    * DO$$_{3}$$
      Imagine assembling a set of eight adjacent conventional bcc unit cells of Fe atoms in a 2 x 2 x 2 configuration.  Among the top four unit cells, select two of them which are opposite one another, i.e. do not share any edges, and replace the Al atoms in the centers of these cells with Fe atoms.  Now proceed to the bottom four unit cells and do the same, but for the two unit cells opposite one another which do not lie beneath the two chosen in the top layer.  See [http://www.geocities.jp/ohba_lab_ob_page/structure2.html](http://www.geocities.jp/ohba_lab_ob_page/structure2.html) for an image.  See also "Intermetallic phases with D0$$_3$$-structure: a statistical-thermodynamic model," Ipser, Semenova, and Krachler. J. Alloys Compd. 338 (1-2), pp.20-25, 2002.
