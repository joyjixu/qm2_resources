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
<script src="https://gist.github.com/joyjixu/91ad8c4178053ab03413327070f42b94.js"></script>

* Then, we used Pandas, a library in Python, to clean the data: keeping only the tweets that were posted with a location attached, making sure the location was a US state and adding a column in the table with the abbreviated state name

* Below is an snippet of code showing how we kept US tweets only:
<script src="https://gist.github.com/joyjixu/7ae0ee9f0f849de66f569922aa0720bd.js"></script>

* After cleaning up the dataset, here is the result:
<script src="https://gist.github.com/joyjixu/1176ab874c716f3749972f85d5076db6.js"></script>
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
<script src="https://gist.github.com/joyjixu/7bdf6aaf0e2d08904f91f0ffd67505a2.js"></script>

* Then, using Python, we can calculate how accurate the results were compared to the manual labels. For example:

(gist of code to calculate accuracy)
<script src="https://gist.github.com/joyjixu/f8aa8e26e9b2deffd9af340221be01e8.js"></script>

* The final results showed that Google's API performed best
* Google accuracy: 0.57
* Textblob accuracy: 0.19
* NLTK accuracy: 0.285

### Using Google's API
* Now that we have determined that Google's model works best, we had to set up trial accounts to be able to use it (it is normally a paid service)
* Following the documentation online, we first [set up](https://cloud.google.com/natural-language/docs/setup) the API, and then used the code provided to base off our [requests for sentiment analysis](https://cloud.google.com/natural-language/docs/analyzing-sentiment)

(gist of function to perform sentiment analysis)
<script src="https://gist.github.com/joyjixu/e3092b341137b47c8d8de5a919afe390.js"></script>

* This was run on all the tweets we had, which added two more columns to our original table of tweets: sentiment and magnitude

(gist of csv)
<script src="https://gist.github.com/joyjixu/08fcbf9098b8daddb85b9c7bc8765bb0.js"></script>

### Visualizations
* With this data, we can already plot some interesting visualizations of the distribution of tweet sentiment over time across the US

#### Chloropleth map slider
code below
<script src="https://gist.github.com/joyjixu/8bd2679bd3fbe5341de217d9c74574d9.js"></script>

#### Violin plot

## COVID-19 Cases and Deaths

### Data preprocessing
* moving on from tweet analysis, we also had to clean and analyze our second main dataset link: https://healthdata.gov/dataset/united-states-covid-19-cases-and-deaths-state-over-time
* After downloading the csv, we selected the data for the relevant timeframe (April 2020), and also added a column with the state abbreviation, and normalized by pop

(csv of output)
<script src="https://gist.github.com/joyjixu/212905380820699aa628b86063a2005f.js"></script>

### Some summary visualizations
* Using [matplotlib](https://matplotlib.org/) (a Python library), we could then plot some graphs which included the change in new COVID cases over time

* Plotly also enabled us to make interactive graphs of the rise in cases over time

(gist of code creating plotly graph)
<script src="https://gist.github.com/joyjixu/c5672dcf80f1f278d1c1c978f083e677.js"></script>
(embed of graph)

## Case studies
### Selecting states
* In order to narrow down our research, we selected two states in the US to examine the relationship between COVID cases/deaths, tweet sentiment and the implementation of state regulations related to COVID-19
* To do so, we randomly selected one Democrat and one Liberal state in Python, data of liberal/democrat states from https://www.bbc.com/news/election/us2020/results

(gist of state selection)
<script src="https://gist.github.com/joyjixu/bbd724e689f162886b330c63f16f4987.js"></script>

* From that, we get Utah (Republican) and Colorado (Democrat), and could select only the relevant tweets from that state


### Visualizing sentiment
* For these two particular states, we wanted to analyse how exactly both sentiment and magnitude varied over time
* We therefore used [hexbins](https://python-graph-gallery.com/84-hexbin-plot-with-matplotlib/#:~:text=A%20Hexbin%20plot%20is%20useful,denotes%20this%20number%20of%20points.) to undertsand the way the tweets were distributed
* We chose the intensity/darkness of the colour to represent the number of tweets in that category/bin
* one hexbin per day merged into a gif


(gist of hexbin creation)
<script src="https://gist.github.com/joyjixu/255ce8ff0bf34e4bd23f8c576f1a1b14.js"></script>
(gif of hexbin)

### Plotting line graphs

### Regulations
(gist of code to plot regulations data)
<script src="https://gist.github.com/joyjixu/bc865857b477ec21ee827a9cb6fc6ac6.js"></script>
