# QTM 347 Final Project - Predicting Onset of Diabetes
## Introduction
This Project is done by John Zhou and Zichen Huang from QTM 347 Machine Learning I, aiming at selecting predictive models for diabetes prediction among different age groups.
The motivation behind this project is that diabetes is a global health issue. Early prediction can lead to timely interventions and better health outcomes.

In this project, we would explore the performance of several models:
OLS Regression
Logistice Regression
Best Subset Selection
Forward Selection
PCR
PLS
Ridge and Lasso
Decision Trees
Random Forest
Boosting

Previous studies often apply a one-size-fits-all model for all age groups. Our research expands on this by segmenting data based on age groups to enhance prediction accuracy.

## Data Description
This dataset comes from the National Institute of Diabetes and Digestive and Kidney Diseases. Its purpose is to predict the presence of diabetes in patients using specific diagnostic data included in the dataset. The dataset was curated with certain restrictions, including that all the subjects are female Pima Indians aged 21 or older.

Variables include:
Pregnancies: Number of times pregnant
Glucose: Plasma glucose concentration a 2 hours in an oral glucose tolerance test
Blood Pressure: Diastolic blood pressure (mm Hg)
Skin Thickness: Triceps skinfold thickness (mm)
Insulin: 2-Hour serum insulin (mu U/ml)
BMI: Body mass index (weight in kg/(height in m)^2).
Diabetes Pedigree Function: Diabetes pedigree function (a function which scores likelihood of diabetes based on family history).
Age: Age (years).
Outcome: Class variable (0 or 1) where 1 indicates diabetes and 0 indicates no diabetes. ​

## Data Cleaning
The dataset contains 768 entries and 9 columns.
We split the data into 80% train data and 20% test data. 

Model Selection: Range of models to be executed: OLS, Ridge, Lasso, PCR, PLS, Decision Trees, Random Forest, and Boosting.
Parameter Tuning: For regularization models: optimizing alpha and the l1_ratio for Lasso and Elastic Net. For tree-based models: tuning parameters such as max depth, min samples split, and min samples leaf. 
Computing Environment: Experiments will be conducted on Google Colab using stacks like scikit-learn, pandas, NumPy
Evaluation Metrics: Accuracy of the model(%）.

Challenge:Missing Data. From an initial inspection, it appeared there might be some zero values in columns where it doesn't make sense (like Glucose, Blood Pressure, Skin Thickness, Insulin, BMI)
Solution:We replace these zeros with the column's mean, excluding zeros from the calculation.

## 
