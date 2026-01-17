# Cancer Survival Prediction Using Regression Models

## Business Problem

Cancer survival outcomes vary significantly based on tumor type, stage at diagnosis,
treatment approach, and population characteristics. Healthcare systems and policymakers
need data-driven insight to understand which factors most strongly influence survival
in order to prioritize early detection, treatment strategies, and resource allocation.

This project uses machine learning to predict **1-year and 5-year cancer survival rates**
using publicly available cancer cohort data from the UK National Disease Registration
Service (NDRS).

---

## Dataset

**Source:** Get Data Out (GDO) – UK National Disease Registration Service  
**Granularity:** Aggregated cancer cohorts by cancer site, stage, age group, region, and treatment pattern  

Each row represents a cohort, not an individual patient.

Key features include:
- Cancer site and tumor type
- Stage at diagnosis
- Region and demographic group
- Treatment distributions (surgery, chemotherapy, radiotherapy, combinations)
- Incidence and cohort size
- Net survival rates at multiple time horizons

---

## Approach

The analysis follows a complete data science workflow:

1. **Data Cleaning**
   - Type conversion and missing-value handling
   - Removal of duplicates
   - Filtering to stable, population-level cohorts
2. **Exploratory Data Analysis**
   - Survival distributions
   - Survival by stage and cancer site
   - Incidence vs survival relationships
3. **Modeling**
   - Multiple regression models:
     - Linear Regression (baseline)
     - Ridge Regression
     - Lasso Regression
     - Random Forest Regression
   - Cross-validation for model robustness
   - Grid search for hyperparameter tuning
4. **Evaluation**
   - R² (variance explained)
   - RMSE and MAE (error magnitude and interpretability)

---

## Key Findings

- **Stage at diagnosis** is the strongest predictor of both 1-year and 5-year survival.
- **Cancer site** explains substantial variation in outcomes, even after controlling for stage.
- **Treatment patterns**, particularly surgery-related combinations, are associated with higher survival.
- Models predict **1-year survival more accurately than 5-year survival**, reflecting increased long-term uncertainty.

The best-performing model achieved strong explanatory power while maintaining interpretability.

---

## Business Implications

- Earlier diagnosis substantially improves survival outcomes, reinforcing the value of screening.
- Certain cancer groups and regions exhibit systematically lower survival, indicating potential gaps in care access.
- Treatment mix data can inform evidence-based planning and comparative effectiveness analysis.

---

## Next Steps

- Incorporate patient-level data if available
- Expand to multi-output survival modeling
- Explore causal inference techniques
- Integrate socioeconomic and comorbidity data

---

## Files

- **Notebook:** `cancer_survival_final.ipynb`
- **Data:** `data/GDO_data_wide.csv`
