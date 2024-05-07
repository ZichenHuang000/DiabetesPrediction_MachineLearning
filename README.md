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
This dataset comes from the National Institute of Diabetes and Digestive and Kidney Diseases.(https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database) Its purpose is to predict the presence of diabetes in patients using specific diagnostic data included in the dataset. The dataset was curated with certain restrictions, including that all the subjects are female Pima Indians aged 21 or older.

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

## Logistic regression
Accuracy:0.7987

About 31.2% of the variability in the outcome can be explained by the model

Glucose has a positive coefficient (0.0066) with a very small p-value, suggesting that it is a significant predictor and that higher glucose levels are associated with an increased likelihood of the outcome occurring.

BMI', and 'Pregnancies' as significant predictors for diabetes, which aligns with medical understanding.

## Best Subset Selection
Nearly half of the variability in the outcome can now be explained by the model, which is an improvement over the previous model.

The significant predictors, according to this model, are 'Pregnancies', 'Glucose', and 'Blood Pressure'.

The non-normal distribution of residuals remains a concern and could suggest that a linear model is not the best fit for this data.

## PCR

PCA (n_components=3): Reducing the data to three principal components means the model is now working in a three-dimensional space.

Using PCA reduces dimensionality, which might improve model performance. However, it loses the ability to interpret the model in terms of the original features directly.


## PLS

PLS can be particularly useful when there is a large number of predictors, many of which are correlated to avoid overfitting.

The components in PLS can be more meaningful than those in PCA since they are designed to explain the dependent variable. The top features for each component give an insight into which combinations of features are most predictive for the outcome.


## Ridge

Ridge regression, tends to shrink the coefficients for less important variables but does not set them to zero, which maintains all the features but reduces the effect of those that are not crucial.

## Lasso

Lasso regression, with non-zero coefficients, suggests that features like 'Pregnancies', 'Glucose', and 'BMI' are important predictors for the outcome. 'BloodPressure' and 'Insulin' have been set to zero, implying that, according to Lasso, they might not be significant predictors given the presence of other variables.

Lasso's feature elimination can be particularly useful as it is simpler and more interpretable while still being predictive.

## Decision Tree

The decision tree has identified 'Glucose', 'BMI', and 'Age' as significant features for predicting the outcome, which aligns with medical understanding of diabetes risk factors.

Prominence of ‘Glucose’ being the decision boundary of branches.

Parameters determined through cross-validation.


## Random Forest

Prominence of ‘Glucose’ being the top 1 (most important) feature among 8, ‘BMI’ being the top 2 feature among 8.


## Boosting

Selected through cross-validation, the optimal learning rate is approximately 0.9, the max depth is 2, and number of estimators be 51.

## Comparison

According to the accuracy data we get, Decision tree has the lowest Accuracy of 0.72, while Random Forest has the highest Accuracy of 0.83 which we will adopt. 

## Futher Study
We have selected Random Forest as our optimal predictive model. Our aim is now to refine its performance further. Given that individuals of varying ages may have distinct risk factors for diabetes, our objective is to identify which attributes significantly influence the likelihood of diabetes within different age groups. 

For the purpose of our analysis, we are adopting the World Health Organization age classification: individuals aged 0-24 will be considered 'young adults', those between 25-44 will be 'adults', ages 45-60 will fall under 'middle-aged', and anyone above 60 will be categorized as 'senior'.






