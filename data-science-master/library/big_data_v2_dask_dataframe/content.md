---
title: Dask DataFrames
author: Thinkful
team: grading
time: 120 minutes
uuid: 678a0942-9c8a-4bc6-a19b-00f2193beb84
timeHours: 2
---

In this checkpoint, you'll learn about *Dask DataFrames*. They are the Dask equivalents of the much-beloved pandas DataFrames—and unlike pandas DataFrames, they have parallelization capabilities. You'll explore the usage of Dask DataFrames by working on a dataset.

Data scientists love pandas DataFrames because they provide a lot of convenient and easy-to-use functionality, which is especially useful in data-munging and analysis. Pandas DataFrames load the data into the memory (RAM) of the machine that they are working on, and the size of that memory naturally restricts them. This is why you wait a lot or even get memory errors when trying to load large datasets into a pandas DataFrame. What Dask DataFrames bring to the table is that they extend the pandas DataFrames with robust and efficient parallelization capabilities. Moreover, Dask DataFrames can also work with data that is larger than the available memory size by using the storage (disk). 

<jupyter notebook-name="3.dask_dataframe" course-code="DSBC"></jupyter>

## Assignments

In this assignment, you'll continue working with the [Credit Card Fraud Detection](https://www.kaggle.com/mlg-ulb/creditcardfraud/download) dataset from Kaggle. Load the dataset before working on the following tasks.

To complete this assignment, submit your solutions to the following tasks as a link to your Jupyter Notebook on GitHub.

1. How many transactions are there in total?
2. How many transactions are fraud, and how many are not fraud?
3. What is the maximum amount in fraud transactions?

Submit your work below. You can also take a look at this [example solution](https://drive.google.com/file/d/19bMnC6yJahYpmcECkZXFiFnb9UHbMwjT/view?usp=sharing).
