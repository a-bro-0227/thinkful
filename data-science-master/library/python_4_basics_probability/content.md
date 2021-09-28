---
title: Basics of probability
author: Thinkful
team: grading
time: 240 minutes
uuid: 282c03c3-e803-4dea-adaa-fa1f1d1deccb
timeHours: 4
---

> "It is remarkable that a science which began with the consideration of games of chance should have become the most important object of human knowledge." —Pierre Simon Laplace, *Théorie Analytique des Probabilités*, 1812

One of the reasons that data science is in such high demand is because organizations want to predict the future. With the right dataset, a data scientist can create models that give information about how likely certain outcomes will be. Those models help organizations steer toward desired outcomes, turn away from negative ones, and create successful businesses.

To accurately predict, you need to be able to apply basic principles from probability. You'll learn about those in this checkpoint as you explore the following topics:

- Frequentist versus Bayesian approaches
- Randomness
- Sampling
- Selection bias
- Independent versus dependent events
- Bayes's rule

This checkpoint ends with a set of drills where you'll apply what you've learned.

## Perspectives on probability: Frequentist versus Bayesian

Probability is a way of quantifying the likelihood of a future outcome. People use probabilities to make decisions all the time. Knowing the probability of rain tomorrow, for example, can help you decide whether to put the rain boots and umbrella in the car tonight.

There are two broad schools of thought about probability in statistics. The *frequentist* school of thought defines probability as describing how often a particular outcome would occur in an experiment if that experiment were repeated over and over. For example, each time a coin is flipped, the outcome is either `1` (heads) or `0` (tails). Each coin flip is an "experiment" with an outcome. Over many coin flips, the coin will come up heads about 50% of the time. For a frequentist, saying that an outcome has a 50% probability is equivalent to saying that if the experiment were repeated many times, that outcome would occur 50% of the time.

The *Bayesian* school of thought defines probability as describing how likely an observer expects a particular outcome to be in the future, based on previous experience and expert knowledge. Each time the experiment is run, the probability is updated if the new data changes the belief about the likelihood of the outcome. The probability based on previous experiences is called the *prior probability*, or the *prior*, while the updated probability based on the newest experiment is called the *posterior probability*.

