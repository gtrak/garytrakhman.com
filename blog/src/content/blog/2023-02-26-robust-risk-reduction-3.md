---
title: "Robust Risk Reduction - Part 3/3"
description: "What's a better strategy?"
pubDate: "Feb 26 2023"
---

This is part 3 in a series of posts on mitigating tech debt, starting [here](/blog/2023-02-21-robust-risk-reduction-1).

# What's a better strategy?

We've seen in the previous post how tech debt by its nature might confound efforts to alleviate it. We struggled to come up with
a viable way to address it that creates value without a lot of extra risk.

Let's work through together what a good strategy might look like.

## What are some characteristics of any good strategy to alleviate tech debt?

### It's dynamic to changing circumstances

This series of posts includes the word 'robust' in the title for this reason. A robust mechanism is something with a bit of flexibility.
Think metal not porcelain. It bends, and it doesn't break, or at least it breaks much, much later than something brittle would. There
should be no circumstance that will cause you to fully abandon the strategy, and it should stay relevant as variables (people, requirements)
change.

### It's self-reinforcing

A good, sustainable, strategy to alleviate tech debt shouldn't require a lot of extra effort to get going or keep alive. Said another way,
a self-reinforcing strategy will _cause_ developers and stakeholders to do the 'right thing' with minimal touchpoints, minimal confusion,
and maximal clarity, and provide positive feedback to make it even more likely to choose the right path next time. Once the strategy is
set in motion, a successful outcome should be a foregone conclusion, although you might not know the exact timeline.

A strategy becomes sustainable when its incentives are aligned with the developers in the short-term as well as the long term, or the
feedback can be automated. A relatable example for engineers is how PR comments change before and after the introduction of linters
and formatters. After the initial discussions and work to get the codebase to conform, further iteration is automatic and low effort.
The tools greatly reduce the amount of style nitpicking in code reviews.

Pretty soon after the initial work, all code gets landed quicker and you realize the benefits of the automation. This automation is
valuable for small teams and large ones.

### It's easy to understand

In order to reduce risk, it's critical to get everyone on the same page. It's likely that solving your architectural problem doesn't require
you to create new fundamental concepts that are challenging to communicate, at least not until you've exhausted the set of well-known solutions. Try
really hard to avoid the temptation to push the frontier too early.

## What's an example strategy?

Let me start this section by stating the obvious: I don't know the answer, and I'm writing this to attempt to work through my past
experiences and possibly find a strategy that will work better next time. That said, I think there's value in showing my work. I can
offer a few tips and guidelines to the next person and my future self.

### Let's start from first principles

How did we get in this situation? Fundamentally, tech debt is the result of a living, breathing system including your current codebase, its
dependencies, your company's requirements, and your changing team's skills and knowledge. A systems approach is suitable to analyze it and
make recommendations. Although I am by no means an expert in systems theory, I think I can apply some basic ideas to the problem.

#### Create a model of the system

A picture is worth a thousand words. It would be a useful exercise to model your dev process and artifacts with simple squares and arrows.

We want to identify the inputs and outputs and general interactions between different parts. Once you have the relationships mapped out,
you can have conversations about them. At a fundamental level, tech debt accumulates when 'the wrong thing' grows faster than it is
addressed. Your systems diagram can be used to frame a conversation about key indicators. Once you have the list of what contributes
to the growth of some specific tech debt, there are some we can apply to fix it at different levels.

#### Collect key metrics

You might have a hunch and intuition about the nature of your tech debt. What do you need to validate it and add support? What would disprove
it or reduce support? It's easy to find evidence to support your early conclusion due to confirmation bias, but it's worth fighting against it.
It's common in statistical analysis to set out to "disprove the null hypothesis," which is to invert your hunch and focus on all the things that
might break your assumptions.

Either way, it's likely the information you need to communicate is not totally clear and organized, and you might need to do some early work. It
should be relatively uncontroversial to take some extra time during your work day to add automated metrics or do a one-off analysis. Some
examples of useful information I have collected in the past include:

- What projects are changed in the same PR? (scripts over git)
- What kinds of tickets have the most PRs or largest diffs? (scripts over git)
- What are the worst-case and common case CI times?

#### Consider some common kinds of general solutions

I can offer some general patterns.

- Add friction to processes that accumulate tech debt
- Reduce friction where you want an alternative to win
- Create or extend a data model to reduce special-case code. You know you are doing this right if end up deleting much more code
  than you add.

#### Consider alternatives and risks

You'll want to anticipate people's questions before having a larger conversation. The solution might involve work at different levels.

If the solution is at the level of code or automation, you'll have to put a lot of consideration into a migration plan and how to enforce
common conventions across code repositories and teams. Not everyone will welcome extra change or work on their side, and you likely don't
want to do it all yourself. The changes might not have as much value in different sets of circumstances, which might mean they never get
fully implemented.

If the solution could involve team processes, it's often going to require a lot of discipline and agreement to add new steps, and process
changes might have unintended consequences. For example, if you add more conversation to incoming tickets, planning meetings will grow and
you are likely to lose capacity in the number of tickets your meeting can handle. An example of a process change I've tried in the past
is to add a 'tax' on velocity in order to have developers work on at least one unfamiliar part of the system. Over time, it would spread
knowledge and reduce bus factor, but it took some extra discipline. A key question to ask about a process change is 'when' or 'how often'
it will apply, and what kinds of scenarios it would miss.

## How do you get there from here?

There are some activities that should be done incrementally, but be careful not to fall into full incrementalism.

### Keep notes

The knowledge-gathering part at the front end of any kind of tech debt or risk reduction is critical, and it can happen over time at low
cost. I encourage you to take plentiful notes and organize them in a kind of second-brain system. It doesn't have to be super high-tech.
Early on in my career I used 'one big text file' to track everything, but more recently I have started using Notion. What matters is
that it's easy to capture input, easy to search what you're looking for, and that there is some place to put more far-out ideas so you can
start to notice patterns.

### Lower the activation energy for larger efforts

In order to reduce the risk from a larger effort, you can chip away at debt over time as part of your normal work. for me, what this looks like
is constant refactoring at PR time. Each individual PR might be a bit bigger until the code settles in to a new pattern. Over time, quality
improves. When working like this, it's key to have some agreement so people aren't working in different directions. You can even have _an actual conversation_
before falling into the 'local minimum' trap. Hopefully you like your coworkers.

To avoid the 'why are you working on this' trap, it helps to have some kind of past artifact or set of agreed-upon guidelines to reference.

Because these changes are applied incrementally as part of your normal work, areas of the code that are changed more often will become better, faster.
The best predictor of the future is the past, and it's likely some specific kinds of work will happen much more often than others. You can take advantage of this tendency
to understand the impact of a change.

Once there is enough clarity to be able to define and finish a larger piece of work (but not too large), write it up in your normal process, then get it done in one shot.

## Good luck!

Seriously, it's hard out there, and I hope this helps. I want to live in a world where it's safe to assume we all want to build better. If this
helps, or you know of a better way, let me know!
