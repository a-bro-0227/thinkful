---
title: What is unsupervised learning?
author: Thinkful
team: grading
time: 80 minutes
uuid: bd7b1fa9-0c58-4884-9361-a8c37e0815a3
timeHours: 1.3333333333333333
---

So far in this program, you've studied machine-learning algorithms for regression and classification problems. All of the algorithms that you've learned so far make use of labeled (or tagged) data, where the ground truths of the observations are given. As you already know, *supervised learning* is about creating algorithms that learn from labeled data. But what if you don't have the ground truths for the observations? Are you at a dead end?

Of course not! In this module, you'll dive into the challenging but exciting domain of *unsupervised learning*. In other words, you'll run algorithms on unlabeled data to derive useful patterns. Unsupervised learning can be challenging, not because the algorithms are too difficult to grasp, but because the problems that unsupervised learning addresses are hard to formalize and evaluate. 

The following quote highlights the current state of data science with respect to the different learning types:

> "**Most of human and animal learning is unsupervised learning.** If intelligence was a cake, unsupervised learning would be the cake, supervised learning would be the icing on the cake, and reinforcement learning would be the cherry on the cake. We know how to make the icing and the cherry, but we don't know how to make the cake. We need to solve the unsupervised learning problem before we can even think of getting to true AI." —Yann LeCun, VP of Facebook and Director of AI Research

The quote above makes it clear why unsupervised learning can be exciting. It's because most of human reasoning and learning operates in an unsupervised manner. In this module, you'll step into the exciting domain of unsupervised learning by exploring two main problems that it needs to tackle:

1. Clustering
2. Dimensionality reduction

Although unsupervised learning includes other interesting topics, like anomaly detection, you'll focus on these two subjects in this module.

## What is clustering?

*Clustering* is all about organizing individual examples or observations into groups, such that individuals in each group resemble fellow group members more than they do nongroup members. This requires the ability to measure similarity.

For example, say that a management team gives you a customer dataset for their company. The management team asks you to help them organize customers into different groups in order to expedite customer service and drive reorganization strategies for the customer service department.

Where to start? There's no need to overthink things, and you could start with a relatively straightforward grouping. You could separate the customers into different groups with respect to their city of origin, gender, income level, or all three of these variables.

Grouping customers with respect to a single variable is easy. For example, you can separate the customers into two groups with respect to income.

![customers](customers.png)

From the graph above, you could assign the customers that lie above the red line to the high-income group and assign the rest to the low-income group. But what if you have hundreds of variables in your dataset, and all of them seem to be useful for the efficiency of the customer service? Assume, for example, that each of the hundred variables has two categories. If you group the customers using the technique above, you'll come up with 2¹⁰⁰ groups—that's 1,267,650,600,228,229,401,496,703,205,376 different groups!

Clustering algorithms solve this problem by grouping observations (in this example, the customers) by taking into account all the variables at hand (in this example, 100 variables). Mathematically, the grouping is done in a high-dimensional space (in this example, 100 dimensions).

Increasing data dimensionality doesn't require an increasing number of groups. Instead, clustering algorithms allow you to create an arbitrary number of groups. This means that you can apply clustering techniques to your customer data and ask the algorithm to come up with just four groups if your company plans to establish four different units inside the customer service department.


## How many clusters?

Many clustering algorithms require that you specify a desired number of groups as an input parameter.

Take a look at an example. Imagine that you have a customer dataset with two variables: age and income. How many clusters do you think are appropriate?

![how to cluster](how_to_cluster_v2.png)

The graphs above show three ways that you could cluster this data:
1. Young versus old
2. Low-income versus high-income
3. Young and low-income versus young and high-income versus old and low-income versus old and high-income

Each of these clusterings may have its own advantages and disadvantages.

In general, as the number of clusters increases, so does the similarity between the individuals within a cluster. This can be good to a point, but you don't want to end up with a large number of overfit clusters. Keep in mind that the limit case for clustering is that each individual case is its own cluster (which is really to say, there are *no* clusters). Just because an algorithm can find a certain number of clusters doesn't mean that those clusters are inherently meaningful.

This gives you a hint as to why clustering is hard. In many cases, there isn't a single correct number of clusters. As you'll see in the upcoming checkpoints, for most clustering algorithms, the number of clusters is a hyperparameter that you need to tune.


## Types of clustering

There are two types of clustering:

- In **hard clustering**, each data point is assigned to only one cluster.
- In **soft clustering**, each data point is assigned a degree of membership for every cluster. 

In both types of clustering, a *cluster* is a set of data points that have been determined to be more similar to one another than to other data points. Depending on the clustering method that you use, you'll use different measures of similarity to analyze clusters.

You will focus mostly on hard clustering methods in this module.

# What is dimensionality reduction?

Unsupervised learning often requires *dimensionality reduction*. In this context, *dimensions* refers to the number of features (or variables) in the dataset. *Dimensionality reduction* is the process of reducing a higher-dimension dataset to a lower-dimension one, while striving to maintain as much information as possible.

As a general rule, high-dimensional spaces contain at least as much information as low-dimensional spaces. That is, a dataset contains more information than a variant of that same dataset where the number of variables is reduced. This is why all dimensionality reduction techniques try to retain as much information as possible.

To give you a sense of how you can represent a high-dimensional observation in a lower-dimensional space, the image below gives a familiar example. Take a look at these lower-dimensional representations of a three-dimensional cube: 

![dimensions](dimensions.png)

In three-dimensional space, the cube has dimensions on the x-, y-, and z-axes. To represent this cube in two-dimensional space, you can use a square with two dimensions on the x- and y- axes. Similarly, you can represent a cube in one-dimensional space as a straight line on the x-axis.

In this example, you retain quite a lot of information about the cube—even with a straight line. This is because the magnitudes of all the dimensions of a cube are the same. Now, think about a more complex three-dimensional object like a prism. In this case, you inevitably lose more information when you represent it in two- or one-dimensional space.

Now, consider why dimensionality reduction is important. Say that you have a dataset that comprises millions of observations and thousands of features. In this case, dimensionality reduction can help with the following challenges:

* Conducting exploratory data analysis on thousands of features is quite difficult and time consuming. It may take days, weeks, or even months to fully understand the relationships between the features.
* Visualizations are one of the easiest ways to intuitively grasp data. But how can you visualize data in more than three dimensions?
* Some machine learning algorithms suffer from the *curse of dimensionality*; as the number of features increases, the number of operations increases exponentially. Given a sufficient number of dimensions and records, algorithms can easily take days, weeks, or even months to run. 
* Last but not least, the more features you have, the more data you need to train your algorithms. Additional data collection is expensive and often not possible.

This is why data scientists look to reduce dimensionality.

You're already familiar with one approach to dimensionality reduction, principal component analysis (PCA), but there are others. In this module, you'll briefly revisit PCA before exploring some other approaches to dimensionality reduction. Earlier in the program, you encountered PCA in the context of exploratory data analysis and feature engineering. In this module, you'll explore how to use dimensionality reduction to derive helpful data visualizations in 2D space.

