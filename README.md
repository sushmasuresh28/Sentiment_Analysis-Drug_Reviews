# Predicting Patient Ratings based on Drug Reviews

## Abstract
Online health-related sites and opinion forums contain abundant information about user preferences and experiences over multiple drugs and treatment. This information can be leveraged to obtain valuable insights using data mining approaches such as sentiment analysis. Sentiment analysis measures the inclination of people’s opinions through techniques like text analysis and natural language processing. Online user reviews in this domain contain information related to multiple aspects such as the effectiveness of drugs and side effects, which make automatic analysis very interesting but also challenging. However, analyzing the sentiments of drug reviews can provide valuable insights. They might help pharmaceutical companies and doctors to quickly get into bad reviews and know patients' complaints. This sentiment analysis on drug reviews is basically modeled as a classification problem (i.e.,) classifying the sentiment of the user whether positive, negative or neutral based on their choice of words and their reviews. A lot of symptoms and drug sides were hidden under reviews, which will be great to be automatically extracted to improve the drug and help to give a better prescription.

## Data
The dataset used in this project provides patient reviews on specific drugs along with related conditions and a 10-star patient rating reflecting overall patient satisfaction. It is derived from Kaggle: https://www.kaggle.com/jessicali9530/kuc-hackathon-winter-2018.
The features are described below.
* drugName - Name of the drug for which review has been posted,
* condition - condition/disease for which the drug has been prescribed
* review - user comments for the corresponding drug
* rating - 10-star rating reflecting overall patient satisfaction
* date - the date on which review has been posted
* usefulcount - count of users who found the review to be useful

## Data Pre-Processing
As our task is to perform sentiment analysis on reviews which is text data, words are our feature set over which we would be building models. Our dataset contains reviews with a lot of unnecessary words and characters which could hamper the performance of our models and must be removed.
The following steps have been incorporated by us to perform data preprocessing:
1) Since the table contains ratings ranging over values from 0 to 10 and we are performing binary classification, we split the ratings from 0 to 5 into the first class 0 implying that the reviews are bad and ratings from 6 to 10 into class 1, implying that the ratings are good
2) A lot of reviews in our data contained HTML characters which have been removed
3) Special characters such as @,#,&, etc. have been removed from the dataset
4) All the characters have been converted to lower-case to maintain uniformity
5) Each review comprises of a lot of words which have been tokenized
6) Lemmatization has been performed so that each word is reduced to its root from
7) Negator words such as ‘don't’, ‘not’, ‘no’ have been removed from the pool of stop words
8) The updated stop words have been removed from the reviews

## Modeling
Given the review of the drug, prediction of patient rating is done which is either positive (1) or negative (0). The patient reviews are first cleaned using earlier mentioned pre-processing steps to remove all special encoded characters, tags, and punctuations. Tokenization, lemmatization and removal of stop words have then been performed. The patient ratings have been divided into two classes positive and negative to create a new column called "sentiment". Rating is from the range 0-10, we have classified the reviews to be positive when their ratings are greater than or equal to 5, negative otherwise.
The models that have been implemented are-
* Naïve Bayes Classifier
* Logistic Regression
* Light Gradient Boosting Model (LGBM)
* Convolutional Neural network (CNN)
* Support vector machine (SVM)
* K nearest neighbors (KNN)
