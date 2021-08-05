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
The first step for creating the model was to transform the raw email content into a format that can be input into a machine learning model. An email consists of several header fields that contain metadata such as the sender, reciever, and subject followed by the email's content. For simplicity, the model that I developed focused only on the fields that contain prose: the subject and body. I used the `mailparser` library to extract these fields from the emails. 

These fields may also contain irregular elements that need to be specially processed to obtain better input data. Specifically, the some emails contained HTML markup in the body: these elements were removed and replaced with plain text using the `beautifulsoup` library. Additionally, some emails contained non-ascii characters or encoding errors: these were handled using `ftfy`, which normalizes common encoding issues. Finally, the subject and body are merged to be processed as a single input for simplicity.

The next step in the pre-processing pipeline is tokenization and stemming. The former breaks a string into its individual building blocks. Although this may seem like a simple step, the peculiarities of natural language, including as non-standard punctionation, constractions, and compound words, make this a non-trivial task. After evaluating several tokenizers, I found that the `TweetTokenizer` in the `nltk` package produced qualitatively the best results for the given dataset. Following this step comes stemming, which reduces each token to its root if one exists. For example, the words  


One of the requirements for this model is that it needed to be easily interpreted, which restricted many of the sophisticated models currently used. This 

# Website

# conclusions