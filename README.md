# Credit Risk Analysis
## Purpose

> evaluate the performance of various models and make a written recommendation on whether they should be used to predict credit risk

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, you’ll oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, you’ll use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Next, you’ll compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. Once you’re done, you’ll **evaluate the performance of these models and make a written recommendation on whether they should be used to predict credit risk.**

## Results
### Random Oversampling
Resampled Training Data:

    low_risk     51352
    high_risk    51352

Balanced Accuracy Score:

    0.6462556051101684

Confusion Matrix:

    [   53,    34]
    [ 5421, 11697]

Imbalanced Classification Report:

                    pre       rec       spe        f1       geo       iba        sup
    high_risk       0.01      0.61      0.68      0.02      0.65      0.41        87
    low_risk        1.00      0.68      0.61      0.81      0.65      0.42     17118
    avg/total       0.99      0.68      0.61      0.81      0.65      0.42     17205

### SMOTE
Balanced Accuracy Score:

    0.6395083215490047

Confusion Matrix:

    [   53,    34]  
    [ 5652, 11466]

Imbalanced Classification Report:

                    pre       rec       spe        f1       geo       iba        sup
    high_risk       0.01      0.61      0.67      0.02      0.64      0.41        87
    low_risk        1.00      0.67      0.61      0.80      0.64      0.41     17118
    avg/total       0.99      0.67      0.61      0.80      0.64      0.41     17205


### Cluster Centroids
Balanced Accuracy Score:

    0.5139669474761392

Confusion Matrix:

    [  49,   38]
    [9163, 7955]

Imbalanced Classification Report:

                   pre       rec       spe        f1       geo       iba        sup
    high_risk      0.01      0.56      0.46      0.01      0.51      0.26        87
    low_risk       1.00      0.46      0.56      0.63      0.51      0.26     17118
    avg/total      0.99      0.47      0.56      0.63      0.51      0.26     17205

### SMOTEENN
Balanced Accuracy Score:

    0.6089496436499591

Confusion Matrix:

    [  58,   29]
    [7682, 9436]

Imbalanced Classification Report:

                  pre       rec       spe        f1       geo       iba        sup
    high_risk     0.01      0.67      0.55      0.01      0.61      0.37        87
    low_risk      1.00      0.55      0.67      0.71      0.61      0.36     17118
    avg/total     0.99      0.55      0.67      0.71      0.61      0.36     17205

### Easy Ensemble AdaBoost
Balanced Accuracy Score:

    0.9188026736413833

Confusion Matrix:

    [   62,    25]
    [ 1372, 15746]

Imbalanced Classification Report:

                  precision    recall  f1-score   support
    high_risk          0.04      0.71      0.08        87
    low_risk           1.00      0.92      0.96     17118
    accuracy                               0.92     17205
    macro avg          0.52      0.82      0.52     17205
    weighted avg       0.99      0.92      0.95     17205

## Summary

| Scoring Summary        | Score       |
|------------------------|-------------|
| Random Oversampling    | 0.646255605 |
| SMOTE                  | 0.639508322 |
| Cluster Centroids      | 0.513966947 |
| SMOTEEN                | 0.608949644 |
| Easy Ensemble AdaBoost | 0.918802674 |


Across all models, the Easy Ensemble AdaBoost proveides the highest Balanced Accuracy Score for all risk loans (~0.919). In approximately 90% of the above analysis, the Easy Ensemble AdaBoost (EasyEnsembleClassifier) will perform a the most precise prediction for high-risk loans. I recommend the EasyEnsembleClassifier.

