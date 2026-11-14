# UrbanNest - Advanced Model Optimization

## Project Overview

This project focuses on improving house price prediction
using the Ames Housing Dataset.

The main objectives were feature engineering, leakage analysis,
model comparison, and hyperparameter optimization.

## Dataset

- Dataset: Ames Housing Dataset
- Original shape: 2930 rows and 82 columns
- Target variable: SalePrice
- Source: https://www.kaggle.com/datasets/preathm/ames-housing-dataset

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Joblib

## Feature Engineering

- House_Age
- Remodel_Age
- Total_Bathrooms
- Total_Porch_Area
- Total_Finished_Area

SalePrice was excluded from the input features.
Order and PID were also removed.

## Data Preprocessing

A leakage-safe Scikit-learn Pipeline was implemented using:
- SimpleImputer
- StandardScaler
- OneHotEncoder
- ColumnTransformer

## Model Comparison

| Model | CV MAE | CV R2 |
|---|---:|---:|
| XGBoost | $14,324.07 | 0.8932 |
| Random Forest | $15,810.82 | 0.8768 |
| Ridge Regression | $16,463.24 | 0.8406 |

## Hyperparameter Optimization

RandomizedSearchCV was used to optimize XGBoost.

Best parameters:

```json
{
    "model__subsample": 0.9,
    "model__n_estimators": 400,
    "model__max_depth": 5,
    "model__learning_rate": 0.03,
    "model__colsample_bytree": 0.7
}
```

## Final Evaluation

- Baseline MAE: $17,309.70
- Optimized Test MAE: $13,603.27
- Optimized Test RMSE: $23,023.79
- Optimized Test R2: 0.9339
- MAE Improvement: 21.41%

## Top 5 Important Features

- Overall Qual: 14353.947461
- Total_Finished_Area: 8537.694727
- Gr Liv Area: 3926.581836
- Year Built: 1668.580957
- Lot Area: 1351.370312

## Project Files

- UrbanNest_Advanced_Model_Optimization.ipynb
- urbannest_best_model.joblib
- model_comparison.csv
- feature_importance.csv
- final_results.json
- final_results.txt
- correlation_heatmap.png
- baseline_vs_optimized.png
- top_5_feature_importance.png
- requirements.txt

## How to Run

1. Install the required libraries using requirements.txt.
2. Download the Ames Housing dataset.
3. Place AmesHousing.csv in the working directory.
4. Open the notebook in Google Colab or Jupyter.
5. Run the notebook cells in order.

## Notes

- The original dataset is not included in this repository.
- Dataset redistribution must follow its applicable license.
- The model was evaluated using a held-out test set.
- Live application deployment was not included.