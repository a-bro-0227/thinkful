---
title: Stochastic processes
author: Thinkful
team: grading
time: 80 minutes
uuid: a2019e90-ba5b-44d2-b14b-a5fcd75a12a2
timeHours: 1.3333333333333333
---

Sometimes when you think about time, you aren't thinking about seasonality. In fact, you may not even have data about the time of year. The data could just be a sequence of variables that are understood to have happened over time. This is typically called a _process_. When those variables are random, based on some known or unknown distribution, then it is said to be a _stochastic process_.

Here, you will get an all-too-brief introduction into stochastic processes and why you need to be aware of them in data science. The goal is for you to gain a lexicon of terms and an understanding of core concepts that will allow you to recognize a stochastic process when you see one and begin to investigate. As has been the case with many topics in this program, this could be many many semesters of work. Also, it is worth mentioning that finance is a field that is often dominated by conversations of stochastic processes. So if you particularly enjoy this, then that may be a field for you to explore further.

## Bernoulli process

Next, you'll crystallize the definition of a stochastic process by considering its simplest example: the Bernoulli process. 

A *Bernoulli process* is a set of independent and identically distributed random variables, each one following a Bernoulli distribution. Now, break that definition down piece by piece.

First, there is *independent*. By now, the idea of independence should be familiar to you; it means that the outcome of one observation does not affect any other outcome. *Identically distributed* means that each random variable is drawn from the same distribution. These two traits are very important to stochastic processes, so often, you'll see "independent and identically distributed" abbreviated as *iid*. 

A Bernoulli distribution is one of the simplest distributions in statistics. It means that the outcome has only two possible values, `1` and `0`, occurring with a probability of `p` and `1-p` respectively. The most common example of a Bernoulli distribution is a coin flip. If it is a fair coin, then that is said to be Bernoulli(0.5), with `0.5` as the value of `p`.

Returning to the definition of a Bernoulli process, that is simply a series of outcomes from a Bernoulli distribution. Again, most commonly, the example given is a series of coin flips, or something like `0`, `1`, `1`, `0`, `1`, `0`, `0`, `0`, `0`, `1`, `1`, `0`, `1`, `0`, `0`, `1`.

If given a Bernoulli process, you can take its average value as an estimate of `p`, and then use a random generator to simulate the process further. So here, `p = 7/16`, and you could simply randomly generate more `0` and `1` values, giving a probability of `p` to `1` and appending them to your set as you continue.

## Random walks

Now, if Bernoulli processes are the simplest stochastic processes, then random walks are the next logical complication. _Random walks_ are defined as the sum of iid random variables. 

Think about someone walking along a path, where each brick in the path is numbered in both a positive and negative direction and the person starts at zero. The person can step forward or backward with some constant probability. A random walk would be the path of the bricks that the person walks. `0`, `1`, `2`, `1`, `2`, `3`, `4`, `5`, `4`, `3`, `4`, `5`, `6` is a random walk. So too is `0`, `1`, `0`, `-1`, `-2`, `-1`, `0`, `1`, `0`, `1`. The step here is either `-1` or `1` with some random probability.

If that random distribution of a step is Bernoulli with `1` and -`1` as the outcomes, then it is called a *simple random walk*. Even further, if the `p` of that Bernoulli is `0.5` and the values are `1` or `-1`, then it is a *symmetric simple random walk*, because the probability of going in either direction is symmetrical.

Random walks are thought of as occurring in discrete time, meaning that there are specified steps where the process moves rather than a smooth and continuous progression.

Another extension of the random walk is the *Wiener process*, also called *Brownian motion*. In this process, the step, or the direction to its next position, is normally distributed. Note that the standard normal distribution has an expected value of zero. In stochastic processes, having an expected value of zero is an important characteristic because it means that the future value of the process is actually expected to be wherever the process is currently. These processes are called *stationary*. If it is expected to deviate from its current position, that is called *drift*.

## Application

This has been very abstract, and deliberately so. Stochastic processes have their own language, and it is important to understand those terms when you're talking about them.

But where will you see these in the wild? You'll see them all the time. When you're tracking a single object or entity over time, the observed values can be thought of as a stochastic process. The object or entity moves randomly in some direction over time, and that randomness is stochasticity. For example, purchases by a customer over their lifetime is a stochastic process. So is the price of a stock.

When you define these time series in terms of their stochastic characteristics, it allows you to model and often predict what they are going to do next.

In the next checkpoint, you'll learn how to model a specific kind of stochastic process modeling using a model called ARIMA. 

If you're interested in more specificity and a wider range of topics in this field, [Introduction to Stochastic Processes](https://www.ma.utexas.edu/users/gordanz/notes/introduction_to_stochastic_processes.pdf) by Gordan Žitković at UT Austin is a good continuation of these notes.

###### Remember *gradient descent*? It's often called *stochastic gradient descent*. *Stochastic* really just means random. Can you think of any part of that process that functions as a stochastic process?
