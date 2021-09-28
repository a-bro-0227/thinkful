---
title: K-means
author: Thinkful
team: grading
time: 80 minutes
uuid: 45fcd007-806f-4ebc-bd23-cff943109d22
timeHours: 1.3333333333333333
---

In this checkpoint, you'll begin your exploration of *clustering algorithms*. Clustering is all about organizing individual examples or observations into groups, such that individuals in each group resemble fellow group members more than they do nongroup members. This requires the ability to measure similarity.

You'll start by exploring the go-to, off-the-shelf algorithm for clustering data: the *k-means algorithm*.

## The k-means algorithm

K-means is an iterative algorithm that eventually converges on a solution. The basic idea in k-means is to find the best *k* points that form the centers of each of the *k* clusters. These points are called *centroids*. The algorithm begins by choosing *k* observations at random and making these observations the initial centroids. Then it iterates over the following two steps: 

1. Assign each data point to its nearest centroid.
2. Create new centroids by taking the mean of all of the data points assigned to each centroid.

The algorithm stops when the difference between the old and the new centroids is lower than a given threshold value.

The gif below illustrates how k-means works:

![k-means gif](kmeans.gif)

In mathematical terms, the algorithm above works as an optimization process. From the optimization point of view, k-means tries to minimize its loss function. The loss function of the k-means algorithm is called the *inertia*, and the k-means algorithm tries to find the means (*centroids*) that minimize the inertia.

The graph above and to the right illustrates how effective the *elbow method* can be when using inertia to identify the optimal number of clusters that can be used in k-means. Simply put, when the inertia begins to decrease linearly (the point where an "elbow" is formed), this is the optimal number of clusters. If you recall the lesson on linear regression, this description for inertia may sound familiar to you.

<jupyter notebook-name="2.kmeans" course-code="DSBC"></jupyter>

## Assignment

To complete this assignment, submit a link to a Jupyter Notebook containing your solutions to the following tasks below. You can also take a look at these [example solutions](https://github.com/Thinkful-Ed/data-201-resources/blob/master/clustering_module_solutions/2.solution_kmeans.ipynb).

1. Your task is to apply k-means to the *iris* dataset and see what happens when you change the value of *k*. Which solution, if any, do you find most compelling? Does complexity start to become an issue with this dataset? Play around a bit and write up your findings and your process. Keep in mind that you may find a solution with more than three clusters that nevertheless better tracks the real, trinary outcome. For example, two of those clusters may map to a single flower type, while the other two map to the other types.
2. In this assignment, you'll be working with the [*heart disease* dataset](http://archive.ics.uci.edu/ml/datasets/Heart+Disease) from the UC Irvine Machine Learning Repository.

    1. Load the dataset from Thinkful's database. To connect to the database, use these credentials:
 
        ```
        postgres_user = 'dsbc_student'
        postgres_pw = '7*.8G9QH21'
        postgres_host = '142.93.121.174'
        postgres_port = '5432'
        postgres_db = 'heartdisease'
        ```
 
    2. The dataset needs some preprocessing. So, before working with the dataset, apply the following code:

        ```python
        # Define the features and the outcome
        X = heartdisease_df.iloc[:, :13]
        y = heartdisease_df.iloc[:, 13]
    
        # Replace missing values (marked by `?`) with a `0`
        X = X.replace(to_replace='?', value=0)

        # Binarize `y` so that `1` means heart disease diagnosis and `0` means no diagnosis
        y = np.where(y > 0, 1, 0)
        ```
        Here, `X` will represent your features and `y` will hold the labels. If `y` is equal to `1`, that indicates that the corresponding patient has heart disease. And if `y` is equal to `0`, then the patient doesn't have heart disease.

    3. Create a k-means solution that correctly assigns patients to *heart disease diagnosis* or *no heart disease diagnosis* clusters. Note that in this case, you actually know the correct number of clusters in the data (two). But you'll test whether k-means assigns observations as you expect it to. Because k-means is an unsupervised learning algorithm, it will be blind to whether or not the patients have heart disease.


For a screencast demo of the techniques covered here, check out the below video.



<iframe id="kaltura_player_1604765732" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604765732&entry_id=1_t4g98h0i" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>
