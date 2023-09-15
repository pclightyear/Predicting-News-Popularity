# Predicting News Popularity

The goal of this project is to predict the popularity of the news crawled from the internet. This is a [competition](https://www.kaggle.com/competitions/datalab-cup1-predicting-news-popularity/overview) from the deep learning course offered in Nation Tsing Hua University. Deep learning based methods are not allowed in this competition, such as pre-trained embeddings, RNN, or transformers, and the focus is to extract features and generate predictions with traditional machine learning methods.

We extract text features, temporal features, and other features from the raw html news pages. The prediction is made by an ensemble of linear classifier, decision tree classifier, and k-nearest neighbor classifier. Our method reaches 0.594 AUC on testing data and places 6th out of 57 teams in the class.

The original competition was hold on Octorber, 2020.

## Major features extracted
### Text features
- Tf-idf features from the news article, with stemming and stop word removal
- Bag of words features from the news title
- Topics of the news

### Temporal features
- Year, month, day, hour of the published time
- Whether the published date is weekend

### Other features
- Author of the news
- Number of images

## Ensemble
- Classifiers: ridge classifier, decision tree classifier with bagging, and k-nearest neighbor classifier
- The weights of the classifiers are determined by grid search.

## Tools in use
- nltk
- scikit-learn
- BeautifulSoup