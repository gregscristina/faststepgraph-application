# Methodology and Experimental Configuration

This document describes the methodology used in the article *"Discovery of Conditionally Independent Networks Among Gene Expressions in Breast Cancer Using Fast Step Graph"*.

## Dataset Description

The data used in this study was obtained from the [Clinical Proteomic Tumor Analysis Consortium (CPTAC)]([https://proteomics.cancer.gov/data-portal](https://paynelab.github.io/cptac/tutorial01_data_intro.html)), specifically the breast cancer (BRCA) proteogenomic dataset. It contains expression values for 23,691 genes across 122 patients. The 50 genes from the PAM50 signature were used for analysis.

## Stratification and Preprocessing

Patients were stratified by hormone receptor status:
- ER positive (n = 81)
- ER negative (n = 39)
- PR positive (n = 68)
- PR negative (n = 47)

Each gene matrix was standardized (mean 0, std 1) using Z-score normalization to ensure that large expression variances do not dominate correlation structures.

## Experimental Design

We applied the `cv.FastStepGraph()` function 100 times per dataset, using:
- 5-fold cross-validation
- Search range: `0.5 ≤ α_f ≤ 0.9`, `α_b = α_f / 2`
- Averaged the optimal `α_f` and `α_b` across runs
- Recorded confidence intervals (CI 95%) and average execution time

Then, we applied `FastStepGraph()` once using the averaged parameters to estimate the final sparse precision matrix Ω.

## Summary of Hyperparameter Results
![Screenshot 2025-05-25 at 20 39 16](https://github.com/user-attachments/assets/e2aec340-dedc-4ad6-9020-a1e240391cfe)

## Graphs generated 
![Colorido2](https://github.com/user-attachments/assets/3cba525e-82f4-45e4-9c06-fd8038571836)


## Biological Interpretation

![Frame 10](https://github.com/user-attachments/assets/6b9857dd-250c-4ae9-ab46-bf0844041d00)

- **MYBL2–UBE2C**: associated with cell replication and resistance to cisplatin
- **TYMS–NDC80**: involved in triple-negative breast cancer and tumor progression
- **GRB7–ERBB2–KRT17–KRT14**: linked to brain metastasis and tumor aggressiveness

These communities appeared across multiple strata and match biological evidence in the literature.

