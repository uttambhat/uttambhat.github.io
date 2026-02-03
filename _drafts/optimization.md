# When not to optimize

## Introduction

Before we dive in, please think of your last project, a business venture, or a problem in society, where the goal was to achieve *something*. Write down the broad steps that you would take. It is likely that it resembles the following,

1. Decide on an observation or measurement that quantifies the progress
2. Brainstorm for ideas, identify the causal variables, and strategies to change them. This is usually the hardest part
3. Implement the strategy. At times, it is possible to test out various scenarios within a model (instead of the real world) and see which strategy best improves the metric.
4. Check if the metric improves
5. The problem is "solved" when the variables are in their "optimal configuration" leading to the "optimum value" of this metric.

The paradigm described above is dominant in many quantitative fields, and recently making headway into historically qualitative fields. For example, we try to

- improve an economy by trying to optimize policies to attain maximum GDP growth,
- improve ocean ecosystems by optimizing harvest management policies, 
- improve business outcomes by optimizing resourcing, optimize supply-chain processes, routing of trucks or airplanes, 
- or even try to optimize life decisions like buying a house, choosing jobs etc. (Echo chamber alert: the last example would be overrepresented in my bubble here in the Silicon Valley!)

We can see this in the usage of the word "optimization" in books,

![image-20260130182629735](/assets/Google_ngram_optimization.png)

