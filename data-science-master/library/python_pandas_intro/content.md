---
title: Introducing pandas
author: Thinkful
team: grading
time: 120 minutes
uuid: cb1bba2f-a15c-46af-ad1e-88f2b6b0ad56
timeHours: 2
---

Now that you know how to load data from a variety of sources, it's time to begin manipulating and analyzing data. Python comes with a rich set of libraries for data science and statistical computation. So rather than program everything yourself, you can rely on these excellent libraries to do much of the heavy lifting for you. But even before you can perform any sort of analysis, you need to represent the data in the memory of the computer in a way that's convenient to access. That is, you have to think about how you structure the data so that you can make meaningful references to parts of the data when you process it.

For example, when you have a table of data to perform some calculations on, you can use a spreadsheet. A spreadsheet has rows of data, numbered from 1 to however many rows of data you have. It also has columns, labeled A, B, C, and so on. This gives you a convenient way to refer to the data. For example, you can refer to the value in cell `A8`, or you can say, "Sum the values in column F and store the results in cell `G20`." You can perform operations like deleting a specific row or column, adding more rows and columns, and sorting and grouping. All of this is possible because of the arrangement of the data in the spreadsheet.

In Python, there are libraries that help you arrange the data in a similar fashion. The most fundamental data structure library is called *NumPy*, and it forms the basis for many other scientific computation libraries. The *pandas* library, which is built on top of NumPy, is another excellent library. Pandas makes use of *DataFrames*, which are a data structure similar to a spreadsheet.

<jupyter notebook-name="python_intro_pandas" course-code="DSBC"></jupyter>

For a visual recap of what you've learned about NumPy and pandas, check out the video below. 

<iframe id="kaltura_player_1590583295" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1590583295&entry_id=1_276npbll" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

