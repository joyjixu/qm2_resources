# Our code
## Github
* All our code used has been uploaded on Github in this repository: https://github.com/joyjixu/qm2_resources/
* They can be run directly online as they are jupyter notebooks, provided that you have the correct files uploaded
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

### Visualizations
* With this data, we can already plot some interesting visualizations of the distribution of tweet sentiment over time across the US

#### Chloropleth map slider

#### Violin plot

## COVID-19 Cases and Deaths

### Data preprocessing
* moving on from tweet analysis, we also had to clean and analyze our second main dataset link: https://healthdata.gov/dataset/united-states-covid-19-cases-and-deaths-state-over-time
* After downloading the csv, we selected the data for the relevant timeframe (April 2020), and also added a column with the state abbreviation

(gist of code to clean)
(csv of output)

### Some summary visualizations
* Using [matplotlib](https://matplotlib.org/) (a Python library), we could then plot some graphs which included the change in new COVID cases over time, for example

(gist of plotting)
(image of plot)

* Plotly also enabled us to make interactive graphs of the rise in cases over time

(gist of code creating plotly graph)
(embed of graph)

## Case studies
### Selecting states
* In order to narrow down our research, we selected two states in the US to examine the relationship between COVID cases/deaths, tweet sentiment and the implementation of state regulations related to COVID-19
* To do so, we randomly selected one Democrat and one Liberal state in Python:

(gist of state selection)

* From that, we get Utah (Republican) and Colorado (Democrat), and could select only the relevant tweets from that state
* For example, for Colorado
(gist of selecting state)
(csv of state sentiment)
(csv of state cases)

### Visualizing sentiment
* For these two particular states, we wanted to analyse how exactly both sentiment and magnitude varied over time
* We therefore used [hexbins](https://python-graph-gallery.com/84-hexbin-plot-with-matplotlib/#:~:text=A%20Hexbin%20plot%20is%20useful,denotes%20this%20number%20of%20points.) to undertsand the way the tweets were distributed
* We chose the intensity/darkness of the colour to represent the number of tweets in that category/bin

(gist of hexbin creation)
(gif of hexbin)

### Plotting line graphs

### Regulations
