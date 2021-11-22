# Lecture 22, Classification metrics: Examples 11/22/21

- The new deadline is on wednesday for the PSET
## Covid Study
- at the beginning of covid, a lot of hospitals were running out of best
- Authorities had to take a call on who to admit/ who to send home.
- Build a **classifier** to suggest who should be admitted and who should go home.
#### Who should get medical attention first
- Issues with the data
	- Data is sourced from online forms and is questionable. 
	- A lot of missing values ignored 
## Covid data
- Primary predictors 
	- age, sex, cough, fever, chills
- Outcomes
	- urgency of admission **Classification**
	- 1-2 day admission
	- 2+ day of admission
- Karandeep Singh

### Scenario #1 Brazil
- new covid variant, the infection rate went down?
- hospitals were avoiding classifing peopel as 'high' risk 
- **TPR + FPR <= 0.5**
	- True pos + false pos rate should be less than 0.5
	- For all people admitted only call less than half of people as high urgency. 
	- The conservatives want to hide the severity of the crisis in Brazil.
	
## Scenario 2 
- Germany wants to be extra careful and classify as many people as possible
- TPR <= 0.85 

## Scenario 3 
- India
- Only 1 million beds left, but 2 million people suspected of having the disease. 
- TPR + FPR <= 1
- 2 million people suspected have covid only 1 million beds left?
	- TPR* 2 million 

## Which model
- Logistic Regression
- KNN Classification
- First thing we do is the evaluate the model 
- **Use SMOTE**
	- SMOTE stands for Synthetic Minority Oversampling Technique. This is a statistical technique for increasing the number of cases in your dataset in a balanced way.
- **STEPS**
	- regularization, hyper paramter
	- fill out SMOTE form then decide which model to use
	- Then play with the trhesholds
	- get the ROC curves
	- Then decide which model to use.


| Classification Metric | Formula                        | Logistic Regression | KNN |
| --------------------  | ------------------------------ | ------------------- | --- |
| Accuracy              |                 .              |    .                |  .  |
| Sensitivity           |            .                   |          .          |   . |
| Specifcity            |             .                  |         .           |  .  |
| Precision             |            .                   |          .          | .   |
| F1 Score              |             .                  |         .           |  .  |

| ............. | Predicted Low | Predicted High |
| Low           | True Negative | False Positive |
| High          | False Negative | True Positive | 


- It is hard to make a decision just looking at Accuracy, Sensitivity, precision 
- FPR acc Log reg 50
- FPR acc KNN 41
- F1 score Log reg 67
- F1 score for knn = 66
- Precision 61
- Precision 60

### Grid Search 
- #clf is the classifier model
- # give model, parameters, number of cv and it does it for you
- #cross validate over 
- c for log reg is the regularization c = 1/reg-strength
- c for knn is the best k 
- c is the hyper parameter

### Bayes Threshold 
- threshold we can play with that.
- Get your ROC curve 
	- ROC Curve is when we change our threshold how do our true positive/ false positive rates change 
- Get ROC curve for the two models 

#### Sensitivity 
- **aka Recall or TPR**
- TPR = recall = TP/OP = TP / (TP +FN)
- The Hit Rate: The fraction of observed positives (1s) the classifier gets right, or how many true positives were recalled. 
- Maximizing recall towards 1 = keep down false negative rate.

#### Specificity 
- **Specificity or True Negative Rate**
- $TNR = \frac {TN} {ON} = TN / (FP + TN)$

#### Precision
- **Positive Predicted Value**
- tells you how many predicted positive (1) hits were truly positive
- Precision = TP / PP = TP / (TP+FP)

#### F1 Score 
- Harmonic Mean of Precision and Recall. 
- Tries to minimize the false positive and the false negatives at the same time.
- F1 = (2 * recall * Precision) / (recall + Precision)

## ROC interpretation
- We have ROC curves 
- Germany (TPR > .85)
	- LOG REG
	- Lowest FPR, but needs to get a model with above threshold.
- Brazilian (TPR+ FPR < 0.5)
	- Get the lower curve
	- Max TPR and Min FPR while being below the red threshold
	- Logistic Regression. 
- India ()
	- Max TPR and Min FPR
	- KNN

- The utility of the interpretation and decisoin on which model are different for these 3 particular scenarios.
- ROC is three dimensional because we can change our thresholds and find the true positive rate
