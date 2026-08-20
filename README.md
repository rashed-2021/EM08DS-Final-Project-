# Predicting Trust in AI-Based Decision-Making

**EM08DS — Research Methods (Final Project)**
**Emirates Aviation University**

## Overview

This repository contains the survey instrument, dataset, and analysis pipeline used to investigate whether individual characteristics, including AI familiarity, technical background, age, usage frequency, perceived transparency, and bias concern, can predict a respondent's overall level of trust in AI-based decision-making using supervised machine learning classifiers.

**Research Question:** Can self-reported attitudinal and demographic survey features predict an individual's level of trust (High vs. Low) in AI-based decision-making, and which factors are the strongest predictors?

## Repository Structure

```text
.
├── data/
│   └── ai_trust_survey.csv              # survey dataset
├── scripts/
│   ├── generate_data.py                 # dataset generation and survey logic
│   └── analysis.py                      # LOOCV classification pipeline
├── figures/
│   ├── fig1_model_comparison.png
│   ├── fig2_feature_importance.png
│   └── fig3_confusion_matrix.png
├── questionnaire.html                    # Activity 5.1 survey instrument
├── requirements.txt
├── LICENSE
└── README.md
```

## Data

See `data/README_DATA.md` for full data documentation, including variables, coding, dataset preparation, and ethical handling.

## Reproducing the Analysis

```bash
pip install -r requirements.txt
python scripts/generate_data.py
python scripts/analysis.py
```

The first script prepares the dataset used for the analysis. The second script runs the classification analysis using Leave-One-Out Cross-Validation and saves the resulting figures.

## Methods Summary

Two classifiers were used to predict the binary trust label (High Trust / Low Trust), which was derived from a composite Likert score:

* Logistic Regression (standardised features)
* Random Forest (300 trees, maximum depth of 4)

Given the small sample size (N = 45), Leave-One-Out Cross-Validation (LOOCV) was used instead of a single train/test split to provide a more stable estimate of out-of-sample performance.

## Ethics

The research design uses anonymous survey-style data and does not include personally identifying information. The dataset and questionnaire are intended for the purposes of the EM08DS Research Methods final project. See the Ethics Statement in the accompanying research report for further details.

## Author

Rashed — MSc / EM08DS Research Methods.


