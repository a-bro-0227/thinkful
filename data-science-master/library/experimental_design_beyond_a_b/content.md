---
title: Beyond A/B tests
author: Thinkful
team: grading
time: 180 minutes
uuid: 90da4981-c1ec-4bbd-ab57-c03f5c1102f1
timeHours: 3
---

In the previous checkpoints, you have been comparing the means of two groups at a single point in time using a t-test. A t-test requires normality, which you have been testing for using visualizations and descriptive statistics.

This checkpoint serves as a brief introduction to the inferential statistics that you can use in other scenarios. What if a sample isn't normally distributed? What if there are more than two groups of interest? How can you test normality using inferential statistics rather than descriptive statistics?

There's a whole world of statistical methods outside of t-tests. Welcome to the party!

<jupyter notebook-name="checkpoint_4_beyond_a_b_testing" course-code="DSBC"></jupyter>

As a data scientist, you will be working with data that is distributed in all sorts of ways, both parametrically and nonparametrically. These approaches use classical inferential statistics to evaluate differences across two or more groups. Inferential statistics uses explicit rule-based logic to test hypotheses about data.

Consider how this compares to machine-learning methods, which aren't rule based, but on the flip side, can't test hypotheses as easily. Many of these machine-learning techniques are computationally intensive in ways that would have been impossible just a few years ago, and there has been some cross-seeding between traditional statistical and machine-learning approaches.

Regardless, no amount of computing power can make up for uninteresting research questions and inadequate experiment designs. Computer science even has a saying that sums this up: "Garbage in, garbage out."

In the next module, you will present the results of an experiment using inferential statistics.

## Parametric versus nonparametric tests

Check out the below video for an overview of parametric versus nonparametric tests.

<iframe id="kaltura_player_1604699946" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604699946&entry_id=1_frfqarbu" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

Check out the below video for a screencast demo of the topics covered here.

**Video correction:** Note that `versicolor` is identified as the "odd" group at 6:36 and 7:35. This is incorrect; as shown in the Notebook, the "odd" group is actually `setosa`.

<iframe id="kaltura_player_1604705871" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604705871&entry_id=1_ui5z64tt" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>


## Assignment

Below are the questions for two real-life social science datasets. For each question, explain why you chose the approach that you did. Keep track of your code and results in a Jupyter Notebook or another source that you can share. 

### European social survey

This is a biannual survey to measure the attitudes, beliefs, and behavior patterns of the various populations in Europe. Using selected questions from the 2012 and 2014 editions, address the following questions. Here is the data [file](https://tf-assets-prod.s3.amazonaws.com/tf-curric/data-science/ess_combined_2012_2014.csv), and here is the [codebook](https://thinkful-ed.github.io/data-201-resources/ESS_practice_data/ESS_codebook.html) with information about the variable coding and content.

**Note:** The field *idno* shouldn't be taken as a unique identifier.

1. Did people become less trusting from 2012 to 2014?
2. Did people become happier from 2012 to 2014? 
3. Pick three or four of the countries in the sample and compare how often people met socially in 2014. Are there differences, and if so, which countries stand out?
4. Pick three or four of the countries in the sample and compare how often people took part in social activities, relative to others their age, in 2014. Are there differences, and if so, which countries stand out?

### Ruff figural fluency test

[This test](https://www.parinc.com/Products/Pkey/360) provides information about nonverbal capacity for initiation, planning, and divergent reasoning. You can find the data [here](https://tf-assets-prod.s3.amazonaws.com/tf-curric/data-science/rfft.csv).

**Notes:** *Casenr* is a unique identifier. When you're comparing data points between measurements, `pivot()` from pandas will be particularly useful.

1. Is there a significant difference in the number of unique designs drawn by the same participants from measurement 2 to measurement 3?
2. Is there a significant difference in the number of perseverative errors drawn by the same participants from measurement 2 to measurement 3? 

When you are finished, compare your answers to [this Notebook](https://colab.research.google.com/drive/1JKq8tFN0heRcdiFoxQnbxOPe8-YSxOKo).

