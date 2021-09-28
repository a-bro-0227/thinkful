---
title: Dimensionality reduction with UMAP
author: Thinkful
team: grading
time: 80 minutes
uuid: 35f8f5b0-78ab-4201-b21d-e6cd470a236a
timeHours: 1.3333333333333333
---

In the previous checkpoint, you learned about t-SNE, a very successful dimensionality reduction algorithm. Since the t-SNE algorithm was proposed in 2008, many data science practitioners have welcomed it; t-SNE has become especially popular for exploratory data analysis tasks. But, as mentioned before, running t-SNE on large datasets requires lots of time and computer resources. This is cumbersome if you're doing research and prototyping, where you need to try many different things as fast as possible.

In this checkpoint, you'll learn about an alternative to t-SNE: *uniform manifold approximation and projection* (UMAP). UMAP's success in producing low-dimensional representations is on par with that of t-SNE, but UMAP runs much faster than t-SNE. This speed makes it a good choice, particularly for researching and prototyping. UMAP is also suitable for feature engineering when you need to reduce the dimensions in your data; in contrast, the t-SNE algorithm again suffers from long computational time when applied on very high-dimensional data.

## What is UMAP?

Uniform manifold approximation and projection is a general-purpose dimensionality reduction technique that can be used for visualization, similar to t-SNE. It can also be used for general nonlinear dimension reduction. The original paper that proposes the algorithm describes it as follows:

> "The UMAP algorithm is competitive with t-SNE for visualization quality, and arguably preserves more of the global structure with superior run time performance. Furthermore, UMAP has no computational restrictions on embedding dimension, making it viable as a general purpose dimension reduction technique for machine learning." —Leland McInnes, John Healy, James Melville, in [UMAP: Uniform Manifold Approximation and Projection for Dimension Reduction](https://arxiv.org/abs/1802.03426)

For more information on UMAP, you can read up on it [here](https://umap-learn.readthedocs.io/en/latest/how_umap_works.html).

UMAP is an even newer algorithm than t-SNE. It was proposed in 2018—so it is a very recent work on dimensionality reduction. This should give you an idea of how active the research related to unsupervised learning is. UMAP builds upon the insights of t-SNE and offers some improvements. So understanding the differences between UMAP and t-SNE can shed some light on what UMAP achieves.

## Differences between t-SNE and UMAP

Compared to t-SNE, UMAP offers three major benefits:

- Probably the most important improvement that UMAP brings to the table is that it's faster than t-SNE. The slowness of applying t-SNE on large datasets is a serious concern for those who lack the appropriate time and computing resources. UMAP's speed makes it the default choice when it comes to visualization of high-dimensional complex data, like image, text, and audio. That being said, keep in mind that UMAP is still slower than PCA.

- In practice, t-SNE doesn't have much use apart from visualization. However, UMAP is a general-purpose dimensionality reduction algorithm that can also be used for feature engineering when a need for reducing the dimensions arises. You can use UMAP wherever you can use PCA.

- When you were learning about t-SNE, it was mentioned that t-SNE preserves the local similarity as well as the global structure. But UMAP actually captures global structure better than t-SNE, while its success in preserving the local similarity is on par with t-SNE's.


<jupyter notebook-name="9.umap" course-code="DSBC"></jupyter>

For a screencast demo of the techniques covered here, check out the below video.


<iframe id="kaltura_player_1604766231" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604766231&entry_id=1_un0g03au" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

## Assignment

In this assignment, you'll continue working with the [*fashion MNIST* dataset](https://github.com/zalandoresearch/fashion-mnist). For the sake of comparability, use the same 10,000-observation sample that you used in the previous two checkpoints. To complete this assignment, submit a link to a Jupyter Notebook containing your solutions to the following tasks below. You can also take a look at [these example solutions](https://github.com/Thinkful-Ed/data-201-resources/blob/master/clustering_module_solutions/9.solution_umap.ipynb).

1. Load the dataset and conduct any necessary preprocessing, such as normalizing the data.
2. Apply UMAP to the data.
3. Using the two-dimensional UMAP representation, draw a graph of the data by coloring and labeling the data points as you did in the checkpoint.
4. Do you think that the UMAP solution is satisfactory? Can you easily distinguish between the different classes? Which algorithm produced better results, UMAP or the others (t-SNE or PCA) that you applied in the assignments from the previous checkpoints?
5. Now, play with the different hyperparameter values of the UMAP, and apply UMAP for each of them. Which combination is the best in terms of the two-dimensional representation clarity?
