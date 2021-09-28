---
title: Feature engineering I
author: Thinkful
team: grading
time: 180 minutes
uuid: 1179fe39-ed2e-403a-b1d1-6955370c2974
timeHours: 3
---

In the previous checkpoint, you went over the steps to clean your dataset and preprocess your data. But one essential problem remains to be solved. Think about the machine-learning models that you learned about throughout this program. The inputs that you feed into these models during training and testing are all numerical. That is because all machine-learning algorithms work with numerical data. But how can you build machine-learning models using text data?

<jupyter notebook-name="4.feature_engineering_1" course-code="DSBC"></jupyter>

For a screencast demo of the techniques covered here, check out the below video.


<iframe id="kaltura_player_1604766583" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604766583&entry_id=1_cbsx0zac" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

## Assignments

Submit your solutions to the following tasks as a link to your Jupyter Notebook on GitHub.

1. Your task is to increase the performance of the models that you implemented in the bank-of-words example. Here are some suggested avenues of investigation:

    * Other modeling techniques and models
    * Making more features that take advantage of the spaCy information, such as grammar, phrases, parts of speech, and so forth
    * Making sentence-level features, such as the number of words and amount of punctuation
    * Including contextual information, such as the length of previous and next sentences, words repeated from one sentence to the next, and so on
    * Or anything else that your heart desires
    
    Compare your models' performances with those of the example. 
    
2. In the 2-gram example above, you only used 2-gram as your features. This time, use both 1-gram and 2-gram features together as your feature set. Run the same models as in the example and compare the results.

Submit your work below. You can also take a look at this [example solution](https://drive.google.com/file/d/1oKw1Rq-cmCsZID5AbfSv9f6K92NLL5fo/view?usp=sharing).
