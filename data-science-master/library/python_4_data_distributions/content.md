---
title: Data distributions
author: Thinkful
team: grading
time: 60 minutes
uuid: af65eb15-c902-4423-9a18-daa1db939293
timeHours: 1
---

A host of common statistical methods are built on the assumption that data is normally distributed. In this checkpoint, you will explore the concept of normality and learn how to test for normality using histograms in Python. You'll also learn about several other common distribution types.

Here are the key topics that you'll learn about:

* Normality
* Normal distribution
* Bernoulli distribution
* Binomial distribution
* Gamma distribution
* Poisson distribution
* Conditional distribution

At the end of this checkpoint, you'll complete a series of drills where you'll practice analyzing distributions with Python.


<jupyter notebook-name="data_distributions_normal_and_otherwise" course-code="DSBC"></jupyter>
    
For a visual recap of the concepts covered here, check out the below video.

<iframe id="kaltura_player_1604698738" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604698738&entry_id=1_nkrqvkhe" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

To view a screencast of the concepts covered here, check out the below video.

<iframe id="kaltura_player_1604704731" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604704731&entry_id=1_bcv6c7eh" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>


## Assignment

To complete the following drills, you'll need to use your Python skills to create some datasets, then use your new statistical knowledge to summarize them. Choose six distributions from [Distributions](https://numpy.org/doc/stable/reference/random/legacy.html#distributions), which is a list of random distributions available in NumPy.

For each distribution, do the following:

1. Generate a random variable with 100 data points. Use the code `distributionvar = np.random.distributionname([arguments], 100)`, replacing `distributionvar` with an appropriate variable name, and replacing `distributionname` with the name of the distribution that you've chosen. Fill in the empty space in the parentheses with your chosen values for the appropriate parameters. If you feel uncertain about how to do this, go back to the *Other distributions* assignment for examples of code to use as a starting point.
2. Graph the variable using a histogram.
3. Compute the mean and standard deviation and plot them as vertical lines on the histogram.
4. Evaluate whether the descriptive statistics provided useful information about the variable. Can you identify any common characteristics of the distributions that could be usefully described using the mean or standard deviation?


Additionally, do the following:

1. Generate two normally distributed variables, one with a mean of `5` and a standard deviation of `0.5`, and the other with a mean of `10` and a standard deviation of `1`.
2. Add them together to create a third variable.
3. Graph the third variable using a histogram.
4. Compute the mean and standard deviation and plot them as vertical lines on the histogram.
5. Evaluate the descriptive statistics against the data.

Once you've given it a try, compare your solution to [this sample solution](https://github.com/Thinkful-Ed/data-201-resources/blob/master/solutions/Prep%20course/3.3.4.ipynb).

