# credit_risk

challenge is under -Module-17-Challenge-Resources
- starter_code


Credit risk is an inherently unbalanced classification problem, as the number of good loans easily outnumber the number of risky loans. Therefore, you’ll need to employ different techniques to train and evaluate models with unbalanced classes. Jill asks you to use imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

Objectives
The goals of this challenge are for you to:

- Implement machine learning models.
- Use resampling to attempt to address class imbalance.
- Evaluate the performance of machine learning models.

I used the imbalanced-learn library to resample the data and build and evaluate logistic regression classifiers using the resampled data. For oversample of the data I usied the RandomOverSampler and SMOTE algorithms. For the undersample the data was analyzed using the cluster centroids algorithm. For the combination approach I used the SMOTEENN algo. For each of these approaches I did the following steps:

1. Train a logistic regression classifier (from Scikit-learn) using the resampled data.
2. Calculate the balanced accuracy score using balanced_accuracy_score from sklearn.metrics.
3. Generate a confusion_matrix.
4. Print the classification report (classification_report_imbalanced from imblearn.metrics).

The SMOTE model has a high blended accuracy score and the highest precision and recall scores as well. The Naive random oversampling has a similar accuracy score, but the recall score is much lower than in SMOTE. The f1 score is also higher for SMOTE. While a 66% score may not be high enough for cancer treatment, it may be acceptable for credit risk. False negatives can always be disputed by the customer and a manual re-evaluation can be done. If it was me having to make the call, I would not want an accuracy of 66% and a recall of 69%. I would have to get get better data and another model to be comfortable predicting credit risk.

Below are the results for each model:

#Credit risk resampling

#Naive Random Oversampling:

Precision: 0.99

Recall: 0.57

F1: 0.72

Balanced accuracy score 0.65

#SMOTE Oversample:

Precision: 0.99

Recall: 0.69

F1: 0.81

Balanced accuracy score 0.66

#Undersample:

Precision: 0.99

Recall: 0.41

F1: 0.58  

Balanced accuracy score 0.55

#Combo SMOTEENN:

Precision: 0.99

Recall: 0.57

F1: 0.72  

Balanced accuracy score 0.55

The data below is for the extension work. The easy ensemble AdaBoost Classifier is the more ideal fit as all four metrics are extremely high. Accuracy by itself can be useless, but if precision and recall are high, then we can rely on the data. This is the model I would use.

top 3 features of importance for the credit model:
loan_amnt: (0.09175752102205247)

int_rate: (0.06410003199501778)

installment: (0.05764917485461809)

#Credit risk ensemble

#Balanced Random Forest Classifier:

Precision: 0.99

Recall: 0.90

F1: 0.94

Balanced accuracy score 0.79

#Easy Ensemble AdaBoost Classifier:

Precision: 0.99

Recall: 0.94

F1: 0.97

Balanced accuracy score 0.93
