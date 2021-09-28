---
title: Analytic report and research proposal
author: Thinkful
team: grading
time: 20 minutes
uuid: f1c28169-b949-4665-b0e1-b659d760bdd1
timeHours: 0.3333333333333333
---

To consolidate all the skills you've learned so far, you'll now embark on completing your first capstone project, an *Analytic Report and Research Proposal* on a [dataset](https://docs.google.com/spreadsheets/d/1OlQr3g2RWn4KBSD9RP4i4LjRakXg4B8hAAP42cYCeiI/edit#gid=1716288019) of your choosing.

In this checkpoint, we'll go over the requirements for the capstone deliverable.


## Requirements

Your *Report* should accomplish these three goals:

 1. **Describe your dataset**. Describe and explore your dataset in the initial section of your *Report*. What does your data contain and what is its background? Where does it come from? Why is it interesting or significant? Conduct summary statistics and produce visualizations for the particular variables from the dataset that you will use.

 2. **Ask and answer analytic questions**. Ask three analytic questions and answer each one with a combination of statistics and visualizations. These analytic questions can focus on individuals behaviors or comparisons of the population.

 3. **Propose further research**. Lastly, make a proposal for a realistic future research project on this dataset that would use some data science techniques you'd like to learn in the bootcamp. Just like your earlier questions, your research proposal should present one or more clear questions. Then you should describe the techniques you would apply in order to arrive at an answer.

See this [analysis on 2016 celebrity deaths](https://medium.com/@jasoncrease/was-2016-especially-dangerous-for-celebrities-79d79b9fae02#.zd8hv5jge) for an excellent example of data-driven story telling that presents a problem, explores data, and produces an answer. The analytics are more robust techniques than we've covered so far, but the general idea and tone are spot on.

## Report guidelines

Keep these guidelines in mind as you draft your *Report*:

 * **Length**. Your *Report* should be three to five pages long with visualizations. Short and clear is better than long and [opaque.](https://en.wikipedia.org/wiki/Obfuscation#Eschew_obfuscation)
 * **Structure**. Pay attention to the narrative structure of your *Report*. Each section should flow into the next and make a logical, readable text. Don't simply create a list of bullet points or present code without explanation. 
 * **Format**. The best format for your *Report* is an interactive Jupyter Notebook `ipynb` file. However, you are welcome to use any format you like, so long as you're able to include visualizations and include (or link to) the code you use to generate your visualizations and summary statistics. If a Jupyter Notebook would be too much overhead or unduly distract you from creating good content, markdown files (hosted on GitHub or as a gist), blog posts, or even Word or Google documents are acceptable.


## Getting started

Your first step is choosing an interesting dataset to work with. This is [a good place to start to find something within scope](https://docs.google.com/spreadsheets/d/1OlQr3g2RWn4KBSD9RP4i4LjRakXg4B8hAAP42cYCeiI/edit#gid=1716288019). Before deciding on a particular dataset think about the kinds of questions you might be able to answer. Consider the format of the data. Do you know how to (or will you quickly be able to learn to) access and load it? Once you've chosen a dataset, write out some of those preliminary questions. Having them early will help guide your initial data exploration.

In order to conduct summary statistics and prepare visualizations you'll need to collect the data and load it into Python / pandas. Some of the data in the sources above will be in a format we didn't teach you to load in this fundamentals course. If necessary, refer to the [pandas I/O documentation](http://pandas.pydata.org/pandas-docs/stable/io.html).

Once you've loaded your data, dig around with pandas and matplotlib to explore it. What variables does your data contain and what distributions do you think they have? Does the data bear on the preliminary questions you wrote down? What new questions might you answer? How does the data look when you plot it out?

At this point you should be ready to start writing your *Report*. Decide what format to use, which three analytic questions you'll ask and answer, which research questions you'd like to ask and which data science techniques might be appropriate to answering them. 

You are encouraged to make use of every resource at your disposal in putting together your *Report*. Seek out [group sessions](https://www.thinkful.com/open-sessions/qa-sessions/), [Slack](https://thinkful.slack.com/messages/data-science/), and  technical coaches for help.
However, you should be ready to explain every decision, conclusion, and visualization you make and all of the code you write.