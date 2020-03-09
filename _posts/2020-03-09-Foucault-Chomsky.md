---
layout: post
title: Predicting Philosophy Authorship -- Michel Foucault vs Noam Chomsky
subtitle: Predict Passage Author / Find Similar Passage from Corpus of Books
gh-repo: tallywiesenberg/Predict-the-Philosopher
gh-badge: [star, fork, follow]
tags: [nlp, naive-bayes, philosophy, nearest-neighbors]
comments: true
---

[Interactive app](https://philosophy-authorship.herokuapp.com/)

## Main Objective: Authorship Prediction
In order to search for a difference in the writing styles and topics of philosophers Michel Foucault and Noam Chomsky, who famously debated in 1971, I decided to run an NLP Project to predict the authorship of a selected passage or a famous quote by either author. The model I chose was trained on 3 full books by each author, credits to the Internet Archive for sourcing the text files for the books. I trained a Naive Bayes classifier on the 6 books (total) split into 5,725 5-sentence samples, and the model predicted the author of each sample with **98 percent accuracy**. 

## Preprocessing
Prior to the Naive Bayes, I first tokenized each word using gensim's thorough *preprocess_string* method, which eliminates stop words, numerics, and symbols, among other tasks. Then, I ran a TFIDF vectorizer to count the appearances of each word in the corpus relative to the length of the document. Finally, I added a Random UnderSampler from the imbalanced-learn library to ensure that the model wouldn't be biased towards one author or the other in deployment.

## Second Objective: Locate Similar Passages
The second objective of this project was to locate the most similar passage from the 6-book selection given any text sample. The model uses a NearestNeighbors algorithm to return the most similar 5-sentence sample from the 6-book collection. I based the similarity of passages on the Euclidean distance between two 2-dimensional vectors, one representing the input text and the other representing the most similar passage. I converted text samples into 2-dimensional vectors using spacy's word2vec pre-trained model, with 2-dimensional PCA applied.