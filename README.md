## Project Title
Predictive-Modeling-of-Insurance-Premiums

## Brief One Line Summary
Predicting individual medical insurance charges using demographic, lifestyle, addictions and health risk factors.

## Overview
This project investigates the drivers of medical insurance pricing and develops predictive models that quantify the effect of demographic and lifestyle variables on healthcare costs. The aim is to create transparency for stakeholders (insurers, regulators, and customers) while enabling actuarial teams to justify pricing models with defensible evidence.

The high-level deliverables are:
1. A cleaned and annotated dataset ready for downstream use.
2. Exploratory and explanatory visualizations illustrating cost drivers.
3. Predictive regression models capable of explaining >75% variance in charges.

## Problem Statement
As healthcare costs rise, customers demand greater transparency into premium pricing. Insurers face regulatory pressure to demonstrate fairness and justify surcharges linked to modifiable risk factors (e.g., smoking, obesity). The business problem is to identify the key variables influencing insurance charges and produce a predictive framework that explains at least 75% of cost variance. Success will be measured by:
- **Model R² > 0.75** on holdout data.
- **Actionable insights** for pricing governance (e.g., quantifiable premium multipliers).
- **Visualization artifacts** consumable by non-technical stakeholders.

## Tools and Technologies
- **Language**: Python 3.10+
- **Core Libraries**:
  - Data Processing: pandas, numpy
  - Visualization: seaborn, matplotlib
  - Modeling: scikit-learn
- **Database**: CSV file input (extensible to SQL)
- **Experiment Tracking**: Jupyter Notebook

## Methods
1. **Data Ingestion**: Load raw CSV from cloud-hosted dataset.
2. **Data Cleaning**:
   - Replace missing values (mean imputation for numerical, mode imputation for categorical).
   - Type casting of `Age` and `Smoker`.
   - Deduplication and formatting of currency values.
3. **Feature Engineering**:
   - Outlier analysis (BMI, Charges).
   - Scaling via `StandardScaler`.
4. **Exploratory Data Analysis**:
   - Correlation heatmaps.
   - Regression plots for continuous predictors.
   - Boxplots for categorical impacts.
5. **Model Development**:
   - Baseline Linear Regression (single and multi-variable).
   - Polynomial regression with pipeline.
   - Ridge regression with hyperparameter tuning (`alpha`).
6. **Validation Strategy**:
   - Train/test split (80/20).
   - R² and RMSE metrics.
   - Cross-validation scoring.
7. **Evaluation Metrics**:
   - R² (explained variance).

## Key Insights
- **Smoking status explains ~62% of cost variance** — insurers must continue to apply differentiated pricing.
- **Age correlates moderately with charges (~0.30)** — older members predictably incur higher costs; pricing tiers should account for age bands.
- **BMI contributes positively to costs (~0.20 correlation)** — overweight members generate elevated claims, warranting targeted wellness programs.
- **Region has negligible impact** — geographic pricing differentiation may not be justified.
- **Gender has minimal correlation with charges** — gender-based pricing adjustments risk regulatory non-compliance.
- **Polynomial regression achieved ~84% R² on training data** — nonlinear effects improve predictive fidelity.
- **Ridge regression with polynomial features yielded ~78% R² on test data** — robust enough for production.

## Results & Conclusion

Baseline Linear Regression (Smoker only): R² ≈ 0.62

Multivariate Regression: R² ≈ 0.75

Polynomial Regression (train): R² ≈ 0.84

Ridge Regression (test): R² ≈ 0.78

These results demonstrate that ~78% of insurance charge variability can be explained using demographic and lifestyle factors. Smoking is the dominant driver, followed by BMI and age. However, unexplained variance (~22%) likely reflects unobserved health conditions, catastrophic events, or data quality limitations.

Limitations:

Dataset lacks chronic disease indicators (diabetes, hypertension).

Model trained on a static CSV, not integrated into production data pipelines
  "Region": "Southeast"
}

## Author & Contact

Author: Sahil Sahu

Role: Data Analyst

Email: sahilsahu20aug@gmail.com
