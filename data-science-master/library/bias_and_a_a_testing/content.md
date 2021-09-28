---
title: Bias and A/A testing
author: Thinkful
team: grading
time: 160 minutes
uuid: 45bab026-6ab4-4684-8185-1fd61bb64c27
timeHours: 2.6666666666666665
---

In experiments, *bias* refers to anything that causes a sample to systematically differ from the population. Bias can come from the sampling procedure, the assignment to conditions procedure, the context of the study, or the people running the study.

As you learned earlier in this program, *sampling bias* (or *selection bias*) is when a sample differs from the population in some way; for example, perhaps the sample has more women, skews either younger or richer, or has more outgoing people. As a result, conclusions based on that sample may not apply to the population. Selection bias can be avoided by choosing the sample randomly from the population.

*Bias in assignment to conditions* is similar to selection bias because it also represents a failure of randomness. In this case, the sample is supposed to be separated into groups that are similar to one another. The groups then each experience one of the study conditions. If the groups are the same before they go into the study, then any differences between the groups during the study must be due to the differences that you introduce as part of the experiment. This ensures that you can conclude that people in the population will react similarly to your experimental stimuli.

For example, imagine that you are comparing the effect of sprinkles on liking ice cream. One group is given ice cream with sprinkles, and one is given plain ice cream. Both groups rate how much they like the ice cream, and it turns out that the ice cream with sprinkles was liked more. If the groups are similar, then you can conclude that sprinkles *cause* people to like ice cream more. If the groups are different—for example, if the sprinkles group had an average age of 13, and the plain group had an average age of 30—then it isn't clear whether sprinkles cause liking, or whether younger people just like ice cream more. Conclusions about the effect of sprinkles on ice cream are biased by the difference in ages of the groups.

Bias can also come from the study *context*, or setting. Imagine that you have a great sample that is very similar to the population, and you divide them into two groups, called group 1 and group 2, who are very similar to one another. Then you separate the groups into two rooms and ask them to read and rate some ads for sodas. You are interested in how small differences between the ads seen by the two groups will affect members' reactions when they leave the rooms and then are offered a soda. To your surprise, members of group 1 overwhelmingly thank you for the soda and drink up immediately, while only half of group 2 accepts the soda. You conclude that the ads for group 1 must be better. Unfortunately, what you don't know is that the heater was broken in group 1's room, and the temperature was 90 degrees. This contextual factor biased your results. Not all sources of *contextual bias* are this obvious, but it underscores the importance of matching the setting for all experimental groups.

Finally, bias can come from the people running the study. This is a broad category, running the gamut from subtle signs to blatant interference. For example, during an interview, perhaps an interviewer smiles when the participants give answers that she likes, and frowns otherwise. Or perhaps an interviewer doesn't record answers that clash with the desired conclusion. *Observer bias* is tough to eliminate. The best way to avoid it is to make sure that the people who interact with study participants don't expect a particular result.


## A/A testing

Of these sources of bias, all but selection bias may be detectable using A/A testing.

*A/A testing* provides context for the results of A/B testing. As the name suggests, A/A testing means comparing the outcome of choice between two identical versions of something. This might seem rather silly—after all, if you divide all newsletter subscribers into two groups but send both groups the same email, you would expect that clickthrough rates for both groups would be identical. In practice, however, that doesn't always happen.

Why is this useful? A/A testing can identify problems with the following:

- **The testing method:** Perhaps all version 1 emails were accidentally set to go out in the morning when people are at work, while all version 2 emails go out in the evening when people have more leisure time to shop.  
- **The random split method:** Maybe the mailing list is arranged chronologically by date subscribed, and version 2 was sent to the first half of the list: the long-term customers who are more likely to click.  
- **The size of the sample:** The rarer the outcome, the bigger the sample is needed to get an accurate estimate of the response rate.  
- **Any other outside factors** that can affect the outcome of a test. 

In addition, if there are no bugs or problems, the size of the difference between groups in an A/A test can be used to define a threshold for subsequent A/B testing. That is, between-group differences that are smaller than the difference observed in the A/A test can be assumed to be due to chance.

## Assignments

For each of the following scenarios, call out the potential biases in the proposed experiment. Do your best to try to discover not only the bias, but the initial design. There is plenty of room for interpretation here, so make sure to state what assumptions you're making.

* You're testing advertising emails for a bathing suit company. You test one version of the email in February and the other in May.
* You open a clinic to treat anxiety, and you find that the people who visit show a higher rate of anxiety than the general population.
* You launch a new billboard-based ad campaign, and you see an increase in website visits in the first week.
* You launch a loyalty program, but you see no change in visits in the first week.
