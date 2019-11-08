---
layout: post
title:  "The True Cost of Software"
categories: [architecture, integration, enterprise]
---
## Introduction
Sometimes, things fall into place in weird ways. On one hand, I'm currently giving a presentation about microservice design
that has a section about granularity (link to blog post here) where a large part of the argument is grounded in [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law).

On another hand, work often touches on questions of an "enterprise architecture" nature. What I mean by that is that every now and again
strategic decisions need to be made about business applications, whether to build them yourself or source externally, and whether to
do that in parts or as a whole. Annoyingly (to me), the framework within which these questions tend to be asked is often oriented towards
* Feasibility - can we technically do it?
* Capital expenditure - how much will it cost to get it done?
* Time to market - how long will it take?

And finally, SpaceX built a giant spaceship. More on that later though.

## A better perspective
What annoys me is that the risks associated with this short sighted perspective are monumental. I'll just go ahead and break them down quickly:

### The problem with "what"
Well, what is 'it'? Right from the start, there's often an assumption that we know in perfect detail what the problem we're solving is, and that
this is set in stone. Let's instead assume that there is a degree of probability for requirements to change over time, that will vary from system
to system. On a tangential note, this is of course one of the reasons not to buy all-in-one solutions, as changing requirements for one part over
time may force you to replace another part that was just fine (smart TV's come to mind).

Another likely fact to accept is that we usually don't know exactly what it is that we need up front. Only after actually applying a solution
can we fully comprehend not only if the solution solves the need in a good way, but also whether we had actually understood the need correctly in
the first place. This obviously makes the case for an iterative approach to problem solving, but that's not what this post is about.

To summarize, I'd like to propose that we accept that instead of trying to understand everything beforehand, we accept that our understanding by
necessity will mature over time. In this perspective, quantifying capex or deadlines is obviously a futile effort.
If this sounds like an undeterministic and potentially expensive approach to you, keep in mind that it only is so in comparison to a version of
reality that most likely is not true.

### The problem with "why"
Arguably, the first question to ask should be "Why do we need this particular piece of functionality?". Assuming the answer to this question would bear
scrutiny in front of the owners of your business, the next question might be "How much so?" Business value is of course not binary, but much like
our certainty of exactly what we need in order to satisfy the "why", a sliding scale from tangential to the core business to absolutely crucial.
Imagine for example that you're an insurance company. In one corner you have your ERP needs. Those are very important, but only in a supporting
role to the actual business. In the other corner you have the very things that make or break your business. The point I'm trying to make here is that depending on
where you are on that scale in a given situation, you should weigh the importance of knowing exactly what you need and how likely that is to change
accordingly. Let's plot these two axes on a graph and see if that helps clarify anything.
![Should you DIY?](/blog/images/should_you_diy.png)
* Bottom Left - With low impact on business value and low innovation pace, you should obviously buy off the shelf. Think Office.
* Top Left - With a very fluid requirement situation, i.e. innovation pace is high but impact on core business is tangential, odds are you're better
off sourcing the solution. You won't have much influence on the direction it goes over time, but that's most likely OK. An example might be the ERP needs mentioned earlier.
Many ERP suppliers compete to raise efficiency in their offerings by some fraction, and while efficiency is important, this is not where you compete. Then again,
building that bespoke plugin or additional feature might still make sense from a business point of view, so it could go either way.
* Bottom Right - Low rate of change, but high impact on your business. Just like top left, this could go either way. If a commercial option is
available that ticks ALL your boxes, it's probably a good idea to go for it, but as soon as any potential for evolution comes into play, you're
likely better of in a situation where you can have a direct impact without relying on a 3rd party. Say for example the backup solution for your
business critical functions. Should be OK to buy off the shelf, but still important enough that it may well justify rolling your own.
* Top Right - If you find yourself here and still have doubts about how to proceed, odds are that you have made a classification error along one or
both of the axes. In the aforementioned insurance company, this might be the software that classifies risk and sets prices. You may be able to start
your business doing what everyone else does, but it's not a healthy option down the line.


## Time To Market, Cost of Change and Total Cost of Ownership
After a slight detour establishing what we know about what we need and why, let's get back to the questions at hand (feasibility, cost, time).

### Feasibility
This one should be simple, the answer is yes. If it isn't, the wrong people are answering it. It should never be acceptable for software to impede or hinder business.
It might be expensive and take a lot of time for good reasons (self-driving cars are a hard problem to solve) or for bad reasons (insufficient competence), but never impossible.
The trick though, is to look beyond the initial challenge and try to take the total cost of ownership into perspective. Solving a software problem once is
usually not very hard, but solving it in such a way that the business logic is easy to adjust as requirements change over time is.

### Cost
If keeping the software in line with business requirements over time is the goal, then that's the cost you should measure, not the cost of
producing software that is sufficient at a specific point in time. The cost of re-writing a solution due to insufficient architectural flexibility
can be massive. The reasons can be many, but usually start in a solution that is either overly complex, not scalable enough or both. Add to this that
the person who wrote it no longer works for the company and you've got a recipe for business disaster. Unfortunately, this isn't a problem easily
solved by simply remembering this the next time around, because the solution itself is a tightrope walk that requires a lot of experience to get right.
Stray too far in the other direction and you may find yourself with a ballooning solution that never really gets to market.

### Time
If business value is in some way established, time will to some degree be a factor although sometimes it's more obvious than other times. Again though,
time to first delivery is important, but it's the compound time to market over all deliveries that must be estimated. This should be one of the deciding
factors between DIY and COTS when you're right on the line shown above. How sensitive will you be to time to market for changing requirements in the future?
Disregarding the fact that you may or may not get exactly _what_ you need, you also may not be able to influence _when_ you get it.


## Making things go fast
So far, so obvious, but what about Conway and Musk? Conway's law states:
> "organizations which design systems ... are constrained to produce designs which are copies of the communication structures of these organizations."
> -- Mel Conway, 1967

From this we learn the value of organizing our resources around business capabilities rather than functions or roles in order to maximize business value efficiency. Awesome.
What is not so clearly spelled out is the cost of the inevitable interfaces between these designs or artifacts, and here's where Mr. Musk comes in.
In an interview with Everyday Astronaut; [![Open in YouTube](https://img.youtube.com/vi/cIQ36Kt7UVg/0.jpg)](https://www.youtube.com/watch?v=cIQ36Kt7UVg&t=60)

Elon is asked how it's possible for SpaceX to have gone
from a complete redesign to a 9 meter diameter, 50 meter tall, almost flight ready spaceship prototype in less than a year. Elon responds that he's
picked up some experience on moving fast over the years (with my comments after);
* "If a design is taking too long, the design is wrong" - accept that you can't design the perfect solution ahead of time or accept horrendous cost and time to market
* "Product errors reflect organizational errors" - problems often occur in the interfaces between systems; interfaces are constraints
* "Everyone is a lead engineer and has to broadly understand how all parts work together" - and must question the constraints from systems they
interface with instead of suboptimizing on their own side

How does that relate to the question of doing yourself or bying off the shelf? From an (enterprise) architectural point of view, both options add the same
complexity, expressed in the interfaces they add to the large picture. Extrapolating from Mr. Musk, a significant cost over time will be associated with these
interfaces, either in plain errors made or simply from the maintenance cost associated with them. Depending on what timescale we're looking at, it will likely turn out
that the up front capital expenditure of acquiring version one of that functionality is outweighed by the operational expenditure from maintaining it, compounded
by 