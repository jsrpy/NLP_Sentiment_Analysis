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

The Reuters datset contains 11,228 newswires from Reuters, labeled over 46 topics. Similar to the IMDB dataset, each wire is encoded as a sequence of integers.

A CNN is built to classify the news topic of each wire.
* [Reuters_news_topic_classify_A](Reuters_news_topic_classify_A.ipynb)
This attempt used a similar method as the IMDB sentiment classification, which means the sequence-of-integers representation of words is retained and directly fed into the convolutional embedding layer. 

#### Results
This approach does not produce a satisfactory result. A second approach with higher accuracy is demonstrated in the next session.

* Test Accuracy: 65.49%

## 3. Reuter_B

* [Reuters_news_topic_classify_B](Reuters_news_topic_classify_B.ipynb)
In this second attempt, the sequence-of-words-integers is vectorise as one-hot word vector, and then fed into a fully-connected perceptrons layer.

#### Results
This second approach is simplier in architecture and attains a higher accuracy than approach A!

* Test Accuracy: 79.70%

## Comparison between Reuters A & B Approach

Approach A attempts to retain to sequential meaning of natural language and use a convolutional neutral nets to learn that semantic meaning for topic classification. It turns out that it is unclear as to how the neural architecture should be set up to properly address this task, and the training time is longer as the matrix is sparse.

Approach B attempts to just use the one-hot word vector, i.e. looking at which words appear in a newswire and fed them directly to a fully-connected neurons to learn the topic relationship. It is fast to train and does not need to consider building up the convolutional layer.

## Requirements:
* keras
