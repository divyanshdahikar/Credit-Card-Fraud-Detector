# 💳 Credit Card Fraud Detection using Logistic Regression

This project analyzes and predicts fraudulent credit card transactions using machine learning. The dataset is highly imbalanced and contains anonymized features due to confidentiality issues. 

---

## 📁 Dataset

- Source: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- Rows: 284,807
- Features: 30 numerical input features (V1–V28, Amount), and 1 target variable (`Class`)
- Target:
  - `0` → Non-fraudulent transaction
  - `1` → Fraudulent transaction

---

## 📊 Exploratory Data Analysis (EDA)

> ✨ Drop your EDA visualizations here 👇


![Screenshot 2025-06-18 173030](https://github.com/user-attachments/assets/be1c8dab-50fe-4960-8e3e-49146bee04cc)

![Screenshot 2025-06-18 173045](https://github.com/user-attachments/assets/2b7d675c-e4bd-42fb-a10f-a0bd48abf7f5)


- Class imbalance visualization  
- Transaction amount distribution (fraud vs non-fraud)  
- Boxplots and pairplots for selected features  

---

## ⚙️ Preprocessing

- Dropped the `Time` column (not relevant for fraud detection)
- Normalized the `Amount` feature using `MinMaxScaler`
- Checked for null values (none found)
- Used `SequentialFeatureSelector` to pick 5 best features:
  - **Selected Features**: `V8`, `V9`, `V12`, `V14`, `V16`
- Applied **SMOTE** to handle class imbalance during training

---

## 🧠 Model

- Model used: **Logistic Regression**
- Feature selection: `SequentialFeatureSelector` (forward selection)
- Oversampling technique: `SMOTE (sampling_strategy = 0.5)`

---

## 🧪 Evaluation Metrics

| Metric         | Score     |
|----------------|-----------|
| Accuracy       | 99.04 %   |
| Precision      | 13.80 %   |
| Recall         | 86.73 %   |
| F1 Score       | 23.81 %   |

> ⚠️ Due to class imbalance, **recall** is prioritized over precision.

---

## 🔍 Confusion Matrix

markdown
Copy
Edit
        Predicted
        Legit   Fraud
Actual Legit TN FP
Fraud FN TP

yaml
Copy
Edit

![Confusion Matrix]![Uploading Screenshot 2025-06-18 172652.png…]()


---

## 📑 Classification Report

markdown
Copy
Edit
          precision    recall  f1-score   support

  Legit       1.00      0.99      1.00     56864
  Fraud       0.14      0.87      0.24        98
accuracy 0.99 56962
macro avg 0.57 0.93 0.62 56962
weighted avg 1.00 0.99 0.99 56962
