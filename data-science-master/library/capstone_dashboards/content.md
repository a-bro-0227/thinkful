---
title: 'Optional: Creating a dashboard'
author: Thinkful
team: grading
time: 8 hours
uuid: 12c150ba-d1e6-47d2-99a1-305f440506c4
timeHours: 8
---

This content will help you to implement an interactive dashboard for your capstone project. Dashboards, which consist of useful plots, a summary, and data tables, are a great way of presenting your results to your audience. A dashboard can display all the necessary information about your project in a condensed and effective manner. Moreover, the interactivity means that all users can play with the data and the associated graphs, so that they can get into your project by themselves.

A common use case for dashboards is to make critical information accessible to the executives of a company. Executives usually need to access information very quickly. So dashboards that summarize the operational outcomes of a company are usually invaluable and indispensable tools for management. 

Here you'll build an optional, *ungraded* interactive dashboard for your project. Your dashboard should include the following:

* Your data as a table. If your data is too large and you're having trouble putting all your data in the dashboard, then you can limit the size of the data that is displayed in the dashboard.
* Your charts from the exploratory data analysis part of your project
* The results of your models in a table

Note that this second optional part of this capstone is a learn-by-yourself task. That is, you need to dig into a new technology and make use of it all by yourself. This is a realistic real-life scenario. When you start to work in a company, you'll see that most of the time, you'll need to learn new technologies by yourself and apply them to your existing work. So, think of this second part as something that you need to do under the pressure of a strict deadline.

Below is a brief introduction to the *Plotly* library and its dashboard application *Dash*. Using these packages is recommended, but feel free to use another library if you find one that is more useful for you.

### Meet Plotly

One of the most popular interactive chart libraries is the *Plotly* library. [Plotly](https://plot.ly/) is essentially a JavaScript library, but it plays well with the Python ecosystem. To use it, you don't need to know JavaScript at all. Plotly is integrated quite well into Python; all you need to do is to write your code in Python, as you do when using Matplotlib and Seaborn.

You can install Plotly from your terminal (or command line) as follows:

```bash
pip install plotly
```

You can also install it from your Jupyter Notebook by running the following code in a cell:

```bash
!pip install plotly
```

If you haven't done so already, you may also need to install *ipywidgets* to run Plotly charts inside Jupyter Notebooks. You can install it as follows:

```bash
pip install ipywidgets
```

To find more information on how to install Plotly, visit [Getting Started with Plotly in Python](https://plot.ly/python/getting-started/). You can also find the documentation with examples of how to use Plotly at the [Plotly Python Open Source Graphing Library](https://plot.ly/python/#fundamentals). You may need to spend some time to learn the basics of the Plotly package. 

### Meet Dash

As stated earlier, Dash is the dashboard facility of the Plotly library. If you installed Plotly using the commands above, Dash comes with it already. You don't need to install anything separately. 

Dash is essentially a web application, but you don't need to learn the details of how to host a web application for the purpose of this capstone. All you need to do is to build a dashboard using Dash and host it on your local computer. You'll be using the open-source distribution of the Dash instead of the enterprise version. 

For a useful article that walks through an end-to-end Dash project, check out [How to Build a Reporting Dashboard using Dash and Plotly](https://towardsdatascience.com/how-to-build-a-complex-reporting-dashboard-using-dash-and-plotl-4f4257c18a7f).

Good luck!
