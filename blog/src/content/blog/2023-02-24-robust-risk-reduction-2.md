---
title: "Robust Risk Reduction - Part 2/3"
description: "What are some possible strategies?"
pubDate: "Feb 24 2023"
---

This is part 2 in a series of posts on mitigating tech debt, starting [here](/blog/2023-02-21-robust-risk-reduction-1).

# What are some possible strategies to mitigate tech debt?

Let's assume there exists a lot of accumulated tech debt in your system. It has these characteristics:

- There is general consensus on the root of the problem. (If not, do the work to socialize the problem)
- Proposed solutions are too big, risky, and intrusive for one person to just do. (It can still happen with
  ample tests and type-systems, believe it or not)
- It's actively hurting the product pipeline, and you can see how much better it would be if the problem was alleviated. (In general,
  engineers play up the benefits, and downplay the costs, but knowing might not be enough to help you)

What are some approaches to tackle it?
What can go wrong with them?

## The Traditional Project Plan (top-down)

In this scenario, someone writes a document in your normal processes. It might be an RFC, an ADR, or a _Formal Technical Specification_
providing _Context_ for a _Decision_ by _Key Stakeholders_.

There are some challenges with this approach.

### It's likely the decision will be _no_

We already said the work was risky, large, and different from normal work your organization plans and executes. All these issues
contribute to the likelihood of a reader saying "WTF am I looking at". If you go through the trouble, and the effort is dead
on arrival once it hits a decision stage, you wasted a good bit of time, are likely a bit demoralized and will try less
hard to do something similar going forward.

Like the honey badger, the tech debt doesn't care. It still grows. Fixing the problem later will likely be harder, not easier.

### If the decision is yes,

it's often because not all the risks have been discovered or understood. Discovering them during implementation adds project scope. After
a few weeks or months, you might be wondering if the "Sunk Cost Fallacy" applies to you. Continuing or turning back are both
_not great_ outcomes.

If you continue, you might eventually alleviate the tech debt, but it will be harder to use the normal process next time.

### The existing system still exists

Until you can replace existing functionality, all inbound work has extra conversations about whether it should be in the new
system (more right) or the old system (expedience). These conversations will slow down very important things. If the decision is
made to add to the old system, your new system plan from 3 months ago will not have taken the new functionality into account and
will increase scope and timeline as a result.

## Forgiveness Instead of Permission (bottom-up)

You think you've got this. You might have one or two engineers onboard with a specific direction, but you know the standard
process will never prioritize this kind of work. Why not skip it this time?

You do a quick win proof of concept and hit all the low-hanging fruit. You get your one or two PR approvals and just YOLO-merge
<look at me, I'm the captain now meme>. Over time it grows organically into _the new way to do things_, which is _clearly superior_.
Even when it's looking good (often it doesn't, and you have to throw it out), you might be subject to a few issues.

### Why are you working on this

Occasionally, a piece of work you didn't anticipate might get big enough to warrant its own ticket or some other actual discussion. An
event like that can make people aware of work you intended to keep under wraps and possibly cause some alarm, or at least some intrusive
questions. At that time, you are likely not prepared to have the conversation because you won't know when it will come.

Don't surprise your manager.

### Feature creep

You are going to be tempted or asked to add more functionality to the new code over time, often before it completely replaces the old
code. Often those features will not quite fit with your initial vision. Eventually, you will have two old things to maintain
instead of one.

### Local minimum

Over time, you will realize the shortcomings of your approach, and maybe you will think of a better one. You might feel that
if you had treated the problem with the upfront respect it was due, you could have skipped some steps and landed on the later
solution more directly. On the other hand, your new approach probably provided value along the way even in an incomplete state. It's not
always so clear.

## Is there another approach?

In part 3, I'll attempt to propose one.
