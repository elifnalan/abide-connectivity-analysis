# abide-connectivity-analysis
Data preprocessing and functional connectivity analysis of resting-state fMRI data from the ABIDE dataset.

ABIDE Connectivity Analysis
Overview

This repository contains an ongoing neuroimaging research project analyzing large-scale resting-state fMRI data from the Autism Brain Imaging Data Exchange (ABIDE). The project focuses on functional connectivity patterns, with particular emphasis on Default Mode Network (DMN) regions, using reproducible data preprocessing and analysis pipelines.

The goal of this repository is to document the data engineering, preprocessing, and feature-extraction workflow that prepares multi-site neuroimaging data for statistical analysis and machine learning.

Dataset

Source: Autism Brain Imaging Data Exchange (ABIDE)

Modality: Resting-state functional MRI (rs-fMRI)

Characteristics:

Multi-site dataset with heterogeneous scanning protocols

Large sample size

Includes phenotypic and demographic metadata

Only quality-checked, preprocessed data are used in this project.

Methods (High-Level)

This repository emphasizes pipeline design and data handling, rather than final results.

Current components include:

Data loading and quality filtering

Alignment of imaging data with phenotypic metadata

Identification of Default Mode Network regions using a functional brain atlas

Extraction of regional time-series signals

Construction of functional connectivity matrices

Preparation of connectivity features for downstream statistical testing and machine learning

Tools & Technologies

Language: Python

Libraries:

Nilearn

NumPy

SciPy

scikit-learn

Matplotlib

Environment: Jupyter Notebooks

Project Status

!! Ongoing research project

This repository is actively under development. Analyses, documentation, and structure may evolve as the research progresses. Final results and interpretations are intentionally not included at this stage.

Reproducibility & Ethics

All analyses prioritize reproducibility and transparent data processing.

No raw neuroimaging data are stored in this repository.

The project adheres to ABIDE data usage guidelines and research ethics standards.

Future Directions

Planned extensions include:

Expanded feature engineering for machine learning models

Cross-validated classification experiments

Subgroup analyses based on demographic variables

Additional documentation and visualization tools
