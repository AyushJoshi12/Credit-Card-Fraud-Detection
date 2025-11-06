# Credit Card Fraud Detection
Dataset Link: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

## Overview
Detect fraudulent credit card transactions using machine learning techniques.  
The dataset contains over **284,807 anonymized transactions** by European cardholders in 2013.  
The target variable (`Class`) indicates whether a transaction is fraudulent (1) or not (0).  

> Only 492 transactions are fraudulent, creating a **highly imbalanced dataset**.

---

## Dataset
- **Records:** 284,807  
- **Features:** V1–V28 (anonymized), Time, Amount  
- **Target:** Class (0 = non-fraud, 1 = fraud)  
- **Class Distribution:** 99.83% non-fraud, 0.17% fraud  

**Feature Notes:**  
- `Time`: Removed from modeling  
- `Amount`: Scaled using **Robust Scaler**  
- `V1–V28`: PCA-anonymized transaction features  

---

## Data Preprocessing
- **Cleaning:** Minimal due to anonymization  
- **Scaling:** Only `Amount` scaled; `Time` removed  
- **Class Imbalance Handling:**  
  - Applied **SMOTE** and **ADASYN** to generate synthetic fraudulent samples  
  - Improves model performance and reduces bias toward the majority class  

---

## Modeling & Evaluation
Implemented models:  
- Logistic Regression  
- Naive Bayes  
- Decision Tree  
- Random Forest  

**Experiments:**  
- Oversampling techniques: SMOTE & ADASYN  
- Feature selection guided by **SHAP interpretability**  
- Hyperparameter tuning via **GridSearchCV**  

**Evaluation Metrics:** Accuracy, ROC-AUC, Confusion Matrix  

**Best Model:** Logistic Regression using ADASYN  

**Example Confusion Matrix:**  
<img width="526" height="350" alt="image" src="https://github.com/user-attachments/assets/c9f52c24-1bef-4b30-9742-1c667449279d" />


---

## User Interface
- Users can input transaction details to predict fraud.  
- Generates **LIME visualizations** showing feature impact on predictions.  

**Example LIME Visualization:**  
<img width="1056" height="625" alt="image" src="https://github.com/user-attachments/assets/e0ebc2d4-a153-4386-95e3-907333a5aa2a" />


---

## Tech Stack
- **Python Libraries:** Pandas, NumPy, Scikit-learn, Imbalanced-learn, LIME, SHAP, Matplotlib, Seaborn  
- **UI:** Streamlit 
- **Tools:** Jupyter Notebook  

