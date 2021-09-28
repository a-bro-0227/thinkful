---
title: Evaluating clusters
author: Thinkful
team: grading
time: 80 minutes
uuid: 3278d300-bab5-4279-82b9-eae52d19cf54
timeHours: 1.3333333333333333
---

You now have experience clustering data with k-means, but a key question remains: what is the right value for k?

To get to an answer to that question—and some others—you'll learn how to evaluate the performance of a clustering model in this checkpoint. Because this is unsupervised learning, you'll evaluate performance differently than you did with supervised learning models. Performance measures will help you understand what a good value for *k* is. It will also allow you to compare the performance of different clustering algorithms for the same k-value. 

<jupyter notebook-name="3.evaluating_clusters" course-code="DSBC"></jupyter>

For a screencast demo of the techniques covered here, check out the below video.


<iframe id="kaltura_player_1604765826" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604765826&entry_id=1_q5v7egxk" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>


## Assignment

To complete this assignment, submit a link to a Jupyter Notebook containing your solutions to the tasks outlined below. You can also take a look at these [example solutions](https://github.com/Thinkful-Ed/data-201-resources/blob/master/clustering_module_solutions/3.solution_evaluating_clusters.ipynb).

1. Get the silhouette coefficient of the two-cluster k-means solution. You'll notice that the silhouette coefficient will turn out to be greater than the one above, where the cluster number is three. You know that the *iris* dataset consists of three different clusters. So the silhouette score of the solution where the number of clusters is *equal* to the correct number of classes is actually lower than the silhouette score of the solution where the number of clusters is *different* from the correct number of classes. Can you explain why this is?

2. In this assignment, you'll continue working with the [*heart disease* dataset](http://archive.ics.uci.edu/ml/datasets/Heart+Disease) from the UC Irvine Machine Learning Repository.

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

    # Binarize `y` so that `1` means heart disease diagnosis and `0` means no diagnosis
    y = np.where(y > 0, 1, 0)
    ```
    Here, `X` will represent your features and `y` will hold the labels. If `y` is equal to `1`, that indicates that the corresponding patient has heart disease. And if `y` is equal to `0`, then the patient doesn't have heart disease.

    1. Split the data randomly into two. Apply k-means using two, three, and four as the number of clusters, as you did when you were exploring consistency earlier in this checkpoint. Assess the consistency of the solutions using visualization. Which one seems to be the best?
    2. Apply k-means on the whole dataset by setting `k` equal to `2`, `3`, and `4`. Get the ARI score for each of them. Which model is best?
    3.  Apply k-means on the whole dataset by setting `k` equal to `2`, `3`, and `4`. Get the silhouette coefficient for each of them. Which model is best?
