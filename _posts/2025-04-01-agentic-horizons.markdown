---
layout: post
title:  "Agentic Horizon"
date:   2025-04-01 20:08:00 -0700
categories: research
---
**Agentic Horizon**

Today’s best machine learning models have a high degree of intelligence, but very little agency. Reasoning models like DeepSeek R1 and o3 can solve tasks at an increasingly high level of difficulty across a wide variety of domains, often far exceeding the capability of any single human. But they can’t break down a fairly unambiguous task that would require a year of dedicated work, sit down, and deliver a solution.

(An example of such a task: Write me a performant simulator of an STM32F103 microcontroller and all of its peripherals.) 

What seems to be lacking is “agency”. 

I’ve heard many people describe agency in terms of “volition”. Ex. Models never go off on their own to solve problems that *they* find interesting. They never do anything unless prompted, etc.

Indeed, models are only now beginning to solve simple Github issues in real codebases. And when they do, they are unlikely to propose a significant refactor, or to seek out a totally novel approach. They certainly would never analyze your codebase, tell you that the business strategy of your SaaS company is crap, and that you should pivot to X instead.

However, I want to separate out this idea of “volition”, and propose a new definition of agency that will better match what will play out over the next few years as models get better:

*Agency* → **Agentic horizon** is simply the length of time over which a model can successfully learn from a sparse reward signal.

More agentic models will have longer “agentic horizons”, and less agentic models will have shorter ones. They will do RLVR on ever sparser reward signals. Volition will have nothing to do with it.

We will still be prompting models to do tasks, but over time, larger and larger tasks will start to have decent success rates when fully automated. Models will become capable of breaking down large tasks into smaller ones, and checking their work at each step. Once agentic horizons greater than just a few hours are possible, models will start doing the things we consider “agentic” automatically.

The predictions in this post: [https://metr.org/blog/2025-03-19-measuring-ai-ability-to-complete-long-tasks/](https://metr.org/blog/2025-03-19-measuring-ai-ability-to-complete-long-tasks/) are highly informative. The agentic horizon of models in early 2025 is about 1 hour, and doubling every 6-7 months. By late 2027, tasks taking around 1 week of human effort (32 hours) will be routinely automated by AI models. (Yes, I know it's hard to extrapolate where you are on an S curve...)

Where is this coming from? From the nature of how the latest generation of models are being trained, namely RLVR (reinforcement learning with verifiable rewards). Companies are seeing good success training models on tasks where you can easily verify the task has been completed in a reliable and automated way. As of early 2025, this training is only at the level of isolated math puzzles and coding tasks for now, and this is why models can only do tasks of approximately that scale. The road to longer agentic horizons is finding ways to let the model train from ever sparser reward signals.

Think about how sparse the reward ultimately is for creating a new startup. You might get a few bits of final reward signal (ex. Go out of business, acquihire, medium success, or IPO), only once a few years have passed.

The way humans do this is that they have strategies for densifying the reward signal. Let me list a couple:
You may try to raise money for your startup, thus giving yourself a reward signal sooner (if someone else is willing to invest, then that can be a proxy for your final reward value).
You may launch a beta version (reward signal if it actually works, and you get reward signal from customers sooner), and force yourself to productionize code sooner (presumably more likely to get a high final reward if your site doesn’t go down).
You may hire people (reward signal if they accept), those people may be organized in a hierarchical structure (useful for propagating intermediate rewards from more experienced to less experienced employees).

We will soon see models that utilize some of these strategies when they work on a task, and it will all boil down to densifying their reward signals.

Models which can do this more efficiently will be more successful.
