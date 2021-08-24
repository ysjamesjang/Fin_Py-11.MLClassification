# Fin_Py-8.MLClassification

## Overview

This repository fulfills the Unit 8 homework of the FinTech Bootcamp at Northwestern University.

Unit 8 falls under 'Algorithms, Statistics and Machine Learning'. 

## Directory

* <ins>**main** </ins>
    * "credit_risk_ensemble.ipynb": Two ensemble algorithms were used to compare their balanced accuracy scores, confusion matrices and imablanced classification reports: Balanced Random Forest Classifier and an Easy Ensemble Classifier. Feature importance in descending order was also calculated for the Balanced Random Forest Classifer.
    * "credit_risk_resampling.ipynb": Five resampling algorithms were used to compare their balanced accuracy scores, confusion matrices and imbalanced classification reports. Simple Logistic Regression was used as the control case; Oversampling was tested using the Naive Random Oversampler and SMOTE algorithms; Undersampling was tested using the Cluster Centroids algorithm; and Over- and undersampling was tested using a combination SMOTEEN algorithm.   
* <ins>**Resources** </ins>
    * PNG files for README.md and Grading Rubric
* <ins>**README.md** </ins>

## Project Conclusion

#### <ins> Resampling Algorithms </ins>

**1. Which model had the best balanced accuracy score?**

> Simple Logistic Regression: 0.9543211898288821 <br>
Naive Random Oversampling: 0.9946414201183431 <br>
SMOTE Oversampling: 0.9946680739911509 <br>
Cluster Centroids: 0.9932813049736127 <br>
SMOTEEN: 0.9946680739911509 <br> <br>
.:. SMOTE Oversampling and SMOTEEN tied at highest balanced accuracy score

**2. Which model had the best recall score?**

> Simple Logistic Regression: 0.99 <br>
Naive Random Oversampling: 0.99 <br>
SMOTE Oversampling: 0.99 <br>
Cluster Centroids: 0.99 <br>
SMOTEEN: 0.99 <br> <br>
.:. All models scored 0.99

**3. Which model had the best geometric mean score?**

> Simple Logistic Regression: 0.95 <br>
Naive Random Oversampling: 0.99 <br>
SMOTE Oversampling: 0.99 <br>
Cluster Centroids: 0.99 <br>
SMOTEEN: 0.99 <br> <br>
.:. All models except Simple Logistic Regression scored 0.99

#### <ins> Ensemble Algorithms </ins>

**1. Which model had the best balanced accuracy score?**

> Balanced Random Forest: 0.781881 <br>
Easy Ensemble Classifier: 0.925456 <br>
.:. Easy Ensemble Classifier scored higher


**2. Which model had the best recall score?**

> Balanced Random Forest: 0.92 <br>
Easy Ensemble Classifier: 0.94 <br>
.:. Easy Ensemble Classifier scored higher

**3. Which model had the best geometric mean score?**

> Balanced Random Forest: 0.77 <br>
Easy Ensemble Classifier: 0.93 <br>
.:. Easy Ensemble Classifier scored higher

**4. What are the top three features?**

> total_rec_prncp: 0.083222 <br>
total_pymnt_inv: 0.069044<br>
last_pymnt_amnt: 0.061120


---
---

## Assignment Instructions 


### Unit 11 - Risky Business
 
![Credit Risk](Resources/Images/credit-risk.jpg)

## Background

Mortgages, student and auto loans, and debt consolidation are just a few examples of credit and loans that people seek online. Peer-to-peer lending services such as Loans Canada and Mogo let investors loan people money without using a bank. However, because investors always want to mitigate risk, a client has asked that you help them predict credit risk with machine learning techniques.

In this assignment you will build and evaluate several machine learning models to predict credit risk using data you'd typically see from peer-to-peer lending services. Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans), so you will need to employ different techniques for training and evaluating models with imbalanced classes. You will use the imbalanced-learn and Scikit-learn libraries to build and evaluate models using the two following techniques:

