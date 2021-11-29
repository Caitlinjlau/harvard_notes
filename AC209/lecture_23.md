# Lecutre 23: Natural Language Processing (NLP) 11/29


#### What is NLP
- NLP branch of AI that allow computers to interpret, analyze and manipulate human language
- NLP develop apps/ services that understand human language
- requireds a lot of preprocessing
- words have "different meaning" based on context
- unstructured data (not tabular data) preprocessing data 
- how to take the unstructured data and start **featurizing** it. 
	- create a tabular form that is machine readable

### Steps of analysis
###### Example Project
- Twitter data (plot the tsla stock price and Elon's Twitter activity)
- Sentiment analysis (are they positive or negative tweet)
- Live feed of the news data to model to stock prices
- Part of speech tagging
- Information Retrieval
- Target Ads 
- Translators 
- Speech Recognition
- Text summarization

##### Pipelines 
1. Tokenization
2. Stopwords
3. Stemming/Lemmatization

##### Model types 
1. NLTK
2. spaCy
3. CoreNLP

##### Lecture Notebook
- JSON files 
- tokenizationL and splt between white spaces wbetweeen caracter A similar place btween charcctera most claim to hremove other extraneous words like acount names/hashtags 
- The number of token in tweets is about 100-1

#### Baseline
batzrj- take all the tokens in the preprocesseddaam
- create a matrix and eac column is a tken.
|loop | Salary | Sag| GOOD
@ UOU NEED TO ADD REVEIWS ON A 
- TO bill context 
- "n-grams"
	- 1 gram is 1 word in words they appear 
- bi gragemP PREIORITIZE A BI GRAM
- TRI GRAM 
- use regulatization fo ra sparse matrix.
- we can use cross validatiaon to figure out what  number gram we should use 
- If we count the most important tokens, we can use a package 

#### Stemming/ Lemmitization 
-**"Stemming**
- ThinkING vs Think 
- the -ing suffix links thinking to think
- We just want to look at the root of the word.
- **LEmitization**
- more advanced stemming
- preserves order like good, better, best

##### Pre process steps 
1. Tokenization 
2. Stop words 
3. Stem/ Lemmitization 

##### Part of Speach
- tag if it is a non, adjective, preposition
- look at adjective then word after the adjective. 
- tag the part of speech and look at set of words that immediately follows it. 
- **very powerful** 
- nltk tag pos_tag

##### Bag of words model 
- Twitter data, cleaned, stop words, lemmitized 
- 100 features 
- countVectorizer( max_features = 100, ngram_range = (1,2))
- look at the word frequencies 
- look at the accuracy of the model 
- multinomialNB (naive bayes)

##### TFIDF 
- inverse document frequency
- the bag of words model counts the number of times a word appears
- think about commoun words in doccument and teh uncommon words in the documents- if the word happy appears in every tweet, not a lot of meaning
- if the word happy appears in a particular subset of tweets, but is uncommon across other it has high signignicance
- **term frequency**
- look at particular token and count the number of times it appears the number of time token appears across different tweets. 
- **completely different way to featurize data**
- How do we use the tokens to a tabular form requires creativity. 

##### Bag of words model vs the TF-IDF model 
- text is very complex and how do we parse this information use these packages
