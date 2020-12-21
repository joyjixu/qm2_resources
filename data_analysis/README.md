# Folder contents
### analyzing_covid_tweets_test.ipynb
Initial graphs generated using the matplotlib library

### get_tweet_sentiment.ipynb
Notebook for Sentiment Analysis with Google Cloud Natural Language API

### sentiment_analysis_notes_and_limitations.md
Initial research of limitations of the libraries and sentiment analysis approaches in data analysis. This will be added to our methodology and literature reviews.

## select_nlp_lib folder

### nlp_samples_unlabeled.csv
Contains 200 tweets with the respective sentiment score from three libraries: textblob, NLTK, and Google, without researcher labels.

### nlp_samples_labeled.csv
We have conducted our own study of 200 tweets to understand which notebook is best to use for sentiment analysis and the justification of our choice. The tweets are the same first 200 tweets of 01/04/2020 for all three libraries. We added a 'researcher label' with the researchers subjective opinion of the sentiment of the tweet. This was then compared to the sentiment scores given by the three notebooks (textblob, NLTK, and Google) to see which notebook provided a sentiment score most similar to the researcher label. The calculation of accuracy is done in check_nlp_accuracy.ipynb.

### check_nlp_accuracy.ipynb
This notebook formats the nlp_samples_labeled.csv and performs some calculations to determine sentiment accuracy on the sample. Google performs the best at 57% accuracy.
