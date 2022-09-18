# Hybrid Recommendation Systems using Deep Learning and Sentiment Analysis

## Introduction

Recommender systems are algorithms designed to provide
relevant item suggestions to the user. These items could be a
TV Show, Movie, E-commerce products, etc., An efficient
recommender system can give significant profits to a business.
Websites like Netflix, and Amazon are great examples, but the
use case of recommender systems doesn’t end there. When it
comes to the different types of recommender systems, they use
3 different techniques which are, Content based filtering
method, Collaborative filtering method, and finally the hybrid
systems. 

Content based recommender systems typically look
for similarities in the item content like descriptions of movies,
shopping items, etc., and recommend a similar item. Whereas
Collaborative Filtering technique uses the data related to the
past interactions of the users with the items. Now the third
category Hybrid Recommender Systems are quite unique,
because they implement a combination of different techniques for improved performance. So, in this project we try to 
experiment the hybrid recommender systems to evaluaute their performance

## Project Architecture

<img width="1162" alt="Screen Shot 2022-09-18 at 5 37 59 PM" src="https://user-images.githubusercontent.com/50517893/190901320-b122efe0-1989-417f-a579-92a47760aade.png">

## Hybrid System Design
APIs used: Keras, Vader, Tweepy, Surprise.

The experimental design involves combining the results of
movie recommendations from neural collaborative filter and sentiment analysis scores from twitter. The
sentiments will act like an extra layer to get public opinion about the movie from twitter.

For our experimental design (HYBRID), we need 3 things.
1. The movie recommendations that we got from the neural
collaborative filtering.
2. Twitter Sentiment Scores per movie (Collected
using Vader)
Example: [9,1,85] Here 9 is the positive score, 1 is the
negative score, and 85 is the neutral score.
3. Positive-Negative ratio tells us weather majority of
people like the movie or dislike the movie.
Example: From the above sample, positive-negative ratio
would be 9:1. This means more people like the movie
than people who don’t like it. So, if we recommend this
movie to our user, he will most probably like it.

If we consider another example where the positive-
negative ratio is 12:13, there are more haters than people
who like the movie, which means if we recommend this
to our user the chance of user disliking it is higher.
Higher positive-negative score is proportional to the
probability of the user liking the movie.

So, we sort the recommendations that we got from
neural collaborative filtering based on the positive-
negative ratio and recommend the top 5 movies to the
user.

Steps involved in the experimental design:

a) Collect sentiment scores for all movies.

b) Get the top 10 recommendation list using the Neural
Collaborative Filtering.

c) Now calculate the positive-negative ratio from the sentiment scores and
combine the results with recommendations list, to narrow down
the reults to a new top 5 movies list.

d) Finally we can check the accuracy using the results from recommendations using matrix factorization which is totally optional.

