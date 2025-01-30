# 🏗️ Data Science Salaries Prediction  

## 📜 Overview  
This project analyzes and predicts **Data Science salaries worldwide (2020-2023)** using **Multiple Linear Regression**. The dataset contains **3,755 observations** from Kaggle, including job details such as **experience level, employment type, salary, company location, and remote work ratio**. The goal is to develop a predictive model that estimates **future Data Science salaries** based on employment attributes.  

## 🎯 Problem Explanation  
The dataset includes **11 attributes** (4 numerical and 7 categorical):  
- **Target Variable:** `salary_in_usd` (Salary in USD).  
- **Independent Variables:**  
  - `work_year` (Year salary was paid).  
  - `experience_level` (Entry, Mid, Senior, Executive).  
  - `employment_type` (Part-time, Full-time, Contract, Freelance).  
  - `job_title` (Data Scientist, Engineer, etc.).  
  - `salary` (Salary in original currency).  
  - `salary_currency` (USD, EUR, GBP, etc.).  
  - `employee_residence` (Country of employee residence).  
  - `remote_ratio` (0 = No remote, 50 = Hybrid, 100 = Fully remote).  
  - `company_location` (Employer's country).  
  - `company_size` (S = <50, M = 50-250, L = >250 employees).  

## 🛠️ Implementation Details  
- **Exploratory Data Analysis (EDA):**  
  - Applied **square root transformation** to normalize salary distribution.  
  - Created **dummy variables** for categorical attributes.  
  - Analyzed **correlations & multicollinearity (VIF test)**.  
- **Regression Models:**  
  - **Full Model:** All predictors included (Adjusted R² = 39.34%).  
  - **Refined Model (Removing Multicollinearity):**  
    - Excluded `company_location` due to high correlation with `employee_residence`.  
    - Improved Adjusted R² to **39.35%**.  
  - **Stepwise Selection Model:**  
    - Reduced to **six key predictors** (Adjusted R² = **39.46%**).  
  - **Final Model (After Outlier Removal):**  
    - Adjusted R² = **41.84%**, RMSE = **64.73**, F-value = **440.04**, P-value < **0.0001**.  
- **Hypothesis Testing (F-Test):**  
  - Null Hypothesis: None of the six predictors significantly impact salary.  
  - Alternative Hypothesis: At least one predictor has a significant impact.  
  - Result: **Rejected Null Hypothesis**, confirming predictor relevance.  
