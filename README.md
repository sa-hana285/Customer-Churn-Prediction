# Hybrid Customer Churn Prediction System

## Overview
This project is about predicting whether a customer will churn or not using machine learning. Instead of relying only on ML models, I also included a rule-based approach and combined both to make the system more practical.
The main idea was not just to predict churn, but to classify customers into different risk levels so that businesses can take better decisions.

## Dataset
The dataset contains basic customer information such as:
- Age  
- Annual Income  
- Purchase Frequency  
- Membership Level  
- Spending Score  

The target variable is **Churn Status** (0 = No churn, 1 = Churn).
Since the dataset was imbalanced, I used SMOTE to balance it before training the models.

## Models Used
I implemented and compared the following models:
- LightGBM  
- XGBoost  
- Random Forest  
- Decision Tree  

Each model was evaluated using multiple metrics like Accuracy, Precision, Recall, F1-score and ROC-AUC.

## Why not just Accuracy?
Accuracy alone is not enough because the dataset is imbalanced. A model can give high accuracy by predicting only the majority class.
So I focused more on:
- Recall (to catch churn customers)
- F1-score (balance between precision and recall)
- ROC-AUC (overall performance)

## Model Comparison
After comparing all models, **Random Forest performed the best** based on ROC-AUC and overall balance of metrics.
Instead of hardcoding a model, I dynamically selected the best model based on performance.

## Rule-Based Logic
Along with ML, I created a rule-based system using simple business logic like:
- Low spending and low purchase frequency → likely to churn  
- High income but low engagement → possible churn  
- High spending and frequent purchases → loyal customers  

This makes the system more interpretable.

## Hybrid Approach
I combined both ML predictions and rule-based logic to classify customers into:

- **High Risk** → both ML and rules say churn  
- **Medium Risk** → either one says churn  
- **Low Risk** → both say no churn  
This gives a more realistic view compared to just prediction.

## Visualizations
I included graphs for:
- Model performance (Accuracy & AUC)
- Feature importance
- Risk distribution
These help in understanding the results better.

## User Input
The project also allows manual input of customer data to:
- Predict churn  
- Apply rule-based logic  
- Show final risk level  

## Conclusion
This project shows how combining machine learning with simple business rules can improve both prediction and usability.
The hybrid approach makes the system more practical for real-world scenarios like customer retention.
