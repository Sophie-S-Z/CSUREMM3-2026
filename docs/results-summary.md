# Results — Summary

This page walks through the project's headline findings for a reader who won't read the full paper. For how these results were produced, see [Methods — High-Level Overview](methods-overview.md); for the underlying data sources, see [Data Sources & Availability](data-sources-availability.md).

## 1. Tau pathology targets dynamically fragile regions, not just well-connected ones

Across a large cohort of patient scans, regions ranked as "hardest to destabilize" by our dynamical model consistently carried the highest tau burden — and this held up even after we accounted for how structurally connected each region was. In other words, a region's dynamical fragility predicted tau pathology *on top of*, not just because of, its hub status. The regions our model flagged as most dynamically vulnerable include exactly the areas long known from neuropathology to be struck earliest by tau, such as the entorhinal cortex and amygdala.

*Figure to be added: `../figures/critical-lever-map.png` — spatial map of dynamically fragile vs. resilient brain regions, overlaid with tau burden.*

## 2. Amyloid shows the opposite pattern — a built-in specificity check

When we ran the same comparison for amyloid, the other hallmark Alzheimer's protein, the pattern flipped: amyloid accumulated preferentially in the *easiest-to-destabilize*, well-connected hub regions, not the dynamically fragile ones. This dissociation matters because it rules out the more boring explanation that our model was just tracking general disease severity or general hub exposure. Tau and amyloid diverging in opposite directions on the same ranking is evidence that dynamical fragility is capturing something specific to tau vulnerability.

*Figure to be added: `../figures/tau-amyloid-dissociation.png` — comparison of tau vs. amyloid correlation with dynamical fragility rank.*

## 3. In simulation, protecting today's most-affected regions beats protecting tomorrow's most-vulnerable ones

We then asked a more practical question: if a future therapy could selectively protect a set of brain regions from tau spread, which regions should it target? We compared several strategies in a personalized simulation of tau spread, including our dynamically-informed ranking, structural hubs, current tau burden, and random selection. The strategy that most reduced simulated whole-brain tau spread was protecting the regions with the *highest existing tau burden* — outperforming the dynamically fragile regions identified earlier in the project.

This isn't a contradiction of Finding 1. It suggests our dynamical ranking is more useful for explaining *why* pathology tends to emerge where it does, while current tau burden is a more effective target *once* pathology is already underway and visible on a scan — the two frameworks appear to be more useful at different points in the disease timeline.

*Figure to be added: `../figures/protection-strategy-comparison.png` — comparison of simulated tau reduction across targeting strategies.*

## 4. Local growth mattered more than network-wide spread

Across our simulations, interventions that slowed a region's own local tau accumulation were consistently more effective than interventions that slowed tau's spread between regions. This points toward local biological processes (e.g., how tau is produced or cleared within a region) as a more promising lever for intervention, at least over the disease window captured in this dataset, than blocking transmission along brain connectivity.

---

This is part of an ongoing research project, and some validation checks are still in progress. A full write-up with methodological detail and caveats will be linked here once available. *TODO: link to published paper/preprint.*
