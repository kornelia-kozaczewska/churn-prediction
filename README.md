# Customer Churn Prediction

This project focuses on predicting customer churn for a fitness club using statistical analysis and machine learning models.  
The workflow includes **data exploration, feature selection, preprocessing, model training, and evaluation**.

Dataset: [Gym customers features and churn](https://www.kaggle.com/datasets/adrianvinueza/gym-customers-features-and-churn/data)


## Exploratory Data Analysis (EDA)

- **Chi-Square Test** was used to check associations between categorical variables and churn.
  - Significant predictors: `Near_location`, `Partner`, `Promo_friends`, `Group_visits`.
  - Not significant: `Gender`, `Phone` (removed from further analysis).

- **Entropy & Information Gain** confirmed that the strongest predictors are:
  - `Age`
  - `Avg_additional_charges_total`
  - `Month_to_end_contract`
  - `Lifetime`
  - `Avg_class_frequency_total`
  - `Avg_class_frequency_current_month`


## Data Preprocessing
- Dataset split: **train (75%)** and **test (15%)**.
- Outliers were detected but retained (not data errors).
- **RobustScaler** applied to numerical features to mitigate outlier influence.


## Modeling
Four supervised learning algorithms were compared:
1. Logistic Regression  
2. Random Forest  
3. Gradient Boosting Classifier  
4. XGBoost  


## Results

| Model                      | Recall | Weighted F1 | AUC    |
|-----------------------------|--------|--------------|--------|
| Logistic Regression         | 0.799  | 0.910        | 0.9665 |
| Random Forest               | 0.805  | 0.912        | 0.9695 |
| Gradient Boosting Classifier| 0.598  | 0.866        | 0.9418 |
| **XGBoost**                 | **0.848** | **0.939** | **0.9791** |

- **XGBoost** achieved the best results, with the highest recall and weighted F1, as well as the highest AUC.  
- The confusion matrices confirmed a strong balance between correctly identifying churners and non-churners.


## Feature Importance
Across models, the most influential variables were:
- `Avg_class_frequency_current_month`  
- `Avg_class_frequency_total`  
- `Lifetime`  
- `Month_to_end_contract`  
- `Avg_additional_charges_total`  
- `Age`  

In all models, **behavioral factors** are more important than demographic or promotional ones.


## Conclusion
- Customer churn can be effectively predicted with **ML models (XGBoost, Gradient Boosting, Random Forest, Logistic Regression)**.  
- **XGBoost** showed the strongest performance (AUC > 0.96).  
- Business recommendations: focus on **longer contracts** and **increasing class attendance** to reduce churn. 
