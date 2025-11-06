# 🚗 Car Price Prediction

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python)](https://www.python.org/downloads/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0%2B-orange?style=for-the-badge&logo=scikit-learn)](https://scikit-learn.org/stable/)
[![Pandas](https://img.shields.io/badge/Pandas-black?style=for-the-badge&logo=pandas)
[![NumPy](https://img.shields.io/badge/NumPy-white?style=for-the-badge&logo=numpy)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

This is a machine learning project that predicts the selling price of used cars using regression. By analyzing various features of a car (like its age, kilometers driven, and fuel type), we train `LinearRegression` and `Lasso` models to estimate its current market value.

---

## 🎯 Problem Statement

The goal of this project is to build a regression model that can accurately predict the `Selling_Price` of a used car. Unlike classification (predicting a category like "Good/Bad"), this is a **regression problem**, where the model learns to predict a continuous numerical value (the price).

The model is trained on a dataset of used car sales, learning the relationships between features like `Present_Price`, `Kms_Driven`, and `Fuel_Type`, and their final `Selling_Price`.

---

## 📋 Project Workflow

1.  **Import Dependencies:** Load essential libraries (`numpy`, `pandas`, `seaborn`, `sklearn`, `matplotlib`).
2.  **Data Collection & Processing:** Load the `car data.csv` dataset and inspect its structure (`.head()`, `.info()`).
3.  **Data Preprocessing (Encoding):**
    * Convert categorical features (`Fuel_Type`, `Seller_Type`, `Transmission`) into numerical values so the model can understand them.
    * `Fuel_Type`: `{'Petrol': 0, 'Diesel': 1, 'CNG': 2}`
    * `Seller_Type`: `{'Dealer': 0, 'Individual': 1}`
    * `Transmission`: `{'Manual': 0, 'Automatic': 1}`
4.  **Splitting Data:** Separate the data into features (`X`) and the target variable (`Y` = `Selling_Price`).
5.  **Train & Test Split:** Split the data into training (90%) and testing (10%) sets.
6.  **Model Training:** Train two different models on the training data:
    * `LinearRegression`
    * `Lasso` (which uses L1 Regularization)
7.  **Model Evaluation:** Evaluate both models using the **R-squared (R²) score** on both the training and test data to check for performance and overfitting.
8.  **Visualization:** Create scatter plots to visually compare the `Actual Prices` vs. the `Predicted Prices` from the models.

---

## 🛠️ Technologies Used

* **Python**
* **Scikit-learn:** For model training (`LinearRegression`, `Lasso`), splitting (`train_test_split`), and evaluation (`metrics.r2_score`).
* **Pandas:** For data loading and manipulation.
* **NumPy:** For high-performance numerical computations.
* **Matplotlib & Seaborn:** For data visualization and creating scatter plots.

---

## 📊 Dataset

The model is trained on the `car data.csv` dataset.

### Features (X)
*(After dropping `Car_Name` and `Selling_Price`)*
1.  `Year`
2.  `Present_Price` (in Lakhs)
3.  `Kms_Driven`
4.  `Owner` (Number of previous owners)
5.  `Fuel_Type` (Encoded)
6.  `Seller_Type` (Encoded)
7.  `Transmission` (Encoded)

### Target Variable (Y)
* `Selling_Price`: (Continuous) The price the car was sold for (in Lakhs).

---

## 🤖 Model Performance

Two regression models were trained and compared for this task.

* **Models:** `LinearRegression` and `Lasso`
* **Metric:** R-squared (R²) Error
* **Lasso Model Test Data R² Score:** **0.87** (or 87%)

This R² score means that the Lasso model can explain **87% of the variability** in the used car prices, which indicates a strong and accurate fit on unseen data.

---

## 🚀 How to Use the Predictive System

You can use the trained model to predict the price of a new, unseen car sample.

1.  Define your input data as a tuple or list containing the 7 features in the correct order:
    ```python
    # (Year, Present_Price, Kms_Driven, Owner, Fuel_Type, Seller_Type, Transmission)
    # Example: 2014, 5.59 Lakhs, 27000 Kms, 0 Owners, Petrol (0), Dealer (0), Manual (0)
    
    input_data = (2014, 5.59, 27000, 0, 0, 0, 0)
    ```

2.  The script will process this data, make a prediction, and print the result:
    ```
    Prediction: [4.5]
    Predicted Selling Price: 4.5 Lakhs
    ```
