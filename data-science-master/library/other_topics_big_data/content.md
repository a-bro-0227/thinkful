---
title: What is big data?
author: Thinkful
team: grading
time: 80 minutes
uuid: 84ac7bbe-3a5c-42ee-8ce5-f6837a927532
timeHours: 1.3333333333333333
---

So what is big data?

The answer depends on who you ask. But a general rule of thumb is that the more experience that someone has working with data and modern techniques, the larger a dataset has to be to qualify as big data.

For some people, big data is anything that's too big for Excel. You can't really look at it in its raw form and learn much. You can't count the number of rows yourself. But from your perspective, and that of people who work with programming languages like Python or R by default, that isn't an interesting definition.

Here's a far more functional and modern definition: big data is data that's too large to work with on a local machine. Note that this doesn't include when a database is too large to clone to a local machine because it has too much data to *store* on your local hard drive. Instead, it's when data that you want from a database is too large to even *work* with on your local machine. 

So how big is that?

It's at least gigabytes of data. That can be millions of rows. Often, it gets into terabytes and billions of rows. It can easily push higher than that. If you're getting into petabytes or exabytes, you're likely working with some really specialized machines. There's no chance that will all be on your local machine.

## Issues with big data

When data gets that big, several issues start to arise.

Firstly, getting the data itself becomes more complicated. You have massive amounts of data that the simple methods that you've used previously wouldn't work. Even single-job SQL, where one processor is searching through the tables to gather your data, is often too slow. Luckily for you, there is a whole set of resources to help you access your data and get it into a usable form. You'll learn about *Hadoop*, some of the infrastructure designed for this, in the next assignment.

Here, it will be assumed that the act of designing a storage system for this falls into data engineering, rather than data science. Your job as a data scientist is to access, manipulate, analyze, and interpret the data once it is stored. Keep in mind, though, that not everyone distinguishes between data engineering and data science, particularly in smaller companies.

You also have to be able to understand what's going on with that data. This is where visualization and summary statistics will come in handy. You've learned about these tools already in this program, but it is worth mentioning that when you're working with truly *big* data, the way that you think about it may change. For example, you've learned about outliers before. But when you're trying to handle millions or billions of observations, there could be thousands of outliers—or even more!

How you might visualize that is something worth considering, though there is no "right" way. But you have to be aware that every visualization simplifies or glosses over some data in some way, and that effect could be magnified when you're working with big data. It can have real implications for your analysis. You won't explore this further in this checkpoint, but it is an important principle to keep in mind.

Lastly, training a model on a massive amount of data is difficult. There are huge advantages to using a large amount of data to build models. For some classes of models, particularly neural networks, a large volume of data can be essential to getting meaningful performance. But again, if you can't bring it all onto your machine, what's a data scientist to do? Or, if it's too slow to work with it all at once, how can you build a model faster? There is a set of tools designed to deal with that as well, and you'll learn about those tools in an upcoming checkpoint.

All of these checkpoints are only introductions to these tools, giving you the vocabulary to port some of your knowledge from previous modules to this framework. This is an ever-evolving sphere of data work that is often specific to the company or infrastructure that you end up working with. Depending on your role, you may need to become more familiar with some of these tools and concepts, should your job ultimately require this complex work.

For a visual overview of how big data works, check out the below video.

<iframe id="kaltura_player_1604701469" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604701469&entry_id=1_g1nmhvyu" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>