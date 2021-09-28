---
title: A/B testing
author: Thinkful
team: grading
time: 60 minutes
uuid: 27916d10-4041-4b07-9435-35e1da6d5d7e
timeHours: 1
---

In this checkpoint, you'll explore A/B testing, which is a common approach to identify which of two versions of some entity performs better with regard to a desired outcome.

## The ABCs of A/B testing

[There are lots of different possible experimental designs](https://cirt.gcu.edu/research/developmentresources/research_ready/experimental/design_types), but *A/B testing* is probably the most common in business and the one that you are most likely to encounter. A/B testing is a technique used to identify whether one version of an object of interest (such as a product, marketing campaign, or email text) is better at producing the desired outcome than another version.

The components of an A/B test are as follows:


- **Two versions** of something whose effects will be compared. Typically one version is a *control* version; this version is often already in use and represents what would happen given no intervention. The other version, the *test* version, has some changes from the control; those changes are often called the *treatment*. If you're starting from scratch, however, you may have two different test versions to compare to each other.

- **A sample** divided into two groups. Each sample should be selected so that it is similar to the population you want to understand. The groups should be similar to one another so that any differences between them can be attributed to seeing version A or version B and not something else. You also want the split between A and B to be as random as possible.

- **A hypothesis** that articulates what you expect to happen. For example, your hypothesis might be, "I expect that the HTML email will achieve a higher open and conversion rate than the plain-text email."

- **An outcome (or outcomes) of interest** and specific descriptions of what you expect will change as a result of using version A or version B, and how you will measure that change. This means that you have to decide on a *key metric*, which should capture the effect of your change and reflect the motivations for the test in the first place.

- **Other measured variables** including information about the two groups that can be used to ensure that they are similar, as well as secondary outcomes that are less important than the primary outcomes of interest but which might *also* change in response to using version A or version B.


## Getting a good sample

As mentioned above, one of the key elements of an A/B test is the sample. Particularly important when it comes to actually designing your own experiment is making sure that the two groups, group A and group B, are as comparable as possible. The only difference should be the treatment that they receive.

If you have a constantly occurring and easily randomizable test, where the thing that you're interested in measuring is happening all the time in easily separable occurrences, this is pretty straightforward. Marketing emails, for example, are usually like this. Thousands of emails are being sent out all the time, and you can easily randomize between A and B.

However, plenty of things can make this more complex. The most common challenge is a test that either has to be "all on" or "all off". This could be something like testing whether playing music in a shop makes people stay longer. You can't really create conditions where some people in a shop hear the music and others don't.

In that case, getting to randomization becomes an art form. You want to think about things like seasonality—making sure that there is no difference in your two groups because of the day of the week or the time of the year. Perhaps behavior is just different on weekends, at nights, or in the summer.


## Keys to key metrics

The other major sticking point is picking what you want to measure: your outcome. You can and should monitor many metrics during most tests—but you typically want to have one *key* metric that will be your determining factor for whether a test is successful or not.

There are several things that make a good key metric. First, you want it to be as closely related to your business goal as possible. For example, measuring clicks is good, but only if you'd rather measure the difference between actual sales versus just looking. Just because people engage doesn't mean that they'll follow through. This helps prevent getting a result that just affects an intermediate step without improving the actual goal. 

You also want your key metric to be reliably measurable. It seems obvious, but many experiments are ruined by measurement error. Ideally, this means something that is passively recorded, rather than requiring additional engagement from subjects or users. You also generally want to avoid self-reported data, because that invites its own host of potential biases.

As much as possible, you also want to capture the complete effect of your change. Sometimes, this may mean that time becomes important. Maybe an email campaign doesn't lead to an immediate increase in sign-ups, but customers convert later. Trying to include a window of impact that's both reasonable and consistent across all observations is a valuable characteristic for your metric.


## This is a test

Now, go through an example. If you were trying to improve the clickthrough rate of an email campaign, you might test two newsletters, one with *black italic text* and one with <span style="color:green">**bold green text**</span> and an exclamation point ("*Sale Today*" versus "<span style="color:green">**Sale Today!**</span>").

You would then randomly send one of the two versions of the email to a subset of subscribers to your newsletter. In this case, all subscribers who get an email represent your sample, and all subscribers who get the same version of an email represent one of your two experimental groups. Then, you would track the number of clicks that each version generated; this is your outcome of interest.

You expect that the bold green text will result in more clicks; this is your hypothesis. To make sure that the groups are similar, you may also want to look at the gender and age of your sample, if you have that information. You can also look at whether the two different newsletters affect how quickly people open the email after receiving it—a secondary outcome—as well as the click rate.

If the two groups appeared similar in age, gender, and anything else that you measured, but click rates were higher for the green bold text version of the newsletter, you would conclude that changing the text to be bold and green caused more clickthroughs. As a result, you would advocate for including green bold text in all future newsletters.


## Assignments

For each of the following questions, outline how you could use an A/B test to find an answer. Be sure to identify all five key components of an A/B test that were outlined above.

 * Does a new supplement help people sleep better?
 * Will new uniforms help a gym's business?
 * Will a new home page improve my online exotic pet rental business?
 * If I put "Please read" in the email subject, will more people read my emails?
