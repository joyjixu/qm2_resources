# Twitter Data Limitations
* The Twitter vernacular is very different from standard English, or the usual literarey texts Natural Language Processing libraries are trained on, 
and thus sentiment analysis oftern performs poorly on Twitter data (cite)
* There might be sampling bias as the population active on Twitter is not representative of everyone in a particular state: could be skewed towards a younger and more "privileged" population

Crampton et al.,‘Beyond the Geotag: Situating “Big Data” and Leveraging the Potential of the Geoweb’, Cartography and Geographic Information Science, 2013 Vol. 40, No. 2, 130-139 
‘A piece of information geotagged to a particular location may not necessarily have been produced in that location, be about that location, or exclude reference to any other geographic locality’. Crampton et. al, p. 132

https://arxiv.org/pdf/1306.5204.pdf
Morstatter et al., ‘Is the Sample Good Enough? Comparing Data from Twitter’s Streaming API with Twitter’s Firehose


# Libraries for NLP (cite)
* TextBlob: gives polarity (positive +1 to negative -1) and subjectivity, pre-trained model but not on tweets
* NLTK: can train a Naive Bayes classifier using a Twitter corpus (already in library)
* Google Cloud Platform: easy to use API of high quality, automatic language detection but may need to pay
