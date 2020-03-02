---
layout: post
title: Predicting Philosophy Authorship -- Michel Foucault vs Noam Chomsky
subtitle: Using Naive Bayes to Predict Passage Authorship
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
tags: [test]
comments: true
---

In order to search for a difference in the writing styles and topics of philosophers Michel Foucault and Noam Chomsky, who famously debated in 1971, I decided to run an NLP Project to predict the authorship of a selected passage or a famous quote by either author. The model I chose was trained on 3 full books by each author, credits to the Internet Archive for sourcing the text files for the books. I trained a Naive Bayes classifier on the 6 books (total) split into 5,725 5-sentence samples, and the model predicted the author of each sample with **98 percent accuracy**. 

## Preprocessing
Prior to the Naive Bayes, I ran a TFIDF vectorizer to count the appearances of each word in the corpus
