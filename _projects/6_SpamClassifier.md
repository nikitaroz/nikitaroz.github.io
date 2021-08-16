---
layout: page
title: SpamClassifer
description: A website to visualize why emails are spam.
img: /assets/img/spam-wordcloud.svg
github: https://github.com/nikitaroz/SpamClassifier
importance: 6
---

# Introduction
I was looking at the [SpamAssassin](https://spamassassin.apache.org/old/publiccorpus) database and I wanted to create a way to easily visualize and understand why certain emails were classified as spam and others were not. The database consists of xx normal emails and xx spam emails, recorded at .. in year, with each email labelled.

# Model
The first step of the modeling pipeline transforms the raw email content into a format that can be input into a machine learning model. An email consists of several header fields that contain metadata such as the sender, reciever, and subject followed by the email's content. The model that I developed focused only on the fields that contain prose: the subject and body. I used the `mailparser` library to extract these fields from the emails. 

These fields may also contain irregular elements that need to be specially processed to obtain better input data. For example, the some emails contained HTML markup in the body: these elements were removed and replaced with plain text using the `beautifulsoup` library. Additionally, some emails contained non-ascii characters or encoding errors: these were handled using `ftfy`, which normalizes common encoding issues. Finally, the subject and body are merged to be processed as a single input for simplicity.

The next step in the pre-processing pipeline is tokenization and stemming. The former breaks a string into its individual building blocks. Although this may seem like a simple step, the peculiarities of natural language, including as non-standard punctionation, contractions, and compound words, make this a non-trivial task. After evaluating several tokenizers, I found that the `TweetTokenizer` in the `nltk` package produced qualitatively the best results for the given dataset. Following this step comes stemming, which reduces each token to its root if one exists. For example, the words "derive", "deriving", and "derived" all stem to the same root "deriv" using the `SnowballStemmer`. Since all these words are analogous, the stemmer reduces them to a common stem, which allows for all these to be treated as one variable. 

Finally, the `tf-idf` vectorizer in `scikit-learn` converts the processed words into a vectorized model that can be input into a classifier. The vectorizer takes the 5000 most frequent words and ... 

I wanted the resulting model to have an easy interpretation, which is why I chose a linear model. I used `XGBoost` to train the linear model. 

# Website
Check out the project here: [SpamClassifier](http://www.myspamclassifier.com). For the frontend, I used a combination of bootstrap, d3, and jquery. The backend relies on sqlite to store the emails and model information as well as flask handle incoming requests and serve content. The searching functionalty of the website is done through the sqlite full text search utility. All the code and the database is combined into a single Docker image and deployed on AWS with the Elastic Beanstalk service.

# Results
The classifier has a 98.9% accuracy when tested on -- of the dataset that was specifically set aside for testing. When using 5-fold cross-validation on the training set, the classifier had an out-of-fold average accuracy of --. This is a significant improvement over 74% accuracy achieved for a classifier that naively classifies all emails are normal. Below is a wordcloud of some of some of the most telling words the classifier uses to determined if an email is spam.

<img class="img-responsive mx-auto d-block" src="{{ '/assets/img/spam-wordcloud.svg' | absolute_url }}" alt="Spam classifier word cloud" data-zoomable>

The words that are red are more likely to be associated with spam emails, while green words indicate that an email is normal. Also, the size of the word corresponds to how frequently it appears within emails from the dataset. 