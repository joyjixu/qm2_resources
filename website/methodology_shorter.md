# Methodology

Our research methodology can be broken down into three distinct stages, informed by the Data Science Process, which we explored as part of our Data Science and Visualisation University Course. 
In this section we will list the Data Science and Visualisation tools we will use at each stage of the project.
The infographic provides a summary of our process. 

## Stage 1. Summary Statistics & Hypothesis Testing
The first stage of the project involved using summary statistics and visualisations to test our initial hypotheses. Informed by our literature review, our hypothesis is: 
There is a relationship between the sentiment score of tweets relating to the COVID-19 and the severity of the pandemic in April 2020.
We conduct two Pearson’s correlation coefficient tests to analyse if there was a statistically significant linear relationship between the average sentiment score for the US with (1) the total new daily cases in the US, and (2) the total new daily deaths
Plot two graphs line graphs to show the change in the daily new cases (normalised) and the average US Twitter Sentiment on COVID-related tweets for April 2020. Another uses new deaths instead of new cases.

## Stage 2. Mapping Data for States
We wanted to see how the relationship changed by state, and thus created:
An interactive choropleth map of the average sentiment score per state
A violin subplot to show the distribution of the sentiment of the tweets, revealing the overall emotion of the tweet.
Another violin subplot to display the distribution of the magnitude, revealing how emotional the tweets are

Another interactive Chloropleth map with a slider shows how daily average sentiment score changes each day of April, revealing both the spatial and temporal trends in sentiment scores.

## Stage 3. Case study states with Regulation Data
We randomly selected one Democrat and one Republican state using a ‘Python Seed’
We used a hex-bin plot to visualise how the sentiment and magnitude varied each day for both states.
An interactive line graph for the two case study states of average daily Sentiment Scores over April with the date of the regulations enforcement superimposed
Point Biserial correlation coefficient to measure the strength of association between the sentiment scores and regulation.
