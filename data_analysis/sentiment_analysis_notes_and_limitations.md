# Twitter Data Limitations
* The Twitter vernacular is very different from standard English, or the usual literarey texts Natural Language Processing libraries are trained on, 
and thus sentiment analysis oftern performs poorly on Twitter data (cite)
* There might be sampling bias as the population active on Twitter is not representative of everyone in a particular state: could be skewed towards a younger and more "privileged" population

# Libraries for NLP (cite)
* TextBlob: gives polarity (positive +1 to negative -1) and subjectivity, pre-trained model but not on tweets
* NLTK: can train a Naive Bayes classifier using a Twitter corpus (already in library)
* Google Cloud Platform: easy to use API of high quality, automatic language detection but may need to pay
