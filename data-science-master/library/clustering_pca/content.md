---
title: Dimensionality reduction with PCA
author: Thinkful
team: grading
time: 80 minutes
uuid: 9cf7ef13-590c-4c7f-af00-fe905a380bfe
timeHours: 1.3333333333333333
---

So far in this module, you've learned about several clustering algorithms. Clustering is an important task in unsupervised learning, and you've learned how to use various methods to discover clusters in data. With this checkpoint, you'll start exploring *dimensionality reduction techniques*. This is another important set of algorithms in unsupervised learning.

In this checkpoint, you'll first review why dimensionality reduction techniques are essential. Then you'll briefly revisit principal components analysis (PCA) and learn how it can reduce dimensionality.

<jupyter notebook-name="7.pca" course-code="DSBC"></jupyter>

For a screencast demo of the techniques covered here, check out the below video.

<iframe id="kaltura_player_1604766079" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604766079&entry_id=1_y8q9cb4n" width="900" height="506" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>


## Assignment

In this assignment and in the assignments in the following checkpoints, you'll work with the [*fashion MNIST* dataset](https://github.com/zalandoresearch/fashion-mnist). This is another image dataset that comprises 70,000 grayscale 28x28 images. The dataset contains the following 10 classes:

* T-shirt/top
* Trouser/pants
* Pullover shirt
* Dress
* Coat
* Sandal
* Shirt
* Sneaker
* Bag
* Ankle boot

You can load the dataset using the `fetch_openml` function of `sklearn.datasets` as follows:

```python
mnist = fetch_openml('Fashion-MNIST', version=1, cache=True)

```
Or, alternatively, you can download it from [this link](https://github.com/zalandoresearch/fashion-mnist) and load it yourself. 

Randomly select 10,000 images, and work on this sample in the following exercises.

To complete this assignment, submit a link to a Jupyter Notebook that contains your solutions to the tasks outlined below. You can also take a look at [these example solutions](https://github.com/Thinkful-Ed/data-201-resources/blob/master/clustering_module_solutions/7.solution_pca.ipynb).

1. Load the dataset and conduct any necessary preprocessing, such as normalizing the data.
2. Apply PCA to the data and get the first two principal components.
3. Using the first two principal components, draw a graph of the data by coloring and labeling the data points as you did in the checkpoint.
4. Do you think that the PCA solution is satisfactory? Can you easily distinguish between the different classes?
