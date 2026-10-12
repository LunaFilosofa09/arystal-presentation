# 5. Scientific limitations and open questions

## What conditions every result
1. **The simulated habit depends directly on provisional inputs.** The relative growth rates of the *m*, *r* and *z* faces have not been calibrated against measurements; the elongation and termination of the simulated crystal follow from them. Changing them changes the shape.
2. **Several other inputs are also provisional and not yet calibrated**, notably the iron uptake coefficients, the dissolved iron concentration, the colour law, the silica diffusion coefficient and the noise amplitudes.
3. **No observational contrast.** The model has not been compared with real crystals.
4. **Tension with geological ages.** With the rate law read, a crystal of millimetres to centimetres would take roughly 10⁷–10⁹ years to grow at 15–60 °C, which is hard to reconcile with the age of host rocks. Possible causes, none verified: alkaline fluids, more strongly supersaturated fluids, other growth mechanisms, or an inadequate extrapolation of the rate constant. Any conversion to real time carries at least two orders of magnitude of uncertainty.
5. **Secondary source for the kinetics.** The rate law and constant were read in an article that quotes data from other authors; the original article was not read. An unresolved difference exists in the activation energy (the equation read implies about 71 kJ/mol; a different value of about 50 kJ/mol is quoted for an earlier rate constant, known only from abstracts).

## Simplifications of the model
2D section · closed container without fluid replenishment or external supply · instantaneous temperature changes · *r* and *z* treated alike (they differ in real quartz) · iron as a passive tracer, no effect of irradiation · no Dauphiné twinning · no pH or salinity effects · geometric surface · transport by diffusion only · a crystal silica capacity far below the real one (so model time is not a physical growth time).

## Numerical limits
- The aspect ratio converges slowly with resolution: at 200 cells across it is about 13 % below the converged value (about 2 % at 800). The *explore* mode is qualitative only.
- The termination of the crystal comes out rounded because of the regularisation of the interface.
- The well-mixed-fluid limit is valid only when the Damköhler number is much smaller than 1; it cannot show depletion zones around the crystal.

## How to read the results
Useful for **exploring trends** (for example how a faceted crystal responds to temperature or iron, with the inputs described above), comparing runs at the same resolution. They are not statements about the growth of a specific amethyst.