1. [Resampling](#Resampling)
2. [Ensemble Learning](#Ensemble-Learning)

- - -

#### Files

[Resampling Starter Notebook](main/credit_risk_resampling.ipynb)

[Ensemble Starter Notebook](main/credit_risk_ensemble.ipynb)

[Lending Club Loans Data](main/Resources/LoanStats_2019Q1.csv.zip)

- - -

#### Instructions

##### Resampling

Use the [imbalanced learn](https://imbalanced-learn.readthedocs.io) library to resample the LendingClub data and build and evaluate logistic regression classifiers using the resampled data.

To begin:

1. Read the CSV into a DataFrame.

2. Split the data into Training and Testing sets.

3. Scale the training and testing data using the `StandardScaler` from `sklearn.preprocessing`.

4. Use the provided code to run a Simple Logistic Regression:
    * Fit the `logistic regression classifier`.
    * Calculate the `balanced accuracy score`.
    * Display the `confusion matrix`.
    * Print the `imbalanced classification report`.

Next you will:

1. Oversample the data using the `Naive Random Oversampler` and `SMOTE` algorithms.

2. Undersample the data using the `Cluster Centroids` algorithm.

3. Over- and undersample using a combination `SMOTEENN` algorithm.


For each of the above, you will need to:

1. Train a `logistic regression classifier` from `sklearn.linear_model` using the resampled data.

2. Calculate the `balanced accuracy score` from `sklearn.metrics`.

3. Display the `confusion matrix` from `sklearn.metrics`.

4. Print the `imbalanced classification report` from `imblearn.metrics`.


Use the above to answer the following questions:

* Which model had the best balanced accuracy score?
>
* Which model had the best recall score?
>
* Which model had the best geometric mean score?

##### Ensemble Learning

In this section, you will train and compare two different ensemble classifiers to predict loan risk and evaluate each model. You will use the [Balanced Random Forest Classifier](https://imbalanced-learn.readthedocs.io/en/stable/generated/imblearn.ensemble.BalancedRandomForestClassifier.html#imblearn-ensemble-balancedrandomforestclassifier) and the [Easy Ensemble Classifier](https://imbalanced-learn.readthedocs.io/en/stable/generated/imblearn.ensemble.EasyEnsembleClassifier.html#imblearn-ensemble-easyensembleclassifier). Refer to the documentation for each of these to read about the models and see examples of the code.

To begin:

1. Read the data into a DataFrame using the provided starter code.

2. Split the data into training and testing sets.

3. Scale the training and testing data using the `StandardScaler` from `sklearn.preprocessing`.


Then, complete the following steps for each model:

1. Train the model using the quarterly data from LendingClub provided in the `Resource` folder.

2. Calculate the balanced accuracy score from `sklearn.metrics`.

3. Display the confusion matrix from `sklearn.metrics`.

4. Generate a classification report using the `imbalanced_classification_report` from imbalanced learn.

5. For the balanced random forest classifier only, print the feature importance sorted in descending order (most important feature to least important) along with the feature score.


Use the above to answer the following questions:

* Which model had the best balanced accuracy score?

* Which model had the best recall score?

* Which model had the best geometric mean score?

* What are the top three features?

- - -

##### Hints and Considerations

Use the quarterly data from the LendingClub data provided in the `Resources` folder. Keep the file in the zipped format and use the starter code to read the file.

Refer to the [imbalanced-learn](https://imbalanced-learn.readthedocs.io/en/stable/) and [scikit-learn](https://scikit-learn.org/stable/) official documentation for help with training the models. Remember that these models all use the model->fit->predict API.

For the ensemble learners, use 100 estimators for both models.

- - -

##### Submission

* Create Jupyter notebooks for the homework and host the notebooks on GitHub.

* Include a markdown that summarizes your homework and include this report in your GitHub repository.

* Submit the link to your GitHub project to Bootcamp Spot.

- - -

© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
