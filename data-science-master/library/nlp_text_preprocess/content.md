---
title: Text preprocessing
author: Thinkful
team: grading
time: 200 minutes
uuid: ceef06f8-7852-4109-9088-20e2b9d63246
timeHours: 3.3333333333333335
---

One of the central challenges of working with text data is that it comes in a raw form more often than not. This means that thorough preprocessing, including data cleaning, is usually required. In this checkpoint, you'll learn about the fundamental steps in preprocessing text data. Another important step, converting textual data into numerical form, will be covered in the next checkpoints.

<jupyter notebook-name="3.text_preprocessing" course-code="DSBC"></jupyter>

For a screencast demo of the techniques covered here, check out the below video.


<iframe id="kaltura_player_1604766526" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604766526&entry_id=1_s22vn5gd" width="100%" height="506" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

## Assignments

In this assignment, you'll clean up the two datasets. You'll be using these datasets in the later checkpoints of this module, and cleaning them up here will help you save time when working with these datasets.

The first dataset is a dialogue dataset called [Cornell Movie--Dialogs Corpus](http://www.cs.cornell.edu/~cristian/Cornell_Movie-Dialogs_Corpus.html). This corpus includes conversations between the characters of more than 600 movies.

The second dataset is the [Twitter US Airline Sentiment](https://www.kaggle.com/crowdflower/twitter-airline-sentiment) dataset from Kaggle. This dataset contains tweets from travelers about some airlines in February 2015. This dataset is usually used in sentiment analysis, but you'll use it for sentence generation later on.

**Note:** Because the memory requirements of the datasets are relatively large, it's best to use Google Colaboratory for this assignment.

Submit your solutions to the following tasks as a link to your Jupyter Notebook on GitHub.

1. Apply the data preprocessing techniques that you learned here to the *Cornell Movie--Dialogs Corpus* data. You'll use this dataset when developing a chatbot in an upcoming checkpoint. Access the dataset from the Thinkful database using the following credentials:

        postgres_user = 'dsbc_student'
        postgres_pw = '7*.8G9QH21'
        postgres_host = '142.93.121.174'
        postgres_port = '5432'
        postgres_db = 'cornell_movie_dialogs'

      The data is in the table called *dialogs*.

2. Apply the data preprocessing techniques that you learned here to *Twitter US Airline Sentiment* data. You'll use this dataset when generating sentences in an upcoming checkpoint. You should access the dataset from the Thinkful database using the following credentials:

        postgres_user = 'dsbc_student'
        postgres_pw = '7*.8G9QH21'
        postgres_host = '142.93.121.174'
        postgres_port = '5432'
        postgres_db = 'twitter_sentiment'

      The data is in the table called *twitter*.
        
**Note**: When parsing the data using spaCy, you may run into some memory issues, even in Google Colaboratory. If you're having memory issues, try parsing your text as follows:

```python
nlp = spacy.load('en', disable=['parser', 'ner'])
nlp.add_pipe(nlp.create_pipe('sentencizer'))
nlp.max_length = 20000000
doc = nlp(the_dialogs_come_here)
```

Submit your work below. You can also take a look at this [example solution](https://drive.google.com/file/d/10UYvnE6kPEE_wLN4LcorN5r917BMjnXL/view?usp=sharing).
