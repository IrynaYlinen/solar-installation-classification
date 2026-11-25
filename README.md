# Solar Installation Customer Segment Classification

## Project Overview

This data science project focuses on classifying solar photovoltaic (PV) installations into two customer segments:

- **RES** — Residential installations
- **NON-RES** — Non-residential installations

The project investigates how technical, financial, and installation characteristics can be used to distinguish between customer segments through machine learning.

## Dataset

The project uses data from the **Lawrence Berkeley National Laboratory (LBNL) — Tracking the Sun** dataset.

- Observations: 1,000,000
- Original variables: 78
- Selected predictor features: 37
- Target variable: `customer_segment`

The dataset exhibits severe class imbalance, with residential installations accounting for 97.43% of all observations.

## Project Workflow

### 1. Data Understanding

- Dataset exploration and variable categorization
- Data quality assessment
- Missing values and duplicate records analysis
- Outlier detection
- Exploratory data analysis
- Feature association and correlation analysis

### 2. Data Preparation

- Binary target variable transformation
- Feature removal and data cleaning
- Feature engineering
- Stratified train–test split
- Feature-specific preprocessing
- Correlation-based feature selection

### 3. Modeling

Three ensemble classification models are evaluated:

- Gradient Boosting Classifier
- XGBoost Classifier
- CatBoost Classifier

Model performance is assessed using stratified 3-fold cross-validation and model-specific class weighting.

## Model Performance

Mean cross-validation results:

| Metric | Gradient Boosting | XGBoost | CatBoost |
|---|---:|---:|---:|
| Accuracy | 0.9491 | **0.9522** | 0.9506 |
| Balanced Accuracy | **0.9191** | 0.9185 | 0.9081 |
| Precision | 0.3218 | **0.3363** | 0.3260 |
| Recall | **0.8875** | 0.8829 | 0.8633 |
| F1-score | 0.4723 | **0.4871** | 0.4731 |
| ROC-AUC | 0.9719 | **0.9729** | 0.9671 |
| Average Precision | 0.7677 | **0.7909** | 0.7464 |
| Log Loss | 0.1937 | **0.1853** | 0.2011 |
| Brier Score | 0.0487 | **0.0462** | 0.0502 |

XGBoost achieved the best performance across seven of the nine evaluation metrics and was selected for further evaluation.

## Key Findings

- System size is a strong predictor of customer segment.
- Residential and non-residential installations differ substantially in system configuration and installation costs.
- Permutation Importance identifies system size and new construction status as the most influential features across all three models.
- Severe class imbalance and low minority-class precision remain important classification challenges.
- Segment-specific missingness requires further investigation for potential data leakage.

## Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- SciPy
- Matplotlib
- Seaborn
- Plotly
- Scikit-learn
- XGBoost
- CatBoost

## Project Notebook

[View the complete project notebook](Portfolio_SP_project.ipynb)

## Data Source

[Lawrence Berkeley National Laboratory — Tracking the Sun](https://trackingthesun.lbl.gov/)

## Project Status

In progress.

Planned next steps:

- Investigation of potential data leakage
- Model optimization
- Classification threshold optimization
- Final evaluation on the held-out test set

## Author

Iryna Ylinen