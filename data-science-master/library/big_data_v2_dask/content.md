---
title: Introduction to Dask
author: Thinkful
team: grading
time: 60 minutes
uuid: 46f825f8-e335-4baa-a094-2b93151e9170
timeHours: 1
---

In this checkpoint, you'll be introduced to *Dask*, a popular parallel computing framework in the Python ecosystem. This framework can handle distributed operations that can scale to thousands of machines. In addition, its ease of use is also a major factor in its adoption among data scientists. As you'll see, Dask's interface is very close to those of NumPy and pandas. This makes its learning curve flatter than the alternatives.

This is how Dask's creators describe it in the [official Dask tutorial](https://github.com/dask/dask-tutorial/blob/master/00_overview.ipynb):

> Dask provides high-level Array, Bag, and DataFrame collections that mimic NumPy, lists, and Pandas but can operate in parallel on datasets that don't fit into memory. Dask's high-level collections are alternatives to NumPy and Pandas for large datasets.

You'll start by learning about what Dask is and what use cases it is good for.

<jupyter notebook-name="2.intro_dask" course-code="DSBC"></jupyter>

###### Before moving forward, just a word of advice: if you are having issues locally with Dask, make sure that you are on the same version as Thinkful's JupyterHub and restart your kernel.

## Assignments

To complete this assignment, submit your solutions to the following tasks as a link to your Jupyter Notebook on GitHub.

1. Parallelize the following code using Dask's `@delayed` decorator and derive the task execution graph.

```python
def sum_up(l): #takes a list of numbers as input
    return sum(l)

def cube(n):
    return n**3

total = []
for i in range(1,10):
    total.append(cube(i))
    
print(sum_up(total))
```

2. Parallelize the following code using Dask's `@delayed` decorator and derive the task execution graph.

```python
# first two fibonacci numbers
fibonacci_nums = [1,1]

# returns the nth fibonacci number
def get_nth_fibonacci_number(n):
    if n == 1:
        return fibonacci_nums[0]
    elif n == 2:
        return fibonacci_nums[1]
    else:
        return get_nth_fibonacci_number(n-1) + get_nth_fibonacci_number(n-2)
        
print(get_nth_fibonacci_number(10))
```

Submit your work below. You can also take a look at this [example solution](https://drive.google.com/file/d/1BKm4EjvviJjj-Pdq0jlJrW8m_8CoHS_o/view?usp=sharing).
