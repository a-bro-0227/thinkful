---
title: Prepare to present your findings
author: Thinkful
team: grading
time: 240 minutes
uuid: 17250c60-89ae-4f58-8ca2-0373c81a5063
timeHours: 4
---

In this checkpoint, you will convert the findings from your research into a slide deck that can be shared with a general audience. This presentation should focus on quantifiable results and visually driven data storytelling. 

For this assignment, use your favorite slide deck interface, such as PowerPoint, Google Slides, or Keynote. 

## Presenting to a general audience

You can assume that the audience who you'll present this slide deck to is not knowledgeable about or interested in the exact techniques and technologies that you used to develop your research. Rather, they will care more about the practical takeaways and recommendations that you can offer—ones that you crafted from your rigorous research.

How can you bridge the gap between your technical research and your audience? In this checkpoint, you'll learn some high-level tips for translating your research into findings for a general audience, and then you'll explore ways to develop slides based on these techniques. 

#### Burn the math

Mathematics is elegant and robust, but too technical and detached to make an impression on most people. Rather than focus your presentation on topics like p-values and standard errors, follow the process of 19th century economist [Alfred Marshall](https://cyberlibris.typepad.com/blog/2005/03/burn_the_mathem.html):

> 1. Use mathematics as a shorthand language, rather than an engine of inquiry.
> 2. Keep to them until you have done.
> 3. Translate into English.
> 4. Then illustrate by examples that are important in real life.
> 5. Burn the mathematics.
> 6. If you can't succeed in 4, burn 3.
>
> This last I did often.

Keep the focus of your presentation on the practical application, rather than the technical methods or the code involved. State in plain English the hypotheses that you are testing. 

#### Convert to dollars

A p-value has in itself has little business value: it is a measure of *statistical* significance. Most managers will instead be interested in *substantive* interest: how large are the real-life benefits that can be expected based on your comparison of two groups, for example? This is where *effect sizes* and *confidence intervals* become crucial for explaining research findings to a general audience. 

So, the quality rating for widgets from Factory A is, on average, two points lower than for widgets from Factory B. What might this difference mean in customer satisfaction, or returns, or margins, or lifetime value? It may take some assumptions to get from your findings to a dollar amount. And that's why it's important as a data scientist to have domain knowledge: so you can make sound assumptions. 

#### Show, don't tell

Similarly, develop intuitive tables and visuals to make your findings more approachable. For example, a confidence interval does measure the expected substantive difference, but it can still be hard to interpret; "difference in means" is an unusual unit of measure. Consider visualizing the difference in means with a [point-plot chart](https://seaborn.pydata.org/generated/seaborn.pointplot.html). 

What do these high-level strategies look like on a slide-by-slide basis? Below are some practical tips for slide deck design. 

## Designing good slides

In the previous module, you learned how to frame, analyze, and report findings for business research. In this checkpoint, you'll explore the basics of designing a visually compelling and effective slide deck to accompany this research. 

Using a slide deck as a teleprompter is usually a recipe for a not-so-great presentation. If you simply read your slides to an audience, you won't connect with them. And successful presentations are all about engaging with the audience. As a data storyteller, you must think about both the form and the function of your slideshow. So congratulations! That makes you a designer.

But there's a fine line between decoration and design. You don't want to adorn your slide show with ornamental embellishments just because you can. Instead, every design element should further your message and help your audience connect with your presentation. Rather than *decorating* a slide show, you want to *design* it—you want to make sure that every choice that you make serves a purpose. And ultimately, you want your design choices to convince your audience to act upon your recommendations. 

Design is both an art and a science. There is no way to cover every theory about design in one checkpoint—design is a complex concept, and people spend their lives studying it. But you can get a start with the basics. Here are some important concepts to keep in mind as you build and design slides.

### Limit how much information you introduce

[The Magical Number Seven, Plus or Minus Two](https://en.wikipedia.org/wiki/The_Magical_Number_Seven,_Plus_or_Minus_Two) was published in the 1950s, and it is one of the most influential papers in psychology today. So, what is this "magical number"? It's the average number of *bits of information* that a human can hold in working memory.

But what exactly constitutes a bit of information? The answer depends on the context and how our eyes *chunk* information. For example, numbers written individually on a report are stored as separate chunks, as are individual lines on a chart. But regardless of the nature of each chunk or bit of information, the primary idea is this: the human working memory is pretty constrained. And presentations should be designed with this constraint in mind. They should make it easier for individuals to process and store away small bits of information.

### Use whitespace

Don't try to fit every piece of relevant information on a slide. After all, you're telling a story about your data, which requires editing and curating. Mentioning every fact about everything is *not* storytelling. With that in mind, keep the content of your slides relevant, and make sure that what you include supports the recommendation that you'll provide to your audience. If the audience wants every conceivable fact or figure, you can create a supplementary document for them.

Because you're not providing every piece of information, your slides should have some breathing room. Whitespace helps your audience take in and process what's important. Use it. Pare down each slide so that it represents one big idea, and ensure that each slide contributes in some way to your story's plot development.

### Map your presentation

Generally speaking, it's better to stick to a single, narrow point in each slide. Each slide should have one big idea. It's better to have many slides with a few words each than to have a few slides with many words each. Consider the following questions:

* **Is it easily readable?** If you can't read a slide's thumbnail on your own computer, it's unlikely that your audience will be able to read it on a projector or in a screencast.

* **Do your headlines connect?** In a traditional story, the first sentences of each paragraph should logically flow together. Similarly, the titles of each of your slides should connect and build on one another. Ask yourself if the slides are helping you tell the story. If the narrative is a little choppy, that's okay; after all, the presentation supports the story, but it's not the story itself. But the slide headlines shouldn't be disjointed or entirely unrelated; there should be some clear, logical cohesion across the slides. 

* **Is it a multimedia experience?** Your presentation should keep your audience engaged. To support this, add some visual variety to your slides. Check their designs: Is there some diversity in the way that the elements are arranged? What about the content of the slides? Are you using a mix of text, images, tables, and charts? A presentation that uses multiple media types may be more compelling to your audience. 


### Use images effectively

Rod Stewart says that "every picture tells a story." And isn't the story what presentations are all about? Remember, you want to create an emotional connection with your audience. There is no better way to do this than through a powerful picture. Check sites like [Pixabay](https://pixabay.com), [Morguefile](https://morguefile.com), or [Unsplash](https://unsplash.com) for royalty-free images.

### Use text effectively

Remember the maxim of storytelling: show, don't tell. So keep the amount of text to a minimum on each slide.

So, how much text is appropriate? Legendary marketer Seth Godin says that no more than six words should ever appear on a single slide. This may be difficult to implement, but it should help guide you. Regardless of the word count, don't cram your slides with text. And make your text big enough for your audience to see. 

### Use transitions and animations effectively

PowerPoint provides a plethora of transitions and animations—but use these with care. These snazzy tricks rarely contribute to the presentation's overall effectiveness, and they may even distract the audience. One animation-like technique that *can* be quite effective is *layering* slides. With layering, you build your slides cumulatively so that information is slowly revealed. Each slide adds to the one before it. This way, you focus on small bits of information at a time, and you keep your audience engaged.

You'll often see layering used with a set of bullet points, with one new bullet point introduced on each slide. You could even apply colors and contrast to a layering technique. For example, you could gray out previous bullets to help emphasize new information.

### Do-no-harm storytelling

Every business presentation is, at its core, a story. Check out the below video for some common mistakes to avoid in your research.

<iframe id="kaltura_player_1590606584" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1590606584&entry_id=1_4yhgmuqv" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

### Example

Take a look at this example of the [kind of slide deck to craft](https://docs.google.com/presentation/d/1QAubjgoKh_YDNgU5ey8BFwsfF20aie6ht9RbznX-Ar8/edit?usp=sharing). Your own presentation should be more comprehensive, covering additional research questions. But you should use the same techniques of keeping the focus on the business needs and quantifiable results from your research without getting bogged down by statistical definitions and techniques.

## Assignment

Use a tool like PowerPoint, Google Slides, or Keynote to create a deck that you would present to a general audience. Reanalyze the data, extract insights using compelling tables and charts, and make recommendations.

### Avoiding presentation pitfalls

Check out the below video for some tips on avoiding common mistakes in designing slide decks using PowerPoint or related programs.

<iframe id="kaltura_player_1590606791" src="https://cdnapisec.kaltura.com/p/2315191/sp/231519100/embedIframeJs/uiconf_id/45331192/partner_id/2315191?iframeembed=true&playerId=kaltura_player_1590606791&entry_id=1_2fgbapq0" width="100%" height="500" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" frameborder="0"></iframe>

When you're done, save a copy of your deck somewhere publicly accessible on the web. Then, submit a link below. You'll receive feedback from a member of the Thinkful team.

