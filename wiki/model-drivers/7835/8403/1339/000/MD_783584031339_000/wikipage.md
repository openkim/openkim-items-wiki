# The Environment-Dependent Interatomic Potential (EDIP)

This directory contains the environment-dependent interatomic potential (EDIP) model driver [[1,2,3,4,5](#references)].

## EDIP model driver

This KIM model driver is written in C++ and implements three styles of environment-dependent interatomic potential (EDIP):

- [edip](#edip-style)
- [edip/multi](#edipmulti-style)
- [edip/c](#edipc-style)

The style of the potential is automatically detected based on the input files to the driver. The input files are ASCII text files formatted to be consistent with LAMMPS.

This driver has a design to mimic and reproduce the behavior of the [edip](https://docs.lammps.org/pair_edip.html), and [edip/multi](https://docs.lammps.org/pair_edip.html) pair styles in [LAMMPS](https://www.lammps.org) and the edip pair style [edip/c](#references) developed for carbon [[2,3](#references)].

We adapted the LAMMPS format from the LAMMPS [documentation](https://docs.lammps.org) as of `July 30, 2021`.

For the two styles of `edip` and `edip/multi` [[4,5](#references)], the driver expects an [**element**](#edip-element-file-format) file and a [**parameter**](#edip-parameter-file-format) file.

For the `edip/c` style [[2,3](#references)], which is a transferable empirical potential developed for carbon, the driver only expects a [**parameter**](#edipc-parameter-file-format) file.

## EDIP style

The current model is an empirical potential popular for modeling silicon materials [[1](#references)]. It consists of two and three-body interactions with theoretically motivated functional forms that capture chemical and physical trends. The two and three-body terms have environment dependence controlled by the atomic coordination Z. The total energy is written as a sum of on-site energies,

$$U_i  = \sum_j U_{2}(r_{ij}, Z_{i}) + \sum_{j < k} U_{3}(r_{ij}, r_{ik}, Z_{i}),$$

The pair potential `U2` is an interaction between atoms `i` and `j` representing pairwise bonds, and `U3` is the interaction between atoms `i`, `j`, and `k` centered at atom `i` representing angular forces.

$$
  \begin{align*}
  &U_{2}(r, Z) = A\left[\left(\frac{B}{r}\right)^{\rho} - e^{-\beta Z^2}\right]exp{\left(\frac{\sigma}{r-a}\right)} \\
  &U_{3}(r_{ij}, r_{ik}, Z_i) = exp{\left(\frac{\gamma}{r_{ij}-a}\right)}exp{\left(\frac{\gamma}{r_{ik}-a}\right)}h(cos\theta_{ijk},Z_i).
  \end{align*}
$$

The two-body term, `U2` includes repulsive and attractive interactions, which go to zero at a distance equals to `a`. The three-body term, `U3` contains radial and angular factors. Both types of interactions depend on the local environment of atom `i` through its effective coordination number, defined by,

$$Z_i = \sum_{j \ne i} f(R_{ij}),$$

where `f` is a cutoff function that measures the contribution of neighbor `j` to the coordination of atom `i` in terms of the separation `r`. The neighbor function is unity for `r` less than `c`, with a gentle drop from `1` to `0` between `c` and `a`, and it is `0` for `r` greater than `a`.

$$
f(r) = \begin{cases}
       1 & \quad r<c \\
       \exp\left(\frac{\alpha}{1-x^{-3}}\right) & \quad c<r<a \\
       0 & \quad r>a
       \end{cases}
$$

All neighbors within the distance `c` to the particle `i` have full contribution, while others between `c` and `a` have a partial contribution to the coordination number `Z`. The angular function,

$$h(l,Z)=\lambda [(1-e^{-Q(Z)(l+\tau(Z))^2}) + \eta Q(Z)(l+\tau(Z))^2],$$

is strongly dependent on the local coordination through two functions,

$$\tau(Z)=u_1 + u_2 (u_3 e^{-u_4 Z} - e^{-2u_4 Z}),$$

and

$$Q(Z)=Q_0 e^{-\mu Z}.$$

These two functions control the equilibrium angle and the strength of the interaction, respectively. The various parameters in the EDIP formulas are listed in a file. The EDIP parameter file. The name usually contains the element name and ends in the `.edip` extension. For example, for a system containing `Si`, the `Si.edip` or `Si.parameter.edip` file contains the specific parameter settings.

### EDIP element file format

The element file contains a unique list of chemical element names separated by spaces:

```bash
  Elem1 Elem2 Elem3 ...
```

For example, for an Si system, the element file may look like this:

```bash
  Si
```

For an Si and C alloy system, the element file may look like this:

```bash
  Si C
```

For an alloy system containing Al, Si, Mg, Cu, and Fe, it could look like this:

```bash
  Al Si Mg Cu Fe
```

### EDIP parameter file format

The EDIP parameter file defines parameters for a triplet of elements. The parameters in a single entry corresponding to the two-body and three-body coefficients in the formula above,

```txt
  element1   element2   element3
  A          B          cutoffA   cutoffC   alpha   beta   eta
  gamma      lambda     mu        rho       sigma   Q0
  u1         u2         u3        u4
```

`element1` is the center atom in a 3-body interaction. The `A`, `B`, `beta`, and `sigma` parameters are used only for two-body interactions. The `eta`, `gamma`, `lambda`, `mu`, `Q0` and all `u1` to `u4` parameters are used for three-body interactions. The `alpha` and `cutoffC` parameters are used for the coordination environment function.

`A` and `lambda` have energy units, while `B`, `cutoffA`, `cutoffC`, `gamma`, and `sigma` have distance units and the rest of the parameters are pure numbers [[1](#references)].

### EDIP style example

As an example, a KIM Portable Model (PM) for pure Si systems that uses this model driver with the edip style contains the following two input files,

```bash
  elems.edip
  Si.edip
```

where `elems.edip` element file contains,

```bash
# list of elements
# Elem1
  Si
```

and the `Si.edip` parameter file contains,

```bash
# DATE: 2011-09-15 CONTRIBUTOR: Unknown CITATION: Justo, Bazant, Kaxiras, Bulatov and Yip, Phys Rev B, 58, 2539 (1998)

# EDIP parameters for various elements and mixtures
# multiple entries can be added to this file, LAMMPS reads the ones it needs
# these entries are in LAMMPS "metal" units

# format of a single entry (one or more lines)
#
#   element 1, element 2, element 3,
#     A   B   cutoffA   cutoffC   alpha   beta   eta
#     gamma   lambda    mu   rho   sigma   Q0
#     u1   u2   u3   u4
#
# units for each parameter:
#     A , lambda are in eV
#     B, cutoffA, cutoffC, gamma, sigma are in Angstrom
#     alpha, beta, eta, mu, rho, Q0, u1-u4 are pure numbers

# Here are the original parameters in metal units, for silicon from:
# J. F. Justo, M. Z. Bazant, E. Kaxiras, V. V. Bulatov, S. Yip
#       Phys. Rev. B 58, 2539 (1998)
#

Si Si Si 7.9821730 1.5075463 3.1213820 2.5609104 3.1083847 0.0070975 0.2523244
         1.1247945 1.4533108 0.6966326 1.2085196 0.5774108 312.1341346
         -0.165799 32.557 0.286198 0.66
```

## EDIP/MULTI style

This style supports multi-element systems, where the element file contains a unique list of elements. In addition, its parameter file must contain the number of unique elements to the power of 3 entries. For example, for a two-element system, the file must contain 8 entries and for a three-element system, the file must contain 27 entries.

### EDIP/MULTI style example

As an example, a KIM Portable Model (PM) for modeling silicon carbide is a two-element system. It contains the following two input files,

```bash
  elems.edip
  SiC.edip
```

where `elems.edip` element file contains,

```bash
# list of elements
# Elem1 Elem2
  Si    C
```

and the `SiC.edip` parameter file contains,

```bash
# DATE: 2017-05-16 CONTRIBUTOR: Laurent Pizzagalli CITATION: G. Lucas, M. Bertolus, and L. Pizzagalli, J. Phys. : Condens. Matter 22, 035802 (2010)
#
#   element 1, element 2, element 3,
#     A   B   cutoffA   cutoffC   alpha   beta   eta
#     gamma   lambda    mu   rho   sigma   Q0
#     u1   u2   u3   u4
#
# units for each parameter:
#     A , lambda are in eV
#     B, cutoffA, cutoffC, gamma, sigma are in Angstrom
#     alpha, beta, eta, mu, rho, Q0, u1-u4 are pure numbers
#

Si Si Si 5.488043 1.446435 2.941586 2.540193 3.066580 0.008593 0.589390
         1.135256 2.417497 0.629131 1.343679 0.298443 208.924548
         -0.165799 32.557 0.286198 0.66

C C C    10.222599 0.959814 2.212263 1.741598 1.962090 0.025661 0.275605
         1.084183 3.633621 0.594236 2.827634 0.536561 289.305617
         -0.165799 32.557 0.286198 0.66

C Si Si  7.535967 1.177019 2.534972 1.973974 2.507738 0.015347 0.432497
         1.191567 3.025559 0.611684 2.061835 0.423863 249.115082
         -0.165799 32.557000 0.286198 0.660000

Si C C   7.535967 1.177019 2.534972 1.973974 2.507738 0.015347 0.432497
         1.191567 3.025559 0.611684 2.061835 0.423863 249.115082
         -0.165799 32.557000 0.286198 0.660000

Si Si C  5.488043 1.446435 2.941586 2.540193 3.066580 0.008593 0.510944
         1.135256 2.721528 0.620407 1.343679 0.298443 229.019815
         -0.165799 32.557000 0.286198 0.660000

Si C Si  7.535967 1.177019 2.534972 1.973974 2.507738 0.015347 0.510944
         1.191567 2.721528 0.620407 2.061835 0.423863 229.019815
         -0.165799 32.557000 0.286198 0.660000

C C Si   10.222599 0.959814 2.212263 1.741598 1.962090 0.025661 0.354051
         1.084183 3.329590 0.602960 2.827634 0.536561 269.210350
         -0.165799 32.557000 0.286198 0.660000

C Si C   7.535967 1.177019 2.534972 1.973974 2.507738 0.015347 0.354051
         1.191567 3.329590 0.602960 2.061835 0.423863 269.210350
         -0.165799 32.557000 0.286198 0.660000
```

The file must contain 8 entries for `SiSiSi`, `SiSiC`, `SiCSi`, `SiCC`, `CSiSi`, `CSiC`, `CCSi`, `CCC`, that specify EDIP parameters for all permutations of the two elements interacting in three-body configurations.

## EDIP/C style

The `edip/c` [[2](#references)] style is a transferable empirical potential developed for carbon by extending the environment-dependent interaction potential proposed for silicon [[1](#references)]. This implementation extends EDIP [[1](#references)] to describe carbon, and in doing so, addresses the most significant weakness of silicon EDIP, namely, the absence of $$\pi$$-bonding effects. With this improvement important phenomena such as dihedral rotation penalties and $$\pi$$-repulsion are described.

The functional form of carbon EDIP consists of three components,

- Two-body pair energy,
- Three-body angular penalty,
- Generalized coordination.

Following silicon EDIP [[1](#references)], the two and three-body terms have environment dependence controlled by the atomic coordination Z. Within this framework, the total energy is written as a sum of on-site energies.

$$U_i=\sum_j U_{2}(r_{ij}, Z_{i})+\sum_{j<k}U_{3}(r_{ij},r_{ik},\theta_{jik},Z_{i}),$$

`U2` resembles the SW potential in being short-ranged, decaying to zero at a distance set by the denominator in the exponential term.

$$U_{2}(r,Z)=\epsilon\left[\left(\frac{B}{r}\right)^4-e^{-\beta Z^2}\right]\exp{\left(\frac{\sigma}{r-a-a'Z}\right)}.$$

The $$-\beta Z^2$$ describes the bond order. The three-body term follows silicon EDIP [[1](#references)] in using SW-like radial and angular terms with environmental dependence, having the form,

$$U_{3}(r_{ij},r_{ik},\theta,Z)=\lambda(Z)g(r_{ij},Z)g(r_{ik},Z)h(\theta,Z).$$

The components of `U3` are defined by,

$$
  \begin{align*}
  &\lambda(Z)=\lambda_0\exp[-\lambda'(Z-Z_0)^2],\\
  &g(r,Z)=\exp[\gamma/(r-a-a'Z)],\\
  &h(\theta,Z)=1-\exp\left\{-q[\cos\theta+\tau(Z)]^2\right\}.
  \end{align*}
$$

$$\tau(Z)$$ describes the variation in ideal bonding angle and is defined by, $$\tau(Z)=1-\frac{Z}{12}\tanh[t_1(Z-t_2)].$$ The spherical coordination contribution $$z_i$$ is
determined by the sum $$z_i=\sum{f(R_{ij})},$$ where $$f(R)$$ is a three-parameter function defined by,

$$
f(r) = \begin{cases}
       1 & \quad r<f_{low} \\
       \exp\left(\frac{\alpha}{1-x^{-3}}\right) & \quad f_{low}<r<f_{high} \\
       0 & \quad r>f_{high}
       \end{cases}
$$

The generalized coordination $$Z_i$$ augments $$z_i,$$

$$
  Z_i=z_i+\pi_3(z_i)X_i^{dih}+\pi_3(z_i)X_i^{rep3}+\pi_2(z_i)X_i^{rep2}.
$$

$$\pi_2$$ and $$\pi_3$$ are switching functions identifying 2-coordinated and 3-coordinated atoms and $$X_i$$ describes dihedral rotation, $$\pi$$-repulsion at a threefold site, and $$\pi$$-repulsion at a twofold site. Vector products capture the appropriate symmetries via the functions,

$$
  \begin{align*}
  &X_i^{dih}=Z_{dih}\sum \pi_3(z_j)(\mathbf{\hat{R}_{jm}.\hat{R}_{ik}\times\hat{R}_{il}})^2C^{dih}_{ijklm},\\
  &X_i^{rep3}=Z_{rep}\sum \pi(z_j)(\mathbf{\hat{R}_{ij}.\hat{R}_{ik}\times\hat{R}_{il}})^2C^{rep3}_{ijkl},\\
  &X_i^{rep2}=Z_{rep}\sum \pi(z_j)[1-(\mathbf{\hat{R}_{ij}.\hat{R}_{ik}})^2]C^{rep2}_{ijk}.
  \end{align*}
$$

where `jkl` are neighbors of `i`, and `m` is a neighbor of `j`, and $$\pi(z)$$ selects for twofold or threefold sites. The distance-based cutoff functions `C` are,

$$
  \begin{align*}
  &C^{dih}_{ijklm}=p(R_{ij})p(R_{ik})p(R_{il})p(R_{jm}),\\
  &C^{rep3}_{ijkl}=(R_{ij}-c_0)^2[1-p(R_{ij})]p(R_{ik})p(R_{il}),\\
  &C^{rep2}_{ijk}=(R_{ij}-c_0)^2[1-p(R_{ij})]p(R_{ik}).
  \end{align*}
$$

with the function `p(r)` equivalent to `f(r)` except for different endpoints. The various parameters in the `EDIP/C` formulas are listed in a parameter file. Usually, it is called the `C.edip` parameter file.

### EDIP/C parameter file format

The `EDIP/C` parameter file defines parameters coefficients,

```txt
  eps   BB       beta         sigma  a      aprime
  Z0    lambda0  lambdaprime  gamma  q
  flow  fhigh    alpha        plow   phigh  Zdih  Zrep  c0
  zbl   cutoff   skin         shift
```

The `eps`, `BB`, `beta`, `sigma`, `a`, and `aprime` parameters are used for two-body interactions. The `Z0`, `lambda0`, `lambdaprime`, `gamma`, and `q` parameters are used for three-body interactions. The `flow`, `fhigh`, `alpha`, `plow`, `phigh`, `Zdih`, and `Zrep` parameters are used for the coordination environment function. The `zbl` parameter indicates whether the pair potential within the EDIP formalism is smoothly switched to the ZBL pair potential at small separations. Due to environmental dependence, this transition is not straightforward. The approach is to use two Fermi-type scaling functions which are defined using three parameters `cutoff`, `skin`, and `shift`.

`eps`, `lambda0`, `Zdih`, `Zrep` parameters have `energy units`, and `sigma`, `a`, `aprime`, `gamma`, `flow`, `fhigh`, `plow`, `phigh`, `c0`, `cutoff`, `skin`, and `shift` have `distance units`. The `BB` parameter has the power of four `distance unit`. And the rest of the parameters are pure numbers.

**NOTE:**

Setting the `zbl` parameter to `1` indicates using ZBL pair potential and setting it to `0` indicates not using it. If `zbl` parameter is set to `0` any other parameter after that is optional and is ignored.

### EDIP/C style example

As an example, a KIM Portable Model (PM) for modeling carbon contains the following parameter file,

```bash
  C.edip
```

where the `C.edip` parameter file contains,

```bash
# DATE: 2021-07-20        Reference: N. A. Marks, Phys. Rev. B 63, 035401 (2000)

# format of a single entry (one or more lines)
#
#     eps   BB       beta         sigma  a      aprime
#     Z0    lambda0  lambdaprime  gamma  q
#     flow  fhigh    alpha        plow   phigh  Zdih  Zrep  c0
#     zbl   cutoff   skin         shift
#
# if zbl is 0, then \c cutoff, \c skin, \c shift are not necessary.
#
# units for each parameter:
#
#     eps, lambda0, Zdih, Zrep -> are in eV
#     sigma, a, aprime, gamma, flow, fhigh, plow, phigh, c0 -> are in Angstrom
#     cutoff, skin, shift -> are in Angstrom
#     BB -> is in Angstrom^4
#     beta, Z0, lambdaprime, q, alpha, -> are pure numbers
#     zbl -> is 0 or 1
#

20.0853862863495  0.827599951322299  0.0490161172713279  1.25714643580808  1.89225338775144  0.169794491000172
3.615             19.86394896867     0.30                1.35419222406125  3.5
1.547             2.270              1.544               1.48              2.000             0.30               0.06  3.2
0
```

## References

[1]  Justo, Jo\~ao F., and Bazant, Martin Z. and Kaxiras, Efthimios and Bulatov, V.V. and Yip, Sidney, "Interatomic potential for silicon defects and disordered phases," Phys. Rev.B, 58(5):2539--2550, Aug 1998.

[2]  Marks, N.A., "Generalizing the environment-dependent interaction potential for carbon," Phys. Rev.B, 63(3):035401, Dec 2000.

[3]  Christie, H.J. and Robinson, M. and Roach, D.L. and Ross, D.K. and Suarez-Martinez, I. and Marks, N.A., "Simulating radiation damage cascades in graphite," carbon, 81:105--114, 2015.

[4] [https://www.lammps.org](https://www.lammps.org)

[5] [https://docs.lammps.org/pair_edip.html](https://docs.lammps.org/pair_edip.html)
