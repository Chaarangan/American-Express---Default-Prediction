### American Express - Default Prediction

- Mini Project - Kaggle Competition and Short Paper Submission
- Competition URL:  https://www.kaggle.com/competitions/amex-default-prediction/overview

#### Dataset
- A Post processed data, where float to int type conversions were done, is used (parquet format)
- It is a denoised version of AMEX dataset (https://www.kaggle.com/competitions/amex-default-prediction/data)
- Available at https://www.kaggle.com/datasets/raddar/amex-data-integer-dtypes-parquet-format

#### Methodology
- The imputation method is used to fill in the missing or NaN values in the dataset
- Numerical columns were scaled using StandardScaler and RobustSclaer for handling outliers
- Find the correlation between the feature column and dropped the columns using different threshold values, i.e, 0.5, 0.4, 03
- Also, having an optional parameter to keep all the columns except S_2.
- To flag problems like imbalanced, overfitting, or selection bias, Stratified K-fold cross-validation was applied.
- Five models were trained: SVM, KNN, Light GBM, and CatBoost, and an ensemble of LGBM & CatBoost during the experiment (hyperparameters are in the notebook)
- Total 10 experiments: without K-fold for 5 models, and with K-fold for 5 models
- In addition, logged the average of the CatBoost & LGBM models' outputs for final submission. This gave the highest score with K-Fold cross-validation.