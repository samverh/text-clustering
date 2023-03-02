# Text Clustering
This repository contains supporting code for a freelance project on topic modelling.

## Goal
Create a data model for the future chatbot of a company. Data consists of a large set of emails and the objective is to find out how they can be divided into frequently asked questions.

## Approach
Clustering (unsupervised learning) techniques will be performed on the emails, since there are no pre-existing labels provided in the data.

<hr>

## Notes
### (1) Cleaning data
It is advised not to clean too much. Be careful with choosing stop-words (and make sure that the stops underwent the same preprocessing and tokenization steps as the words in the vectorizer. Remember stemming words to their root such that words in different forms can be treated as similar words.

### (2) Feature engineering
#### TF-IDF
Useful for shorter texts.

Using `TfifdVectorizer` from sklearn. Settings:
* `max_df=50` excludes words which occur in more than 50% of the text
* `min_df=5` remove words that rarely occur
* `lowercase=True` convert all inputs to lower, useful for cleaning
* `ngram_range=(1,3)` use to consider subset of words (ngrams) in clustering

### (3) Clustering

#### KMeans
Can be used but has several limitations.

#### LDA
Useful for longer texts and when texts contain multiple topics.

### (4) Computation limitations
#### Big data
Possibly make use of `HashingVectorizer` to deal with large dataset, however it does not provide IDF weighting.

#### Sparsity
From the sklearn documentation: "For instance a collection of 10,000 short text documents (such as emails) will use a vocabulary with a size in the order of 100,000 unique words in total while each document will use 100 to 1000 unique words individually." 

Therefore `scipy.sparse` is useful to speed up algebraic operations on matrices and vectors.


### (5) Visualization
Multiple variables per topic, PCA needed for plotting in 2 dimensions.

![alt text](https://github.com/samverh/text-clustering/blob/main/results/clustered_articles.png)
