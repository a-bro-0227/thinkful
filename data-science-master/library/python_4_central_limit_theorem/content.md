---
title: Central limit theorem
author: Thinkful
team: grading
time: 240 minutes
uuid: ce66791d-89fa-4af6-902a-2e0781046616
timeHours: 4
---

This checkpoint serves as a bridge between descriptive and inferential statistics. While descriptive statistics can give vital information about the dataset at hand, inferential statistics provides an almost-magical ability to infer estimates of an entire population from just a sample.

Conducting tests of inferential statistics and applying them to real-world scenarios is the focus of the next module. For now, you'll explore what's powering these statistics under the hood; you'll learn about the law of large numbers and the central limit theorem.

For each, you'll explore the basic theory and work through a demonstration in Python where you'll simulate rolling a die hundreds of times.

<jupyter notebook-name="checkpoint_sampling_and_the_central_limit_theorem" course-code="DSBC"></jupyter>

## Central limit theorem: Illustrated examples

Take a look at an interactive visualization of the central limit theorem:

<iframe src='https://seeing-theory.brown.edu/probability-distributions/index.html#section3' frameborder="0" height='500px' width="100%" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>


For a visual recap of the concepts covered here, check out the below video.

<iframe id="kaltura_player_1604698822" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604698822&entry_id=1_ko6cjwrr" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

Finally, for a screencast demonstration of the central limit theorem in Python, check out the below video.

<iframe id="kaltura_player_1604704767" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604704767&entry_id=1_s6x7dxpc" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>


## Assignment

Complete these steps for two of the following distributions:

- Normal
- Binomial
- Gamma
- Poisson


1. Create a line chart that plots the sample mean as more and more trials are conducted, up to 1,000 trials.

2. Randomly sample the mean 1,000 times, and plot the resulting frequency of sample means as a histogram.


When you are finished, compare your results to [this sample solution](https://github.com/Thinkful-Ed/data-201-assignment-solutions/blob/master/python_4_central_limit_theorem/answers_probability_central_limit_theory_drills.ipynb).

