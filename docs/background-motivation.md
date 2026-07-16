# Background & Motivation

Alzheimer's disease (AD) is defined, in part, by the buildup of a misfolded protein called tau. What's striking is that tau doesn't show up randomly across the brain — it follows a strikingly consistent spatial pattern, first appearing in a small set of regions (notably the entorhinal cortex, part of the brain's memory circuitry) years before symptoms appear, and only later spreading to the rest of the brain. This staged progression, first documented neuropathologically in the early 1990s, is one of the most reliable observations in AD research.

And yet, more than thirty years later, there is still no mathematical explanation for *why* those specific regions are struck first. That gap matters for two reasons. Scientifically, it means we don't fully understand the mechanism driving one of the two hallmark pathologies of Alzheimer's disease. Practically, it matters because any future therapy aimed at slowing or stopping tau spread will need to target *specific brain regions*, and right now we don't have a principled, mechanistic way to choose which ones.

## The leading explanation, and its blind spot

The most common explanation on offer is **hub vulnerability**: the idea that heavily connected brain regions ("hubs") are exposed to more pathological traffic simply because more pathways run through them, similar to how a well-connected airport sees more passengers pass through than a small regional one. This idea is supported by a body of prior work modeling protein spread as a diffusion process over the brain's structural wiring diagram (its *connectome*).

The blind spot in this explanation is that connectivity is a purely structural, static property — it describes how regions are wired together, not how each region's own local activity behaves once perturbed. Two regions can have identical connectivity and still respond completely differently to the same disturbance: one might quickly settle back into a stable pattern of activity, while the other might be tipped into a runaway, destabilized state far more easily. Because how-connected-you-are and how-easily-destabilized-you-are tend to be correlated but are not the same thing, existing connectivity-only models can't cleanly separate the two — meaning we don't actually know whether tau targets regions because of how they're wired, because of how their local dynamics behave, or some mix of both.

## This project's angle

This project asks a more dynamics-focused version of the vulnerability question: instead of "how connected is this region?", we ask "**how much of a push would it take to destabilize this region's own activity, given everything it's connected to?**" We treat that as a computable, region-by-region property of the brain, independent from (though related to) raw connectivity, and test whether it does a better job explaining where tau pathology actually shows up in real patient data.

If a region's dynamical fragility — rather than, or in addition to, its hub status — predicts where tau accumulates, that reframes what "vulnerability" means in Alzheimer's disease, and opens a path toward using computational models to identify which regions are worth protecting before pathology takes hold, rather than only describing pathology after the fact.

This page intentionally stays conceptual. For how these ideas were actually computed and tested, see [`methods-overview.md`](methods-overview.md); for what we found, see [`results-summary.md`](results-summary.md).
