---
title: Feature engineering II
author: Thinkful
team: grading
time: 180 minutes
uuid: ec63c477-5f3a-477c-8eb6-3e97f638c592
timeHours: 3
---

In the previous checkpoint, you saw that n-gram models, which you can use to create numerical features from the text data, count the occurrences of single words or word couples. As highlighted before, converting text into numerical form is crucial because machine-learning models can only work on numerical data. And although the bag-of-words (BoW) approach is easy to implement, it does have some drawbacks. One of those drawbacks is that BoW doesn't take into consideration the meaning (or semantics) of the words at all. However, you know that language exists to convey meaning!

In this checkpoint, you'll explore another popular approach in language modeling: *TF-IDF*. With this approach, you'll start to take into account the meanings of the words as well as their numbers of occurrences. You can consider TF-IDF as a modification of the plain BoW approach. You'll also see two applications of TF-IDF toward the end of the checkpoint. In the next checkpoint, you'll see another way of modeling the language—one that is dramatically different from the BoW and TF-IDF methods.

<jupyter notebook-name="5.feature_engineering_2" course-code="DSBC"></jupyter>

For a screencast demo of the techniques presented here, check out the below video.

<iframe id="kaltura_player_1604712035" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604712035&entry_id=1_347tvqo4" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>


## Assignments

Please submit your solutions to the following tasks as a link to your Jupyter Notebook on GitHub.

1. Converting words or sentences into numeric vectors is fundamental when working with text data. To make sure that you have a solid handle on how these vectors work, generate the TF-IDF vectors for the last three sentences of the example from the beginning of this checkpoint (from the *BoW revisited: TF-IDF* section).

2. In the 2-grams example above, you only used 2-grams as your features. This time, use both 1-grams and 2-grams together as your feature set. Run the same models as in the example and compare the results.

Submit your work below. You can also take a look at this [example solution](https://drive.google.com/file/d/1lSzF8xlJS2k3ZSnGLv2CRcZ3jcrYIDjR/view?usp=sharing).
