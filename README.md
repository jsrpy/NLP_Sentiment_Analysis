# Sentiment_Analysis_Word_Embeddings
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

## 2. Reuters_A

The Reuters datset contains 11,228 newswires from Reuters, labeled over 46 topics. Similar to the IMDB dataset, each wire is encoded  as a sequence of integers.

A CNN is built to classify the news topic of each wire.
* [Reuters_news_topic_classify_A.ipynb](Reuters_news_topic_classify_A.ipynb)
This attempt used a similar method as the IMDB sentiment classification, which means the sequence of integers representation of words is retained and directly fed into the convolutional embedding layer. 

#### Results
This approach does not produce a satisfactory result. A second approach with higher accuracy is demonstrated in the next session.

* Test Accuracy 67.00%

## 3. Reuter_B

# Requirements:
* keras
