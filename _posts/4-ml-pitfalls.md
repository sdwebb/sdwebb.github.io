---
layout: post
title: "The Four Pitfalls of Machine Learning Problems"
author: "Stephen Webb"
categories: journal
tags: [projects,ml]
image: mountains.jpg
---

The word has come down from the upper echelons of management that there's a Problem, and your team is responsible for delivering a
Solution. But as you get into building that Solution, taking inventory of the data available and crafting the fanciest in
bleeding edge machine learning models, you notice that the Problem isn't going away, and in fact now there's new Problems
that weren't there before. You probably fell into one of the Four Pitfalls of Machine Learning Projects.

## The Four Pitfalls You Meet in Project Hell

> All happy projects are the same, but each unhappy project is unhappy in its own way
> 
>   - Not Leo Tolstoy

There are enumerable ways for data-oriented projects to go cattywampus, so for editorial sake I'm going to lump pretty much
all of them into one of the Four Pitfalls:

1. Falling in love with using a tool instead of solving a problem
2. Treating data points as unit tests
3. Treating machine learning models like software
4. Environments change, your model does not

Each of these can uniquely contribute to the failure to deploy a machine learning model into production as a Solution that solves
a Problem for your org. Of course there's many, many, many, many, many other tactical/strategic issues with why these things can 
fail, don't at me, but I want to highlight how a Problem that should be perfectly amenable to a machine learning based Solution can 
fall apart despite the best efforts of a perfectly competent team.

## Ooooooooo shiny!

Your Chief Product Officer went to some industry meeting and came back obsessed with 
[LLM-RAG](https://en.wikipedia.org/wiki/Retrieval-augmented_generation). Or some marketing email landed in the inbox of your CTO and
now everything needs to use "[Agents](https://www.ibm.com/think/topics/ai-agents)". 

"But sir", you protest, "we handle logistics for a bottled water company. Why do we need this?"

You've been struck by the most obvious version of **Falling In Love With Using A Tool Instead Of Solving A Problem**. If you've been in
the data science space for any length of time, you've almost certainly had 
[certain feelings](https://ludic.mataroa.blog/blog/i-will-fucking-piledrive-you-if-you-mention-ai-again/) about this when it
comes from, say, that Product Manager who seems to really want to put GPT on his resume for some reason. But you know you didn't get
into a data science career to sober-mindedly train an XGBoost model on your laptop and have it ready to be deployed within a week
or two. No! You read about [Kolmogorov-Arnold Networks](https://arxiv.org/abs/2404.19756) and GANs and diffusion models and
all that good stuff, and it was cool and exciting to you. 

So you, yes you, savvy tech-knower, are just as prone to this as anyone else. And it's important to acknowledge that your brain
is chock full of the same cognitive biases as everyone else, so you can recognize when your 
[nucleus accumbens](https://en.wikipedia.org/wiki/Nucleus_accumbens) starts whispering that everything, and it means _everything_, 
looks an awful lot like a nail, and you just so happen to have the coolest hammer ever in your hand.

How do you avoid this cognitive trap? Sometimes the new fancy thing is the right tool! You should use the right tool for the job, right!?
Here's a checklist of questions to ask yourself to see if that new toy is right for you or not:

### Is the new solution in every news article about machine learning?

The first test is a smell test for whether you're chasing the new hotness. Would your mother, who's retired and mostly watches cable news,
recognize the name of the tool you're using to "Solve" your Problem? If so, you should be on high alert that you're chasing a trend, and
continue down the checklist. If not, you should continue down the checklist, but the threat level is closer to "orange" than "red"

### Has your exact problem been solved in a blog post?

If thirty seconds of internet search crops up a blog post written three years ago by a Sr Data Scientist at another company describing
in detail how they solved the problem using some clever feature engineering and logistic regression, you should probably start by
doing some clever feature engineering and training a logistic regression model. They've already found a solution to the problem,
and it's going to be a lot of data wrangling to get your company's data into the simple solution, anyway, so you might as well do
the data wrangling you'll need to do for a more sophisticated model anyway, try out the simple solution, and see if it's a path to 80/20
this shit. You'll have time to get it the rest of the way with some new model anyway, but at least then you'll have a baseline to
evaluate the extremely complex and expensive-to-deploy solution against later.

### Does your description of the problem allude to any business case whatsoever?

As of March 2025 every company thinks untold productivity gains are available if only they implement a chatbot. What does the chatbot do?
Well, you can interact with it. Why are we interacting with it? Well, because it will answer your questions. But LLMs can hallucinate
and besides, you're a regional distributor for beverage companies, what questions need to be answered by your customers that can't
be solved with a [semantic search](https://www.geeksforgeeks.org/what-is-semantic-search/) of your documentation? If you cannot find a
specific reason why this specific new tool Solves your specific business Problem that needs to be solved in a way that other tools 
literally cannot, then you or your org is definitely falling into this trap. All machine learning models come with a lot of 
[tech debt](https://research.google.com/pubs/archive/43146.pdf), and the more sophisticated your model is the higher the tech debt.
You need to be able to justify that tech debt in business terms, preferrably with a dollar sign attached to it.

## [This problem has overindexed!](https://youtu.be/yJt7SDALKzc?si=_hxTX1jycMiZfEVl)

The first Pitfall is about using the wrong tool for the job. This Pitfall has more to do with insisting the tool solve the problem
exactly the way you want it to.

