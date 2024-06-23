# Data Science Project Overview : Predict Churn Analysis

## Introduction
Company provides home phone and internet services with several additional services such as internet security, technical support, cloud storage, and TV streaming. Information from various sources has been collected for this analysis, including contract data, client personal data, internet service information, and phone service information.
This report aims to forecast the churn rate of Company clients. By identifying clients who are likely to leave, the company can offer promotional codes and special package options to retain them.

## Data Description
* contract.csv
* personal.csv
* internet.csv
* phone.csv

Here is the step for analyze :

## Data Preprocessing
The preprocessing steps performed include:
* Handling Data Types: Convert data type into the correct types.
* Data Merging: Merging data from the four files based on customerID.
* Handling Missing Values: Filling or dropping missing values as appropriate.

## EDA
I looked at the distributions of the data and the value counts for the various variables. Below are a few highlights :

![alt text](https://github.com/desynoerhayati/ds_predict_churn/blob/main/Churn_Client.png?raw=true) 
![alt text](https://github.com/desynoerhayati/ds_predict_churn/blob/main/Distribution_Monthly.png?raw=true) 
![alt text](https://github.com/desynoerhayati/ds_predict_churn/blob/main/Clients_Phone.png?raw=true)
![alt text](https://github.com/desynoerhayati/ds_predict_churn/blob/main/Churn_Client.png?raw=true) 
![alt text](https://github.com/desynoerhayati/ds_predict_churn/blob/main/Internet_Users.png?raw=true) 
![alt text](https://github.com/desynoerhayati/ds_predict_churn/blob/main/Number_Client.png?raw=true) 

## Feature Engineering
The feature engineering steps performed include:
* Feature Selection : Selecting the most relevant features (columns) that contribute significantly to the model's predictive power while removing those that have low correlation with the target variable. 
* Feature Transformation : Creating new features or modifying existing ones to better capture the underlying patterns in the data.
* Separating Features and Target : Separate the features (independent variables) from the target (dependent variable). The features will be used to predict the target.
* OrdinalEncoder : Convert categorical features into ordinal integers. It assigns a unique integer to each unique category in the feature, thereby transforming categorical data into a format that many machine learning algorithms can work with effectively.
* Scaling Data with MinMaxScaler : Scale numerical data to a specified range, typically between 0 and 1. This ensures that all features contribute equally to the model training process, especially when features have different ranges or units.

## Model Building 
1. Split the data into train and tests sets with a test size of 10%.
2. I tried seven different models and evaluated them using Accuracy and ROC-AUC.

Model with hyperparameter :
* DecisionTreeClassifier
* RandomForestClassifier
* XGBClassifier
* LGBMClassifier
* GradientBoostingClassifier

Model without hyperparameter :
* LogisticRegression
* K-Nearest Neighbors

## Evaluation Result 
![image](https://github.com/desynoerhayati/ds_predict_churn/assets/173496275/f1fc7b76-a538-48f8-bf54-edc6168c5a70)

## Conclusion

Based on the evaluation results, XGBClassifier shows the best performance with an AUC-ROC of 0.923684, followed by LGBMClassifier with an AUC-ROC of 0.918360. Both models demonstrate excellent accuracy and ROC-AUC metrics, exceeding the target AUC-ROC ≥ 0.88.

Effectiveness of Boosting Models:
XGBClassifier and GradientBoostingClassifier are the most effective in terms of balancing accuracy, ROC-AUC, and execution time. They exhibit superior predictive capability with reasonable execution times.

Efficiency of LGBM:
LightGBM is highly efficient with the highest accuracy and fastest execution time, making it ideal for large datasets or scenarios where computational efficiency is critical. LightGBM demonstrates its ability to handle complexity effectively while maintaining time efficiency.

Performance of Random Forest:
RandomForestClassifier is a good choice with relatively fast execution time, although it shows a slight decrease in performance compared to boosting models.

Simple Models:
Logistic Regression and KNN have fast execution times but their performance does not match more complex models. They are suitable for establishing a baseline or scenarios where interpretability and speed are primary concerns.

The objective of the report to forecast client churn rates for Company has been successfully achieved. The developed churn prediction model demonstrates high performance and reliability. The insights generated from this analysis can be used by the company to offer promotional codes and special package options to retain their clients.
