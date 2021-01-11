### Where did we collect the our data from?
To collect Tweets relating to COVID-19, we decided to use a dataset on github containing the Tweet-IDs, and instead focus our time on the analysis. At first, we were going to gather tweets ourselves using the API, but realised that we would miss a lot of covid-related tweets as our self-made covid dictionary is not extensive and would inevitably miss covid-related tweets. Furthermore, because we cannot retrieve historical tweets, only ones that are posted while the API is receiving requests could be collected. This means we would have been unable to analyse tweets from earlier in the year. 

The other two main datasets were easy to find, with one including data on the different regulations that were imposed in states across the US, and the other containing the daily COVID-19 cases and deaths per state. We sourced a data set containing population estimates for the US in April 2020.

### Why did we choose the USA and April 2020?
We selected the US rather than looking at a global scale as this provides more relevant information that is contextualised. Given the time restrictions and scope of our research, we focused on the month of April, as this is long enough to see the temporal distribution of data. April is also the month that coincided with the first peak of the virus (citation), and significant regulations were imposed across the state (), as demonstrated through our data sets. 
Why did we look at one democrat and one Republican case study?

In order to narrow down our research, we selected two states in the US to examine the relationship between COVID cases/deaths, tweet sentiment and the implementation of state regulations related to COVID-19, understanding the effect of factors beyond deaths and cases could affect sentiment score. 
The pandemic was also highly politicised (find article) and so we decided to look at one Democrat and one Republican state.Any distinction between these two states could be potentially indicative of the influence of political discourse on the public perception of COVID-19, upon which we could recommend further research. 

### How did we choose our case study states using python?
So that our results are reproducible, we randomly selected one Democrat and one Liberal state in Python:

 data of liberal/democrat states from https://www.bbc.com/news/election/us2020/results

(gist of state selection)
<script src="https://gist.github.com/joyjixu/bbd724e689f162886b330c63f16f4987.js"></script>


From that, we get Utah (Republican) and Colorado (Democrat), and could select only the relevant tweets from that state


