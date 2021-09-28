---
title: Activation and loss functions
author: Thinkful
team: grading
time: 180 minutes
uuid: a8397b21-fa48-4115-9485-490cb198dc53
timeHours: 3
---

When you implemented your ANN in the last checkpoint, you used some concepts like the activation functions and the loss function. Because you've already learned how to implement an ANN using Keras, you're now ready to learn about different activation and loss functions as well as implement them. In this checkpoint, you'll learn why data scientists use activation functions and why they are crucial in the success of any deep-learning model. You'll also learn about several loss functions in this checkpoint. Using an appropriate loss function is necessary when implementing a deep-learning model. Because classification and regression tasks address different types of problems, they require different types of loss functions.

In this checkpoint, you'll get started with the activation functions. Then you'll explore loss functions.

<jupyter notebook-name="4.activation_loss_functions" course-code="DSBC"></jupyter>

## Assignments

In this assignment, you'll continue working on the *MNIST* dataset. Train and test the models specified in the tasks below using the *MNIST* data. You can choose the number of epochs for training, but for the sake of comparison, it's a good idea to start by training for 20 epochs. And remember, you almost always want to use Softmax for the output layer.

To complete this assignment, create a Jupyter Notebook containing your solutions to the following tasks:

1. In this task, you'll implement several ANN models with different activation functions. For each, use the cross-entropy loss function as the loss function. Specifically, do the following:

    1. Implement a three-layer ANN model with 128, 64, and 10 neurons in the layers. Use the tanh activation function for each layer.
    2. Implement a three-layer ANN model with 128, 64, and 10 neurons in the layers. Use the sigmoid activation function for each layer.
    3. Implement a three-layer ANN model with 128, 64, and 10 neurons in the layers. Use the ReLU activation function for each layer.
    4. Compare the results of each model. Which activation function performed best?

2. In this task, you'll implement the ANN models specified below. For each, use the hinge loss function as the loss function. Specifically, do the following:

    1. Implement a three-layer ANN model with 128, 64, and 10 neurons in the layers. Use the tanh activation function for each layer.
    2. Implement a three-layer ANN model with 128, 64, and 10 neurons in the layers. Use the sigmoid activation function for each layer.
    3. Implement a three-layer ANN model with 128, 64, and 10 neurons in the layers. Use the ReLU activation function for each layer.
    4. Compare the results of each model with the result of the same model from the previous task. Which loss function performed best?

Submit your work below. You can also take a look at this [example solution](https://drive.google.com/file/d/1aEzAW-cDZdpz79kdQ1O3d1ExkvZwYudp/view?usp=sharing).
