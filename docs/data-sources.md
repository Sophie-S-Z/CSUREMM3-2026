# Data Sources & Availability

This project draws on data from access-controlled research cohorts and repositories. Two consortia apply:

- **ADNI** (Alzheimer's Disease Neuroimaging Initiative) — cross-sectional and longitudinal tau-PET, amyloid-PET, and structural (atrophy) biomarker data, along with clinical diagnosis information, used to validate the dynamical fragility ranking and to calibrate the tau-propagation model.
- **HCP** (Human Connectome Project data from the PIT Bioinformatics Group) — diffusion tractography used to build the structural brain networks (connectomes) that the dynamical model runs on.

Our data pipeline & documentation:

Tau-PET, non-PVC: UCBERKELEY_TAU_6MM.csv
UC Berkeley tau PET regional SUVR table, 6 mm, used for the main tau analysis. The current cleaning step keeps only QC-pass scans and FTP/flortaucipir tracer data in 01_clean_tau_pet.py.

Tau-PET, PVC: UCBERKELEY_TAUPVC_6MM.csv
The same UC Berkeley tau-PET product in PVC-corrected form, used as the robustness variant in DATA_GUIDE.md.

Amyloid-PET: UCBERKELEY_AMY_6MM.csv
UC Berkeley amyloid PET regional SUVR table, used after tracer restriction to FBP/florbetapir in the current pipeline in pet_pipeline.py.

Structural MRI / atrophy metrics: UCSFFSX7.csv
UCSF FreeSurfer v7 morphometry table containing cortical thickness and subcortical volume metrics used for the atrophy analysis in DATA_GUIDE.md.

Clinical/diagnosis table: ADNIMERGE_grouping.csv
Subject-level ADNI grouping/diagnosis table used for diagnosis, age/sex covariates, amyloid status, and ABETA positivity in 04_pet_per_subject_wscores.py.

## Why raw data isn't included here

Datasets like these are distributed under Data Use Agreements (DUAs) that prohibit public redistribution of raw or subject-level (including derived subject-level) data. In line with those agreements, this repository does not include:

- Raw imaging or tabular data
- Subject-level derived measures (e.g., per-subject rankings, per-subject fitted parameters)
- Intermediate data products

## Getting access

Readers interested in working with the same class of data sources can apply for access directly through the originating consortia:

- **ADNI:** [https://adni.loni.usc.edu/data-samples/access-data/](https://adni.loni.usc.edu/data-samples/access-data/)
- **HCP:** [https://www.humanconnectome.org/study/hcp-young-adult/data-use-terms](https://www.humanconnectome.org/study/hcp-young-adult/data-use-terms)
