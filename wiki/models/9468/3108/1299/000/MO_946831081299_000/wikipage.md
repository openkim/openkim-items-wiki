## 1. Inconsistency in parameters

Line 5 of an EAM file in setfl format lists Nrho, drho, Nr, dr, cutoff, where Nrho is the number of tabulated values for embedding function and Nr is the number of tabulated values for electron density function and pair energy function in the subsequent arrays, drho is the spacing in electron density for embedding energy and dr is the distance space for electron density function and pair energy function, and cutoff is the global cutoff radius for both electron density function and pair energy function. The maximum electron density for embedding energy, rhomax, is 50 [1]. These variables should meet the following relations:

$$
drho = \frac{rhomax}{Nrho - 1}
$$

and

$$
dr = \frac{cutoff}{Nr - 1}
$$

However, the values in the parameter file (PtAu.eam.alloy), which are 

5000 1.000000000000e-02 5000 1.150000000000e-03 5.750000000000,

do not satisfy these relations.

## 2. Discontinuity issue

The model does not pass the continuity test (vc-dimer-continuity-c1) because the electron density and pair energy functions change too abruptly toward the cutoff radius.

## References

[1] O’Brien CJ, Barr CM, Price PM, Hattar K, Foiles SM. Grain boundary phase transformations in PtAu and relevance to thermal stabilization of bulk nanocrystalline metals, Journal of Materials Science, 53, 2911–2927, 2018.
