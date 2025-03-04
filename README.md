# Project-Classification

# 📊 Telecom Churn Prediction using Machine Learning

## 🔍 Project Overview
This project aims to predict **customer churn** for a telecom company using **Machine Learning models**. We compared **Logistic Regression, Random Forest, and Support Vector Machine (SVM)** to determine the best model for identifying customers at risk of leaving.

### 🎯 **Objective**
- Develop a **classification model** to predict whether a customer will **churn** or **stay**.
- Compare **different machine learning models** to determine the most effective one.
- Use **feature selection and hyperparameter tuning** to improve accuracy.

---

## 📁 **Dataset**
- 📂 **Dataset Name:** `churn_data.csv`
- 🔢 **Target Variable:** `Churn Value` (0 = No Churn, 1 = Churn)
- 📊 **Key Features Used:**
  - `Tenure Months` (Customer duration)
  - `Monthly Charges`
  - `Total Charges`
  - `Contract Type`
  - `Internet Service Type`
  - `Payment Method`
  - `Tech Support`
  - `Online Security`

---

## 🏆 **Best Model: Support Vector Machine (SVM)**
After training and evaluating **Logistic Regression, Random Forest, and SVM**, the **SVM model performed the best**, achieving:
- ✅ **Highest accuracy**
- ✅ **Better balance between Precision & Recall**
- ✅ **Higher ROC-AUC score**

---

## 🛠 **Machine Learning Workflow**
### **1️⃣ Exploratory Data Analysis (EDA)**
- Checked for missing values and outliers.
- Dropped irrelevant columns (`Customer ID`, `Zip Code`, etc.).
- Visualized **feature correlations** using a **heatmap**.

### **2️⃣ Data Preprocessing**
- **Encoded categorical variables** using `OneHotEncoder`.
- **Scaled numerical features** using `StandardScaler`.
- **Split data into training (80%) & testing (20%) sets**.

### **3️⃣ Model Training & Comparison**
| Model | Accuracy | Recall (Churn) | Precision (Churn) | AUC Score |
|--------|----------|----------------|-------------------|------------|
| **Logistic Regression** | 74% | 78% | 51% | 0.848 |
| **Random Forest** | 77% | 75% | 55% | 0.85 |
| **SVM (Final Model)** | **79%** | **80%** | **58%** | **0.86** |

### **4️⃣ Hyperparameter Tuning**
- Used `GridSearchCV` to optimize:
  - `C` (regularization parameter)
  - `kernel` (`linear` vs. `rbf`)
  - `gamma` (`scale` vs. `auto`)
- The final SVM model had:
  ```python
  best_params_ = {'C': 9.5, 'kernel': 'rbf', 'gamma': 'scale'}
