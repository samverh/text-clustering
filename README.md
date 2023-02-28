# Text clustering / Topic modelling
This repository contains supporting code for a Blackbear challenge.

## Goal
Create a data model for the future chatbot of a company. Data consists of 25000 emails and the objective is to find out how they can be divided into frequently asked questions.

## Approach
Clustering (unsupervised learning) techniques will be performed on the emails, since there are no pre-existing labels provided in the data.

## Notes
### Cleaning data
It is advised not to clean too much. However, remember stemming words to their root.

### Feature engineering
#### TF-IDF
Useful for shorter texts

Using `TfifdVectorizer` from sklearn. Settings:
* `max_df=50` excludes words which occur in more than 50% of the text
* `min_df=5` remove words that rarely occur
* `lowercase=True` convert all inputs to lower, useful for cleaning
* `ngram_range=(1,3)` use to consider subset of words (ngrams) in clustering

#### LDA
Useful forlonger texts and when there are multiple topics per email.


### Plotting
Multiple variables per topic, PCA needed to plot
