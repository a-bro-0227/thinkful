---
title: SVM extensions
author: Thinkful
team: grading
time: 40 minutes
uuid: 84989d8f-ffcd-4e20-a6ff-94383466a023
timeHours: 0.6666666666666666
---

So far, you've learned about the simplest possible version of support vector machines. There are many different scenarios that make slight alterations to the model. In this program, you'll explore these alterations from a conceptual basis. You won't go through the mathematical proofs behind these alterations or fully chart out their ramifications for things like the loss function or how the algorithm iteratively finds optimal boundaries.


## Multiple classes

So far, you've focused on using SVM as a binary classifier. But if SVM only worked as a binary classifier, it probably wouldn't have seen the wide adoption and use that it has. How can you extend it to cover multiple classes?

The simplest way is to do a hold-one-out form of binary classifier many, many times (or for as many values as your outcome can take). Then, for each category, you create a binary classifier between having that category or having any other outcome. To aggregate these and create a multiclass classifier, each one has an output function to define its confidence in classification. This is related to its distance from the boundary and the weights for the accuracy of the classifier. The highest output value dominates, thereby deciding the class.

Another way to do it is pairwise, where every category is compared to the others in pairs. In this case, the class is decided by the maximum number of wins, given an observation's characteristics. So an observation is categorized under every possible pair of outcomes, and then the outcome is assigned to the one that was most common.


## SVM as a regressor

Support vector regression (SVR) operates much like an inversion of the classification problems that you've been dealing with so far. In classification, you had a computational advantage because you were only interested in the points closest to the boundary. In regression, you instead are only interested in values far away from the prediction.

There are two major values that you tune in SVR: C and epsilon. C is called the *box constraint*; it sets the penalty for being outside of your margin. Epsilon sets the size of your margin. So again, much like a classification problem, you gather your data and find its distance from a specified point (previously the boundary, now the prediction). Then you optimize the cost from observations being outside of the margin. This ends up being a huge advantage of SVM for regression: you can set the sensitivity when building the model, not just after the fact.


## Clustering

SVM can also be used as an unsupervised clustering algorithm. This program hasn't yet covered unsupervised learning (other than a brief foray into PCA) or what a clustering algorithm does, and you won't learn about all of that here. Rather, remember this technique of defining boundaries and margins for when you start exploring classifiers. It will be hugely relevant.


## So, why SVM?

SVM's primary advantage is its flexibility. It can have great visual explanatory power (linear SVC), tremendous accuracy (kernel smoothing), clustering (SVClustering), or the ability to control the specificity of training (SVR). Some of these options do come at the cost of computational efficacy and explanatory power, particularly when in high dimensions when kernels get involved. But overall, it remains a versatile modeling class that is capable of doing many different things very well.

