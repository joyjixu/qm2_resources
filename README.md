# qm2_resources
Resources for QM2 2020 Project

## Contents of repository

### data_preprocessing
* includes information on how we cleaned our datasets to be able to perform analysis on them afterwards
* notebook on cleaning tweets after hydration: cleaning_tweets/clean_tweets.ipynb
* notebook to select relevant information on covid cases and deaths in the US for April 2020 from the raw dataset: clean_covid_cases_deaths_population_new_dataset.ipynb

### data_analysis
* notebooks on sentiment analysis using Google Natural Language API: get_tweet_sentiment.ipynb
* notebook for plotting and calculating correlation between twitter sentiment & deaths/cases: correlation.ipynb
* notebook to plot violin graphs with plotly: month_violin.ipynb (daily_violin.ipynb was a preliminary test using a day's worth of tweets)
* notebook to plot month average sentiment chloropleth with plotly: month_chloropleth.ipynb (no slider)
* code for summary stats on covid cases and deaths
* folder: covid_stats (notebooks to plot preliminary graphs on covid deaths and cases)
* folder: case_studies (notebooks to plot regulation data & hexbins for Utah and Colorado, and to randomly select states)
* folder: select_nlp_lib (notebooks to determine what methods to use for sentiment analysis, & manually labeled sample tweets)

### website
* content and written analysis to be added on our project website
* https://joyxuuni.wixsite.com/sentco

### datasets
* links to our main datasets used in large_dataset_links.md
* smaller datasets used for additional analysis (for example US population by state)

### data_visualization
* pngs of graphs created using the notebooks in data_analysis

### group_presentation
* script and info on first group presentation

# qm2_graphs
* html embeddings for the visualizations are available in a separate repo which is a github page to be able to link to website
* https://github.com/joyjixu/qm2_graphs
