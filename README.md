# Project_3-Classifying-Subreddit-

In this project, we were tasked to select two subreddits and create a classification model that is able to classify each post into the correct subreddit accurately.
The objective is to improve on the model to achieve the best prediction results.

# Problem Statement

How do we correctly classify respective posts into the correct subreddit? 
Which words is used most and is related to the subreddit? 
So that users of reddit would be reading the correct posts based on the topics that they search on anytime instead of getting random posts.

# Summary of Process

First we had to scrape the posts from each subreddit using the API that is provided by reddit. From there our dataset would consist of the subreddit title(target variable), title of the posts and the actual contents of each posts.
The idea is to use NLP techniques taught to apply on text, thus using text to classify each post into their respective subreddits

My dataset had 3442 observations and 2 features. 1 of them is the target subreddits and the other is the text.

3 Models were created and the best one was selected.

# Process

After the data was collected. The title column was melted and combined with the selftext column. There were 440 null values which were pictures that were scrapped. The rows with null values were dropped.
Then the data was cleaned by removing punctuation and symbols, tokenized and stopwords removed and lemmatized as well.

First model was built using LogisticRegression. Using Count Vectorizer and TFIDF VEctorizer and putting it through a gridsearch to find the best parameters for best result for each Vectorizer, I determined that the model using Count Vectorizer has a better accuracy.

2nd and 3rd Model were built the same way as the first except I used MultiNomial Naive Bayes and Random Forest method respectively.

# Conclusion

Those 3 model were then put through the test and evaluation set of data to determine the best performing one. The result was Count Vectorizer MultiNomial Naive Bayes method is the best.
From there I tweaked the Threshold of the model to try and achieve an even split between false negative and false positive results instead of a skewed result.

Final Result : 
- Accuracy of Training Set = 0.8993824918270977
- Accuracy of Testing Set = 0.8737300435413643
