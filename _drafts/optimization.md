# When not to optimize

## Introduction

The modern world is awash with metrics, quantification, and optimization frameworks.





















# Old version

## Introduction

Before we dive in, think of your last project, a business venture, or a problem in society, where the goal was to achieve *something*. Write down the broad steps that you would take. It is likely that it resembles the following,

1. Decide on an observation or measurement that quantifies the progress
2. Brainstorm for ideas, identify the causal variables, and strategies to change them. This is usually the hardest part
3. Implement the strategy. At times, it is possible to test out various scenarios within a model (instead of the real world) and see which strategy best improves the metric.
4. Check if the metric improves
5. The problem is "solved" when the variables are in their "optimal configuration" leading to the "optimum value" of this metric.

The paradigm described above is dominant in many quantitative fields, and recently making headway into historically qualitative fields. For example, we try to

- improve an economy by trying to optimize policies to attain maximum GDP growth,
- improve ocean ecosystems by optimizing harvest management policies to minimize the probability of extinctions
- improve business outcomes by optimizing resourcing, optimize supply-chain processes, routing of trucks or airplanes, to maximize profits
- or even try to optimize life decisions like buying a house, choosing jobs etc. What is the metric here? What is the space of strategies? (Echo chamber alert: the last example would be overrepresented in my bubble here in the Silicon Valley!)

We can see this in the usage of the word "optimization" in books,

![image-20260130182629735](/assets/Google_ngram_optimization.png)

## History

