---
title: History of artificial neural networks
author: Thinkful
team: grading
time: 60 minutes
uuid: 669a0469-120f-4a66-8072-529d1c16b1ad
timeHours: 1
---

A long time ago, people started building artificial neural networks. Artificial neural networks (ANN) were, somewhat unsurprisingly, born of a desire to simulate neural networks in the brain. This work really began in the 1950s. And although it is now considered a significant development in computer science, it wasn't really seen that way at the time.

In fact, although there were some significant developments along the way, neural networks faded from the general consciousness. A now [very popular lecture from MIT](https://www.youtube.com/watch?v=uXt8qF2Zzfo) on neural networks acknowledges that they were almost scrapped from MIT's machine-learning curriculum. It may seem extreme now, but that was the reality a little over a decade ago. Neural networks were ineffective and inefficient.

Now, of course, ANN has become one of the most exciting and influential facets of machine learning. Deep learning is one of the most in-demand skills in the world today, based entirely on ANN as a framework.

So, how did this happen?

### The rebirth of neural networks

Most people would point to 2006 as the year that the rebirth of neural networks started to regain traction.

Several competitions (imagine an older, more exclusive version of Kaggle) were won by several machine-learning teams that used neural networks. A particularly famous team of researchers from this period was led by Jürgen Schmidhuber out of a Swiss lab called IDSIA. As what are now called neural networks started winning competition after competition, people began to take notice.

At the time, ANNs were being used as an unsupervised technique. As computational power continued to develop, however, they also became relevant for supervised learning problems. Some people started to develop ways to run these algorithms even more efficiently using things like *GPUs*, or *graphics processing units*. GPUs are highly [parallelizable](https://www.quora.com/Why-and-how-are-GPUs-so-important-for-Neural-Network-computations) and allowed for these systems to get even more complex.

To this point, however, coding up a neural network required a lot of manual development of algorithms. This limited their impact to only the most technical projects in the machine-learning world.

That would soon change.

## New tools

As with many open-source tools in the past decade or so, this story now has to turn to Google. Around 2011, a team at Google started working on a tool called *DistBelief*. This was a key part of Google Brain, one of Google's earlier artificial intelligence projects, and became the backend for several different internal projects.

As DistBelief became increasingly impactful, Google chose to make it open source in 2015 in a new iteration that's now known as *TensorFlow*. TensorFlow is a robust toolset for building a variety of models, but it is particularly useful for neural networks. 

Initially, TensorFlow was relatively complex to use; it required quite a bit of expertise. Elsewhere, a tool called *Keras* was developed as a way of making the process of creating a neural network easier out of the box. Keras sat on top of TensorFlow and made it so that you could make a fully functional neural network in just a few lines of code; it delivered usability without sacrificing robustness. Keras can also sit on top of some other neural network packages, such as Theano, although those won't be covered here.

Then, even more recently, Keras and TensorFlow integrated. Because of this integration, you can use Keras natively with TensorFlow, and modeling is even easier. This is a huge part of what has led to the popularity of neural networks as a modeling framework—and even Python as a language for data science.

If you're building a bespoke neural network, the Thinkful team recommends using Keras. That said, to really understand how it works, you're going to need to know more about TensorFlow.
