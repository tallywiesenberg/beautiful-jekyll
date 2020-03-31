---
layout: post
title: Spotify Song Recommender
subtitle: A Song Recommender Web App with Nearest Neighbors
gh-repo: spotify-song-suggester-1/DS-API
gh-badge: [star, fork, follow]
tags: [keras, nearest-neighbors, spotify-api]
comments: true
---

[Click here for interactive streamlit app](https://spotify-recommender-streamlit.herokuapp.com/)

## Main Objective: Spotify Recommendation Engine
The main idea behind this project was to create a web application that recommends music based on a given song. Such an application is a simulation of a common business problem, which is recommending a product to a customer. In the next section, I will explain how my team and I solved this business problem in this particular use case. 

### Spotify API
My team and I accessed the Spotify API through a Python library called Spotipy. With Spotipy, we queried 160,000 songs and their attributes (acousticness, danceability, energy, instrumentalness, key, liveness, loudness, mode, speechiness, time signature, and valence -- note: these are measured by Spotify). Using this database, we trained a Nearest Neighbors model to return the most similar song from our database based on song attributes. On the front end, we displayed visualizations of a given recommended song's attributes and the percent difference of each attribute vs the original song.
