# Folder contents
### analyzing_covid_tweets_test.ipynb
Initial graphs generated using the matplotlib library

### get_tweet_sentiment.ipynb
Notebook for Sentiment Analysis with Google Cloud Natural Language API

### make_chloropleth_slider.ipynb
Notebook to maje visualization of chlrorpleth map with average sentiment and slider for days

### month_violin.ipynb
Notebook to make vioin distributions of sentiment and magnitude for all of April (daily_violin.ipynb was a preliminary test using a day's worth of tweets)

### get_tweet_sentiment.ipynb
Notebook for Sentiment Analysis with Google Cloud Natural Language API

### correlation.ipynb
Notebook to plot sentiment and covid deaths over time, and to find Pearson's correlation

### average_sentiment.ipynb
Notebook to aggregate individual tweet sentiment and magnitude as averages

### get_tweet_sentiment.ipynb
Notebook for Sentiment Analysis with Google Cloud Natural Language API

### month_chloropleth.ipynb
Notebook to plot month average sentiment chloropleth with plotly (no slider)

### sentiment_stats.ipynb and sentiment_stats_plotly.ipynb
Notebooks to plot initial exploratory graphs/plots on sentiment

## Folder: select_nlp_lib

### nlp_samples_unlabeled.csv
Contains 200 tweets with the respective sentiment score from three libraries: textblob, NLTK, and Google, without researcher labels.

### nlp_samples_labeled.csv
We have conducted our own study of 200 tweets to understand which notebook is best to use for sentiment analysis and the justification of our choice. The tweets are the same first 200 tweets of 01/04/2020 for all three libraries. We added a 'researcher label' with the researchers subjective opinion of the sentiment of the tweet. This was then compared to the sentiment scores given by the three notebooks (textblob, NLTK, and Google) to see which notebook provided a sentiment score most similar to the researcher label. The calculation of accuracy is done in check_nlp_accuracy.ipynb.

### check_nlp_accuracy.ipynb
This notebook formats the nlp_samples_labeled.csv and performs some calculations to determine sentiment accuracy on the sample. Google performs the best at 57% accuracy.
