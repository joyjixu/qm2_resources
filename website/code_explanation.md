# Our code
## Github
* All our code used has been uploaded on Github in this repository: https://github.com/joyjixu/qm2_resources/
* Interactive visualizations such as the maps that were embedded in this website can be found here: https://github.com/joyjixu/qm2_graphs/

## Collecting tweets, hydration and cleaning
* From https://github.com/echen102/COVID-19-TweetIDs/tree/master/2020-04, we downloaded all tweets IDs from April 2020. Next, we installed and ran [Hydrator](https://github.com/DocNow/hydrator), an open-source software that allows us to [hydrate](https://covid.dh.miami.edu/2020/06/11/hydrating-tweetsets/) these tweets (i.e., retreiving the original text and associated information from the tweet ID)
* This is done because Twitter's Terms of Service do not allow people to share this information, only the tweets IDs
* This gives us a csv (essentially a table) of tweets for each hour of each day of April 2020, in the following format:

(Gist of csv sample)

* Then, we used Pandas, a library in Python, to clean the data: keeping only the tweets that were posted with a location attached, making sure the location was a US state and adding a column in the table with the abbreviated state name

* Below is an snippet of code showing how we kept US tweets only:
(gist of code)

* After cleaning up the dataset, here is the result:
(gist of csv)

* we can move on to perform [sentiment analysis](https://towardsdatascience.com/sentiment-analysis-concept-analysis-and-applications-6c94d6f58c17) on these tweets

## Sentiment Analysis

### Selecting a library/API
* Performing sentiment analysis on a tweet (determining how positive/negative it is) requires a Python library or an API (link to definition) - there are many that are able to do this with varying degrees of accuracy.
* Usually, they will give sentiment/polarity (positive, negative or neutral), as well as magnitude (how much emotion is in the text -higher magitude suggests more emotional text)
* We tested out three options:  [NTLK](https://www.digitalocean.com/community/tutorials/how-to-perform-sentiment-analysis-in-python-3-using-the-natural-language-toolkit-nltk) (Natural Language Toolkit), [TextBlob](https://textblob.readthedocs.io/en/dev/quickstart.html), and [Google Cloud Natural Language API](https://cloud.google.com/natural-language)
* Using the first 200 tweets from 01/04/2020, we manually labeled each with what we believed the sentiment was (positive, negative or neutral)
* We then ran each of the sentiment analysis models on these tweets and added a column for each of their results

(gist of csv)

* Then, using Python, we can calculate how accurate the results were compared to the manual labels. For example:

(gist of code to calculate accuracy)

* The final results showed that Google's API performed best, at xx accuracy, followed by xx (xx% accuracy) and xx (xx% accuracy)

### Using Google's API
* Now that we have determined that Google's model works best, we had to set up trial accounts to be able to use it (it is normally a paid service)
* Following the documentation online, we first [set up](https://cloud.google.com/natural-language/docs/setup) the API, and then used the code provided to base off our [requests for sentiment analysis](https://cloud.google.com/natural-language/docs/analyzing-sentiment)

(gist of function to perform sentiment analysis)

* This was run on all the tweets we had, which added two more columns to our original table of tweets: sentiment and magnitude

(gist of csv)

## COVID-19 Cases and Deaths
* moving on from tweet analysis, we also had to clean and 
