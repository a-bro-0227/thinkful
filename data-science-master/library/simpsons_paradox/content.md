---
title: Simpson's paradox
author: Thinkful
team: grading
time: 60 minutes
uuid: 6737e511-e0a5-48ab-bb90-581556bb5b5d
timeHours: 1
---

Imagine that you're analyzing gender differences in a university's admissions rate for graduate programs. You compute the proportion of successful female applicants and compare it to the proportion of successful male applicants, and you get the following numbers:

|       | **Applicants** | **Admitted** |
| ----- | -------------- | ------------ |
| Men   | 8,442          | 44%          |
| Women | 4,321          | 35%          |

Overall, women are less likely to be admitted to graduate programs at that university than men. Intrigued, you dig deeper and compute the proportion of successful applicants of each gender for each graduate program separately. Then you get the following numbers. (The higher percentage for each department is bolded.)

| **Department** | **Male applicants** | **Male admitted** | **Female applicants** | **Female admitted** |
| -------------- | ------------------- | ----------------- | --------------------- | ------------------- |
| A              | 825                 | 62%               | 108                   | **82%**             |
| B              | 560                 | 63%               | 25                    | **68%**             |
| C              | 325                 | **37%**           | 593                   | 34%                 |
| D              | 417                 | 33%               | 375                   | **35%**             |
| E              | 191                 | **28%**           | 393                   | 24%                 |
| F              | 373                 | 6%                | 341                   | **7%**              |

When broken down by department, women appear to have the same or a slightly better chance of being admitted than men—exactly the opposite of what you observed above. At this point, you may start checking your code for errors, but there's no need. This data, drawn from evidence presented in a [1975 article about gender bias in Berkeley graduate admissions](http://homepage.stat.uiowa.edu/~mbognar/1030/Bickel-Berkeley.pdf), is a classic example of Simpson's paradox.

*Simpson's paradox* is the phenomenon when an average over several groups shows one trend, but an average for each individual group shows the opposite trend or no trend. Another name for Simpson's paradox is the *lurking variable problem*, where an unaccounted-for third variable changes the relationship between two other variables.

In the case of Berkeley, the third variable is the total number of men and women who applied to each program. Looking at the numbers above, many more men than women applied to programs A and B, which had high admittance rates. Women were more likely to apply to the programs with low admittance rates. This means that overall, a man had a greater chance of being admitted not because he was a man, but because he was more likely to apply to a program that admitted a high percentage of its applicants.

Another example involves [changes in the median wage](https://economix.blogs.nytimes.com/2013/05/01/can-every-group-be-worse-than-average-yes/?_r=0). From 2000 to 2013, the median wage rose slightly. Yet during the same period, the median wage for every educational group (high school dropouts, high school graduates, college graduates, and so on) went down. The lurking variable here is demographic changes in the United States over that period—a greater proportion of Americans had college degrees in 2013 than in 2000. Since people with college degrees get paid, on average, more than people with only a high school diploma, the overall median wage could rise for the population even as it dropped for each group.

The lesson of Simpson's paradox is this: pay attention to how groups differ from one another before averaging across them. Averaging a small group with a large one, or averaging multiple groups with very different demographics, can produce unexpected or illogical results.

## Think like a data scientist

When you're doing A/B testing, hopefully, all your participants will have an equal chance of being assigned to see version A or version B, and both your groups will be equal in size. By using randomization to equalize lurking variables like demographics, you can avoid Simpson's paradox. Because randomization is random, however, there is always the chance that your groups will end up with some lurking difference.

Before interpreting your results, always do what you can to confirm that the groups are similar. Make it a habit to look at subgroups within your A/B test to make sure that the overall trend is reflected in the subgroups. If the subgroups differ from the overall trend, your question should guide whether you report conclusions based on the overall sample, the subgroups, or both. You don't want to advocate for condition A, even if it performs better overall, if condition B actually works better within every subgroup!

For a deep dive into the data underlying Simpson's paradox, check out [this Technical Report from UCLA](http://ftp.cs.ucla.edu/pub/stat_ser/r414.pdf).
