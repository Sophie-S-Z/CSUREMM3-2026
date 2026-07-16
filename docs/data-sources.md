# Data Sources & Availability

> **Draft — confirm exact dataset names/versions with the team before treating this page as final and public.**

This project draws on data from access-controlled research cohorts and repositories. Two consortia apply:

- **ADNI** (Alzheimer's Disease Neuroimaging Initiative) — cross-sectional and longitudinal tau-PET, amyloid-PET, and structural (atrophy) biomarker data, along with clinical diagnosis information, used to validate the dynamical fragility ranking and to calibrate the tau-propagation model.
- **HCP** (Human Connectome Project) — diffusion tractography used to build the structural brain networks (connectomes) that the dynamical model runs on. *TODO: confirm with the team whether the connectome data used here should be cited/accessed as standard HCP data, or whether it requires going through the specific processing group's own data-sharing terms, since it is a derived tractography product rather than the raw HCP release.*

*TODO: once finalized, list the exact ADNI data products/versions used (e.g., specific tau-PET and amyloid-PET processing pipelines, the clinical/diagnosis table, and the structural metrics table), so a reader applying for ADNI access knows precisely which tables to request.*

## Why raw data isn't included here

Datasets like these are distributed under Data Use Agreements (DUAs) that prohibit public redistribution of raw or subject-level (including derived subject-level) data. In line with those agreements — and independent of that requirement, because we also don't want to hand over a turnkey reproduction — this repository does not include:

- Raw imaging or tabular data
- Subject-level derived measures (e.g., per-subject rankings, per-subject fitted parameters)
- Intermediate data products

## Getting access

Readers interested in working with the same class of data sources can apply for access directly through the originating consortia:

- **ADNI:** [https://adni.loni.usc.edu/data-samples/access-data/](https://adni.loni.usc.edu/data-samples/access-data/)
- **HCP:** [https://www.humanconnectome.org/study/hcp-young-adult/data-use-terms](https://www.humanconnectome.org/study/hcp-young-adult/data-use-terms)

*TODO: add any additional application link(s) if the connectome processing pipeline used here (beyond the base HCP release) has its own separate access process, once confirmed.*
