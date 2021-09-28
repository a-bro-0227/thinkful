---
title: Working with Dask arrays
author: Thinkful
team: grading
time: 90 minutes
uuid: 36e40ef3-db0a-4e7a-804b-1ed1e327d253
timeHours: 1.5
---

Now that you've learned how to use Dask DataFrames in place of pandas DataFrames, you're ready to move on to the next topic. Pandas uses NumPy under the hood in DataFrames and its other data structures. NumPy provides a huge set of analytical functionalities, and it's one of the central scientific packages in the Python ecosystem. Some data scientists even prefer to work on NumPy instead of pandas—especially those who are accustomed to thinking mathematically. 

<jupyter notebook-name="4.dask_array" course-code="DSBC"></jupyter>

## Assignments

In the following exercises, you'll be working with the code snippet below:

```python
%%timeit
x = da.random.random((10000, 10000), chunks=(1000, 1000))
y = x + x.T
z = y[::2, 5000:].mean(axis=1)
z.compute()
```

To complete this assignment, submit your solutions to the following tasks as a link to your Jupyter Notebook on GitHub.

1. Change the code above by setting `chunks=(250, 250)`. How long does it take to run?
2. Now, set the parameter to `chunks=(500, 500)`. How long does it take to run? Does this one or the previous one run more quickly? Why?

Submit your work below. You can also take a look at this [example solution](https://drive.google.com/file/d/1ulyVmcIbFaYFd6_zQO4UzLkKVWFM5BsP/view?usp=sharing).
