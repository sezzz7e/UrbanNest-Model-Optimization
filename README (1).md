
# UrbanNest - Advanced Model Optimization

## Project Overview

This project focuses on improving house price prediction using the Ames Housing dataset.

The main objectives are:
- Analyze correlations and investigate potential data leakage.
- Perform numerical feature engineering.
- Build leakage-safe Scikit-learn preprocessing pipelines.
- Compare Ridge Regression, Random Forest, and XGBoost.
- Tune the best-performing model using RandomizedSearchCV.
- Identify the top five features using permutation importance.
- Save the final trained model.

## Dataset

Ames Housing Dataset:
https://www.kaggle.com/datasets/preathm/ames-housing-dataset

The dataset contains property information, with SalePrice as the prediction target.

Download AmesHousing.csv separately and place it in the same directory as the notebook before running it.

The dataset is not included in this repository.

## Feature Engineering

The project creates:
- House_Age
- Remodel_Age
- Total_Bathrooms
- Total_Porch_Area
- Total_Finished_Area

No feature derived from SalePrice is used as an input predictor.

## Data Leakage Prevention

- SalePrice is separated as the target.
- Order and PID are excluded from model inputs.
- Numerical imputation and scaling are performed inside a Scikit-learn Pipeline.
- Categorical imputation and one-hot encoding are performed inside the same Pipeline.
- Five-fold cross-validation is used on training data.
- The test set is held out for final evaluation.

## Models Compared

1. Ridge Regression
2. Random Forest Regressor
3. XGBoost Regressor

The best model is selected based on cross-validation MAE and tuned using RandomizedSearchCV.

## Evaluation

The project reports:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R-squared (R2)

See final_results.json, final_results.txt, and model_comparison.csv for the actual results.

## Feature Importance

Permutation importance is used to identify the five most important original input features.

See feature_importance.csv and top_5_feature_importance.png.

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

1. Clone or download this repository.
2. Install the dependencies:

   pip install -r requirements.txt

3. Download AmesHousing.csv from the dataset source.
4. Place AmesHousing.csv beside the notebook.
5. Open the notebook in Google Colab or Jupyter.
6. Run the cells in order.

## Baseline Comparison

Task 1 used Linear Regression as the baseline model.

Baseline MAE: $17,309.70

The Task 2 test results and percentage improvement are recorded in final_results.json and final_results.txt.

## Limitations

Results depend on the dataset, selected features, train-test split, and model settings. Permutation importance indicates predictive reliance, not causation.

## Author

UrbanNest Internship Project
