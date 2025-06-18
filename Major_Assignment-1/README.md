# Bulldozer Price Prediction

This project builds a regression model to estimate the auction sale prices of bulldozers based on historical sales data. The goal is to help Fast Iron create a pricing guide similar to a “Blue Book” for heavy equipment.

## Objectives
- Understand auction data and identify key price factors
- Build a predictive model using regression techniques
- Evaluate the model using RMSLE (which penalizes large errors)

## Data Cleaning & Feature Engineering
- Filled missing values using median for numerical columns and “Missing” for categoricals
- Extracted new features from the `saledate`, such as `saleYear`, `saleMonth`, and calculated `machine_age`
- Dropped irrelevant or ID-like columns (e.g., `SalesID`, `ModelID`)
- Used `OrdinalEncoder` for categorical variables, which works well with tree-based models

## Modeling Approach
I tested a few regression algorithms including:
- Random Forest
- Ridge Regression
- Decision Tree
- Gradient Boosting

Random Forest gave the best performance on the validation set, so I used it for the final predictions.

## Evaluation
I used RMSLE (Root Mean Squared Log Error) as the metric, since the competition penalizes under-prediction more heavily. Feature importances were also visualized to understand which inputs had the most influence on price.
