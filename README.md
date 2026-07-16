# CSUREMM3-2026 — Public Summary

> This is a curated, public-facing repository for a CSUREMM 2026 research project. It exists to give readers an accurate overview of the motivation, approach, and high-level results. See [Repository Scope](#repository-scope) for what is and isn't included, and why.

## Status

This repo is currently being updated and items will be added incrementally as the team finalizes what's ready to publicly share.

## Overview

Alzheimer's disease tau pathology doesn't spread randomly — it reliably starts in specific brain regions, like the entorhinal cortex, years before symptoms appear, but there's no mathematical explanation for why those regions are hit first. This project asks whether the answer lies not in how connected a region is, but in how easily its local activity can be pushed out of a stable state. We built a computational framework that ranks brain regions by this dynamical fragility, tested whether that ranking predicts where tau pathology actually accumulates in real patient data, and used it to simulate which regions would be most valuable to protect with a future anti-tau therapy.

## Research Questions

RQ1: Network Control Theory vs. Tau Pathology - To what extent does regional minimum control energy predict spatial tau accumulation in early Alzheimer's disease, even after controlling for structural hub degree?  
RQ2: Targeted Protection - How does protecting dynamically-informed ``critical lever'' regions and hard-to-tip regions in a tau-propagation simulation compare with protecting high-degree hubs, highest-baseline-tau regions, or random regions in mitigating whole-brain tau accumulation?

## Approach (high level)

The project uses a two-stage computational pipeline. First, we model each brain region's activity with a neural mass model tuned near a critical operating point, then use network control theory to calculate how much external "push" it would take to destabilize each region, producing a brain-wide ranking from most to least dynamically resistant. We test whether this ranking predicts real tau and amyloid burden in a large ADNI cohort. Second, we calibrate a reaction-diffusion model of tau spread to each patient's own longitudinal tau-PET scans, and use it to simulate and compare strategies for protecting brain regions from tau accumulation. View the full description in docs/methods-overview.md.

## Key Results

- Tau pathology consistently accumulates in the most dynamically resistant ("hardest-to-tip") brain regions rather than the most connected ones, and this relationship holds — and strengthens — even after accounting for hub degree.
- Amyloid shows the opposite pattern, accumulating in easy-to-tip hub regions, which helps confirm that the tau finding is a specific signal rather than a generic marker of disease burden.
- In simulation, protecting regions based on their current tau burden slowed whole-brain tau spread more effectively than protecting the dynamically fragile regions identified in the first half of the project, suggesting the two frameworks may be more useful at different stages of disease progression. View the full walkthrough in docs/results-summary.md.

## Repository Scope

**Included:**
- Project background & motivation ([`docs/`](docs/))
- A high-level, conceptual description of the methods (not full derivations, hyperparameters, or calibration procedures)
- Final, polished figures ([`figures/`](figures/))
- Presentation materials — poster / slides ([`poster/`](poster/)), once finalized
- Optionally, an example/synthetic-data demonstration illustrating the *shape* of the approach ([`demo/`](demo/))

**Not included:**
- Raw or subject-level data (e.g., neuroimaging cohort data) — see [`docs/data-sources.md`](docs/data-sources.md) for why and how to get it yourself
- The full analysis/modeling pipeline, calibration code, or tuned parameters
- Intermediate results, exploratory analyses, or working notebooks

This is a private research collaboration, and the full working repository and data are not public.

## Team

Sophie Zhang (Columbia College '29), Rafia Hossain (Barnard College '28), & Arda Alisan (General Studies '28) 

Part of Columbia CSUREMM 2026 (summer mathematical modeling research program).

## Citation

If you reference this work, please cite it — see [`CITATION.cff`](CITATION.cff).

## License

- Text, docs, and figures in this repository: **CC BY-NC-ND 4.0** — see [`LICENSE`](LICENSE). You may share with attribution, but not adapt or use commercially.
- Any illustrative demo code carries its own permissive license scoped to that subfolder.

## Contact

Contact sz3438@columbia.edu, rh3272@barnard.edu, & aa5975@columbia.edu for questions about this project.
