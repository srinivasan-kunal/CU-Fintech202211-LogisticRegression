# CU-Fintech202211-LogisticRegression

## Overview of the Analysis


The purpose of the analysis was to build a logistic regression to predict high risk loans in a portfolio. The data used included customer level attributes like income, size of the loan, interest rate along with along with attributes related to total customer debt and negative information. 

There were a total of 79536 records available for the analsis of which 2500 were tagged high risk loans in the data. The low count of high risk loans in the data data make it imbalanced. 

75% of the data was used for training while the rest was for testing.  

To identify the best possible outcome the analysis included two variations of logistic regression models. One with the original data and one after resampling the original data. Due to the low volume of high risk loans in the data, oversampling approach was used when resampling the data. 

## Results

**Model 1: Using original data

Testing data accuracy score using original data: 0.9218

Confusion matrix & Classification Report for testing data: 

```python
                                     (18663   102)
                                     (   56   563)
                                     
                                     
                                     
                   pre       rec       spe        f1       geo       iba       sup

          0       1.00      0.99      0.91      1.00      0.95      0.91     18765
          1       0.85      0.91      0.99      0.88      0.95      0.90       619

avg / total       0.99      0.99      0.91      0.99      0.95      0.91     19384
```

**Model 2: Using Resampled data

Testing data accuracy score using resampled data: 0.9937

Confusion matrix & Classification Report for testing data:

```python
                                         (18649   116)
                                         (    4   615)
                                         
                                         
                                         
                   pre       rec       spe        f1       geo       iba       sup

          0       1.00      0.99      0.99      1.00      0.99      0.99     18765
          1       0.84      0.99      0.99      0.91      0.99      0.99       619

avg / total       0.99      0.99      0.99      0.99      0.99      0.99     19384
```

## Summary

The accuracy score of the logistic regression is better on resampled data ~99% (vs 92% in original data). New model continues to perform extremely well on the healthy loans. However the performance in terms of the precision and recall for the high-risk loan is different. In the resampled data the precision remain the same (~85%) but the recall shows an improvement from 91% originally to 99% after resampling.

Based on the above the model using the resampled data would be recommended for it's better recall.