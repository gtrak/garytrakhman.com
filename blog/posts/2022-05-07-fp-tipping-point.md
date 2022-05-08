---
title: The Functional Programming Tipping Point
description: or, why I'm just not that into Clojure going forward
date: 2022-05-07
tags:
  - programming
  - clojure
  - typescript
  - ocaml
layout: layouts/post.njk
---

or, why I'm just not that into Clojure going forward.

Functional programming had an interesting allure to me. I started
off my serious programming by learning C and C++, then quickly found
them to be onerous and full of pitfalls. I reached for Python (2.5) as an
alternative and found I could try stuff out much more quickly, but it was
also just very messy once your program got large.

I resolved to _really learn_ 'Object-Oriented Programming' by reading 'Design Patterns'
and other resources I could find, but to be honest, it seemed like a lot of work for
little benefit. I thought there were 2 possibilities, either OOP was complete trash,
or maybe I just wasn't smart enough. I suspected that the real truth was we were working around
language limitations without revisiting the underlying assumptions.

Eventually, I came across [Peter Norvig's great presentation](https://norvig.com/design-patterns/)
on how design patterns present themselves in dynamic languages, and it suddenly all made sense.
I had an existence proof that you can just stop repeating yourself so much if you use a different
language. The presentation suggests lisp, but I didn't see Common Lisp or Scheme to be feasible for
my job prospects. Python was fine, but I was feeling some friction with the GIL and it was a worse fit
for the J2EE work I was doing early in my career. The timing lined up with Clojure gaining traction,
so I resolved to learn more about it and get a chance to work with it.

I then spent a few years as a satisfied clojure enthusiast, I really loved the power the
language provided and felt like I could really do anything with it. I did work on a few very interesting
problems early on, and they just couldn't have gotten done in Java. I saw the value of using all the
features Clojure provided in certain contexts. It seemed like a no-brainer to continue down that path,
so I did. Some forces conspired to change my opinion, though.

- My particular local tech job market was relatively small. It was tough to attempt to
  introduce Clojure at companies that didn't already use it. It's not 'just a jar'. I enjoyed
  working on a team more than being the solo clojure expert. Even when one company formally decided to adopt
  Clojure, too many other issues prevented it from being effective.
- Other languages got better. In particular, we saw the rise and fall of many experiments, some of
  which are still in use and some which became dead ends.
  - CoffeeScript: used it, rewrote all we had to ES6 once that landed.
  - Elixir: looked like it took a lot of developers from Ruby, but I didn't use it.
  - Elm, Purescript, ReasonML: showed there was some pent-up demand for applying FP principles on the
    frontend, but didn't catch on.
  - Rust: Not really FP, but it had some interesting ideas and took some of the audience. Companies
    that scaled up on scripting languages are rewriting core parts in Rust for performance.
  - Ocaml: used it professionally. I like the language, but it was frustrating experience. It got
    some more attention due to ReasonML. I'll write what I like and don't like about it in more detail separately.
- Node.js grow from a niche use-case to being a mainstream language.
- Microsoft changed the game with VSCode, .NET Core on Linux/Mac, and Typescript.
  - Flow deserves honorable mention, but I think Typescript won.
  - VSCode and LSP have dominated the IDE scene. I still use Emacs where it's more convenient,
    but I have been using VSCode for javascript, python, and C# and am quite happy with it.

While all this was happening, Clojure barely changed at all. Other people have written much
around issues in the Clojure community. Personally, I found it frustrating to have no roadmap and
no idea what the future holds. There were a lot of early decisions that made sense in 2008, but
would have gone differently if it were rewritten today. I really now prefer for Clojure to have been a
community project with clear process and community governance. It's not enough to commit to no breaking
changes and only do incremental improvements.

At this rate, Clojure is long in the tooth. Type systems are actually worth it, and a language very
similar to Clojure could be made with one. Would that be better? Can you definitively say that it
wouldn't be better, all other things the same? In general I feel there is too much post-hoc rationalization of
prior decisions. Writing a language and leading a language's growth sounds hard, and I haven't done it,
but I don't think other communities spend as much effort justifying past decisions so much.

Having attempted to teach Clojure to others a few times, it's tiring to constantly apologize
for its warts, and the gap between other languages is thinning especially for more common
use-cases. It used to be the case that there was a clear payoff after the initial learning hump, but
now it's less obvious since fewer people are coming from Java.

I now find myself in the surprising position where I am doing my prototyping in Clojure or
Ocaml, but consider Javascript(Typescript) to be more suitable for production. I didn't expect
to end up here.
