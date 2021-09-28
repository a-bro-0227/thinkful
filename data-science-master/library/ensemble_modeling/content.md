---
title: Ensemble modeling
author: Thinkful
team: grading
time: 7 minutes
uuid: 71dea2b6-f889-4d1f-a506-8abcf492d94c
timeHours: 0.11666666666666667
---

Learning about random forests leads you to another, much larger, topic: *ensemble models*. Ensemble models are essentially models that are made up of other models. These component models are often models that are simpler than would be necessary to accurately predict the desired outcome on their own. In the case of random forest, those submodels are decision trees. Random forest generates many decision trees and combines them to generate a single prediction via a voting process.


## Methods of ensemble modeling

There are many kinds of ensemble models. In fact, there are infinite kinds of ensemble models, because you can combine most kinds of models together and create a new kind of ensemble model by mixing and remixing different component models. However, most ensemble models fall into three main categories:

- **Bagging:** In this ensemble technique, you take subsets of the data and train a model on each subset. Then the subsets are allowed to _simultaneously_ vote on the outcome, either taking a majority or a mean. You just saw this in action with random forests, the most popular bagging technique.
- **Boosting:** Rather than build multiple models simultaneously like bagging does, boosting uses the output of one model as an input into the next, in a form of _serial processing_. These models then get daisy-chained together sequentially until some stopping condition is met. You'll learn about boosting methods later.
- **Stacking:** This method is a two-phase process. In the first phase, multiple models are trained in parallel. Then, in the second phase, those models are used as inputs into a final model to give your prediction. This approach combines the parallel approach embodied by bagging with the serial approach of boosting, creating a hybrid of the two.

You can create your own ensemble methods by manually combining models, but there are already several widely used forms of ensemble learning in use. You'll cover these later in the program. Random forest is really just the tip of the iceberg.

<div class="think-like-a-data-scientist">

<p>There are advantages and disadvantages to ensemble models. Most notable is, of course, their performance. Ensemble models are often some of the most accurate techniques to apply to a problem. They also tend to have low variance because they're built from multiple internal models.</p>

<p>However, there are also downsides. Most notably, some ensemble techniques—particularly boosting—are prone to overfitting. You also lose a lot of the transparency that individual models offer. You saw this clearly in the random forest example, where the easy explanations offered by decision trees are abstracted away by the forest.</p>
</div>

For a screencast demo of the techniques covered here, check out the below video.


<iframe id="kaltura_player_1604765353" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1604765353&entry_id=1_4bcak8ab" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>