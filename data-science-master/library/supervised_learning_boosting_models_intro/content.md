---
title: Intro
author: Thinkful
team: grading
time: 7 minutes
uuid: 276a114a-70a2-4ddc-a1e7-da573cbf9f4a
timeHours: 0.11666666666666667
---

In this module, you'll learn about *boosting*, a type of ensemble modeling that's very popular for its flexibility and predictive power. Many a Kaggle competition has been won using boosting! Specifically, in this module, you'll learn about the following:

 * Boosting compared to other ensemble methods
 * Gradient boosting
 * Boosting with classifier and regression problems

## What is boosting?

Nearly every time that you've learned about a new model in this program, you've been asked to play with it to see if you can increase its predictive accuracy. You've tried all sorts of tweaks by now: new features, dropping features, adjusting the fitting algorithm, adding or subtracting thresholds, and so forth. Optimizing models this way involves trial and error, and a lot of time. There has to be a better way!

In fact, there is, and you've already encountered it briefly. Ensemble models combine many less effective models (*weak learners*) into a single, more effective model (a *strong learner*). Random forests are a type of bagged ensemble model where many models are run in parallel and their outputs are aggregated. Another class of ensemble models, boosting models, models the data over and over, adjusting the model each time based on what was learned from the previous one.

The boosting approach is exceptionally flexible. It works for classification and regression, and it can be combined with any of the modeling approaches that you've learned about so far. The principle behind boosting is iterative. You start by fitting a simple model on all the data. You identify the information that the model was not able to account for, whether that's incorrect predictions in classification or residuals in regression. Then you build a new simple model that targets that new pool of information. You repeat this until you reach some predetermined stopping rule. The combination of all the models is then used to make the final predictions.

Boosting is great because you can arrive at very accurate predictions using many simple models that are each computationally fast. There are many different implementations of boosting, and they vary along the following axes:

 * **Type of simple model:** You can use almost any model you like.
 * **Index of error:** You can use residuals from regression, classification errors, or any cost function.
 * **How the next iteration targets the error:** You can weight inaccurately predicted cases high and accurately predicted cases low, you can directly model residuals, or you can model only the subset of the data that was inaccurately predicted.
 * **Stopping rule:** You can stop once you've run a certain number of models, or once the amount of variance explained by the most recent iteration of the model is lower than some threshold. Or you can stop once the change in weights between the two most recent model iterations is lower than some threshold.

Clearly, there are many different ways to do boosting. In the next assignment, you'll explore the most commonly used implementation: gradient boosting.
