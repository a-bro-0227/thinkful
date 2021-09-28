---
title: Spark streaming with network traffic data
author: Thinkful
team: grading
time: 160 minutes
uuid: 06b626c9-cf98-48af-90c2-a2b77e8dd1fa
timeHours: 2.6666666666666665
---

Now that you have worked through some examples with batch data, it's time to turn your attention to Spark Structured Streaming. Your goal here is to stream and process data in real time with Spark. There are a ton of streaming data sources out there, such as Foursquare, Twitter streaming, Citibike data, and NYC MTA train arrivals. Those are all excellent data sources, and you'll get an opportunity to work with one of them—Foursquare's API—in the next checkpoint.

But, as you're first learning about streaming, keep in mind the first problem of using real-time data: how can you really know that you have your data right? You need a static baseline to compare your streaming analysis against to ensure that you get properly formatted incoming data, thus ensuring data integrity. Benchmarking the streaming data against a baseline is the hardest part of streaming correctly.

To that end, you actually won't do much heavy lifting on the machine-learning side of things to start with. Your first analysis will be relatively simple. You'll explore streaming data by working with a small subset of the *Unified Host and Network* dataset from Los Alamos National Lab. This dataset contains data about internet traffic. First, you'll do a static analysis of this data to get a baseline result, and then you'll rerun the analysis by streaming that same data in Colab. This will prepare you to work with real-time streaming data in the next assignment.

As with the introduction to batch processing, you'll start by learning the background and context that you need about the data and approach here. Then you'll walk through an example in a Jupyter Notebook that is provided in your [big data student resources directory](https://github.com/Thinkful-Ed/big-data-student-resources).

## Background on streaming

Before you start, it's a good idea to read through the following articles:

* [Structured Streaming in Apache Spark](https://databricks.com/blog/2016/07/28/structured-streaming-in-apache-spark.html)
* [Spark Streaming Programming Guide](https://spark.apache.org/docs/latest/streaming-programming-guide.html)

These resources will give you a sense of how you can use streaming; you'll learn about its advantages as well as some of the challenges that you'll face. Make no mistake: streaming can be hard to get right! This walkthrough will be challenging, but worth it.

## The  *Unified Host and Network* dataset from Los Alamos National Lab

Los Alamos has posted a huge amount of network data online in [CSV files](https://csr.lanl.gov/data/2017/)). For the purposes of this walkthrough, the original dataset is way too large. To make things manageable, the Thinkful team took a small subset of the data—only about 2.5 minutes worth, comprising around 500,000 flows—and split it up into a series of 50 JSON files. JSON was chosen because that's the most common format for streaming data. This will allow you to simulate streaming real-time data by treating each of the 50 JSON files as a separate stream object. Each entry in the dataset represents a "conversation" between two computers. For each entry, the following fields are captured:

* `Time`: The start time of the conversation (in a proprietary time-stamp format)
* `Duration`: The length of the conversation (in seconds)
* `SrcDevice`: Name of the device that initiated the conversation
* `DstDevice`: Name of the device that was requested
* `Protocol`: Network protocol used (such as TCP or UDP)
* `SrcPort`: Network port (0-65,536) on the originating device
* `DstPort`: Network port (0-65,536) on the destination device
* `SrcPackets`: Network packet count sent from the source to the destination
* `DstPackets`: Network packet count sent from the destination to the source
* `SrcBytes`: Byte count sent from the source to the destination
* `DstBytes`: Byte count sent from the destination to the source 

As you can see, there's a lot here. However, you'll try to answer a relatively simple question: from this data, how many web servers can be identified?

## Identifying web servers

To answer this research question, you'll rely on some basic knowledge about network behavior. Web servers typically communicate on one of two ports: `8000` or `443`. So, if a computer requests one of those ports as the `dstPort` in a flow, it's likely that the destination device (`dstDevice`) is a web server. If you see that computer name come up repeatedly in your request list, then there's a good chance that the device is a web server. So for the streaming exercise, you need to build a count query that processes streams as they come in, updates the count of web servers, and then reports what it sees.

## Do the walkthrough

With that background out of the way, it's time to work through the *Spark_streaming* Notebook. As in the batch-processing walkthrough from before, you'll need to run this Notebook on Colab. To that end, you need to upload your Notebook to the *Colab Notebooks* folder. You also need to upload the data files directory (`datasets/lanl`) in the student repository to the *Colab Datasets* folder in your drive. Because there are 50 files in `datasets/lanl`, it is easier to upload the entire folder to *Colab Datasets* instead of uploading each file one by one in the *lanl* folder.


For a screencast demo of the techniques covered here, check out the below video.

<iframe id="kaltura_player_1604711343" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604711343&entry_id=1_f4ltl1lq" width="100%" height="506" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>