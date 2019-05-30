# Natural Language Processing - Amazon Alexa Reviews

## A. Goal
We have built a text classifier – a sentiment analysis model to predict whether the customer reviews are positive or negative. For the products/services/brands with large customer bases, it is impossible to manually glean negative reviews (or positive ones) from huge datasets.  

Using Natural Language Processing (NLP), businesses can automate the process of highlighting negative reviews and thus can effectively uncover the major gaps in their products/services; however, it is important to note that frequency of positive and negative reviews plays an important role determining the performance of the model. In our data set, positive reviews outnumbered negative ones comprehensively (Positive: 2286, Negative: 161); hence, the accuracy while predicting positive reviews was significantly superior.

## B. Data Source
https://www.kaggle.com/sid321axn/amazon-alexa-reviews

## C. Summary

_Analysis_
1. We created a column to store the text length and created boxplots of text lengths for different ratings  
a. We observed that the text length for rating 5 is smaller (excluding outliers) than those of lower ratings. This could be because people are more descriptive/vocal in negative feedbacks, but not so much in positive ones.

![](NLP_Images/.png)

2. We then also created a bar chart to know the count of the different ratings. The count of 5 star ratings was much higher than those for other ratings. Hence, our model was better at predicting the ratings for positive reviews.

3. To build our model, we have used only the 1 star and 5 star ratings.

4. We then created a function (word_list) that would remove all the punctuations and stopwords, and return a list of important words. Following is an example of how the function works.

5. We have used Count Vectorizer object to get the weights of the tokens – the number of times a token appear in a document.  
a. Following is an example of the number of unique words and their frequencies shown by the vectorizer.


This review had 39 unique words and 4 of them were repeated twice (shown by the blue pointers).

Following are the words

6. The shape of our sparse matrix is 2447 * 3986, and it has 25728 non-zero values.

7. Prediction Model – Multinomial Naive Bayes

Confusion Matrix and Classification Report


In the confusion matrix, it can be seen that the recall rate for 5 star ratings is 99%, but it is just 42% for 1 star ratings – with the overall accuracy of 96%. The performance aligns with our expectation that few instances of 1 star rating will negatively impact recall for 1 star ratings.
