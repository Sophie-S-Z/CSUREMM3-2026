# Methods — High-Level Overview

This page intentionally stops at a conceptual level. It should let a reader understand what was done and why, without providing a reproduction recipe (exact hyperparameters, calibration procedures, or full pipeline code). Implementation specifics, tuned parameters, and full derivations are kept out of this repository; see [Data Sources & Availability](data-sources-availability.md) for why, and check back here for a link to the published paper/preprint once available.

The project has four stages, organized into two broad modeling "pillars." The first two stages build and validate a map of brain regions ranked by dynamical fragility. The last two stages use that map to simulate and compare strategies for protecting the brain from tau spread.

## Stage 1 — Modeling Regional Brain Dynamics

**Question it answers:** How does a brain region's local activity behave, given the activity of everything it's structurally connected to?

**Method class:** Each region's activity is represented with a *neural mass model* — a standard class of model in computational neuroscience that summarizes the collective behavior of a large population of neurons (rather than simulating individual cells) as a small number of coupled equations. The whole-brain system is then examined in the neighborhood of a *critical operating point*, a regime in which the brain's dynamics are maximally sensitive to perturbation — thought to be where healthy brain networks normally operate.

**Connects to:** This gives a mathematical description of each region's dynamics that Stage 2 can probe to ask how easily each region can be pushed out of that stable regime.

## Stage 2 — Ranking Regions by Dynamical Fragility

**Question it answers:** Given the whole-brain dynamical system from Stage 1, how much external "push" would it take to destabilize each individual region?

**Method class:** We apply *network control theory*, a mathematical framework for quantifying how easily a networked dynamical system can be steered toward a target state. Applied here, it produces a single number per brain region — the minimum control energy required to destabilize it — which we use to rank all regions from easiest-to-destabilize to hardest-to-destabilize. We refer to this ranking as the **critical lever map**.

**Connects to:** The lever map is a prediction about which regions are more or less dynamically vulnerable. Stage 3 tests that prediction against real patient data.

## Stage 3 — Validating Against Real Patient Data

**Question it answers:** Does the lever map actually predict where disease pathology shows up in real patients, and does it hold up under reasonable scrutiny?

**Method class:** We compare the lever map to multiple independent, real-world measurements of brain pathology (tau, amyloid, and structural atrophy) using standard rank-correlation and statistical-control methods, so the comparison isn't confounded by a region's raw connectivity. We also check that the result survives a battery of standard robustness checks (e.g., across disease stages, and against a randomized comparison model) rather than being an artifact of one particular slice of the data.

**Connects to:** A validated lever map gives us a principled, biologically grounded criterion to test in Stage 4, alongside other more conventional criteria (e.g., connectivity hubs, current disease burden).

## Stage 4 — Simulating Tau Spread & Protection Strategies

**Question it answers:** If we could selectively protect a set of brain regions from tau pathology, which selection criterion works best?

**Method class:** We use a *reaction-diffusion model* — a standard mathematical framework (originally developed to describe processes like population growth and gene spread, and previously adapted by other groups to model protein spread in neurodegenerative disease) that combines local pathology growth with spread along brain connectivity. The model is personalized to each patient using their own repeated brain scans over time. We then simulate several different strategies for choosing which regions to "protect" in this model — including the dynamically-informed lever map from Stage 2 — and compare how much each strategy slows simulated whole-brain tau accumulation.

**Connects to:** This is the project's practical payoff: a framework for comparing candidate targeting strategies for future anti-tau interventions, grounded in the dynamical framework developed in Stages 1–3.

---

*TODO: link to a published paper/preprint once it is completed.*
