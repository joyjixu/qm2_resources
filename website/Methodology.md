# Methodology

Our research methodology can be broken down into three distinctive phases, informed by the Data Science Process.

## PHASE 1:  Exploratory Data Analysis

The first phase of the project involved using summary statistics and visualisations to test our initial hypotheses. The direction of our research was informed by this analysis and the summaries produced of the main characteristics.

Therefore our hypothesis is:
There is a relationship between the sentiment score of tweets relating to the COVID-19 and the severity of the pandemic in April 2020?

To test this, we used a dataset from -- , providing data on the new and total deaths and cases per state in the US.  We cleaned the data set to include only the month of April and variables we are concerned with (total deaths, new deaths, total cases and new cases). We merged this dataset with a csv containing population data for each state. Subsequently, we normalised the data such that the cases and deaths took into account the varying population size per state. 

Using this dataset, we could use some descriptive statistics to evaluate the feasibility of our hypothesis. We initially created a scatter plot of the number of deaths and cases with the sentiment score. This revealed...

## PHASE 2:  Spatial Mapping
Using the Geopandas library in python, we created an interactive choropleth map of average sentiment score per state for each day in April 2020. This enabled us to understand both the spatial and temporal trends in sentiment score across the US.

We also used the violin plot for both the sentiment score and sentiment magnitude. The former reveals the emotional leaning of the tweets across the US (whether they are positive or negative), whilst the latter indicates the overall strength of emotion in the tweets (both positive and negative).

## PHASE 3: Case study

Looking at one state in greater depth allows us to produce more meaningful analysis given the time restrictions of the project. We are able to understand how other factors beyond deaths and cases could affect sentiment score. For example state imposed regulations could affect the public sentiment. We choose the state by…[justify]. We cleaned the dataset on imposed COVID-19 regulations across states in the US such that it only included regulations of the selected state. We then mapped a timeline of the sentiment score overtime, with markers for when regulations were imposed.