Optimization, a paradigm that became popular through the [new field of Operations research during the second world war](https://www.britannica.com/topic/operations-research/History) was rapidly adopted by an increasing number of fields. From the [Encyclopedia Britannica article](https://www.britannica.com/topic/operations-research/Essential-characteristics),

*To formulate an operations research problem, a suitable measure of performance must be devised, various possible courses of action defined (that is, controlled*[ *variables*](https://www.britannica.com/topic/variable-mathematics-and-logic) *and the constraints upon them), and relevant uncontrolled variables identified. To*[ *devise*](https://www.britannica.com/dictionary/devise) *a measure of performance, objectives are identified and defined, and then quantified.*

This topic is close to my heart, since I studied stochastic optimization during my PhD. I initially studied simple scenarios such as optimizing [finding a target at an unknown location](https://arxiv.org/pdf/1605.08812.pdf), and later applying the framework to understand ecological processes such as [animals foraging for food](https://link.aps.org/accepted/10.1103/PhysRevE.95.062119) or the [effect of random distributions of food on evolutionary pathways](https://www.pnas.org/doi/full/10.1073/pnas.1907998117). Even then, I remember being bothered by how constrained the framework is. It is only possible to find the optimum strategy (or even define what optimum was) only in the simplest of situations. Adding any real-world complexity would make the space of strategies intractably difficult. Don’t get me wrong, mathematicians, physicists (and other quantitative folks) have come up with incredibly sophisticated tools to tackle really hard optimization problems. But these tools pale in comparison with the complexity of the real world. (In fact [ecological / biological fitness is really hard to define](https://www.bio.vu.nl/thb/course/ecol/MetzNisb92.pdf) contrary to popular discussions of “survival-of-the-fittest”. [A classic example from evolutionary biology](https://www.science.org/doi/abs/10.1126/science.186.4164.645) shows that even in simple single-species models of population dynamics, increasing reproduction rate (a popular proxy for fitness) can actually make a population more unstable and prone to extinction. If this reminds you of the “[butterfly effect](https://en.wikipedia.org/wiki/Butterfly_effect)”, you are right! It is common to see chaos (small changes in one variable lead to large and diverging changes in another variable) and, critical phenomena (behavior changes suddenly instead of gradually) in real world complex systems (in fact, the more variables in a system, the [more likely the system is chaotic](https://academic.oup.com/icesjms/article/77/4/1463/5643857). Add to that the complexity due to the sheer number of components in any system, (interactions between millions and billions of people, billions of living organisms, countless physical entities etc.), and it is almost miraculous that we sometimes see simple patterns emerge!

The role of setting objectives and working towards them by regularly checking our progress using metrics and heuristics is ubiquitous. This has come to be the dominant paradigm In many spheres of our lives. For example, to learn a new skill, say playing the guitar - we first set the objective, then measure progress (e.g: number of chords or songs learnt) and try to maximize this metric. Or if we want to move up in our career, we set the objective (say to be a director in your company), then measure your progress while you are working towards this goal. Need better examples

As a society we are obsessed with “optimizing” everything. This is especially true among people with a background in the sciences, engineering, business etc. The lack of a powerful alternative to objectives-and-optimization thinking leads us to dismiss bad outcomes from optimization (as well as good outcomes from non-optimization processes) as exceptions .

Today we see the optimization paradigm applied in increasing number of fields, and too often, we see they fail or lead to unintended consequences or worse make the problem even worse! To get a better idea of what could be going on, let us try to define the process.

## Optimization - an ill-defined process 

Given all the complexity in nature and human societies, let us now discuss where the process of optimization fits in. In simple terms, the process of optimization is identifying the variables we control, and twiddling them to reach the best outcome. To do this we require a few ingredients

- A metric that summarizes the goodness of a solution, and more importantly, that allows comparing one solution to another
- A space of possible solutions, usually denoted by the variables (allotment of resources, potential routes, quantities of ingredients in a recipe etc.)

On the face of it, this seems fairly general. However, as we’ll see below the process of casting most real world problems into this framework requires many more simplifying assumptions.

- Visualization (1d and 2d landscape)

## Problem of one-dimensional or low dimensional metrics 

 The first step in any optimization exercise is to define a metric (also called objective function, fitness function, loss function etc). It assigns a numeric score for every possible outcome. The metric may measured (or calculated from a set of measurements) or may be calculated from the outputs of a model that describes the scenario. Gross Domestic Product or GDP measured in units of a currency is famously used to evaluate the economy of a country. Number of citations is a metric used to quantity the impact of a scientific paper.

- (Tyranny of metrics ref)
- Utility function in economics (reference to research on insufficiency of one dimensional utility metric)
- Physics action principle - interestingly there is formulation of physics which is centered around a single quantity called the action function, optimizing which, 

reproduces the observed dynamics. The action function in some sense stores all the necessary information to predict the evolution of a system. However the action function gets incredibly complicated even for microscopic systems with just hundreds of particles. So in some sense defending utilitarianism saying we just need to update the utility function is unfalsifiable and may lead us down an impractical path. There is also some new research on the insufficiency of a one dimensional utility function in capturing real world preferences that are perfectly logical.

- Statistical metrics - which one to use? AUROC? Sensitivity, specificity?
- Optimizing over distributions: optimize the worst case? Or average case? Most likely case?
- Whose metric? Inequality / GDP issues

## Gaming metrics

### Goodhart’s law, Campbell’s law

The reader may have experienced that often we actively need to ignore the metric to do a good job at something. E.g: if the metric is number of deliverables delivered, we rely heavily on an internal standard that each deliverable is done well. Without such a standard sticking to the metric will just result in a lot of frequently delivered shoddy work! This is so widespread, there are multiple adages ([Campbell's law](https://en.wikipedia.org/wiki/Campbell's_law), [Goodhart's law](https://en.wikipedia.org/wiki/Goodhart's_law), [Cobra effect](https://en.wikipedia.org/wiki/Perverse_incentive)). Tyranny of metrics has multiple examples of this happening in practice.

### P-hacking

### Profit and Stock price metrics

Optimizing for profit leads to deterioration of everything else, working conditions, health of competition, quality of products they produce (link references)

### GDP

Tainting of GDP (increased healthcare costs, increased sickness, increased crime and number of lawyers, increased real estate costs, increased financialization, all increase GDP without increasing any real products or services)

## Traps

### Rugged landscape

### Bounded rationality / compute

### Forecast trap

### No free lunch theorem 

# Discussion

## Potential costs of wrongly using the optimization paradigm 

- Relying on simple models and optimizing the parameters in a complex scenario can not only give a false sense of control but actively harm progress by wrongly giving credibility to the generalist quantitative types over people with experience and subjective expertise in the domain
- The unmeasurable will be neglected in our optimization rituals.
  - E.g: happiness, community 
- Logical case for non-optimization-based processes 
- The view that there exists an optimal solution, and it is just a matter of finding it or recognizing we might not have the computational resources to find it, might not even be the right mental model for most of the complex problems we have

## Alternative paradigms

- Satisficing paradigm where we look at a bunch of metrics and focus on directions that aren't doing so well (not satisfactory)
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
- 

Anyone interested to collaborate on follow up projects contact me at [uttam@duck.com](mailto:uttam@duck.com)

## Digressions / Case studies / follow-up questions: 

- a large class of dynamics can be recast as optimizing some action function (utility function?) At the same time there are valid logical preferences that can't be modeled with a single dimension utility, how do we square this with the earlier point?
- Do extremely simple business "models" (usually linear regression extrapolation based on few variables), do better than subjective decisions? This is an empirical question. Daniel Kahneman demonstrated in psychological evaluations assigning a simple formula does work better than purely subjective evaluation. Our foraging models show otherwise, one tiny change in assumption can make the best policy the worst one. But the business case does remain an empirical question

## Other digressions

- Against techno-ablism - Ashley Shu (Disability podcast factually)
  - Why do we need to slow down and not optimize all the time. It allows a larger set of people to discover their capabilities, exploration. It is completely wrong that some people are more capable from others, because this set has changed enormously over time. Capability comes from not from specific structures of our bodies, mind or genetics but from the astronomical complexities of our brain and biology etc, degrees of freedom which can be used to creatively solve problems or explore ways to modify our environment in interesting ways. "Disabled* people have this just as much as abled people
  - Wrong mental model: there is in theory the best human who is optimized in lots of things. In reality though "No free lunch theorem"
- Other thoughts
  - In biology, high rates of change or mutation causes cancer, we may even argue that some of the biggest corporations in the world are cancerous tumors brought about by rapid growth!

# References

- Stanley - Myth of the objective
- Tyranny of metrics
- Vergassola Infotaxis
- P-hacking, GDP, capitalism as an optimizer
- No free lunch theorem
- The forecast trap - Boettiger 2022
- GDP
- When McKinsey comes to town
- Others
  - Messy - Tim Hartford
  - Utopia of rules - Graeber
  - Michael Sandel - Morality of markets, and Tyranny of merit
  - Jenny Odell - how to do nothing 

Older material / notes etc.

# Introduction

This is (hopefully) the first among a series of articles that dig deep into some mainstream paradigms by studying the assumptions that go into these frameworks / models, and explore alternatives. In this article we explore Optimization.

This article is inspired by Kenneth Stanley’s book, “Why greatness cannot be planned: the myth of the objective” and 



# Optimization: an ill-defined process

Even though language allows us to propose “Let’s optimize that” in any context (including when speaking of the optimization algorithms themselves), such proposals may not make logical sense. To understand this, let us discuss where our instinct to optimize comes from. The usual picture in our mind, when we think of optimization is a 2d landscape of possible strategies / solution, and the third dimension (height) measuring the ‘goodness’ of a solution. Picture a vast landscape with hills of different heights as far as the eye can see. Now add a layer of fog, so that we can only see the gradients right below us. The goal is to walk to the top of the tallest mountain.

Picture 1 and 2D versions

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

## Problem of extrapolation

Example from Tyranny of merit by Sandel, Chinese student saying it is okay that the rich and buy kidneys from the poor since they earned the money and so the right to live longer. Extrapolation issue here is that at reasonable income levels it maybe possible that hard work and "merit" deservingly leads to more income, but at the extremes it is rarely the case if at all.

We extrapolate and analogize constantly. But these are rarely iron-clad logic and often wrong.

## Complex systems

Complex systems studies have brought rich new vocabulary and phenomena.

Complex systems are those that not only have a large number of parts but also a emergent structure at multiple scales (e.g: a box of gas has many atoms but no emergent structure, an ecosystem on the other hand is a really complex system). New phenomena of dynamic fitness landscapes etc etc

## What is the strongest animal? (possibly in the Appendix)

Is this a well-defined question? To make progress we have to make assumptions. For starters, let us consider the question, “Which animal can move the most mass?”. Elephants come to mind. However, we all know per body weight, ants can carry way more mass than elephants. If the final goal is to move a bunch of sand, we can accomplish that with an army of ants far less massive than a single elephant. However, is it really that impressive that an ant can carry 50 times its weight? Ecological scaling theory says all small animals will be strong in this sense, since they have a higher surface area to volume ratio. The surface area gives us a rough estimate of how much cross-sectional space there is to dedicate to structural integrity, whereas the volume gives us the raw weight of the animal. An elephant is at a clear disadvantage having so much bulk compared to the potential cross section of its bones. All tiny insects like ants can carry a lot of weight compared to their own body weight. An astute reader would now say “Let’s first remove the mass-specific trend, and then see which animal stands out”. We may find out that a leopard is particularly strong given its peers of the same body weight. But then, there may be a sequence of other traits that give the leopard that edge, just as having a high surface-area-to-volume ratio gave the ant an edge over the elephant. We may be splitting hairs here. The main point of this exercise is that

## We always have unknowns

Optimization is always carried out within models, and we know models always miss lots of things. Models are far from perfect. Optimizing too much within a model will only make us worse in the dimensions that aren’t modeled. E.g. no metric for the importance of community, so we pay less attention to the importance of community in our models

The unmeasurable will be neglected in our optimization rituals.

## Alternate Paradigms

- Satisficing
- Exploration
- Negotiation
- Tinkering
- Learning
