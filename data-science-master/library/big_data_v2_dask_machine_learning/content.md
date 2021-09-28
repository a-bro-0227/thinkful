---
title: Machine learning with Dask
author: Thinkful
team: grading
time: 180 minutes
uuid: 86db9b85-4e86-4374-b55d-e70f42bfb480
timeHours: 3
---

So far in this module, you've learned about how to work with large datasets and get the benefit of parallel processing when working with DataFrames and arrays. The next natural step is to learn about how to train machine-learning models on large datasets. 

If you've worked on a large dataset before in the program, you may have realized that training some algorithms on these large datasets can take hours or even days. In this checkpoint, you'll learn how to take advantage of parallel computing using Dask when you train machine-learning models. You'll see that you can parallelize some of the machine-learning pipelines using Dask. That being said, keep in mind that not all of the models implemented in scikit-learn are designed to handle very large datasets that don't fit into memory. For this purpose, you'll learn about Dask's own machine-learning module, which includes several machine-learning algorithms that can handle very large amounts of training data.

<jupyter notebook-name="5.dask_machine_learning" course-code="DSBC"></jupyter>


## Assignments

In the following task, you'll continue working with the [Credit Card Fraud Detection](https://www.kaggle.com/mlg-ulb/creditcardfraud) dataset from Kaggle. Before moving on to the tasks, load the dataset using Dask.

To complete this assignment, submit your solutions to the following tasks as a link to your Jupyter Notebook on GitHub.

1. In this task, you'll train several machine-learning models from scikit-learn, using Dask as the backend of joblib. This time, you need to use all of the variables except `Class` as your feature set. The `Class` variable will be your target variable.
2. Compare the results of your models.

Submit your work below. You can also take a look at this [example solution](https://drive.google.com/file/d/14CliRImmsuIzBRSYV4Mi1CH2HDVTdumi/view?usp=sharing).
