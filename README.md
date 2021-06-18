# Credit_Risk_Analysis

## Overview 

Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans.  In this project, we will need to employ different techniques to train and evaluate models with unbalanced classes.  We have been asked to use imbalanced-learn and scikit-learn libraries to build and evaulate models using resampling.  Using the credit dataset from LendingClub, a peer to peer lending services company, we will oversample the data using RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then we will use a combinatorial apporoach of over and undersampling using the SMOTEEN algorithm. Next, we well compare the two machine learning models that reduces bias, BalaceRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk.  Once done, we will evlauate the performance of these models and make a written recommendation on whether they should be used to predict credit risk. 

## Results

Imbalanced classification reportes were created for each training model: RandomOverSampler, SMOTE, ClusterCentroids, SMOTEEN, BalancedRandomForestClassifier, and EasyEnsembleClassifier. These were created in Jupyter Notebook. Training variables were created by converting the string values into numerical ones using the get_dummies method. Then the LogisticRegression classifier to make predictions, calculate the accuracy score, and generate a confusion matrix.  Finally, the imbalanced classification report was created using the test data and predictions.

## Over Sampling 

- RandomOverSampler
    - Accuracy: 66%
    - High Risk Precision: 1%
    - High Risk Recall: 70%
    - Low Risk Precision: 100%
    - Low Risk Recall: 63%

![image](https://github.com/snkty8/Credit_Risk_Analysis/blob/main/Images/RandomOversampler.png)


- SMOTE
    - Accuracy: 66%
    - High Risk Precision: 1%
    - High Risk Recall: 63%
    - Low Risk Precision: 100%
    - Low Risk Recall: 69%

![image](https://github.com/snkty8/Credit_Risk_Analysis/blob/main/Images/SMOTE.png)


- ClusterCentroids
    - Accuracy: 66%
    - High Risk Precision: 1%
    - High Risk Recall: 69%
    - Low Risk Precision: 100%
    - Low Risk Recall: 40%

![image](https://github.com/snkty8/Credit_Risk_Analysis/blob/main/Images/ClusterCentroids.png)

## Undersampling

- SMOTEEN
    - Accuracy: 54%
    - High Risk Precision: 1%
    - High Risk Recall: 72%
    - Low Risk Precision: 100%
    - Low Risk Recall: 57%

![image](https://github.com/snkty8/Credit_Risk_Analysis/blob/main/Images/SMOTEEN.png)


## Combination

- BalancedRandomForestClassifier
    - Accuracy: 78%
    - High Risk Precision: 3%
    - High Risk Recall: 67%
    - Low Risk Precision: 100%
    - Low Risk Recall: 88%

![image](https://github.com/snkty8/Credit_Risk_Analysis/blob/main/Images/BalancedRandomForestClassifier.png)


- EasyEnsembleClassifier
    - Accuracy: 92%
    - High Risk Precision: 9%
    - High Risk Recall: 89%
    - Low Risk Precision: 100%
    - Low Risk Recall: 94%

![image](https://github.com/snkty8/Credit_Risk_Analysis/blob/main/Images/EasyEnsembleClassifier.png)


## Summary
The purpose of this project was to determine if these models could be used to accurately predict credit risk. All three of the oversampling models had an accurary of 66%, undersampling yielded an accuracy of 54%, and using a combination of the undersampling and oversampling yielded 78% and 92%.  While undersampling yielded a higher level of accurary than undersamling, the combination model EasyEnsembleClassifier had the highest level of accuracy of 92%. But, accuracy isn't the only metric we should relay on. We also have to take a look at precison and recall.  Although the low risk precision in all models were 100%, the high precision was 1% in the oversampling and undersampling models, 3% in BalancedForestClassifier, and 9% in EasyEnsembleClassifer. Sensitivity is the metric we could depend most on. This is the metric that does accurately describe the situation. The EasyEnsembleClassifier model is still the most reliable when determining credit risk. 