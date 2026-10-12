# 2. Conceptual description of the model

This page describes **what** the model represents, not how it is implemented.

## Ingredients
1. **Phase field.** A variable between 0 (fluid) and 1 (crystal) with a thin, smooth interface; the interface moves according to the local supersaturation and the orientation of the surface.
2. **Dissolved silica.** It diffuses in the fluid and is consumed by the crystal as it grows. The container is closed: total silica (dissolved plus held in the crystal) is conserved.
3. **Supersaturation and solubility.** The driving force depends on how far the dissolved silica exceeds the solubility of quartz at the fluid temperature. The solubility curve is that of Rimstidt (1997), whose coefficients were read as quoted in Takeno et al. (2000) and reproduce the value of about 11 ppm at 25 °C quoted by Verma.
4. **Surface kinetics.** The net precipitation rate per unit surface is proportional to (S − 1), where S is the supersaturation ratio, with a temperature-dependent rate constant (Takeno et al., 2000, a secondary source).
5. **Anisotropy and flat faces.** Each face family (*m*, *r*, *z*) grows at its own relative rate, so slow orientations survive as flat faces and fast ones disappear (Frank's kinetic construction). These relative rates are provisional inputs of the current version (see document 5).
6. **Iron.** A second solute taken up by the crystal with a coefficient specific to each growth sector; the final colour is computed from the incorporated iron.
7. **Randomness.** A small, reproducible random perturbation of the interface and of the initial seed.

## Link to physical time
Internal time is dimensionless. In the surface-limited regime it can be related to real time through the rate law, with an uncertainty of at least two orders of magnitude (document 5).

## Modelling approximations
- The model uses a crystal silica capacity far below the real one, so that a closed container can form a visible crystal; as a consequence, model time is not a physical growth time (document 5).
- A well-mixed-fluid limit is used when transport is much faster than growth; it was checked against the full solution under the conditions tested.
