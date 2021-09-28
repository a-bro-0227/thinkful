---
title: Other terms in neural networks
author: Thinkful
team: grading
time: 80 minutes
uuid: 38057b12-6387-4a7b-b75a-c205193d4747
timeHours: 1.3333333333333333
---

Before you move on, there are a few other terms that you need to get familiar with. You don't need to know all the inner workings of these topics, but it's important that you understand what they are because you may come across these terms.


## Recursive neural networks

So far in this program, neural networks have only been mentioned in a feedforward context. _Feedforward_ means that there is a clear directionality or flow to the network. Things start at the beginning, move in one direction, and proceed to the end. That doesn't have to be the case, though.

Data can run through nodes or neurons more than once. These kinds of networks are called _recursive neural networks_ (RNN). These networks can be extremely useful for drawing out more complex relationships.


## Convolutional neural networks

If you start working with neural networks, you'll also probably hear about *convolutional neural networks*. So far, you've learned about these neurons linking together in a gridlike structure. If you've read through the additional texts, then you know that the gridlike structure can be represented using matrices.

Typically, the relationship between layers is (relatively) simple matrix multiplication. But the link can involve another level of complexity by linking those matrices via linear equations, called _convolutions_. These linear transformations are specialized and can have huge effects on the network that you create. But you won't explore how to decide these here, because it requires a much deeper understanding of linear algebra and neural networks than this program covers.


## Deep learning

Another buzzword running around neural networks and unsupervised learning is _deep learning_. It sounds terribly exciting, and if you look at a lot of the literature around data science, it could seem like deep learning is a magical solution to everything.

But deep learning isn't magical. In fact, you already know what deep learning is. It's just a neural network with several hidden layers. There's no explicit cutoff to when something has enough layers to qualify as "deep" learning. A big downside of deep learning is that the additional complexity can add to runtime and make the model even more of a black box and more difficult to understand what's going on inside.


## Reinforcement learning

Lastly, it's good to know what *reinforcement learning* is. Reinforcement learning is occasionally grouped within supervised learning, but more and more, it's becoming its own discipline.

Reinforcement learning is an incredibly useful and exciting form of data science. It refers to a model that gets feedback from its environment or system. The model tries potential actions at random and then sees what kind of feedback it receives. It eventually learns a way to operate through a series of events that generates the most positive feedback.

This kind of learning is used for anything from automatically playing a video game (walking into red shells = bad) to learning how to drive a car (crashing into walls = bad). It is a fascinating field, and many of the underlying tools are covered in this module and this program as a whole. However, in general, it requires a different kind of data than is readily available. And properly linking that feedback loop may require a more significant engineering background than the scope of this program allows.
