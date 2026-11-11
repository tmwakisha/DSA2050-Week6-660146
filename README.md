# DSA 2050 – Week 6 Guided Regression Lab

**Student name:** Tamara Mwakisha  
**Student ID:** 660146

## Objective
Estimate continuous sales (`Sales_KES`) from numeric business measures and categorical business descriptors, compare models against simple baselines, and examine validation performance and error behaviour.

## Models compared
Mean and median `DummyRegressor` baselines, Linear Regression, Ridge Regression (`alpha=1.0`), and a shallow Decision Tree (`max_depth=4`, `min_samples_leaf=8`). The analysis uses a reproducible 80/20 train/test split (`random_state=42`), leakage-safe preprocessing pipelines, and 5-fold cross-validation on training data only.

## Best model and findings
- Best single test-set candidate: **Ridge Regression** (MAE approximately **KES 13,714**, RMSE approximately **KES 17,459**, R² approximately **0.870**).
- Strongest test baseline: **Median Baseline** (MAE approximately **KES 39,147**). Ridge substantially improves on the baseline; its advantage over Linear Regression is very small.
- Training-only cross-validation also slightly favours Ridge, closely followed by Linear Regression.
- Linear-regression test residuals are near-centred, while some large errors remain; Retail has the highest customer-segment MAE among the checked segments.
- The unrestricted decision tree has zero training MAE but materially larger test MAE, consistent with overfitting.

## Limitations
1. The dataset is small (320 rows), making holdout and subgroup estimates uncertain.
2. Available predictors omit potentially important factors such as seasonality, product/store context, inventory and campaign details.
3. Data provenance and representativeness are not established, and future data drift may reduce model performance.
4. Predictive associations do not establish causation.

## Files
- `DSA2050_Week6_Guided_Regression_Lab.ipynb` — executed lab notebook with code, output tables, charts, and interpretation.
- `DSA2050_Week6_Sales_Data.csv` — supplied source data.

Before submission, replace the name/ID placeholders, restart the notebook kernel, and run all cells from top to bottom.
