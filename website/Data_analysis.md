This graph represents the average US twitter sentiment on Covid-19 in April 2020. 
Here, no surprises: we can see that, overall, the average sentiment on Covid-19 is negative, as the graph varies between -0.136 and -0.174, two negative numbers. 
Regarding the evolution of the average sentiment, we can see a clear improvement from the 1st to the 10th. Indeed, the average sentiment reaches his peak around the 10th, before a strong decrease. 
From the 12th, the average sentiment starts to stabilize itself around -0.165, although it varies between -0.152 and -0.174, showing a certain instability in the degree of negativity. 
Overall, the average sentiment becomes more negative over time. 
Main take-away from that graph: the average sentiment on Covid-19 is, of course, negative; therefore we will be working on the degree of negavity of sentiments.

In addition, the two violins plot provide some further informations about the distribution of the average sentiment.  
We can firstly see that the mean of tweet’s sentiment is -0.155, corroborating that idea that the average sentiment is, logically, negative. 
Secondly, we can also see that a large number of tweets are neutrals. This information echoes our limitations, as we couldn’t establish the positivity/negativity of jokes, pictures, etc… 
Thirdly, and finally, we can see that not all tweets are negative and that ¼ of them have an above 0 sentiment score (q3 being 0). This is a surprisingly high number, which could be interesting for further research. Furthermore, it is also interesting to see that the magnitude of tweets sentiment is very low. It means that the strength of the sentiment expressed in tweets is low. 
Main take-away from these graphs: the majority of tweets are negative and show some pretty moderated feelings. 

Regarding the number of new deaths and cases per day, it is difficult to see a clear trend. 
The number of new cases is pretty unstable, even if we can see a clear increase from the 20th to the 25th. 
Overall, the number of cases and the number of deaths both increase within the month of April. The number of new deaths is, logically, way smaller than the number of cases, as most of Covid-19 patient recovered from the disease. 
Main take-away from that graph: both the number of deaths and the number of cases increase, we can start to establish a correlation with the average sentiment.

Now that we have briefly explained the evolution of the average sentiment on Covid-19 tweets and the number of Covid-19 new cases in April 2020, let’s start the verification of our hypothesis. 
We established that there is a negative correlation between the number of new cases and the average sentiment (Pearson correlation coefficient of -0.039). 
It means that a larger number of new cases comes with a lower average sentiment. 
This is not a surprising conclusion; the spread of the disease logically comes with an increased unhappiness of the US population. 
But, interestingly, our p-value is way greater than 0.05 (0.839), meaning that there is no causal relation between the number of new cases and the average Covid-19 sentiment. 
Main take-away for that graph: there is no causal relation between the number of new cases and the average sentiment, our hypothesis is partly invalidated.  

Now, let’s compare the changes in daily new Covid-19 deaths with the average sentiment.
The correlation is, one more time, negative: a larger number of deaths comes with a worst average sentiment. However, here, the Pearson correlation number is almost 10 times stronger (-0.360 vs. -0.039) than the one of the new cases / average sentiment, indicating a stronger negative correlation. It means that a change in one of the two variables comes with a stronger opposite change in the other variable. 
Furthermore, regarding this relation, there is a causal link. It means that a change in one of the variables causes a change in the other. We know that because our P-value equals 0.05 which is the minimum number for a causality link. 
Now, we must establish the direction of this causality. What comes first? A change in the average sentiment or a change in the number of deaths? In order to answer that question, we just have to look at the graph as the answer is visual. 
Again, the result is not surprising. Changes in the number of deaths come first. It means that Covid-19 deaths clearly influence the overall tweet sentiment. 
Main take-away from that graph: This result clearly has some great implication and partly (if not fully) validates our hypothesis: there is a relationship between the severity of Covid-19 and the average twitter sentiment! 

The trends we just analyzed are the results of the US as a country. 
But we wanted to investigate the federal level, as we hoped to find some geographical trend within the US. 
But, as shown by the map, no real tendencies can be established. Almost all of the states do show a great variability in their average sentiment. 
The geographical localization of the state doesn’t seem to change anything. 
Main take-away from these visualizations:  there are no geographical trends for the repartition of the average sentiment on a federal level. 

Furthermore, the number of deaths, even if it is correlated with the average sentiment on a national basis, does not seem to be correlated with the average sentiment on a state basis. 
Indeed, the states with the larger numbers of normalized deaths do not seem to be the darker on the map. 
This could be explained by the fact that the number of deaths is reported on a national basis in the US, and that, therefore, states react to that number instead of the number of new deaths on a federal level. 
Main take-away from these visualizations: in terms of sentiments, states react to the national number of Covid-19 deaths, not the federal numbers. 
