# Arystal

**Physics-based simulation of crystal growth. First case study: amethyst growing in a geode.**

> **Version 1 · exploratory tool, under development.** This repository presents the scientific approach, the current state and the limits of the project. Arystal is **not** a validated predictor of how real amethyst grows and must not be used as one. The simulation software itself is not distributed here.

---

## What is Arystal?

Arystal is a simulator of crystal growth from solution. It follows the boundary between crystal and fluid with a **phase-field model** and couples it to the transport of dissolved silica, to a **temperature-dependent solubility** of quartz, and to the kinetics of attachment at the crystal surface.

The first material studied is **amethyst** (α-quartz, SiO₂, with traces of iron) growing from the wall of a **geode** into a low-temperature hydrothermal fluid.

## Goal

To provide a tool for **exploring qualitatively** how a crystal's shape, iron zoning and growth rate respond to temperature and dissolved iron, and to move step by step towards a version **tested against observations**.

## Scientific approach

- **Diffuse interface.** A phase field marks crystal and fluid, with a thin smooth boundary that moves according to the local driving force and the orientation of the surface.
- **Supersaturation as the driver.** Growth is driven by the excess of dissolved silica over the solubility of quartz at the fluid temperature (Rimstidt, 1997, as reported in Takeno et al., 2000). Cooling raises supersaturation.
- **Flat faces.** The prism (*m*) and rhombohedral (*r*, *z*) face families grow at different relative rates that depend on surface orientation (Frank's kinetic construction). The simulated section is two-dimensional, longitudinal, parallel to the c-axis.
- **Iron zoning.** Iron is a second solute that is taken up by the crystal differently in each growth sector; the colour is **computed from** the incorporated iron.
- **Closed container.** Total dissolved-plus-crystal silica and iron are conserved, and this is checked numerically.
- **Controlled randomness.** Small random perturbations of the interface and the starting seed, reproducible from a single integer.

### Growth regime
With the published quartz rate law (Takeno et al., 2000) and an estimate of the silica diffusion coefficient, growth of geode crystals up to about 10 cm is estimated to be **limited by the surface reaction, not by diffusion** (Damköhler number between about 10⁻⁷ and 3×10⁻⁴). A numerical study shows a **plateau**: below a Damköhler number of about 0.06 the crystal shape at equal size no longer depends on it. See [`docs/04_validation_status.md`](docs/04_validation_status.md).

## Current capabilities (Phase 1)

| Capability | Status |
|---|---|
| 2D growth of a longitudinal section with flat faces | Implemented |
| Dissolved silica and temperature-dependent solubility (15–60 °C explored) | Implemented |
| Iron by growth sector and computed colour | Implemented (inputs provisional) |
| Changes of temperature and iron during a run, recorded so the run can be repeated exactly | Implemented |
| Sets of replicas with different random seeds, with statistics | Implemented |
| Two resolution modes: *explore* (qualitative) and *research* (aspect ratio converged to about 2 %) | Implemented |
| Interactive local interface | Implemented (local use only) |
| Internal checks of conservation, symmetry and convergence | 13 groups of checks, all passed |

## What it does **not** do (yet)
- It has not been compared with any real crystal or experimental data.
- It does not predict the shape, colour or growth time of a specific amethyst.
- It is not 3D, does not model fluid replenishment or gradual cooling, and treats iron as a passive tracer.

## Validation status (honest summary)
The current checks verify that the model **solves its own equations correctly**: mass conservation, symmetry, convergence with resolution, and agreement with reference solutions. **None** compares with observations of real crystals. Details and limits: [`docs/04_validation_status.md`](docs/04_validation_status.md) and [`docs/05_limitations_and_uncertainties.md`](docs/05_limitations_and_uncertainties.md).

## Figures
Illustrative outputs of version 1, with captions that state their limits, are in [`figures/`](figures/).

## Documentation

| Document | Content |
|---|---|
| [`docs/01_scope_and_approach.md`](docs/01_scope_and_approach.md) | Scope, physical system and approach |
| [`docs/02_model_overview.md`](docs/02_model_overview.md) | Conceptual description of the model (no implementation) |
| [`docs/03_verified_parameters.md`](docs/03_verified_parameters.md) | Quantities taken from sources that were read, with their provenance |
| [`docs/04_validation_status.md`](docs/04_validation_status.md) | What has been checked and what has not |
| [`docs/05_limitations_and_uncertainties.md`](docs/05_limitations_and_uncertainties.md) | Scientific limitations and open questions |
| [`docs/06_sources.md`](docs/06_sources.md) | References and how each was accessed |
| [`docs/07_roadmap.md`](docs/07_roadmap.md) | High-level roadmap |

## Author and citation
Luna Filosofa. See [`CITATION.cff`](CITATION.cff).

## License
The documentation and figures in this repository are licensed under [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International](https://creativecommons.org/licenses/by-nc-nd/4.0/) (see [`LICENSE`](LICENSE)). The Arystal simulation software is **not** part of this repository and is not covered by this license.
