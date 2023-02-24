---
title: "Robust Risk Reduction - Part 1/-"
description: "Define the problem we're trying to solve"
pubDate: "Feb 21 2023"
---

# Why

A common issue that many engineering teams face is tension between the priority of tech debt and the priority of
product commitments. Although it's an issue that many engineers have experienced, the definition of tech debt and
communication of it up and down the organization is still very difficult. It's a very fuzzy phrase that can mean a lot of things.
It can be difficult to articulate as an engineer, and difficult to understand as a nontechnical stakeholder. There are
some common traps when it comes time to actually do something specific to alleviate tech debt.

# What is problematic about tech debt?

## It's hard to measure

Tech debt is often not captured by existing metrics and processes, and it is often not a result of an intentional decision.
One way tech debt manifests itself is as an accumulation of widespread papercuts due to how the existing system makes different
types of work easy or hard.

In UX jargon, there is a concept of
[affordances](https://uxplanet.org/ux-design-glossary-how-to-use-affordances-in-user-interfaces-393c8e9686e4). A system's
developer UX makes certain behaviors easy or hard. It's often the case that requirements change or some other practical limit
is reached, requiring you to reevaluate fundamental system assumptions.

When the system is no longer practical for current and future requirements, the burden is on the engineer or engineering manager
to identify a common thread, organize the issues, and communicate them. There often aren't great incentives to do this on top
of a normal workload.

Consequently, it's easy to ignore existing debt, easy to pile up more debt, and hard to demonstrate value from reducing debt.

## Different developers and stakeholders have different viewpoints

In general, when planning who will do a piece of work, it's usually better in the short term (at the expense of the long term)
to hand it to the person who is most familiar in that area and can get it done the quickest. As a result of repeatedly
applying the 'get more done in the short term' work assignment strategy, individual developers tend to become sticky to certain
parts of the codebase and might have differing views about what's painful and time-consuming.

- They might have their own workarounds that make some kinds of tasks faster only for them
- They might not understand the nuances of a different area of the code and why it's problematic
- You might not understand their point of view

We are all working with partial information, and it's just tough to bridge those gaps.

## If left unchecked, tech debt will eventually block product priorities

Developers and stakeholders don't know what the future holds, but it's key to work hard to keep your options open. Some future
work can become 'too hard' to realistically get done, depending on the team process, ticket discipline, and competing priorities.
For example, you don't need to know what particular clients will come in to guess what multiple of today's load will cause the
database to fall down, or to know how many concurrent clients you can onboard given your team capacity. When you start nearing
those limits, all other work becomes 'too hard'. Avoid those!

At a less stressful time, we should try to avoid having implementation costs drive what features are delivered. Ideally, we
deliver functionality with the most impact, an impact that should be much higher than its implementation costs and higher
than the value from competing priorities.

An 'agile' process framework recommends delivering early and often. If what you want to deliver is too large, you should reduce scope until
you can deliver an MVP and get some market feedback. If the tech debt of the existing system prevents you from scoping down enough to deliver
a viable MVP within a sprint or two (when some incoming crisis preempts the work, and you lose momentum), your choices are realistically:

### Don't attempt to deliver it

<iframe src="https://giphy.com/embed/Yycc82XEuWDaLLi2GV" width="480" height="400" frameBorder="0" class="giphy-embed mx-auto" allowFullScreen></iframe>

This is another way to say "I can't do my job". It doesn't look great. In the long run, you will just no longer be able to make any
significant changes. You, and everyone around you will be frustrated.

### Build something in isolation

<img class="mx-auto" src="https://imgs.xkcd.com/comics/standards.png" />

#### How many of those prototypes can your team realistically maintain in production?

The answer is that you probably can't maintain many one-offs, especially if they're written by just one or two people in a
different toolchain.

#### How many prototypes have you worked on and delivered, and subsequently thrown away?

Again, the answer is probably not that many. Working code is likely to stick around, so there should be a
plan and bandwidth to integrate it into the existing system. It can be tough to advocate for migration
of a working prototype after launch when stakeholders have moved on to the next set of priorities.

## Conclusion

We've talked about some consequences of tech debt and some choices you might have to make as a result of it.
These aren't great choices. It would be much better if we avoid having to make them!

In the next part of this, we'll explore what are some possible strategies to keep tech debt in check.
