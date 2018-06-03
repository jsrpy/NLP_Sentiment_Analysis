# Sentiment_Classification_Word_Embeddings
Examples of using Keras word embedding to perform sentiment classification on IMDB and Reuters datasets.

## 1.IMDB

This dataset contains 25,000 movie reviews from IMDB, labeled with sentiment (positive or negative). The test data is of the
same size (25,000) rows of data, i.e. it is ia 0.5 split by default.

A 1D Convolutional neural network is trained on the training set and tested.
* [IMDB movie reviews sentiment classification](IMDB_reviews_sentiment_classify.ipynb)

#### Why 1D ConvNet?
Text data is sequential data. A 1D neural network is best at retaining and learning the sequential patterns in a corpus.

So generally speaking, we should use a 1D architecture whenever countering textual data.

#### Results:
* Test Accuracy: 86.42% 

# Requirements:
* keras
