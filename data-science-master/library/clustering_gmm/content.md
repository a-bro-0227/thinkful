---
title: Clustering with Gaussian mixture models
author: Thinkful
team: grading
time: 80 minutes
uuid: 39fdf62a-a63c-486c-8314-25b370983dd9
timeHours: 1.3333333333333333
---

So far in this module, you've reviewed hard clustering algorithms, which are algorithms that assign observations to a single cluster. As mentioned earlier, there is also another type of clustering algorithms: *soft clustering*. In soft clustering, each observation is assigned to several clusters with associated probabilities.

In this checkpoint, you'll learn about a soft clustering algorithm called *Gaussian mixture models* (GMM). This algorithm belongs to a general class of probabilistic clustering algorithms.

The main advantages of GMM are as follows:

* It's a soft clustering algorithm. So, you can assess the confidence of the cluster assignments by investigating the probabilities.
* It doesn't assume anything about the geometry of the clusters, unlike k-means. So, it can also tackle nonlinear geometries.

<jupyter notebook-name="6.gmm" course-code="DSBC"></jupyter>

For a screencast demo of the techniques covered here, check out the below video.


<iframe id="kaltura_player_1604766026" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604766026&entry_id=1_020itecy" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>




## Assignment

In this assignment, you'll continue working with the [*heart disease* dataset](http://archive.ics.uci.edu/ml/datasets/Heart+Disease) from the UC Irvine Machine Learning Repository.

Load the dataset from Thinkful's database. To connect to the database, use these credentials:

```
postgres_user = 'dsbc_student'
postgres_pw = '7*.8G9QH21'
postgres_host = '142.93.121.174'
postgres_port = '5432'
postgres_db = 'heartdisease'
```

The dataset needs some preprocessing. So, before working with the dataset, apply the following code:

```python
# Define the features and the outcome
X = heartdisease_df.iloc[:, :13]
y = heartdisease_df.iloc[:, 13]

# Replace missing values (marked by `?`) with a `0`
X = X.replace(to_replace='?', value=0)

# Binarize y so that `1` means heart disease diagnosis and `0` means no diagnosis
y = np.where(y > 0, 1, 0)
```
Here, `X` will represent your features and `y` will hold the labels. If `y` is equal to `1`, that indicates that the corresponding patient has heart disease. And if `y` is equal to `0`, then the patient doesn't have heart disease.

To complete this assignment, submit a link to a Jupyter Notebook containing your solutions to the following tasks below. You can also take a look at these [example solutions](https://github.com/Thinkful-Ed/data-201-resources/blob/master/clustering_module_solutions/6.solution_gmm.ipynb).

1. Apply GMM to the *heart disease* dataset by setting `n_components=2`. Get ARI and silhouette scores for your solution and compare it with those of the k-means and hierarchical clustering solutions that you implemented in the previous checkpoint assignments. Which algorithm performs best?
2. GMM implementation of scikit-learn has a parameter called `covariance_type`. This parameter determines the type of covariance parameters to use. There are four types that you can specify:

    - `full`: This is the default. Each component has its own general covariance matrix.
    - `tied`: All components share the same general covariance matrix.
    - `diag`: Each component has its own diagonal covariance matrix.
    - `spherical`: Each component has its own single variance.
    
Try all of these. Which one performs best in terms of ARI and silhouette scores?
