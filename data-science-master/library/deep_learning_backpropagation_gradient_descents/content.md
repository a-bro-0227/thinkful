---
title: Gradient descent and backpropagation algorithms
author: Thinkful
team: grading
time: null
uuid: 8c29ff44-a839-41e3-b9e2-1944a4c082ed
timeHours: null
---

So far in this module, you've learned the fundamental architecture of deep neural networks. You've also learned how to implement them using Keras. And in the last checkpoint, you went further and explored several activation functions and loss functions. But one very important aspect of training deep learning models is waiting for your treatment: how do you train deep neural networks?

As you've already learned, training a neural network means estimating its parameters. In a modest-size neural network, you can have hundreds of thousands or even millions of parameters. So finding the best possible value for each of these parameters is a challenging task. As you'll see in this checkpoint, the most common method—if not the only method—that is used for training neural networks is the *gradient descent algorithm* and its variants.

In this checkpoint, you'll learn about the gradient descent algorithm and its several variants. You'll also learn about the *backpropagation algorithm*, which provides a way to apply gradient descent in deep neural network architectures. Before diving into these topics, briefly consider what the *objective function* and *optimization* are.

<jupyter notebook-name="5.backpropagation_gradient_descents" course-code="DSBC"></jupyter>

For a visual overview of how gradient descent and backpropagation algorithms work, check out the below video.

<iframe id="kaltura_player_1604701879" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604701879&entry_id=1_te9ecmq7" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

## Assignments

In this assignment, you'll continue working on the *MNIST* dataset. So, train and test the models specified in the tasks below using the *MNIST* data. You can choose the number of epochs for training. But for the sake of comparison, it's a good idea to train for 20 epochs.

To complete this assignment, create a Jupyter Notebook containing your solutions to the following tasks:

1. In this task, you'll implement several ANN models with different batch sizes. Specifically, do the following:
    * Implement a three-layer ANN model with 128, 64, and 10 neurons in the layers. Use 8 as the mini-batch size.
    * Implement a three-layer ANN model with 128, 64, and 10 neurons in the layers. Use 128 as the mini-batch size.
    * Implement a three-layer ANN model with 128, 64, and 10 neurons in the layers. Use the full sample as the batch size.
    * Compare the results of each model. Which batch size performed best?
    
2. In this task, you'll implement several ANN models with different learning rates for the stochastic gradient descent. In all of the models below, use 128 as your mini-batch size.
    * Implement a three-layer ANN model with 128, 64, and 10 neurons in the layers. Use 0.01 as the learning rate.
    * Implement a three-layer ANN model with 128, 64, and 10 neurons in the layers. Use 100 as the learning rate.
    * Implement a three-layer ANN model with 128, 64, and 10 neurons in the layers. Use 0.0000001 as the learning rate.
    * Compare the results of each model. Which learning rate performed best?

Submit your work below. You can also take a look at this [example solution](https://drive.google.com/file/d/1Tux1Bb6FV_8_DfoqKztiTbhevdphoUzh/view?usp=sharing).
