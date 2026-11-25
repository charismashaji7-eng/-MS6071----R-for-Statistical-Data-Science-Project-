# MS6071 Volatility Prediction Project

This project investigates whether recent market information can be used to predict periods of unusually high volatility in the S&P 500.

SPY ETF data from 2010–2025 were obtained from Yahoo Finance and used as a proxy for the S&P 500.

## Aim

The aim of the project is to predict whether volatility over the following five trading days will be high relative to recent historical volatility.

## Predictors

The final models use:

- Daily Return
- 20-Day Rolling Volatility
- 14-Day Relative Strength Index (RSI)

## Models

Two models were compared:

- Logistic Regression
- XGBoost

Logistic Regression was used as an interpretable baseline model, while XGBoost was used to investigate whether nonlinear relationships could improve predictive performance.

## Validation

Model performance was evaluated using expanding-window walk-forward validation from 2018 to 2023.

XGBoost hyperparameters were selected using a grid search across different tree depths, learning rates and numbers of boosting rounds.

A final untouched holdout period covering 2024–2025 was then used to evaluate both models.

## Evaluation Metrics

Models were compared using:

- Accuracy
- Area Under the ROC Curve (AUC)
- Brier Score

## Interactive Dashboard

A Shiny dashboard was developed to allow users to explore historical model predictions during the 2024–2025 holdout period.

Users can select a trading date and view:

- Market conditions on that date
- Logistic Regression probability of high volatility
- XGBoost probability of high volatility
- Model classifications
- The actual volatility outcome over the following five trading days

A link to the dashboard can be found here - https://darraghmcm.shinyapps.io/Downloads 

## Files

`SPY_Volatility_Prediction.R`  
Main analysis script containing data preparation, feature engineering, model fitting, validation, tuning and final evaluation.

`app.r`  
Shiny dashboard used to explore predictions from the final holdout period.

`final_test.rds`  
Saved final test dataset used by the Shiny application.

The repository also contains figures generated during the analysis.
