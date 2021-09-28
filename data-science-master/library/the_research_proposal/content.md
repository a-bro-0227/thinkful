---
title: The research proposal
author: Thinkful
team: grading
time: 80 minutes
uuid: de3eb101-2eb3-415b-8cec-a0f831e887b2
timeHours: 1.3333333333333333
---

Experiments work best when they build on existing knowledge to address a clearly defined problem. A *research proposal* is an organized "battle plan" in three parts:


## The problem

This is where you *define* the question or problem, *justify* why the problem should be studied, and *review* what you already know about the problem. Here's an example:

>How to decrease employee churn? Churn creates inefficiency as new people have to be trained in and knowledge from experienced workers is lost. In exit interviews, employees name "out-of-date technology" and "poor communication" as major motivations to leave.

## The potential solution

Here, you *propose a hypothesis* (potential explanation) to be tested. Here's an example:

>Adding Slack to employee computers will decrease churn by increasing communication.

## The method of testing the solution

Describe the *design* of the experiment, the *analysis plan*, and set *benchmarks*. Here's an example:

>Install Slack on half of the employees' computers and monitor churn for the next two months. The variable of interest is churn in Slack and non-Slack groups. This is an A/B manipulation where Slack is installed or not installed.
>
>We will compute the churn rate for two months before the study and compare it to the churn rate in Slack and non-Slack groups for two months during the study.
>
>If churn in the next two months decreases by 10% among Slack users (using churn estimates from the past year), conclude that Slack is effective and install on all computers. If churn in the next two months decreases among Slack users, but by less than one standard deviation, observe for two more months before deciding. If churn does not decrease in two months, uninstall Slack.

Even if no one reads the research proposal but you, it is important to clearly lay out exactly what you plan to do and why. A research proposal helps to avoid many common experimentation pitfalls, such as the following:

 * Mismatch between question and study design
     * For example, a study that claims to address churn but actually focuses on employee communication and doesn't measure churn.
 * A design that does not generate usable data
     * For example, we want to compare employee satisfaction in two groups, but the groups use different satisfaction measures and there's no way to compare them.
 * False positives
     * For example, changing the endpoints midway through a study by moving benchmarks or stopping data collection early when things start to look promising increases the risk of getting results that look good but reflect random chance rather than real trends.
 * The research proposal also presents and maintains a standard. It should outline the way that things should be and hold you to it. In the real world, there will be pressure to run things faster, reduce costs, or cut corners. The proposal provides the standard for how the experiment _should_ be run. It also provides an easy response to questions like, "Why is this taking so long?"

A good research proposal starts with a big question ("How to reduce employee churn?") but rapidly narrows in scope ("Adding Slack to employee computers will decrease churn by increasing communication"). It is a practical reference document that helps to maintain a straight line between goals and actions.

For a deep dive into designing a promising proposal, see [this chapter excerpt](http://searchbusinessanalytics.techtarget.com/feature/How-to-evaluate-the-viability-of-a-data-mining-project) from *Commercial Data Mining: Processing, Analysis and Modeling for Predictive Analytics Projects* by David Nettleton, and [a follow-up commentary](http://www.ibmbigdatahub.com/blog/delicate-art-data-science-project-prioritization-and-triage) from a data scientist at IBM. Note that they focus on evaluating data mining proposals, rather than experimentation proposals, but the underlying logic is the same.

## Drill: Make a quick research proposal

Look back to the potential experiments in the previous assignment. For one of those experiments, write up the essential points of a research proposal for an improved version of that experiment and then submit it.
