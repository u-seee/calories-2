Calorie Expenditure Prediction
Predicting calories burned during physical activity using Machine Learning
A complete end-to-end regression project built in R with the tidymodels ecosystem. The goal is to accurately predict calorie expenditure based on user and workout features.

Dataset

calorie_train.csv → Training data (features + target)
calorie_test.csv → Test data for final predictions
calorie_submission.csv → Kaggle-style submission template

Features: age, sex, weight, height, duration, heart_rate, body_temp, and several engineered variables.

Key Highlights

Exploratory Data Analysis with rich visualizations (histograms, boxplots, correlation matrices, pair plots)
Feature Engineering:
BMI
Heart Rate Reserve
Weight × Duration
Age²
Temperature difference from 37°C
Heart Rate × Duration & Heart Rate / Duration

Target transformation: log1p(calories) → better distribution & model performance
Preprocessing: Yeo-Johnson, normalization, dummy encoding, correlation & zero-variance filters
Model: Tuned Random Forest (ranger) with racing method (tune_race_anova)
Evaluation: RMSE + detailed residual analysis (log & original scale)


Final Workflow

5-fold stratified cross-validation
Hyperparameter tuning (mtry + min_n)
Final model refit on 100% of training data
Submission-ready predictions (back-transformed to original scale)


Technologies

Core: tidymodels, ranger, doFuture, bonsai
EDA & Viz: tidyverse, GGally, ggcorrplot, ggplot2
Others: janitor, skimr, vip, yardstick, flextable
