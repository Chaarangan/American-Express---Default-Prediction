### American Express - Default Prediction

- Mini Project - Kaggle Competition and Short Paper Submission
- Competition URL:  https://www.kaggle.com/competitions/amex-default-prediction/overview

#### Dataset
- A Post processed data, where float to int type conversions were done, is used (parquet format)
- It is a denoised version of AMEX dataset (https://www.kaggle.com/competitions/amex-default-prediction/data)
- Available at https://www.kaggle.com/datasets/raddar/amex-data-integer-dtypes-parquet-format

#### Techniques
- Numerical columns were scaled using StandardScaler
- Find the correlation between the feature column and dropped the columns using different threashold values, i.e, 0.5, 0.4, 03
- Also, having an optional parameter to keep all the columns except S_2.
- To flag problems like overfitting or selection bias, K-fold cross-validation was applied.
- Three models were trained: Light GBM and CatBoost, and their ensemble during the experiment (hyperparameters are in the notebook)
- Averaged both models' outputs gave the highest score.
