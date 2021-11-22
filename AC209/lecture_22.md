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
| Accuracy              |                                |                     |     |
| Sensitivity           |                                |                     |     |
| Specifcity            |                                |                     |     |
| Precision             |                                |                     |     |
| F1 Score              |                                |                     |     |

| ............. | Predicted Low | Predicted High |
| Low           | True Negative | False Positive |
| High          | False Negative | True Positive | 

