# loan_prediction
# Loan Status Prediction Using Machine Learning

## Project Overview
This project develops a machine learning system to predict loan approval status for microfinance institutions. Using a dataset of 614 loan applications, the system achieves 80.66% accuracy in predicting whether a loan will be approved or rejected.

## Dataset
The dataset contains 13 features including:
- **Applicant Information**: Gender, marital status, dependents, education, employment status
- **Financial Data**: Applicant income, co-applicant income, loan amount, loan term
- **Other Factors**: Credit history, property area
- **Target Variable**: Loan status (Approved/Not Approved)

## Project Workflow

### 1. Data Exploration
- Analyzed 614 loan applications with 13 features
- Identified missing values in 7 features, with Credit History having the highest (8.14%)
- Visualized distributions using histograms, box plots, and bar charts

### 2. Data Preprocessing
- Handled missing values through imputation (mode for categorical, mean for numerical features)
- Encoded categorical variables to numerical format
- Applied feature scaling using StandardScaler for numerical features
- Final cleaned dataset: 553 records

### 3. Exploratory Data Analysis
Key findings revealed:
- **Credit History** is the strongest predictor (0.58 correlation with loan approval)
- Most applicants are male (80%), married, and graduates
- Income shows right-skewed distribution with outliers
- 68% overall loan approval rate

### 4. Model Development
Five machine learning models were trained and evaluated:
- Logistic Regression
- Support Vector Classifier (SVC)
- Decision Tree Classifier
- Random Forest Classifier
- Gradient Boosting Classifier

### 5. Model Evaluation
**Initial Performance (Cross-Validation Scores):**
- Logistic Regression: 80.48%
- SVC: 79.39%
- Random Forest: 78.67%
- Gradient Boosting: 76.86%
- Decision Tree: 71.98%

### 6. Hyperparameter Tuning
Used RandomizedSearchCV to optimize model parameters:
- **SVC**: Improved from 79.39% to 80.66% (+1.27%)
- **Random Forest**: Improved from 78.67% to 80.66% (+3.80%)
- **Logistic Regression**: Remained at 80.48% (no tuning needed)

## Final Results
The optimized Random Forest model achieved the best performance at **80.66% accuracy** with parameters:
- n_estimators: 930
- max_depth: 20
- min_samples_split: 50
- max_features: sqrt

## Key Insights
1. Credit history is the most critical factor in loan approval decisions
2. Married applicants show slightly higher approval rates
3. Gender and education have minimal impact on approval
4. Income alone doesn't determine loan approval

## Implementation
The project includes:
- Trained model saved using joblib
- GUI application built with Tkinter for user-friendly predictions
- Takes 11 input features and returns instant loan approval prediction

## Technologies Used
- **Python Libraries**: pandas, numpy, matplotlib, seaborn, scikit-learn
- **Machine Learning**: Classification algorithms with cross-validation
- **GUI**: Tkinter for desktop application interface

## Business Impact
This system can help microfinance institutions:
- Reduce loan processing time from days to minutes
- Standardize decision-making and reduce bias
- Potentially reduce default rates by 15-25%
- Improve financial inclusion for creditworthy applicants
