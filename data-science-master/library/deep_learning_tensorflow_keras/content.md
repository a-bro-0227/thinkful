---
title: TensorFlow and Keras
author: Thinkful
team: grading
time: 180 minutes
uuid: 7cd70a2e-53fb-46f4-920e-b435b70c0d6a
timeHours: 3
---

In this checkpoint, you'll be introduced to *TensorFlow*, which is the most popular programming framework in the deep-learning community. TensorFlow was initiated and backed by Google, and then adapted and advanced by a huge open-source community. It is such an important tool that any deep-learning practitioner should learn at least its basics. Even if you use other frameworks, it will help you to understand the code written by others. Due to TensorFlow's popularity, much of the code that you'll encounter will be written in this framework.

When you're coding deep-learning models, you'll be using *Keras*, which is the high-level API of the TensorFlow. Keras abstracts away the low-level data structures of TensorFlow with intuitive, easily integrated, and extensible structures. Throughout this checkpoint, you'll implement an ANN using Keras.

**Note:** Keras used to be a separate framework that could work on top of TensorFlow as well as some other deep-learning frameworks, like Theano and CNTK. However, the TensorFlow community has now integrated Keras as TensorFlow's official high-level abstraction. With TensorFlow 2.0, Keras is the official high-level API of TensorFlow. 

<jupyter notebook-name="3.intro_tensorflow_keras" course-code="DSBC"></jupyter>

For a screencast demo of the techniques covered here, check out the below video.

<iframe id="kaltura_player_1604711197" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604711197&entry_id=1_jg1u54ta" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

## Assignments

To complete this assignment, create a Jupyter Notebook containing your solutions to the following tasks:

1. In this task, you'll build an ANN and train and test it using the *MNIST* data. This ANN should consist of two hidden layers and one output layer. All of the hidden layers should be dense. The first layer and the second layer should have neuron sizes of 32 and 16, respectively. Train this model for 20 epochs, and compare your training and test set performance with the example in the checkpoint. Is there any difference? If so, why?

2. In this task, build another ANN. This ANN should have five hidden layers and one output layer. All of the layers should be dense. The neuron numbers for the hidden layers should be 1024, 512, 256, 128, and 64. Train this model for 20 epochs, and test it using the same data from the previous task. Then compare your results. Is there any difference? If so, why?

Submit your work below. You can also take a look at this [example solution](https://drive.google.com/file/d/1J6jgJ9-oWyXDYKV66a4-DjXSvi-04OuG/view?usp=sharing).
