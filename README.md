# Credit Risk Analysis

***Version 1.0.0***

---

## Overview of Project
#### This project makes an analysis of credit card risk for loans risks, since credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. I had to employ different techniques to train and evaluate models with unbalanced classes.

#### Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, I'll oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, you’ll use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Next, you’ll compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk.

Regarding the files you'll find here, let me explain them:

*  credit_risk_resampling.ipynb - In this script you'll find the algorithms test like: Naive Random Oversampling, SMOTE Oversampling, Undersampling and SMOTEENN algorithm.
*  credit_risk_ensemble.ipynb - Here you'll find the script for the Balanced Random Forest Classifier and Easy Ensemble AdaBoost Classifier. 
*  Resources - Here you'll find the results matrix from all the algorithms used on this project.

## Results
#### Since we are making an analysis of high-risk loans and try to predict if a loan is a high risk or not, we need to see the following:

<img src="https://github.com/SeRoGaTa/Credit_Risk_Analysis/blob/main/Resources/Premise.png" width="400">

This image tells us what the most important quadrants are that we need to analyze, for example:
- Green, these cells will be accurate, and we want our most values here.
- Yellow, this cell will let us know how many loans are wrongly predicted as high risk, this will avoid us to give loans to a request with low risk so we will lose money.
- Red, this cell will let us know how many loans are wrongly predicted as low risk, this will let us give loans to a high-risk request which will lose money.

With this said let’s analyze the accuracy, the precision, and the recall for all 6 models

- Accuracy: In the image below, you will see the results of accuracy for all models, as we can see our best model, our best model will give us an error of 4K loans bad predicted out of 68470 loans.
<img src="https://github.com/SeRoGaTa/Credit_Risk_Analysis/blob/main/Resources/Accuracy.png" width="400">
- Precision: In the image below, you see the precision of all models, here you see that our best model will have 979 bad predicted loans as high risk
<img src="https://github.com/SeRoGaTa/Credit_Risk_Analysis/blob/main/Resources/Precision.png" width="400">
- Sensitivity: In the following image you see the sensitivity for all models, here you see that our best model will have just 8 loans bad predicted as low risk.
<img src="https://github.com/SeRoGaTa/Credit_Risk_Analysis/blob/main/Resources/Sensitivity.png" width="400">
 
## Summary
#### In summary we can say that performing different algorithms to the same dataset is very helpful to detect the best depending on what you are following. I'll split my summary in the biggest four metrics:

- If we focus in the Balanced Accuracy, we will see how this model or algorithm is able to detect HR loans, in just the Easy Ensemble AdaBoost Classifier model we achieved the 94%, in which we can say with a total of 68470 loans we will mismatch nearly 4000 loans which area a lot, this means we can't just rely on this measure and that is why we look for the following measures.
- If we focus on the Precision, we will focus on get the most predicted HR are actually HR, but we see on the analysis that this number is too low since a lot of loans are predicted as HR when they actually are LR so we could lose a bunch of loans because they are wrong predicted as HR. So, our biggest lost is to have less loans as we want to. In this case Easy Ensemble AdaBoost Classifier since is the one with 7% and it could make us to lose the less loans possible 979.
- If we focus in the Sensitivity, we will be focused on finding the actual HR and the minimum HR that are predicted as LR, so with this our biggest problem is to give a loan that seems to be LR but is HR. In this case the best algorithm is also Easy Ensemble AdaBoost Classifier because it has a 90% of sensitivity so we will lose just 8.
- If we focus in the F1 Score, we will be having a good idea of an imbalanced data where it will help us getting the best result, in this measure also the Easy Ensemble AdaBoost Classifier is the highest score. 

Here as we read on the bullets above, the best algorithm to follow is the Easy Ensemble AdaBost since it will give us the smaller number of bad predicted HR which could help us giving more loans, the smaller number of bad predictions of LR which will help us to avoid giving loans to high-risk loans and will be the most accurate with just 4K wrong predictions.

You can see all these values summarized on the following matrix.

<img src="https://github.com/SeRoGaTa/Credit_Risk_Analysis/blob/main/Resources/Algorithms_report_matrix.png" width="1050">

Please find the complete analysis of the algorithms here [Credit_Risk_Analysis](https://github.com/SeRoGaTa/Credit_Risk_Analysis) and the resources presented out of this folder [Resources](https://github.com/SeRoGaTa/Credit_Risk_Analysis/tree/main/Resources)
