# Customer Churn Prediction

This project focuses on predicting customer churn for a fitness club using statistical analysis and machine learning models.  
The workflow includes **data exploration, feature selection, preprocessing, model training, and evaluation**.

---

## 📊 Exploratory Data Analysis (EDA)

- **Chi-Square Test** was used to check associations between categorical variables and churn.
  - Significant predictors: `Near_location`, `Partner`, `Promo_friends`, `Group_visits`
  - Not significant: `Gender`, `Phone` (removed from further analysis)

- **Entropy & Information Gain** confirmed that the strongest predictors are:
  - `Age`
  - `Avg_additional_charges_total`
  - `Month_to_end_contract`
  - `Lifetime`
  - `Avg_class_frequency_total`
  - `Avg_class_frequency_current_month`

---

## ⚙️ Data Preprocessing
- Dataset split: **train (75%)**, **validation (15%)**, **test (10%)**
- Outliers were detected but retained (not data errors)
- **RobustScaler** applied to numerical features to mitigate outlier influence

---

## 🤖 Modeling
Four supervised learning algorithms were compared:
1. Logistic Regression  
2. Random Forest  
3. Gradient Boosting Classifier  
4. XGBoost  

---

## 📈 Results

| Model                     | Accuracy | AUC    |
|----------------------------|----------|--------|
| Logistic Regression        | 0.90     | 0.9656 |
| Random Forest              | 0.90     | 0.9598 |
| Gradient Boosting Classifier | 0.89   | 0.9666 |
| XGBoost                    | 0.91     | 0.9669 |

- **XGBoost** achieved the best trade-off between accuracy and AUC.  
- Confusion matrices showed a strong balance in detecting churners and non-churners.  

---

## 🔑 Feature Importance
Across models, the most influential variables were:
- `Avg_class_frequency_current_month`  
- `Avg_class_frequency_total`  
- `Lifetime`  
- `Month_to_end_contract`  
- `Avg_additional_charges_total`  
- `Age`  

These features provide **clear business insights**: customers with shorter contracts, lower attendance, and shorter lifetime are more likely to churn.

---

## 📝 Conclusion
- Customer churn can be effectively predicted with **ML models (XGBoost, Gradient Boosting, RF, Logistic Regression)**.  
- **XGBoost** showed the strongest performance (AUC > 0.96).  
- Business recommendations: focus on **longer contracts** and **increasing class attendance** to reduce churn.  
