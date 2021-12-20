# Credit_Risk_Analysis
## Overview of the analysis
The purpose of this project is to use imbalanced-learn and scikit-learn libraries to build and evaluate credit card risk models using resampling and to identify whether they should be used to predict credit risk.
## Results
Using imbalanced-learn and scikit-learn libraries, four machine learning models: RandomOverSampler, SMOTE algorithms, undersampling ClusterCentroids and SMOTEENN algorithms were evaluated to determine which one is better at predicting credit risk. In addition to that, two different ensemble classifiers: BalancedRandomForestClassifier and EasyEnsembleClassifier were trained and compared to predict credit risk. For each resampling algorithm, the following were performed:
- LogisticRegression classifier to make predictions and evaluate the model’s performance.
- Accuracy score of the model was calculated.
- Confusion matrix was generated.
- Imbalanced classification report was printed.

The following table summarizes the balanced accuracy score, precision and recall scores of all six machine learning models for both the classes (High Risk and Low Risk).

| Algorithms                     | Precision(High Risk) | Recall(High Risk) | Precision(Low Risk) | Recall(Low Risk) | Balanced Accuracy Score |
| ------------------------------ | -------------------- | ----------------- | ------------------- | ---------------- | ----------------------- |
| RandomOverSampler              |   0.01               |   0.63            |   1.00              |   0.66           |   0.647                 |
| SMOTE                          |   0.01               |   0.65            |   1.00              |   0.69           |   0.671                 |
| ClusterCentroids               |   0.00               |   0.42            |   0.99              |   0.52           |   0.671                 |
| SMOTEENN                       |   0.01               |   0.65            |   1.00              |   0.57           |   0.614                 |
| BalancedRandomForestClassifier |   0.03               |   0.60            |   1.00              |   0.89           |   0.747                 |
| EasyEnsembleClassifier         |   0.09               |   0.92            |   1.00              |   0.94           |   0.931                 |

## Summary
It is evident from the above table that the models have a very low precision score for High Risk predictions. This could be the result of class imbalance. Comparing to the High Risk class, the precision rate for low risk is quite high. All the models have a balanced accuracy score > 0.5. 

I would recommend *EasyEnsembleClassifier* to predict credit risk based on above observations since the scores are higher compared to the other models. The following are the observations that led to my conclusion. 
- The recall score which is the ability of the classifier to find all the positive samples is very high in this model. 
- The precision score which is the ability of the classifier not to label a positive sample that is negative is also high for the low risk class and is higher for the high risk     compared to other models. 
- The balanced accuracy which is defined as the average of recall obtained on each class is the highest in this evaluation. 

In order to increase the precision score in the above case, we can check for additional features that can be extracted or engineered from the dataset. It could be possible that there are other features that are strong correlates to the target class that can help boost the precision score. 

