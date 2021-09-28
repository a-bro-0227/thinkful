---
title: Hadoop and big data storage
author: Thinkful
team: grading
time: 60 minutes
uuid: 55a0a578-668f-434b-aeba-db6a871197a9
timeHours: 1
---

So, you're working somewhere with a lot of data, but what tools are you going to need? Chances are, you're going to be using Hadoop.

In this program, the term *Hadoop* will refer to the larger environment of Hadoop-based software that is used for storing, moving, and analyzing big data under a unified framework. As such, there will be several different components that you'll learn about, but they will only be part of the picture. Specifically, you'll focus on the parts that are touched or used for model-building and analytics, and you'll ignore much of the infrastructural backend. If you're going to be building this kind of infrastructure or just want more details about it, check out [Hadoop's web page](http://hadoop.apache.org/), which lists Hadoop and several associated projects.

## Key components

*Hadoop*, sometimes called a *Hadoop cluster*, has four core components.

Two of them aren't very interesting from a data science perspective (assuming that you're not maintaining the cluster). Commons is the utilities structure for Hadoop. But you're a data scientist, so utilities will typically be handled for you by a data engineer. YARN is a scheduling and resourcing tool.

HDFS, or *Hadoop Distributed File System* (there's that word, *distributed*), is where the data in Hadoop actually lives. This is a distributed data store with fast-access tools. Functionally, what this means is that instead of all the data being stored on a single machine and a single drive, it is distributed across many. This has advantages in both stability (one machine goes down and the world does not end) and speed of access.

MapReduce, the final component and the basis of the Hadoop project as a whole, is a data-processing tool for distributed systems. But usually, data scientists use tools like PIG for pulling raw data from HDFS or other large-form data stores. PIG is functionally the same as MapReduce, but it has an easier-to-use interface; it's more querying based than the original MapReduce. PIG looks a little like SQL, and the challenges of navigating data with it usually have more to do with the internal data model and structures than PIG itself.

## Other pieces

Though it is important to understand a bit of this aforementioned Hadoop architecture, as a data scientist, you won't actually be working with those tools most of the time. (One possible exception is PIG, which executes jobs in a language called Pig Latin.) That's because the data will usually be set up with a querying layer. In the case of Hadoop, the querying layer is typically Hive. It could also be something like Presto, and you could accomplish a lot of the same goals with a PIG script.

Querying is a nice, easy way to access huge amounts of data, get only what you want, and bring it to your local machine or keep it on a separate server. You learned about queries in PostgreSQL earlier in this program. Hive allows you to use those same tools and structures for large datasets in HDFS. It even has its own SQL-like querying language called HiveQL.

So, what are the differences between HiveQL and PostgreSQL?

A major difference is speed. HiveQL is slow. Part of this is a function of the size of the dataset, but it also is just generally pretty slow software. It's not uncommon for Hive queries to run over the course of hours or even days. Again, there are faster tools for accessing data in HDFS, particularly Presto, or using other database types (such as Redshift and Vertica). But these can require more hardware and are generally much more expensive.

Otherwise, the differences are very minor from a user perspective. (From an engineering perspective, the distributed nature of working on a distributed dataset is a huge difference.) Engineers have done a lot of work to make distributed data work feel as similar as possible to local work. There is slightly different syntax around joins; you have to specify if the join is outer using [left and right joins](https://cwiki.apache.org/confluence/display/Hive/LanguageManual+Joins). The syntax around datetimes is also a little different; every SQL language seems to have slight variations around how it uses time.

For a screencast demo of the techniques covered here, check out the below video.


<iframe id="kaltura_player_1604766288" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604766288&entry_id=1_hmujg0oo" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>