### What is Tweet Hydration?
From https://github.com/echen102/COVID-19-TweetIDs/tree/master/2020-04, we downloaded all tweets IDs from April 2020.

 Next, we installed and ran Hydrator (https://github.com/DocNow/hydrator) , an open-source software that allows us to hydrate (https://covid.dh.miami.edu/2020/06/11/hydrating-tweetsets/) these tweets (i.e. retrieving the original text and associated information from the tweet ID). This is done because Twitter's Terms of Service do not allow people to share this information, only the tweets IDs

This gives us a csv (essentially a table) of tweets for each hour of each day of April 2020, in the following format:

(Gist of csv sample)
<script src="https://gist.github.com/joyjixu/91ad8c4178053ab03413327070f42b94.js"></script>

### How did we clean Tweets by location?

Then, we used Pandas, a library in Python, to clean the data: keeping only the tweets that were posted with a location attached, making sure the location was a US state and adding a column in the table with the abbreviated state name

Below is an snippet of code showing how we kept US tweets only:

<script src="https://gist.github.com/joyjixu/7ae0ee9f0f849de66f569922aa0720bd.js"></script>

After cleaning up the dataset, here is the result: (gist of csv)
<script src="https://gist.github.com/joyjixu/1176ab874c716f3749972f85d5076db6.js"></script>

we can move on to perform sentiment analysis (https://towardsdatascience.com/sentiment-analysis-concept-analysis-and-applications-6c94d6f58c17) on these tweets
How did we clean the dataset on COVID-19 deaths and cases?
Moving on from tweet analysis, we also had to clean and analyze our second main dataset link: https://healthdata.gov/dataset/united-states-covid-19-cases-and-deaths-state-over-time

After downloading the csv, we selected the data for the relevant timeframe (April 2020. We cleaned the data set on deaths and cases by creating a python notebook, extracting daily data of new deaths, total deaths, new cases and total cases. 

The .csv file with population per state was merged, and we subsequently normalised the data by dividing the total and new deaths and cases by population. 

We also added a column with the state abbreviation
(csv of output)
<script src="https://gist.github.com/joyjixu/212905380820699aa628b86063a2005f.js"></script>
Where did we get the data on state-imposed regulations for the case study states?
The regulation data was relevant for our two case study states was downloaded from the online data set which allowed us to filter the results.

### What are the limitations of poor internet connection? 
A lot of the computational work required a stable and suitable internet connection, especially when doing sentiment analysis and hydrating the tweets. Not all of us had adequate speed so work had to be redistributed to account for that, with the people with better internet doing more of the hydration/sentiment analysis. 
What is sentiment analysis?
Performing sentiment analysis on a tweet (determining how positive/negative it is) requires a Python library or an API (link to definition). There are many libraries that are able to do this with varying degrees of accuracy. Usually, they will give sentiment/polarity (positive, negative or neutral), as well as magnitude 
(how much emotion is in the text -higher magnitude suggests more emotional text).

### How did we choose our method of sentiment analysis?
To choose the most accurate model, we conducted a test on 200 sample tweets out three options: NTLK (https://www.digitalocean.com/community/tutorials/how-to-perform-sentiment-analysis-in-python-3-using-the-natural-language-toolkit-nltk) (Natural Language Toolkit), TextBlob (https://textblob.readthedocs.io/en/dev/quickstart.html) , and Google Cloud Natural Language API.(https://cloud.google.com/natural-language) 

The tweets, selected from data on 01/04/2020, were manually labeled each with what we believed the sentiment was (positive, negative or neutral).

We then ran each of the sentiment analysis models on these tweets and added a column for each of their results.
(gist of csv)
<script src="https://gist.github.com/joyjixu/7bdf6aaf0e2d08904f91f0ffd67505a2.js"></script>

Then, using Python, we can calculate how accurate the results were compared to the manual labels. For example:
(gist of code to calculate accuracy)
<script src="https://gist.github.com/joyjixu/f8aa8e26e9b2deffd9af340221be01e8.js"></script>

* The final results showed that Google's API performed best
* Google accuracy: 0.57
* Textblob accuracy: 0.19
* NLTK accuracy: 0.285


### How do you use Google's API?
Now that we determined that Google's model works best, we had to set up trial accounts to be able to use it (it is normally a paid service). This does however reduce the reproducibility of the results, but we decided it was important to select the most accurate model based on our researcher trial.
Following the documentation online, we first [set up](https://cloud.google.com/natural-language/docs/setup) the API, and then used the code provided to base off our [requests for sentiment analysis](https://cloud.google.com/natural-language/docs/analyzing-sentiment) 

(gist of function to perform sentiment analysis)
<script src="https://gist.github.com/joyjixu/e3092b341137b47c8d8de5a919afe390.js"></script>
 
This was run on all the tweets we had, which added two more columns to our original table of tweets: sentiment and magnitude
 
(gist of csv)
<script src="https://gist.github.com/joyjixu/08fcbf9098b8daddb85b9c7bc8765bb0.js"></script>
 
More info on interpreting sentiment and magnitude can be found here: https://cloud.google.com/natural-language/docs/basics#interpreting_sentiment_analysis_values 

What are the limitations of using Google’s API for sentiment analysis? 

When using the API, there was a break in internet connection at times, and the cells were interrupted when they were running. This meant work was lost and we had to try to run the sentiment analysis again. This was an issue because we had limited credit to use on our free trial accounts.  Thus, we transitioned to visual studio code which is a software that provides an interface for coding similar to colab and supports jupyter notebooks, but does not require internet connection as it runs locally. It also saves files directly to the computer and has more features such as linting (automatically flags syntax mistakes), and integration with github

Furthermore, if the cell was run twice all variables were overwritten so the process had to be redone. This was solved by adding a line at the end of the cell which saved the temporary data frame in case the cell was rerun. 

## Visualisations & Analysis
 
### Why did we use a chloropleth map for sentiment score per state?
We wanted to see how the relationship changed by state and thus used the Plotly library in python to create an interactive choropleth map of the average sentiment score per state. 
How did we create an interactive chloropleth map?
Another interactive Chloropleth map with a slider allows the user to engage with the visualisation and see how daily average sentiment score changes each day of April, revealing both the spatial and temporal trends in sentiment scores.
<script src="https://gist.github.com/joyjixu/8bd2679bd3fbe5341de217d9c74574d9.js"></script>
Why did we use a violin plot to show magnitude and sentiment of tweets?
Two violin subplots display the distribution of the magnitude and sentiment of the tweets. The former reveals the emotional leaning of the tweets across the US (whether they are positive or negative), whilst the latter indicates the overall strength of emotion in the tweets (both positive and negative).
 
### How did we analyse the relationship between sentiment scores and COVID-19 deaths and cases?
We produced two line graphs, one mapping how the total new daily cases in the US, and the other the total new daily deaths, varied with the average sentiment score for the USA. We used the Pearson Correlation Coefficient to analyse if there was a statistically significant linear relationship and .as our two variables (cases and sentiment) are quantitative.

### What is a hex-bin plot and why did we choose it?
We used a hex-bin (add definition) plot to visualise how the sentiment and magnitude varied each day for both states over time. This was useful for visualising our large data set where other visualisations may be difficult to understand due to overplotting and demonstrated the way the tweets were distributed. 
We chose the intensity/darkness of the colour to represent the number of tweets in that category/bin. 
How did we create a hex-bin to visualise sentiment scores? (Case study)
Estate had one hexbin per day which we merged into a gif. 
(gist of hexbin creation)
<script src="https://gist.github.com/joyjixu/255ce8ff0bf34e4bd23f8c576f1a1b14.js"></script>
(gif of hexbin)
How did we analyse the relationship between the sentiment score of tweets and state-imposed regulation?
An interactive line graph of average daily Sentiment Scores for Utah (Republican state) and Colorado (Democrat State) in April 2020 were plotted against time, with the date of the regulations enforcement superimposed. The user can engage with the map to see details of the regulation including the length and date of announcement. 
how did we create one to visualise sentiment scores?
We conducted a Point Biserial correlation coefficient to measure the strength of association between the sentiment scores and regulation.
(gist of code to plot regulations data)
<script src="https://gist.github.com/joyjixu/bc865857b477ec21ee827a9cb6fc6ac6.js"></script>

