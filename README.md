# Customer-Attrition-Prediction

# Details of the Project

- **Host** : Kaggle
- **Partner** : Kharagpur Data Analytics Group
- **Duration of competition** : May 3, 2021 -> May 11, 2021
- For more details visit [competition page](https://www.kaggle.com/c/customerattritionprediction/overview)

# Dataset

- Structure of Dataset is as follows:
     - train.csv [Contains training data]
     - test.csv [Contains 25% of test data]
     - Sample Submission.csv [sample csv file for submission]
- Prediction column : `Customer Attrition`
- Unique ID of customer : `ID`
- Dataset contains 14 features related to telecom data:

      `Sex`, `Aged`, `Married`, `Total Dependents`, `Service Span`, `Mobile Service`, `4G Service`, `Cyber Protection`, `Hardware Support`, `Technical Assistance`, `Film Subscription`, `Settlement Process`, `Quarterly Payment`, `Grand Payment`
- `Quarterly Payment`, `Grand Payment` are *continuous* data columns [In some experiments `Service Span` is also considered as continuous] and remaining are *Categorical* columns.

# Training

- I used `CatBoost`, `XGBoost`, `LightGBM`, `Histogram Gradient Boosting` techniques for training.
- After training based on obtaied feature importances, Various features were removed and experimented with different combination of features.
- In some cases I changed `Service Span` columns as continuous or `Bucketed data`, but there is no much change in leaderboard score.
- Finally the best models are ensembled and achieved 80.79% accuracy on 2800 unseen data samples.
- Even though I experiemnted with many models and enselbling models, kfold cross validation, leaderboard score saturated at around 81% accuracy.
- Following is one of the feature importance plot obtained from CatBoost training. [Use light model for better visualization of image :)]

![image](https://user-images.githubusercontent.com/65073329/124431650-3c32f880-dd8e-11eb-9073-df3f62eafdc4.png)

# models

- models folder contains the sample models (`.dump` format) obtained from 5 fold cross validation training with CatBoost model.

# catboost_info

- This folder consists of `logs` obtained during training of `CatBoost Classifier`.

# Conclusion 

- The order of score with various models given same data pipeline is as follows : 
            Cat Boost > Light GBM > XG Boost > Histogram Gradient Boosting
- **Note** :  This order varies with varying Training data and features.

                  
