
# Capstone Project: What Drives National Mortality Rates?

## Summary

This project analyzes a global health statistics dataset to determine which factors most strongly influence a nation's overall mortality rate.

The analysis used both exploratory data analysis and multiple machine learning models.  
Careful examination of the dataset's feature distributions and relationships revealed strong indications of **synthetic data balancing**, which impacted model interpretability and real-world generalizability.

---

## Techniques Used

- Exploratory Data Analysis (EDA)
    - Feature distributions
    - Correlation heatmap
    - Feature vs. Mortality Rate scatterplots
    - Feature vs. Mortality Rate grid with correlation values
- Feature Engineering & Scaling
- Dimensionality Reduction (PCA)
- Regression Models:
    - Linear Regression
    - Random Forest Regression
    - K-Nearest Neighbors (KNN) Regression
    - Multi-layer Perceptron (Neural Network) Regressor
    - XGBoost Regressor

---

## Findings

### Data Quality & Structure

- The mortality rate (%) showed a **uniform distribution**, rather than the expected real-world skew toward lower mortality.
- All key feature vs. mortality rate scatterplots appeared **flat**, with correlation coefficients close to zero.
- Even features expected to correlate with mortality (DALYs, Healthcare Access, Education Index, Per Capita Income) showed **no meaningful relationship**.
- This indicates that the dataset is likely **synthetically generated or balanced** and may not represent actual global mortality patterns.

### Model Performance

- XGBoost Regressor consistently achieved the best performance (highest R², lowest RMSE), but given the flat feature relationships, this primarily reflects the model fitting noise or artifacts in the dataset.
- Simpler models (Linear Regression, KNN) performed similarly poorly, further confirming the lack of strong underlying patterns.

### Key Insight

- **The lack of feature-mortality relationships indicates that the dataset is not suitable for drawing causal inferences or actionable insights about real-world mortality rates.**

---

## Interpretation of Results

> We conducted an in-depth exploratory analysis of feature relationships with mortality rate.  
> The scatterplots and correlation grid confirm that the features have little to no linear relationship with mortality rate in this dataset (most correlation coefficients ≈ 0), further suggesting synthetic balancing or lack of real-world signal.  
> As such, while the project successfully applied a range of ML techniques, the findings primarily highlight **the importance of validating dataset realism** before trusting model outputs.  
> This is a critical takeaway for data science best practice.

**Disclaimer:** The observed lack of feature relationships and uniform distribution of mortality rates suggest that this dataset may not accurately reflect real-world global health patterns. As such, model findings from this project should not be interpreted as causal or predictive insights about actual national mortality rates, but rather as a demonstration of machine learning techniques on the provided dataset.

---

## Next Steps

- Apply this same modeling pipeline to a validated, real-world health outcomes dataset to compare findings.
- Use SHAP or LIME explainability tools to further confirm whether any weak patterns exist in this dataset.
- Explore potential time series modeling if longitudinal data becomes available.
- Repeat this pipeline on a **validated, peer-reviewed dataset** to generate more actionable insights.

---

## Files

- `Capstone_Mortality_Rate_Project.ipynb` — complete notebook with full EDA, PCA, regression models, and interpretability analysis.

---

## Executive Summary

This project explored which factors drive national mortality rates using a global health statistics dataset.  
We applied a full suite of exploratory data analysis (EDA), feature engineering, dimensionality reduction, and multiple machine learning models including XGBoost, neural networks, and ensemble techniques.

Our analysis revealed that key features such as DALYs, Healthcare Access, Per Capita Income, and Education Index showed no meaningful relationship with mortality rate — confirmed visually and via correlation analysis.  
The mortality rate itself was uniformly distributed, suggesting that the dataset was synthetically balanced rather than representative of real-world mortality patterns.

While our models performed technically well, their outputs reflected data artifacts rather than genuine predictive relationships.  
This project highlights the critical importance of validating dataset realism before applying machine learning to health outcomes.  
Future work should repeat this pipeline with a validated real-world dataset to derive actionable insights.

---
