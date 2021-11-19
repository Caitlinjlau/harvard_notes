# Lab 11 Notes  11/19/21

- **Permutation importance**: looking at feature importance from the trees themselves using the ELI5 package. 
- **ELI5 package** is really good at showing the weights and features of different models 
- Every single model except the adaboost model say that Age is the most important factor
- This occurs because there are a lot of features that are correlated with Age. 
- Why use ELI5 package? if you have 20,000 coefficients it makes it easier. 
- NLP words like Athiesm are the most popular on Athiesm news site. 
- The NLP was recognizing particular words like email addresses: this is NOT what we want! get rid of all the headers with emails, but now we are predicting the actual content of our page, NOT the background noise
- There is a strange occurance: common words like "for" and "what" are strong predictors? 
	- In order to avoid this we will avoid **stop words** like pronouns, and common words in order to better understand the content of the text data. 
	- **Words with apostrophes** are not considered **stop words** so be careful!
- Instead of looking at just the counts of the words, if the word is so common, it is not relevent to our classification
	- An alternative is to use a type of weighting called **TFIDF**. 
- The best model was **weighting of words + removing the stop words**
- You want the NLP model to make robust conclusions. 
- **count vectorizer**
- How the predictor is important
	- How to determine the importance of the relationship other than magnitude?
- Usually we make a prediction plot. Plot the predictions against the predictors 
	- This doesn't work when you have **alot** of predictors!
- Convention in plotting (**It assumes that the first arg __ x ___ is the y axis!!**)
	- **y vs x axis**
- You can hit an **accurate ceiling** if you just look at accuracy doesn't go up anymore, however as you continue to increase the complexity, the predicted probabilities can become **even more overfitted** 
	- having models **overly confidence is not a good thing**
- see how a predictor affects the relationship. Can we vary one predictor and keep the rest fixed in order to see how the other predictors are affected
- let's take every observation in the dataset and duplicate that row and only change the "age" variable.
- For categorical predictors you can use the **mode** in order to replace **missing values**

#### Surrogate explainer model 
- Black box model and we train an interpretable model to explain the predictions of teh Black box model (the response is the prediction of the original Black box model)

