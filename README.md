# CO₂ Emission Prediction for Automotive Policy & Design Decisions

## 📌 Project Overview

The Global Automotive Council aims to understand the key factors influencing vehicle CO₂ emissions and explore data-driven strategies for emission reduction.

This case study analyzes vehicle specifications, engine characteristics, fuel types, and fuel consumption patterns to identify the major factors associated with CO₂ emissions and develop a simple, interpretable predictive model.

The project covers data cleaning, exploratory data analysis, correlation analysis, multicollinearity detection using VIF, feature selection, categorical encoding, regression modeling, and model evaluation.

---

## 🎯 Objectives

* Understand the structure and characteristics of the vehicle dataset
* Identify and address data quality issues
* Explore relationships between vehicle characteristics and CO₂ emissions
* Identify multicollinearity among numerical features using VIF
* Select relevant and interpretable features for modeling
* Compare Linear Regression, Ridge Regression, and Lasso Regression
* Evaluate model performance using R² and other regression metrics
* Identify the key factors influencing vehicle CO₂ emissions
* Provide insights that can support automotive design and policy decisions

---

## 📊 Dataset

The dataset contains information about vehicles, including:

* Vehicle make and model
* Vehicle class
* Engine size
* Number of cylinders
* Transmission
* Fuel type
* City fuel consumption
* Highway fuel consumption
* Combined fuel consumption
* Combined fuel consumption in MPG
* CO₂ emissions

### Dataset Dimensions

| Stage                   |  Rows | Columns |
| ----------------------- | ----: | ------: |
| Initial dataset         | 7,385 |      12 |
| After duplicate removal | 6,282 |      12 |

No missing values were identified in the dataset.

A total of **1,103 duplicate records** were identified and removed.

---

## 🔎 Exploratory Data Analysis

The analysis included:

* Dataset structure and summary statistics
* Unique-value analysis
* Missing-value analysis
* Duplicate detection
* Distribution analysis
* Outlier analysis
* Correlation analysis
* Numerical feature visualization
* Comparison of emissions across fuel categories and vehicle characteristics

The analysis showed that **fuel consumption, engine size, and number of cylinders** have strong relationships with CO₂ emissions.

---

## 🔗 Correlation Analysis

The final selected numerical variables showed the following correlations with CO₂ emissions:

| Feature                          | Correlation with CO₂ Emissions |
| -------------------------------- | -----------------------------: |
| Engine Size(L)                   |                         0.8549 |
| Cylinders                        |                         0.8347 |
| Fuel Consumption Comb (L/100 km) |                         0.9170 |

Fuel Consumption Comb (L/100 km) showed the strongest correlation with CO₂ emissions among the selected numerical features.

---

## 🧮 Multicollinearity Analysis

Variance Inflation Factor (VIF) was used to identify multicollinearity among numerical predictors.

Initially, the fuel-consumption variables showed very high VIF values, indicating substantial redundancy.

For example:

* Fuel Consumption Comb (L/100 km): **5045.26**
* Fuel Consumption City (L/100 km): **2225.28**
* Fuel Consumption Hwy (L/100 km): **623.63**

To reduce redundancy, highly correlated fuel-consumption variables were removed.

The final numerical features were:

* Engine Size(L)
* Cylinders
* Fuel Consumption Comb (L/100 km)

Final VIF values:

| Feature                          |  VIF |
| -------------------------------- | ---: |
| Engine Size(L)                   | 8.75 |
| Cylinders                        | 7.35 |
| Fuel Consumption Comb (L/100 km) | 3.08 |

These features were retained for model building.

---

## 🛠️ Feature Preparation

The final model used:

### Numerical Features

* Engine Size(L)
* Cylinders
* Fuel Consumption Comb (L/100 km)

### Categorical Feature

* Fuel Type

Categorical variables were converted into numerical representations using **One-Hot Encoding**.

Numerical features were standardized using **StandardScaler** as part of the modeling pipeline.

---

## 🤖 Models

Three regression models were developed and compared:

1. Linear Regression
2. Ridge Regression
3. Lasso Regression

Cross-validation and model evaluation were used to compare their predictive performance.

---

## 📈 Model Performance

| Model             |    Test R² | Train R² |
| ----------------- | ---------: | -------: |
| Linear Regression |     0.9393 |   0.9384 |
| Ridge Regression  |     0.9394 |   0.9385 |
| Lasso Regression  | **0.9396** |   0.9390 |

### Final Model

**Lasso Regression** was selected as the final model because it achieved the highest Test R² score of approximately **0.94**.

The close relationship between Train and Test R² indicates that the models generalize well without significant overfitting.

The final Lasso model explains approximately **94% of the variation in CO₂ emissions** in the test data.

---

## 💡 Key Findings

The analysis identified the following major factors associated with CO₂ emissions:

### 1. Fuel Consumption

Fuel consumption showed the strongest relationship with CO₂ emissions among the selected numerical variables.

Vehicles with higher fuel consumption generally produced higher CO₂ emissions.

### 2. Engine Size

Larger engine sizes were associated with higher CO₂ emissions.

### 3. Number of Cylinders

Vehicles with more cylinders generally showed higher emission levels.

### 4. Fuel Type

Fuel type also contributed to differences in CO₂ emission levels.

---

## 🌍 Business & Policy Insights

These findings can support automotive decision-making in several ways:

* Manufacturers can focus on improving fuel efficiency.
* Engine specifications can be optimized to reduce emissions.
* Policymakers can develop fuel-efficiency regulations.
* Emission standards can be informed by vehicle characteristics.
* Incentives can be designed to encourage lower-emission vehicles.

---

## 🧰 Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab
* Git & GitHub

---

## 📁 Project Structure

```text
CO2-Emission-Case-Study/
│
├── data/
│
├── images/
│
├── notebooks/
│   └── CO2_Emission_Case_Study.ipynb
│
├── reports/
│
├── .gitignore
├── requirements.txt
└── README.md
```

---

## 📓 Notebook

The complete analysis, visualizations, feature selection process, VIF analysis, model development, and evaluation are available in the project notebook.

---

## 👨‍💻 Author

**S. Venkatesh Prasad**

Computer Science Engineer | Aspiring AI Engineer
