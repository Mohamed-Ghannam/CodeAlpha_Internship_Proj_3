# Credit Scoring Model

## Project Overview
The goal of this project was to develop a credit scoring model to predict the creditworthiness of individuals based on their historical financial data. The task involved data preprocessing, exploratory data analysis (EDA), feature engineering, and the application of various classification algorithms to evaluate model accuracy.

## Table of Contents
1. [Introduction](#Introduction)
2. [Dataset Overview](#Dataset-Overview)
3. [Exploratory Data Analysis (EDA)](#Exploratory-Data-Analysis)
4. [Data Preprocessing](#Data-Preprocessing)
5. [Feature Engineering](#Feature-Engineering)
6. [Modeling](#Modeling)
7. [Evaluation](#Evaluation)
8. [Conclusion](#Conclusion)

## Introduction
Credit scoring is crucial in the financial industry to determine the creditworthiness of individuals. This model predicts whether an individual will have a good or bad credit score based on historical financial and personal data. We utilized various classification algorithms and evaluated their performance to choose the best-performing model.

## Dataset Overview
The dataset consists of various financial and demographic features related to credit history. Key features include:

- `ID`	
- `Customer_ID`	
- `Month	Name`	
- `Age`	
- `SSN`	
- `Occupation`	
- `Annual_Income`	
- `Monthly_Inhand_Salary`	
- `Num_Bank_Accounts`	
- `Num_Credit_Card` 
- `Interest_Rate`	
- `Num_of_Loan`	
- `Type_of_Loan`	
- `Delay_from_due_date`	
- `Num_of_Delayed_Payment`	
- `Changed_Credit_Limit`	
- `Num_Credit_Inquiries`	
- `Credit_Mix`	
- `Outstanding_Debt`	
- `Credit_Utilization_Ratio`	
- `Credit_History_Age`	
- `Payment_of_Min_Amount`	
- `Total_EMI_per_month`	
- `Amount_invested_monthly`	
- `Payment_Behaviour`	
- `Monthly_Balance`	
- `Credit_Score`

## Exploratory Data Analysis
We performed EDA to understand the data structure and distribution. Key steps involved:

- Dropping unnecessary columns.
- Converting object-type columns like `Age` into numerical format.
- Handling missing values and duplicates.
- Descriptive statistics and data distribution visualization using histograms, KDE plots, and boxplots.
  
We identified and handled:
- **Unrealistic age values** (e.g., values above 120 years).
- **Negative values** in columns like `Age` and `Num_Bank_Accounts`.
  
### Handling Outliers
Outliers were detected using boxplots. We developed a function to remove outliers based on the Interquartile Range (IQR).

### Data Transformations
To address the skewness and kurtosis in numerical features, we applied various transformations:
- Log transformation
- Square root transformation
- Square transformation
- Yeo-Johnson transformation

### Multicollinearity
We calculated the Variance Inflation Factor (VIF) to detect multicollinearity and plotted a correlation matrix to visualize relationships between features.

## Data Preprocessing
We split the dataset into training and validation sets and applied preprocessing steps:

- **Numerical columns** were processed using transformations such as imputation (median strategy) and scaling.
- **Categorical columns** were handled using `SimpleImputer` (most frequent strategy) and `OneHotEncoder` for encoding.

This was achieved using `Pipeline` and `ColumnTransformer` from `sklearn`.

## Feature Engineering
Key steps in feature engineering included:
- Capping values for age at 120.
- Removing outliers in critical columns like `Num_Bank_Accounts`.
- Creating additional interaction terms based on domain knowledge.

## Modeling
We used several classification algorithms to build the credit scoring model, including:

1. **Logistic Regression**
2. **Random Forest**
3. **XGBoost**
4. **Artificial Neural Networks (ANN)**

## Evaluation
Models were evaluated based on accuracy and other key metrics such as precision, recall, and F1-score. Cross-validation was used to ensure the robustness of the model performance.


## Conclusion
We successfully built a credit scoring model that can accurately predict the creditworthiness of individuals based on their financial and personal data. The XGBoost model demonstrated the highest accuracy, making it suitable for credit risk prediction.
