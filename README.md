# ABIDE Connectivity Analysis

## **Project Overview**
This repository contains an ongoing neuroimaging research project analyzing resting-state fMRI data from the **Autism Brain Imaging Data Exchange (ABIDE)**. The study focuses on identifying functional connectivity differences between individuals with **Autism Spectrum Disorder (ASD)** and typically developing controls, with a specific emphasis on the **Default Mode Network (DMN)**.

The primary objective of this project is to design a **reproducible data pipeline** that transforms large-scale, multi-site neuroimaging data into structured connectivity features suitable for statistical analysis and machine learning.

---

## **Dataset**
- **Source:** Autism Brain Imaging Data Exchange (ABIDE)
- **Modality:** Resting-state fMRI (rs-fMRI)
- **Data Access:** `nilearn.datasets.fetch_abide_pcp`
- **Preprocessing Pipeline:** CPAC  
  - Motion correction  
  - Slice timing correction  
  - Normalization to MNI space
    
- **Quality Control:** Only quality-checked subjects are included

### **Final Sample**
- **Total subjects:** 871  
  - ASD: 403  
  - Control: 468  

### **Phenotypic Variables Used**
- `DX_GROUP` (ASD vs Control)
- `AGE_AT_SCAN`
- `SEX`

---

## **Default Mode Network (DMN) Definition**
The Default Mode Network is defined based on convergent findings from prior literature. Core DMN regions examined in this project include:
- **Medial Prefrontal Cortex (mPFC)**
- **Posterior Cingulate Cortex / Precuneus (PCC)**
- **Inferior Parietal Lobule (IPL)**

---

## **Atlas and ROI Selection**
- **Atlas:** Schaefer 2018 Local-Global Functional Atlas
- **Parameters:**
  - 200 cortical parcels  
  - 7 functional networks  
  - 2 mm spatial resolution  

Using this atlas, **16 regions of interest (ROIs)** corresponding to DMN subregions were selected across both hemispheres, including subdivisions of:
- `PFCmp`
- `pCunPCC`
- `Default_Par`

---

## **Time-Series Extraction**
Regional time-series signals are extracted for each subject using:

- `nilearn.maskers.NiftiLabelsMasker`

This step:
- Applies the selected DMN ROIs as a mask
- Excludes non-DMN regions
- Outputs a matrix of **timepoints × 16 ROIs** per subject

---

## **Functional Connectivity Analysis**
Functional connectivity is computed using:
- **Pearson correlation**
- `nilearn.connectome.ConnectivityMeasure`

For each subject, a **16 × 16 connectivity matrix** is generated, representing pairwise correlations between DMN regions.

---

## **Statistical Analysis**
Group-level differences between ASD and control participants are assessed using **Welch’s t-tests**, which account for unequal variances and sample sizes.

- Each ROI-to-ROI connection is tested independently
- **Negative t-values:** hypo-connectivity in ASD
- **Positive t-values:** hyper-connectivity in ASD

Preliminary results indicate widespread **hypo-connectivity between anterior (mPFC) and posterior (PCC/precuneus) DMN regions** in ASD.

---

## **Visualization**
Results are visualized using:
- Connectivity matrices
- T-statistic plots
- Brain maps highlighting DMN ROIs

Visualizations are used for interpretation and exploratory analysis rather than final conclusions.

---

## **Machine Learning (In Progress)**
Planned extensions of this project include:
- Feature extraction from connectivity matrices
- Support Vector Machine (SVM) classification
- Hyperparameter optimization using `RandomizedSearchCV`
- Multiple kernels (linear, RBF, polynomial, sigmoid)
- Cross-validated evaluation metrics (accuracy, F1 score, balanced accuracy, ROC AUC)

---

## **Tools & Environment**
- **Language:** Python
- **Libraries:**
  - Nilearn
  - NumPy
  - SciPy
  - scikit-learn
  - Matplotlib
- **Environment:** Jupyter Notebook

---

## **Project Status**
 **Ongoing Research**

This repository reflects an active research project. Analyses, documentation, and structure may evolve as the study progresses. Final results are intentionally not included at this stage.

---

## **Ethics & Data Use**
- No raw neuroimaging data are stored in this repository
- All analyses follow ABIDE data-sharing guidelines
---

## **Author**
**Elif Nalan Mutlu**  
Undergraduate Researcher