Optimization, a paradigm that became popular through the [new field of Operations research during the second world war](https://www.britannica.com/topic/operations-research/History) was rapidly adopted by an increasing number of fields. From the [Encyclopedia Britannica article on Operations Research](https://www.britannica.com/topic/operations-research/Essential-characteristics),

*To formulate an operations research problem, a suitable measure of performance must be devised, various possible courses of action defined (that is, controlled*[ *variables*](https://www.britannica.com/topic/variable-mathematics-and-logic) *and the constraints upon them), and relevant uncontrolled variables identified. To*[ *devise*](https://www.britannica.com/dictionary/devise) *a measure of performance, objectives are identified and defined, and then quantified.* 

This topic is close to my heart, since I studied stochastic optimization during my PhD. I initially studied simple scenarios such as optimizing [finding a target at an unknown location](https://arxiv.org/pdf/1605.08812.pdf), and later applying the framework to understand ecological processes such as [animals foraging for food](https://link.aps.org/accepted/10.1103/PhysRevE.95.062119) or the [effect of random distributions of food on evolutionary pathways](https://www.pnas.org/doi/full/10.1073/pnas.1907998117). Even back then, I remember being bothered by how constrained the framework is. It is only possible to find the optimum strategy (or even define what optimum was) only in the simplest of situations. Adding any real-world complexity would make the space of strategies intractably difficult. Don’t get me wrong, mathematicians, physicists (and other quantitative folks) have come up with incredibly sophisticated tools to tackle really hard optimization problems. But these tools pale in comparison with the complexity of the real world. (In fact [ecological / biological fitness is really hard to define](https://www.bio.vu.nl/thb/course/ecol/MetzNisb92.pdf) contrary to popular discussions of “survival-of-the-fittest”. [A classic example from evolutionary biology](https://www.science.org/doi/abs/10.1126/science.186.4164.645) shows that even in simple single-species models of population dynamics, increasing reproduction rate (a popular proxy for fitness) can actually make a population more unstable and prone to extinction. If this reminds you of the “[butterfly effect](https://en.wikipedia.org/wiki/Butterfly_effect)”, you are right! It is common to see chaos (small changes in one variable lead to large and diverging changes in another variable) and, critical phenomena (behavior changes suddenly instead of gradually) in real world complex systems (in fact, the more variables in a system, the [more likely the system is chaotic](https://academic.oup.com/icesjms/article/77/4/1463/5643857). Add to that the complexity due to the sheer number of components in any system, (interactions between millions and billions of people, billions of living organisms, countless physical entities etc.), and it is almost miraculous that we sometimes see simple patterns emerge!

Setting objectives and metrics to gauge progress is ubiquitous. This has come to be the dominant paradigm in many spheres of our lives. For example, to improve student outcomes, it is common to track the average grades or fraction of the class that gets a passing grade (note the significant difference between these two ways of tracking student outcomes). To measure the utility of an app, it is common to measure engagement (daily active users, average weekly hours of engagement).

As a society we are obsessed with “optimizing” everything. This is especially true among people with a background in the sciences, engineering, business etc. The lack of a powerful alternative to objectives-and-optimization thinking leads us to dismiss bad outcomes from optimization (as well as good outcomes from non-optimization processes) as exceptions .

Today we see the optimization paradigm applied in increasing number of fields, and too often, we see they fail or lead to unintended consequences or worse make the problem even worse! To get a better idea of what could be going on, let us try to define the process.

## Optimization - an ill-defined process 

In simple terms, the process of optimization is identifying the variables we control, and twiddling them to reach the best outcome. To do this we require a few necessary ingredients

- A metric that summarizes the goodness of a solution, and more importantly, that allows comparing one solution to another
- A space of possible solutions, usually denoted by the variables (allotment of resources, potential routes, quantities of ingredients in a recipe etc.)

On the face of it, this seems fairly general. However, as we’ll see below the process of casting most real world problems into this framework requires many more simplifying assumptions.

## Problem of metrics 

 The first step in any optimization exercise is to define a metric (also called objective function, fitness function, loss function etc). It assigns a numeric score for every possible outcome. Already, you maybe thinking, "who decides this metric?" or even "is it possible to have a single number that defines the goodness of solution?" For example, imagine you are a policy maker working to improve quality of life of people in our society. Every person might have a different notion of what matters to improve quality of life. Usually the agreed-upon metric is the common denominator like longevity. However, living a long life fraught with stress, economic uncertainty etc is not exactly a quality life.

 Gross Domestic Product or GDP measured in units of a currency is famously used to evaluate the economy of a country. Number of citations is a metric used to quantity the impact of a scientific paper.

- Statistical metrics - which one to use? AUROC? Sensitivity, specificity?
- Optimizing over distributions: optimize the worst case? Or average case? Most likely case?

In the book Tyranny of Metrics, they state that the three key components of metric fixation as the following three beliefs
- it is possible and desirable to replace experience with numerical indicators based on standardized data 
- making the metrics public / transparent assures accountability 
- the best way to motivate people is to attach rewards and penalties to their measured performance 

The book also outlines the recurring flaws

- Measuring the easily measurable but not the most important 
- measuring inputs rather than outcomes. E.g: measuring resources or person-hours spent
- degrading information quality through standardization/ quantification simplifying and stripping away the context 
- gaming - filtering for easy projects, lowering standards to improve the numbers 

## Gaming metrics

### Campbell’s law (similarly Goodhart’s law)

Donald Campbell, a sociologist, is credited to stating,

*The more any quantitative social indicator is used for social decision-making, the more subject it will be to  corruption pressures and the more apt it will be to distort and corrupt  the social processes it is intended to monitor.*

Tyranny of metrics has multiple examples of this happening in practice.

### P-hacking

### GDP

Tainting of GDP (increased healthcare costs, increased sickness, increased crime and number of lawyers, increased real estate costs, increased financialization, all increase GDP without increasing any real products or services)

## Whose metric? 

Inequality / GDP issues

## We always have unknowns

Optimization is always carried out within models, and we know models always miss lots of things. Models are far from perfect. Optimizing too much within a model will only make us worse in the dimensions that aren’t modeled. E.g. no metric for the importance of community, so we pay less attention to the importance of community in our models

The unmeasurable will be neglected in our optimization rituals.

# Discussion

## Costs of wrongly using the optimization paradigm 

- Relying on simple models and optimizing the parameters in a complex scenario can not only give a false sense of control but actively harm progress by wrongly giving credibility to the generalist quantitative types over people with experience and subjective expertise in the domain
- The unmeasurable will be neglected in our optimization rituals.
  - E.g: happiness, community 
- Logical case for non-optimization-based processes 
- The view that there exists an optimal solution, and it is just a matter of finding it or recognizing we might not have the computational resources to find it, might not even be the right mental model for most of the complex problems we have

## Fallacy of The Most Good for The Most People

This argument has been used to justify a lot of atrocities in history. Is a large amount of superficial good for a large number of people enough to justify a deep suffering of a smaller number of people? Or should the right paradigm be More good for any group of people as long as it doesn't add to the suffering of any other group of people (or more strongly doesn't neglect the more urgent good of the oppressed?)

- [Does the Philosophy of “the Greatest Good for the Greatest Number” Have Any Merit? Michael Shermer 2018](https://www.scientificamerican.com/article/does-the-philosophy-of-the-greatest-good-for-the-greatest-number-have-any-merit/)
- [Pinchot and Utilitarianism](https://www.fs.usda.gov/greatestgood/press/mediakit/facts/pinchot.shtml)



## Alternative paradigms

- Satisficing paradigm where we look at a bunch of metrics and focus on directions that aren't satisfactory
- Exploration 
  - Exploration let's us feel-out new scenarios previously unimaginable and hence outside our optimization models
  - We should actively invest in exploration, there is no "optimal" amount, trying to estimate that is foolish, different investments will lead to different trajectories not comparable with each other
  - Novelty search
  - Infotaxis
- Tinkering 
- Negotiations 
  - This is probably the most important paradigm in a society which values every human being (e.g: in a working democracy XD), EXPAND ON THIS
- Optimization with uncertain gradients (infotaxis and the other paper Sid mentioned)
- Search without gradients (we-know-when-we-find-it searches, finding your keys, stochastic search, foraging etc.)
- Observation and Perception
- Learning

# References

- Stanley - Myth of the objective
- Tyranny of metrics
- Jenny Odell - how to do nothing
- C. Thi Nguyen - The Score

# Book Summaries

## Stanley - Myth of the objective

This book questions the ubiquitous status of setting objectives and optimizing and tries to paint an alternative paradigm.

- Optimization is just a model

- As a society we quietly moved from using the optimization framework to optimize something concrete and low-dimensional (like efficiency of a particular type of engine) to optimizing more vague and grand (extremely high-dimensional) problems in more abstract spaces (e.g: the idea space, 'optimize a company', 'optimize the markets' etc.)

- Most optimization problems are ill-defined (but we can always ask the question, "Can we optimize that?"

- **Basic requirements of optimization - one-dimensional metric, low dimensional finite strategy space, measurability, predictability of consequences of actions we haven't taken, static fitness landscapes, long data (instead of broad data)**
  - one-dimensional metric: multi-dimensional metric - partially ordered sets
  - static fitness landscapes: our actions change the fitness landscape (analogy with heisenberg uncertainty)
  - predictability of consequences of actions we haven't taken

- Our intuition is very poor in infinite spaces, and high-dimensional spaces with uncertainty

- Currently, all the rational and logical arguments' might is behind the optimization framework. When artists and poets talk about exploring novelty, it is assumed to be a distraction. This book is part of building a logical framework for the alternative

- This is a more radical point-of-view than the one in _Tyranny of metrics_

- **Can take many locally optimal steps only to reach a globally shitty place**

- the mental models we have directly reflects in the questions we ask, assumptions we make

- **Our intuition for search and optimization comes directly from real space which is restricted to 1,2 and 3 dimensions**

- Generally, our culture has a tendency to confuse models with reality 

- when we are obsessed with optimization, we choose problems where the assumptions are satisfied (measurable etc.)

- artificial precision, premature quantification

- stochastic search, optimization - penalty tradeoff
- optimal foraging - with every added detail, the optimal solution completely is in the opposite direction
- whole field can be wrong - e.g. chaos in ecology (out of 700 papers, most were low-dimensional ODEs when that is a very narrow framework, and people are amazed when we talk of other ways to model things)


- **To be clear, this book isn't against short term objectives or objectives to achieve something specific (e.g: say complete this task by tomorrow**



## Tyranny of metrics

Introduction
- Doctors and police case study where introducing the metric led to gaming (not taking the harder cases to keep the stats high)

1) The argument in a nutshell 

- Key components of metrics fixation are the following three beliefs 
	- it is possible and desirable to replace experience with numerical indicators based on standardized data 
	- making the metrics public / transparent assures accountability 
	- the best way to motivate people is to attach rewards and penalties to their measured performance 

Most organizations have multiple purposes, focusing on some might come at a cost to others.
Campbell’s law, Goodhart’s law

The belief in efficacy of metrics seems to outlast evidence - feels like a cult. Metric fixation which aspires to resemble science, too often resembles faith.

2) Recurring flaws

- Measuring the easily measurable but not the most important 
- measuring inputs rather than outcomes. E.g: measuring resources or person-hours spent
- degrading information quality through standardization/ quantification simplifying and stripping away the context 
- gaming - filtering for easy projects, lowering standards to improve the numbers 

3. The origins of measuring and paying for performance

Taylorism - organizing factory production inn companies like general motors, where sociologist Daniel bell noted that managerial planning and scheduling drew all brain power away from the shop and reinforced minds numbing routine for workers


4. Why metrics became so popular

## Jenny Odell - how to do nothing

## C. Thi Nguyen - The Score

### Part 1: Opening Moves

**Chapter 1: Is This the Game You Really Want to Be Playing?**

- A lot of the time we don't know the real reason we're doing something. For example: start climbing for fitness, then realize you just like the feeling of climbing on your body
- Losing the joy of the activity from too much emphasis on the score
- Thomas Hobbes: Ultimate power comes fro mthe ability to control language and define terms, especially of success. The power over definitions is stronger than military or economic power. Because if you can define what good and evil mean for people, if you can control what success and failure mean for them, then you can control them from the inside.
- Games wake us to a life of play; metrics drive us down into grueling optimization. When external institutional system (rankings, metrics, measures) set our desires and goals, we call it *value capture*. It happens when,
  - 1. Your values are rich and subtle
    2. You enter some social (typically institutional) setting that offers you simplified, often quantified renditions of your values,
    3. The simplified versions take over.
  - Value capture happens when students top caring about education and start caring about their GPA, when scientists stop caring about finding truth and start caring about citations / biggest grants, when restaurant stops caring about making good food and starts caring about maximizing its Yelp ratings.
- Reiner Knizia (prodigious game designer): the most important tool is the scoring system, because it *sets the player's motivations* in the game.
- This is the peculiarity of games, they tell you what to desire. We can slip into alternate motivational states like a new set of clothes.
- Often in games, the goal isn't what matters. We adopt the gbhoal to *experience the process*. The beauty is in the struggle. Call it the *striving play*. In striving play, you temporarily induce a desire to win, so you can enjoy the process of trying - an inversion of ordinary life where we struggle to attain a goal. Here we set a goal to attain a particular beautiful struggle!
- 

# Appendix

## Optimization: an ill-defined process

Even though language allows us to propose “Let’s optimize that” in any context, such proposals may not always make logical sense (e.g: the problem may not satisfy the requirements of a well-posed optimization problem). 

To understand this, let us discuss where our instinct to optimize comes from. The usual picture in our mind, when we think of optimization is a graph with the x-axis plotting the possible strategies, and y-axis measuring the ‘goodness’ of a solution. The strategies are sometimes also depicted as lying in a 2D landscape with the height of this landscape measuring the goodness of the solution. Often, the full landscape is not visible to us. Picture a vast landscape with hills of different heights as far as the eye can see. Now a.dd a layer of fog, so that we can only see the gradients right below us. The goal is to walk to the top of the tallest mountain.

There are several things that don’t carry over from this picture to real world optimization problems,

1. The metric need not be one-dimensional like the height of the hills
2. The spaces are generally infinite for all practical purposes (as far as the eye can see)
3. Additionally, the dimension of the search landscape is far higher than two in any real world problem leading to a different problem of saddle points than the proliferation of local minima as suggested by the low-dimensional picture (https://proceedings.neurips.cc/paper/2014/file/17e23e50bedc63b4095e3d8204ce063b-Paper.pdf, https://arxiv.org/pdf/1405.4604.pdf) 

## Multidimensional fitness / Partially ordered sets

What do we do when we care about multiple things? Common solution is to weight the different dimensions to compress the fitness to a single dimension. We always lose something in the process. E.g: GDP

Is it just a question of finding the “right” weighting scheme? How can it be, when there are multiple stakeholders? Also, the information we lose from this compression - is it guaranteed to be never important?

## No free lunch theorems

https://en.wikipedia.org/wiki/No_free_lunch_theorem

https://en.wikipedia.org/wiki/No_free_lunch_in_search_and_optimization

## Bad intuition in infinite spaces

The Hilbert’s hotel paradox - https://medium.com/i-math/hilberts-infinite-hotel-paradox-ca388533f05

https://www.cantorsparadise.com/hilberts-hotel-an-ingenious-explanation-of-infinity-1d1a79932080

## Bad intuition in high-dimensional spaces

Chaos review examples?

Interpolation vs. extrapolation

https://arxiv.org/pdf/2110.09485.pdf

https://www.wired.com/story/a-mathematicians-guided-tour-through-higher-dimensions/

## What is the strongest animal? (possibly in the Appendix)

Is this a well-defined question? To make progress we have to make assumptions. For starters, let us consider the question, “Which animal can move the most mass?”. Elephants come to mind. However, we all know per body weight, ants can carry way more mass than elephants. If the final goal is to move a bunch of sand, we can accomplish that with an army of ants far less massive than a single elephant. However, is it really that impressive that an ant can carry 50 times its weight? Ecological scaling theory says all small animals will be strong in this sense, since they have a higher surface area to volume ratio. The surface area gives us a rough estimate of how much cross-sectional space there is to dedicate to structural integrity, whereas the volume gives us the raw weight of the animal. An elephant is at a clear disadvantage having so much bulk compared to the potential cross section of its bones. All tiny insects like ants can carry a lot of weight compared to their own body weight. An astute reader would now say “Let’s first remove the mass-specific trend, and then see which animal stands out”. We may find out that a leopard is particularly strong given its peers of the same body weight. But then, there may be a sequence of other traits that give the leopard that edge, just as having a high surface-area-to-volume ratio gave the ant an edge over the elephant. We may be splitting hairs here. These types of questions are routinely dealt with by the Olympics committee trying to decide on the *fairness* of competitions (e.g: a debate on Trans-athletes has been trending the recent years. Here is a [video discussion on this](https://www.youtube.com/watch?v=cZ9YAFYIBOU))

### 
