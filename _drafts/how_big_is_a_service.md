---
layout: post
title:  "How big is a service?"
categories: architecture ddd
---
## Introduction
A major promise when going from a monolith to a distributed architecture (such as microservices) is that
your organization can scale with the granularity of the architecture. I.e, split your thing into ten parts,
put one team on each of those parts and all of a sudden you can have ten teams working independently of each other. In theory, that is.


### The Risk
The risk with going down this route is that growth becomes its own goal, and you end up with more parts than you actually need.
That's a problem because every boundary comes with a cost. There's the technical aspect of maintaining a very strict interface
between services that can introduce unnecessary cost, but perhaps more costly is the human interface between teams. It appears
that that many early adopters of microservices have found themselves with too many services to handle, and the need to
consolidate rather than divide.


### Conway's Law
In 1967, Mel Conway [stated that](https://en.wikipedia.org/wiki/Conway%27s_law) organizations are constrained to produce designs
that are copies of their communication structures. When asked how it's possible for SpaceX to move at the pace it does,
[Elon Musk responded](https://www.youtube.com/watch?v=cIQ36Kt7UVg) that most problems occur in the boundaries between teams.
In other words, if you split your rocket development project into two parts, say engines and the rest, chances are you'll be
running into issues in the boundary between them, because communication is inherently harder between groups than within them.
Elon claims that the secret sauce behind solving this is to make everyone "chief engineer", and simply not allow anyone to accept
an inferior interface that requires changes locally to work, but rather to work together with the other team in designing something
that works for both sides. While a very admirable goal, it should perhaps be pointed out that this assumes an organization capable
of shouldering such a responsibility and thus a very high level of competence on all parts.


### Lewis and Lewis
Way back in 2014, Martin Fowler and James Lewis wrote an [excellent article](https://martinfowler.com/articles/microservices.html),
giving definition to the new idea of microservices, and on the topic of division they identify the importance of having
cross-functional teams organized around business capabilities, because that's what you're going to get out in the end. Excellent
advice of course, but it doesn't fully answer the question of how many teams you should have, and how many services each team should be responsible for.


### Bounded Context
[Domain driven design](https://en.wikipedia.org/wiki/Domain-driven_design) to the rescue!
