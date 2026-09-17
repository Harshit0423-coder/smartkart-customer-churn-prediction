# smartkart-customer-churn-prediction
# 🛒 SmartKart Customer Churn Prediction

An end-to-end Machine Learning project that predicts whether SmartKart customers are likely to churn using **Logistic Regression**.

The project demonstrates a complete ML workflow starting from a messy customer dataset and ending with a business-ready customer churn risk report.

## 📌 Project Overview

Customer churn is a major business problem in retail. The goal of this project is to identify customers who are likely to leave SmartKart so that the retention team can take action before they churn.

The dataset intentionally contains real-world data-quality issues such as duplicate records, invalid values, inconsistent data types, missing values, and outliers.

## 🎯 Business Objective

Predict customer churn using:

* Customer Age
* Monthly Spend
* Number of Complaints

The model produces both a **churn prediction** and a **churn probability**, allowing customers to be ranked according to their predicted risk.

## 📊 Dataset

Dataset used:

`SmartKart_dirty_100_rows.csv`

Initial dataset:

* 100 customer records
* 5 columns
* Customer ID
* Age
* Monthly Spend
* Complaints
* Churn

After data cleaning, the dataset contains **95 usable records**.

## 🔄 ML Pipeline

The notebook follows a complete **15-step Machine Learning pipeline**:

1. Data Collection
2. Data Understanding / Inspection
3. Data Cleaning
4. Outlier Detection & Treatment
5. Feature Selection
6. Target Variable Definition
7. Target Encoding Verification
8. Train-Test Split
9. Feature Standardisation
10. Model Building
11. Model Training
12. Prediction
13. Model Evaluation
14. Model Interpretation
15. Final Business Output

## 🧹 Data Preprocessing

The project handles several data-quality problems:

* Removes duplicate records
* Removes unnecessary whitespace
* Converts `Age` into numeric format
* Corrects invalid textual values
* Handles invalid age values
* Handles negative monthly spending
* Fills missing values using the median
* Detects and treats outliers using the IQR method

Outliers are capped instead of removing complete customer records.

## 🤖 Machine Learning Model

### Logistic Regression

Logistic Regression was selected because churn is a **binary classification problem**:

* `0` → No Churn
* `1` → Churn

### Features

The model uses:

```text
Age
Monthly_Spend
Complaints
```

`Customer_ID` is excluded because it is an identifier rather than a predictive feature.

## ⚙️ Train-Test Split

The cleaned dataset is divided using an **80/20 train-test split** with stratification.

* Training set: 76 customers
* Testing set: 19 customers
* `random_state = 42`
* Stratification maintains a similar churn ratio in both sets.

## 📏 Feature Standardisation

`StandardScaler` is used to standardise the numerical features.

The scaler is fitted only on the training data and then applied to the test data to avoid data leakage.

## 📈 Model Performance

The model achieved the following results on the test set:

| Metric    |   Score |
| --------- | ------: |
| Accuracy  |  89.47% |
| Precision |  83.33% |
| Recall    | 100.00% |
| F1-Score  |  90.91% |

### Confusion Matrix

```text
[[7, 2],
 [0, 10]]
```

The test set contained 19 customers.

## 🔍 Model Insights

The trained Logistic Regression model provides coefficients that help interpret the relationship between the selected features and predicted churn risk.

According to the notebook:

* `Monthly_Spend` has a negative coefficient.
* `Complaints` has a positive coefficient.
* `Age` has a smaller positive coefficient.

The notebook identifies customer complaints as an actionable factor associated with higher predicted churn risk.

## 📋 Business Output

The project generates:

`smartkart_churn_risk_report.csv`

The report contains:

* Customer ID
* Age
* Monthly Spend
* Complaints
* Actual Churn
* Predicted Churn
* Churn Probability
* Risk Label

Customers are sorted by churn probability so that the retention team can identify higher-risk customers first.

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab
* Logistic Regression

## 📁 Project Structure

```text
smartkart-customer-churn-prediction/
│
├── SmartKart_Customer_Churn_Prediction.ipynb
├── SmartKart_dirty_100_rows.csv
├── smartkart_churn_risk_report.csv
└── README.md
```

## ▶️ How to Run

1. Open the notebook in Google Colab.
2. Upload `SmartKart_dirty_100_rows.csv` when prompted.
3. Run the notebook cells from top to bottom.
4. The complete preprocessing and ML pipeline will execute.
5. The final churn risk report will be generated as a CSV file.

## 💡 Key Takeaway

This project demonstrates how a messy business dataset can be transformed into a useful Machine Learning solution through data cleaning, preprocessing, feature selection, Logistic Regression, model evaluation, and business-oriented interpretation.

## 👨‍💻 Project Type

**Machine Learning | Supervised Learning | Binary Classification | Customer Churn Prediction**
