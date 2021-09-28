---
title: Text generation
author: Thinkful
team: grading
time: 120 minutes
uuid: 89a1cf36-2b47-4286-b943-9522168ead4d
timeHours: 2
---

> "We can't have, like, willy-nilly proliferation of fake news. That's crazy. You can't have more types of fake news than real news. That's allowing public deception to go unchecked. That's crazy." —[Elon Musk](https://www.cbsnews.com/news/elon-musk-tesla-model-3-problems-interview-today-2018-04-11/)

<jupyter notebook-name="8.text_generation" course-code="DSBC"></jupyter>

For a screencast demo of the techniques covered here, check out the below video.

<iframe id="kaltura_player_1604711623" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604711623&entry_id=1_3mzv9jfj" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>


## Assignments

In the following assignments, you'll use [Twitter US Airline Sentiment](https://www.kaggle.com/crowdflower/twitter-airline-sentiment) data. Access the dataset from the Thinkful database using the following credentials:

        postgres_user = 'dsbc_student'
        postgres_pw = '7*.8G9QH21'
        postgres_host = '142.93.121.174'
        postgres_port = '5432'
        postgres_db = 'twitter_sentiment'

   The data is in the table called *twitter*.

**Note:** It's recommended to use Google Colaboratory to work on this assignment. Submit your solutions to the following tasks as a link to your Jupyter Notebook on GitHub.

1. First, do some data preprocessing to clean up the data as necessary. You can use your solution to the assignment of the *Text preprocessing* checkpoint.
2. Train a Markov chain model by using only the negative sentiment tweets. Generate some random sentences. Do the generated sentences exhibit the same negative sentiment?
3. Repeat the previous task, but this time, use only the positive sentiment tweets. Generate some random sentences and observe whether they exhibit positive sentiment or not.
4. Now, train your Markov chain model using all of the tweets. Generate some random sentences. Can you say something systematic about the sentiments of the generated tweets?

Submit your work below. You can also take a look at this [example solution](https://drive.google.com/file/d/1AlcF8fXZ7d-LBI41FQr8o5RrbAnlOqtL/view?usp=sharing).
