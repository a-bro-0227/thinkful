---
title: Introduction to Keras
author: Thinkful
team: grading
time: 60 minutes
uuid: 49a71818-7745-4b37-ba14-8eb4d6a13de9
timeHours: 1
---

At the beginning of this module, it was mentioned that you would use Keras to build neural networks. But so far, this module has been all about TensorFlow. That changes now. Before you can start using Keras, however, you need to understand how it differs from TensorFlow.

Keras is a much more user-friendly system than TensorFlow. It was designed to work quickly while maintaining as much adaptability as possible. Of course, some sacrifices were still made, and it is nowhere near as flexible as TensorFlow. 

Hopefully, through the past two checkpoints, you have seen the very granular controls that TensorFlow gives you for setting up a session and creating a model. Keras is not that kind of program. Keras was made specifically for neural networks, and it aims to provide maximum flexibility while maintaining a relatively easy frame of use. As such, it emphasizes modularity of customizability. How does it do that? Well, it all comes down to how Keras thinks about structures. Instead of nodes and variables and the like, Keras thinks in terms of *models* and *layers*.

# Keras has layers

The simplest level of structure in Keras is the layer. These are like the layers that you learned about in the previous neural networks section; a layer is a set of nodes or perceptrons that connect in some form to both the preceding and following layers.

There are many different kinds of layers in Keras. Perhaps the most common of these layer types is the *Dense* layer (also known as the *fully connected* layer). In this type of layer, each node connects to each node in the following layer.

[There is a lot more to layers](https://keras.io/layers/about-keras-layers/) than just Dense. You can have convolutional layers or recurrent layers or many other kinds that haven't even been mentioned. The documentation here is extremely strong; as you expand the kinds of networks that you build, it's a good idea to refer back to the documentation. To explain every possible type of layer here would be work worthy of a dissertation, if not several. Until you've spent a lot more time working on these kinds of models, try to stick mostly to structures that you've read about elsewhere, rather than attempting to innovate in this space.

# Model types

Models in Keras come in two varieties: *Sequential* and *Complex*.

Sequential models are simpler to implement, and this model type implies a basic stack of layers with a linear progression. The more complex models (made through the Keras API) can have any kind of graphical structure that you could imagine.

So, how do you make a model? You add layers.

```
from keras.models import Sequential

model = Sequential()

from keras.layers import Dense, Activation

model.add(Dense(units=100, input_dim=100))
model.add(Activation('relu'))
model.add(Dense(units=10))
model.add(Activation('softmax'))

```

The code above sets up a sequential model and then adds two layers with two different activation functions. These layers are fully connected, or Dense. Also note that the first layer specifies *units* (which is the width of the layer) and the *input dimension* (which is necessary for the first layer in order to specify the number of input variables).

Also, your last layer has a number of units that is the number of outputs that you want. So ten outputs would be for a ten-class classifier, with a softmax function to pick which category. (Again, there are more functions to choose from. The softmax function is just one of the most common for classification problems.)

# Compile and fit

Once you've established the model, you have to compile it and then fit it.

To compile the model, you need to specify two arguments: loss and optimizer. The loss function explains what you'd want to minimize, as before. Keras has several kinds of loss functions built in under `keras.losses`. You can choose the one that is most appropriate for your given problem.

The optimizer is something that you learned about in the previous checkpoint with the implementation of gradient descent, which is the primary optimizer that you've worked with so far. But under `keras.optimizers`, there are several other options.

These are the key components for working with Keras. Now it's time to build something with them.
