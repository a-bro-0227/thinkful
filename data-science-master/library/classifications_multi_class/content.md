---
title: Building and analyzing performance of multiclass classifiers
author: Thinkful
team: grading
time: 120 minutes
uuid: e002c522-e376-4a3a-b159-012d819b28b4
timeHours: 2
---

So far, you have mainly focused on binary classification, where the target to be predicted was a binary value that belonged to one of two classes. Many problems can have more than two outcomes, however. For example, the *20 newsgroups* dataset contains posts that belong to 20 different classes. In an earlier checkpoint, you used this dataset but deliberately transformed it into a binary classification problem by training your model to predict just one of the classes. At the end of this checkpoint, you will submit a Jupyter Notebook to a graded challenge focusing on multiclass classifiers.

Some classifiers, such as random forest, are capable of handling multiple classes directly. In other words, nothing special needs to be done to use them in a multiclass environment. But other classifiers, such as logistic regression, are strictly binary classifiers—so using them in a multiclass environment requires some further thought.

There are two main strategies for using a binary classifier in a multiclass environment: 

 - **One-vs-rest (OvR)**, which is also known as *one-vs-all* (OvA), involves transforming the problem into multiple binary problems.
 - **Multinomial**

In the Notebook below, you'll use the random forest classifier to build a model to predict categories for posts in the *20 newsgroups* dataset. Then you'll compare that to a binary classification using the *Breast cancer* dataset.

<jupyter notebook-name="Multiclass_Classification" course-code="DSBC"></jupyter>

For a screencast demo of the techniques covered here, check out this video.

<iframe id="kaltura_player_1604710340" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604710340&entry_id=1_bgjep7qb" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>



## Assignment

To complete this assignment, submit a link to a Jupyter Notebook containing your solutions to the tasks outlined below. A member of the Thinkful team will follow up with you shortly.

<jupyter notebook-name="multiclass_classifiers_assignment" course-code="DSBC"></jupyter>
