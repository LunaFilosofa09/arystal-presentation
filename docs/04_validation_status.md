# 4. Validation status

## What has been checked (internal checks)
13 groups of checks, with 60 judged tests and 3 informative measurements, **all passed**:

- **Isotropic case:** without anisotropy the crystal is a smooth half-disc and grows at the speed predicted by theory (difference below 1 %).
- **Symmetry and flat faces:** with *r* and *z* equal, the section is symmetric about the c-axis; with *r* ≠ *z* it is not; flat faces sit where Frank's construction places them (errors of 2–4 %). The apex of the termination comes out rounded, about 15 % below the ideal: a known numerical limitation.
- **Conservation** of silica and of iron to rounding level, while growing and while dissolving.
- **Solubility:** the implemented curve coincides with the published equation and reproduces about 11 ppm at 25 °C.
- **Resolution convergence:** the aspect ratio changes by 7.3 %, 5.0 % and 2.1 % when refining from 200 to 1600 cells across the container; the ratio of the *r* and *m* face distances by 3.5 %, 1.4 % and 0.45 %. At 200 cells the aspect ratio is about 13 % below its converged value.
- **Comparison between numerical schemes:** the fast variants agree with the readable reference (differences of about 10⁻¹⁵ after thousands of steps), and the numerical approximations agree with the full solution in the cases tested.
- **Reproducibility:** the same seed, parameters and record of changes give the same result.
- **Qualitative behaviour:** higher supersaturation gives faster growth (4.3 times faster between S = 1.6 and S = 3.3, in model time).

## Study of the growth regime
Varying the model's Damköhler number (the ratio of attachment speed to diffusive supply speed), the crystal shape at equal size changes strongly above about 0.6 and **stops changing** (by 0.4 % or less) below about 0.06. The estimated real value (about 10⁻⁷ to 3×10⁻⁴) lies on that plateau. Within the model, therefore, the shape in the estimated regime does not depend on the exact value of this number.

## What has **not** been checked
- **No comparison with real crystals or experiments.**
- The expectation that very high supersaturation destabilises flat faces was not observed up to S = 30 with small crystals; the expectation itself has not been verified against the literature, so the result is reported as a measurement, not a conclusion.
- The plateau was measured for one geometry and a few conditions (20 and 40 °C).
- The spread between replicas depends on noise amplitudes that are not calibrated against real crystals.
