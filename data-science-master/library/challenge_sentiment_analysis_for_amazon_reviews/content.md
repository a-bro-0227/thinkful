---
title: 'Challenge: Sentiment analysis for Amazon reviews'
author: Thinkful
team: grading
time: 80 minutes
uuid: b3e17176-a451-4383-9e09-48ce5d04b6f2
timeHours: 1.3333333333333333
---

Now that you've looked at an example of how you can use Spark in batch mode, it's time to try it out on your own.

In this challenge, you'll work on a sentiment analysis dataset: the [Amazon product](http://jmcauley.ucsd.edu/data/amazon/) dataset. Choose one of the 5-core datasets from this page. Keep in mind that if the data is a GZIP file, you'll need to extract the data before you use it.

Complete this challenge in a Jupyter Notebook, which you'll need to work on Colab.

Now, on to the task at hand!

It's always important to start with a clear goal in mind. In this case, your goal is to determine if you can predict whether a review is positive or negative based on the language in the review.

You're going to tackle this problem with Spark, so you'll need to apply the principles that you've learned so far in the context of Spark.

Here are some tips to help you get started:

* Don't forget to install Java, Spark, findspark, and PySpark. You may also need to remount your drive to Colab. You can use the codes from the previous assignment for this purpose. 
* PySpark always needs to point at a running Spark instance. You can do that using a *SparkContext*.
* You're working in batch mode, so you'll need to load an entire file into memory in order to run any models that you build.
* Spark likes to execute models in a pipeline, so remember that when the time comes to set up your model.
* Spark's machine-learning algorithms expect numeric variables.

When you're done, save your Notebook and push it to GitHub. Submit a link to your Notebook below.

After submitting your work, review the [example solution](https://github.com/Thinkful-Ed/big-data-student-resources/blob/master/examples/Amazon%20Reviews%20Exercise.ipynb) provided in the big data student resources directory.
