Slide 1: Joy (Introduction)
Hi everyone, today we are presenting our research proposal, looking at the reality of covid 19 in terms of total deaths vs the perception of the virus on Twitter, using sentiment analysis

Slide 2: Salomé (Sentiment analysis definition: the process of computationally identifying and categorizing opinions expressed in a piece of text, especially in order to determine whether the writer's attitude towards a particular topic, product, etc. is positive, negative, or neutral)
First, we are gonna look at the existing literature and define what sentimental analysis is. this will help us place our research in the wider context.
Sentimental analysis consists of categorising opinions expressed by people in their tweets. In this case sentimental analysis would be positive, negative or neutral. 
We will then be able to visualize it on interactvive maps to engage users.

Slide 2-5: Safiyah (Literature Review)
There are few articles looking at the sentiment analysis of tweets relating to COVID-19.
One example was conducted over one week in March on a global scale, using two hashtags #COVID-19 and #Coronavirus.

This is another graph [next slide] showing how external factors, such as announcements of lockdowns such as in Italy and first reported deaths causes rises in the number of related tweets, showing that the reality of COVID-19 had some relationship with the online sentiment.

[next slide] Our study aims to build on this research to both fill knowledge gaps and add to the existing stock of knowledge. 
Our research question asks “What is the relationship between the sentiment score of tweets relating to the COVID-19 across states in the US and its severity (measured in this case by total deaths) in April 2020?”
Our specific aims are to Understand whether, and the extent to which, the positivity and negativity of tweets is influenced by, or independent of, reality.
we specifically aim to understand: a) the relationship between total deaths and the sentiment scores of tweets, as well as b) the relationship between imposed COVID-19 state regulations and the sentiment scores of tweets. 
We have outlined the following objectives to help achieve this aim, involving data processing, analysis and visualisations
First, we will pre-process and perform sentiment analysis on tweets collected from the dataset in order to obtain sentiment scores
We will then analyse the correlation between the daily change in the number of total COVID-19 deaths and sentiment scores of the tweets over the month of April
Finally, we will analyse the relationship between the implementation of COVID-19 regulations by one state, and the sentiment scores of tweets for that state

Slide 7: Macrina (Applications of our research)
There are a lot of useful applications of this research. It is important as the perception analysis of Tweets can inform us about public perception of COVID-19 & how reactions may be linked to, or differ from, regulations and the reality of cases and deaths.
Futhermore there are useful applications for Public policy in the future if there are further waves or other possible pandemics.
There are also further implications for adding to the interdisciplinary research in cyberpsychology, such as understanding how and whether the democratisation of digital technologies affects our perceptions of reality.

Slide 8-11: Joy (Data Analysis)
Now we will move on to the data analysis - We are going to use three main datasets outlined below.
In order to process the data we will do the following:
1. Hydrating tweets: the dataset on covid tweets consists of lists of tweet ids, rather than the tweet itself. We will be using an executable application called hydrator, to hydrate these tweets ids. This means using twitter’s API's to fetch the tweet text and metadata (location etc) from the tweet id, returning to us a csv of tweets
2. Cleaning up: most tweets do not have location attached, so we will need to discard them. We also only keep the tweets which has a us state as a location. We use google colab notebooks and pandas to do this
3. Sentiment analysis: determining how positive, negative or neutral a tweet is. Natural language tool kit NLTK and textblob are python libraries that may be used
In depth analysis: seeing how twitter sentiment is influenced by deaths

Slide 12-15: Joy (Visualizations)
Visualisations are crucial to demonstrate our narrative. We will use libraries such as Folium and plotly.
First, to gain an overview of all states we will use a line chart tracking COVID-19 deaths and tweet sentiment against days in April allows us to understand if there is a correlation. We will normalise the data to account for the difference in scales.
We will use a heatmap to show the sentiment (averaged) per state.
For the individual case study we will also be looking at how polarised the tweets are

Slide 16-17: Safiyah (Visualizations)
For the specific case study state, we will use a drop down to allow users to interact with the map and seen one day of average sentiment scores
We will also use a timeline (shown on the right) of the variation in Twitter sentiment over a month with markers for when regulations were set to understand if theres a correlation with the sentiment score
 
Slide 18: Noé (limitations)
Regarding the limitations, several points must be considered.
Firstly, many different things could bias the sentiment analysis. Take ironic tweets for example, or jokes, is it negative, positive, neutral. Furthermore the majority of sentiment analysis models aren’t that accurate for tweets as it’s a challenging field. 
Secondly, and fourth limitations, there are over 40 million native Spanish speakers in the US. That’s 12% of the overall population so we’re going to miss tweets because of the translation process, especially for the border’s regions such as New-Mexico or Texas.
Thirsly, the API only allows us to process a small number of tweets, therefore we might face a sample bias.
As a fifth limitation, several tweets will not be considered: we cannot consider some tweets with spellings problems, some tweets simply deal with Covid without explicitly mentioning it.
Futhermore, location is a very important part of our project and we must also acknowledge that some people do not turn their location on, so we’re going to miss some more tweets. 
Finally, we’re not taking into account the sentiments linked to emojis which are, of course, way too subjective. 

Slide 18-22: Macrina (Web Design)
Here is an example of what our website will look like. We will have interactive maps and include our liscenes and limitations of our research.

Slide 23: salomé (Project timeline)
Here is our expected timeline for the project. the main stages are hydrating tweets, followed by analysing the sentiment (tone) using a python library, which can either be positive or negative. We will then analyse the data linked with covid total death and state regulations. Finally, we will visualise the data and publish our results in a designed website. Each stage of the research requires a specific amount of time so timeline will help us: indicating us deadlines for the different steps in order to finalise our website and research according to the deadline.

Slide 24: salomé (Meet the Team)
Now we will introduce our team and responsibilities
I will be responsible for context and analysis. 

Hi, i'm Safiyah, i'm responsible for Research, context & web design.

Hi i'm Joy, i'm responsible for Data analysis and visualisation.

Hi i'm Noe, i'm responsible for visualisation.

Hi, i'm Macrina, i'm responsible for web design.

[Next slide]
Here are the sources for our data, academic papers, and graphs.

Thank you! Let us know if you have any questions.
