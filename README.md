# Subreddit-Classification
Classifying Music Genres from Reddit Posts

## Problem Statement
 
The goal is to create a model that will be able to take a reddit post and determine whether it came from two possible subreddits: r/EDM or r/rock. These are two subreddits for discussing two distinct genres of music. The question is, how well can we distinguish between the two? While both subreddits are similar in that they both talk about music, I believe we can find enough difference in the language people use to talk about electronic music vs. rock music to be able to make a predictive model.

---

## Data Collection

A little under 2000 posts were gathered from each of the two subreddits. This was done using reddit's API. The posts for an entire day were collected going back 30 days at a time for as many days as was necessary to produce enough data. Because the amount of posts on the EDM reddit is so much greater than on the rock reddit, this meant going back over a much larger timespan for the rock data than for the EDM data so that a roughly even number of posts could be collected from both.

---

## Data Munging

Any duplicates that existed among the posts were deleted. The titles of each post were merged with the text of the post in order to have enough data to work with. Any posts that said 'removed' or 'deleted' were replaced with empty strings, as well as any posts that had null values. Links were treated in the same way, and punctuation was also removed from the end of any words that had them. Finally, lemmatization was used to account for similar words that could be thought of as the same word.

---

## Preprocessing and Modeling

Both count vectorizer and TF-DIF vectorizer were tried for this project, and the better performer between the two was actually dependent on the model used for classification. The models that were tried and compared were Logistic Regression, Naive Bayes, Random Forest, and K Nearest Neighbor. The best performing model was the Naive Bayes. Gridsearch was used with cross-validation to ensure that the best parameters were used for these models.

---

## Conclusion and Recommendations

The best models performed at close to 90% accuracy. I believe this process could be improved if more data could be collected, and if comments were also introduced into the analysis, however these are pretty decent model for predicting the majority of the posts correctly.