---
title: Chatbot
author: Thinkful
team: grading
time: 135 minutes
uuid: 9565e5b8-3fbc-47ce-adc7-21bf4cd2252e
timeHours: 2.25
---

> "The voice that navigated was definitely that of a machine, and yet you could tell that the machine was a woman, which hurt my mind a little. How can machines have genders? The machine also had an American accent. How can machines have nationalities? This can't be a good idea, making machines talk like real people, can it? Giving machines humanoid identities?" —Matthew Quick, *The Good Luck of Right Now*

So far in this module, you've learned how to preprocess text data, and you've learned several ways to convert text into numerical form. You've also used supervised machine-learning models to explore how you could use these numerical representations of the text data. But now, enough of text-classification examples. In this checkpoint, you'll explore another popular NLP application area: you'll build a simple chatbot.

At the start of this module, virtual assistants like Amazon's Alexa were mentioned. The interaction between humans and machines through speech and language is one of the most important focal points of artificial intelligence research, and it's also one of the oldest ones. You may have heard of the Turing test, which was proposed by Alan Turing. Turing was a famous mathematician who is widely considered the father of artificial intelligence research. The Turing test suggests a proxy for assessing the intelligence of an AI machine; a machine is said to pass the Turing test if it holds a conversation with someone, and that person cannot discern if they're interacting with a machine or a human. If you're interested in learning more about the Turing test, you can read the [Wikipedia article](https://en.wikipedia.org/wiki/Turing_test).

Although you won't learn about the speech-related parts of human-machine interactions here, you will touch upon the NLP components. In the remainder of this checkpoint, you'll build a simple chatbot that responds to your inputs. As you'll see shortly, you'll make use of the NLP techniques that you've learned so far.


<jupyter notebook-name="7.chatbot" course-code="DSBC"></jupyter>

For a screencast demo of the techniques covered here, check out the below video.

<iframe id="kaltura_player_1604711679" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604711679&entry_id=1_c0oeffc6" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

## Assignments

In this assignment, you'll work with a dataset called [Cornell Movie--Dialogs Corpus](http://www.cs.cornell.edu/~cristian/Cornell_Movie-Dialogs_Corpus.html), which was released by the Cornell University. The dataset contains conversations from more than 600 movies. Use the following credentials to access the dataset from the Thinkful database.

        postgres_user = 'dsbc_student'
        postgres_pw = '7*.8G9QH21'
        postgres_host = '142.93.121.174'
        postgres_port = '5432'
        postgres_db = 'cornell_movie_dialogs'

   The data is in the table called *dialogs*.

**Note:** It's recommended to use Google Colaboratory when working on this assignment. Submit your solutions to the following tasks as a link to your Jupyter Notebook on GitHub.

1. First, do some data preprocessing to clean up the data. You can use your solution to the assignment of the *Text preprocessing* checkpoint. 

2. Develop a chatbot using this corpus. In doing this, you're free to choose a chatbot development library like ChatterBot or write your own code from scratch.

3. Start a conversation with your chatbot, and discuss its strengths and weaknesses.

**Note:** When parsing the dialogs using spaCy, you may run into some memory issues, even in Google Colaboratory. If you're having memory issues, try parsing your text as follows:

```python
nlp = spacy.load('en', disable=['parser', 'ner'])
nlp.add_pipe(nlp.create_pipe('sentencizer'))
nlp.max_length = 20000000
doc = nlp(the_dialogs_come_here)
```

Submit your work below. You can also take a look at this [example solution](https://drive.google.com/file/d/1Juw6r5jiIFwpjc6nWDf84yvHLmtrlp1-/view?usp=sharing).
