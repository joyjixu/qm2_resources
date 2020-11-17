# Cleaning the COVID tweets dataset
* Original dataset: https://github.com/echen102/COVID-19-TweetIDs

## Summary

### Hydration
The original dataset contains the tweet IDs of all the tweets tracked per hour for each day, relating to the COVID-19 pandemic. 
The tweet IDs must first be hydrated: getting the tweet text and metadata from the tweet IDs given in the dataset.
To do this, we use an executable application called [Hydrator](https://github.com/DocNow/hydrator) and Twitter developer accounts, which returns to us a csv file of tweets.

### Preprocessing using Python
We created a Colab notebook to then clean the tweets. This includes only keeping tweets with a location attached, filtering the location so that it must contain a US state, and adding a column indicating what state the tweet is from in a standard format (state initials).
The libraries we used are Pandas, NumPy and Regex.

### Google Colab Notebook Link
* https://colab.research.google.com/drive/1aros8J5HKntPZG3UlTKTEhl7AuKhBLNm?usp=sharing
* A copy of the notebook is also included in this folder