Both Bayesian and frequentist approaches to probability are used to model data, depending on the question being asked. Disagreements between the two camps can [get](https://xkcd.com/1132/) heated, but there's no need to take sides: most of the time, the Bayesian and frequentist approaches arrive at the same answer. Here's a good way to think about each approach: Frequentists are trying to calculate the likelihood of getting the data that you have in the context of a fixed, if unknown, "true" population value. Bayesians are trying to calculate the most likely population value, given the data that you have. As the data changes, Bayesian beliefs about the population value change as well.

For a more in-depth discussion with complex examples of how frequentist and Bayesian approaches can be used to answer a question, including code in Python, see this [series of articles](http://jakevdp.github.io/blog/2014/03/11/frequentism-and-bayesianism-a-practical-intro/) by data science writer Jake VanderPlas.

## Randomness, sampling, and selection bias

The concept of probability is fundamental to data science. A lot of the value that a data scientist brings comes from the ability to *quantify uncertainty*—to go from a vague and woolly "maybe it will rain" to a clear and precise "65% chance of rain with a margin of error of 3%." Quantified uncertainty not only defines what is known; it also specifies how confident you can be about that knowledge.

Probability is also the fundamental basis of another critical element of the data scientist's toolkit: *randomness*. Randomness can be defined as the apparent lack of pattern or predictability in events. A random sequence of events, symbols, or steps often has no order and does not follow an intelligible pattern or combination. Individual random events are, by definition, unpredictable. But because they often follow a probability distribution, the frequency of different outcomes over numerous events (or *trials*) is predictable.

It is rarely possible to gather data from all elements of a population of interest. For example, you can't get questionnaires to *all* potential customers around the world, or vital health statistics for each citizen of a country. Instead, data scientists leverage the concept of randomness to gather a representative sample from the population. Using randomness, each element of a population has an equal chance of being chosen for the sample.

In an ideal world, *random sampling* creates a smaller group (a *sample*) that is sufficiently similar to the population that anything that you learn about the sample also applies to the population. Larger samples are more likely to resemble the population because they are less swayed by the occasional extreme value. On the other hand, smaller samples may be cheaper and faster to collect. Deciding how large a sample to collect depends in part on how variable you think the population is. The more variability there is in the population, the larger the sample that you'll need to get to be confident that your sample is a good stand-in for the population. However, it is important to keep in mind that the sample is *random*: it may, through sheer dumb luck, sample enough unusual individuals to be unrepresentative.

In practice, random sampling depends on perfect access to the population, which is very rarely possible. When studying customers, for example, not all customers may be interested in or willing to participate in data collection. The sample, in that case, differs from the population of all customers: the customers in the sample are all people who are willing to be studied. Systematic differences between the sample and the population are known as *selection bias*. If the sampled individuals differ from the others in important ways, such as spending rates or purchasing behavior, the knowledge gained from their data might not apply to all customers.

### Selection bias: A practical example

An example from US history illustrates the pitfalls of generalizing from a biased sample. The 1936 US presidential election pitted Alfred Landon against Franklin D. Roosevelt. The largest preelection poll of the time, conducted by the respected magazine *Literary Digest*, projected that Landon would beat Roosevelt by 14%. This projection was based on ballots sent to 10 million US citizens—nearly a quarter of all eligible voters at the time. Yet the *Literary Digest* turned out to be impressively wrong, with Roosevelt beating Landon by 24%. The poll was off by an astounding 38%. How did this happen?

The *Literary Digest*'s sampling efforts, though broad, were flawed: they sampled people by drawing from the telephone directory. But in the middle of the Great Depression, phones were luxuries that many could not afford. The Digest's methods led to a sample that was considerably older and richer than the general population—with predictable results for their election forecast. When it comes to sampling, it is better to have a small but representative sample than a large and biased one.

For more details on the Literary Digest poll, see [this case study](https://www.math.upenn.edu/~deturck/m170/wk4/lecture/case1.html).

## Dependent versus independent events

When talking about probabilities of events, whether Bayesian or frequentist, it's important to consider whether the events are independent or dependent on one another. An event is independent of other events in the sample space if the outcome of that event is not affected by the outcome of other events in the sample space. 

For example, imagine a bag of ten marbles, with five blue marbles and five red marbles. Without looking, you reach into the bag and draw out a red marble. Then you put the marble back in the bag and draw a blue marble. The probability of drawing a red marble first is 5/10, or 50%. The probability that the second marble will be blue is also 5/10, or 50%. Because you put the first marble back, the probability of drawing the second marble is independent of the first. Neither event affects the other.

Here's the probability of drawing and replacing a red marble:


    P(red) = 1/2

`P` in the formula above means *probability*.

And here's the probability of drawing and replacing a blue marble after drawing and replacing the red marble:


    P(red) = P(blue) = 1/2

The probability of two or more independent events can be calculated by multiplying the probabilities of each individual event. Here's the probability of drawing a red marble and then a blue marble:


    P(red ∩ blue) = P(red) * P(blue) = (1/2) * (1/2) = 1/4

When the probability of event B changes based on the outcome of event A, the probability of event B is said to be dependent on, or *conditional* on, event A. Returning to the bag of marbles, again you reach into the bag and take out a red marble. Again, the probability that the first marble will be red is 5/10, or 50%.


    P(red) = 1/2

Next, without replacing the red marble, you draw a blue marble. Now, the probability of drawing a blue marble depends on the color of the first marble drawn. The character `|` is used to denote a condition on the probability that you're talking about. This is where the information that you already have can be disclosed.

If the first marble was blue, then the probability of drawing a red marble the second time is 5/9 (because one blue marble is missing from the bag).


    P(red | blue) = 5/9

You can read the `|` symbol as "given", so `P(red | blue)` would read "the probability of red given blue".

If the first marble was blue, then the probability of drawing a blue marble the second time is 4/9 (because one blue marble is missing from the bag).


    P(blue | blue) = 4/9

The probability of drawing a blue marble the second time is conditional on the outcome of the first draw.

The probability of two conditional events can be calculated by multiplying the probability of event A by the probability of event B conditioned on A.


    P(A ∩ B) = P(A) * P(B | A)

Here's the probability of drawing two blue marbles in a row without replacement:


    P(blue) * P(blue | blue) = (1/2) * (4/9) = 2/9

And here's the probability of drawing a red marble and then a blue marble without replacement:


    P(red) * P(blue | red) = (1/2) * (5/9) = 5/18

In data, conditional variables in a dataset contribute less information than independent variables, because some information is duplicated among conditional variables. For example, a survey may ask four questions:
1. A customer's age
2. Their income
3. Whether they bought any widgets that month
4. How much money they spent on widgets that month

###### *Conditional* and *dependent* are synonymous. However, because *dependent variable* has a specific meaning in experimental design, *conditional* will be used here when referring to variables.

The age and income variables are independent in the sample space. Although knowing someone's age may give some hints about their income, there is enough variability in incomes between people of the same age that every data point is giving new information. Similarly, although the income variable is probably related to how much money people have available to spend on widgets, people with the same income may buy different quantities of widgets (or no widgets at all). So each data point provides new information for both variables.

Questions three and four, on the other hand, are conditional. If someone says that they didn't buy any widgets in the last month, you *already know* that they spent $0 on widgets. Conversely, if someone says that they spent $0 on widgets last month, you *already know* that they didn't buy any widgets. The two variables aren't perfect duplicates, because knowing that someone did buy one or more widgets isn't the same as knowing how much money they spent. But for at least some cases, knowing the answer to question three means that you can be 100% certain that you know the answer to question four (and vice versa).

## Bayes's rule and conditional probability

On a random day, you see a pop-up clinic for an instant test for a new disease that you've heard of: Weapon X. It's an incredibly rare disease with almost no symptoms for months, and then it suddenly becomes fatal. It's affecting about one in a million people, from what you've heard. This test says it's 99.99% accurate in both directions (false positives and false negatives), so you decide that it's worth taking the test.

It comes back positive.

Should you panic?

*Bayes's rule* explains that, in actuality, you're probably just fine.

In this scenario, you're not focused on the probability of an independent event. It's not the probability that you are infected with Weapon X. It's the probability that you're infected *given the condition* that you get a positive test.

That positive test provides additional information about what's going on, and you can use that information to improve your probability estimate.

For this example, imagine that you have a million people. The chances are good that one of them is infected, since the disease affects one in a million, and that person will likely get a positive test result. However, if you tested every one of those other 999,999 people, you'd expect about 100 people to get positive results.

Once you see that positive test, what do you know about your likelihood of being infected? Since you know that you have a positive test, you can consider only the people in that group who have seen a positive test result. In that group are 101 people, and only 1 of them actually has the infection. This works out to roughly a 1% chance that you're infected.

Now, these counts are a bit of a simplification, because they use expected counts rather than probabilities. Bayes's rule gives you this relationship in terms of probabilities.

### Bayes's rule

Bayes's rule can be put in its simplest and most abstract terms as follows:

    P(A | B) = P(B | A) * P(A) / P(B)
    
Or
    
    P(A | B) = P(B | A) * P(A) / [P(A)*P(B|A) + P(A~)*P(B|A~)]

In English, this formula says that the probability of `A` given `B` equals the probability of `B` given `A`, times the probability of `A`, divided by the probability of `B`. The second formula expands the probability of `B` where `A~` is the inverse of `A`—so in this case, not being infected. The numerator is the scenario of interest, while the denominator represents the realm of scenarios that could give the condition.

You can put that in terms of the example pretty simply:

    P(Infected| Positive Test) = P(Positive Test| Infected) * P(Infected) / P(Positive Test)
    
    = .9999 * .000001/(.000001*.9999 + .999999*.0001) = .0099 or .99%

So that says that there's less than a 1% chance that you're really infected—which is still reasonably unlikely.

This may seem like a detached example, but it does happen. In general, people can be very bad at this kind of probabilistic reasoning. For example, clinics in New York and San Francisco stopped using a rapid HIV test [because it was scaring healthy people](http://www.nytimes.com/2005/12/10/health/false-positives-from-hiv-test.html?_r=0). It's why a lot of these tests get run multiple times before their results are given. If a test result suggests that an individual has a rare disease, the first response is usually to run it again.


## Illustrated examples

### Bayes's rule: An illustrated example

Equations are great, but so are animated visualizations! To see Bayes's rule in action, check out [this interactive simulation](https://seeing-theory.brown.edu/bayesian-inference/index.html#section1) from the textbook [Seeing Theory](https://seeing-theory.brown.edu). 

What happens when you increase the prior probability of the event or type I and II errors?

<iframe src='https://seeing-theory.brown.edu/bayesian-inference/index.html#section1' frameborder="0" height='500px' width="100%" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

### Frequentist inference: An illustrated example

Next, take a look at an animated example for frequentist inference.

<iframe src='https://seeing-theory.brown.edu/frequentist-inference/index.html' frameborder="0" height='500px' width="100%" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

## Video: Basics of probability

Last but not least, check out the below video, which reviews the basics of probability.

<iframe id="kaltura_player_1604698541" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604698541&entry_id=1_eggllbs2" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>
