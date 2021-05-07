---
layout: post
title:  "Build or buy?"
categories: [architecture, enterprise, cots, value]
date:   2021-04-27 15:36:00 +0200
---
## Build or buy
Need a digital solution?. Every now and again strategic decisions need to be made about business applications, whether to build them yourself or source externally, and whether to do that in parts or as a whole. 
In this post I'd like to make an argument for a method of making such decisions that factors in business value both short and long term.
It's probably safe to assume that once we're in a position to decide about buying a solution off the shelf or building it in-house, we've established _what_ we're getting and _why_, right? 
I'd like to take a closer look at those assumptions and maybe challenge them a little bit.

### The problem with "why"
Arguably, the first question to ask should be "Why do we need this particular piece of functionality?". Assuming the answer to this question would bear scrutiny in front of the owners of your business, I'd like to pose the question "How much so?" 
Business value is not binary, and I would like to make an argument for trying to quantify that business value on a scale from "tangential" to "competitive edge" as an input to use in the decision to build or buy. That may sound like a no-brainer, and if it is there's not much effort lost, is there? 

Sometimes though, especially in larger organizations, there is a risk of local sub-optimizations in different departments due to factors such as political maneuvering or simply a lack of visibility of the larger perspective that may not always align with the global optimum, so this quantification can if nothing else serve as a common point for alignment within the company.

For arguments sake, let's imagine that we're starting an insurance company. We'll need a way to keep track of all our clients, contracts, claims, accounts and so on, so some sort of ERP system would be nice. It will be important for the efficiency of the business, but can the same be said for effectiveness? Efficiency is of course important, and maybe, with everything else being equal, that efficiency can be what allows us to pull ahead in a competitive market, but odds are effectiveness will have a larger impact. How do we achieve effectiveness? By being good at assessing and managing risk, and thus pricing our contracts in a profitable and sustainable way. There may be other ways of being competitive, but being good at the core of the business is likely to be a success factor.
With this in mind, we can determine that an ERP system is probably closer to the "tangential" end of the previously mentioned business value scale, while a system that calculates risk and pricing might land closer to "competitive edge". Is that then enough to make a decision about whether we should build or buy them? Not so fast...


### The problem with "what"
Having established why we need something, let's also look at what it is we think we need. Different types of software have different rates of innovation and evolution, and I believe this to be a crucial factor to consider. Just like we had an axis for business value, let's imagine another axis for "rate of change" or "innovation pace". It's not easy to look into the crystal ball and determine how much something will need to change over time, but let's go back to the fictive insurance company and add two more pieces of functionality we'll probably need; some form of office software suite and some kind of backup solution for all of our business data.
We need an office suite for writing all sorts of documents, but apart from look and feel and perhaps collaborative functions, very little has changed in Word, Excel or Powerpoint over the last 20 years in how you use them on a daily basis, or what you use them for. The same can be said for backup solutions, it's not a terribly complicated use case and the innovation rate is not very high.
On the other hand, the ERP market is pretty competitive, especially when it comes to synergetic effects made possible by integrations, and the rate of change can be high. When it comes to the core business aspects of risk assessment and pricing calculations, it's easy to see that whoever has the upper hand here will come out on top over time, and these systems will therefore by their very nature have to evolve over time.
The innovation pace axis should also help us project a total cost of ownership for the system we're considering, which underlines the importance of a solid architectural foundation and codebase under control for systems that are prone to change over time. When talking about the core business, it's even likely that we don't even know exactly what the first iteration _should_ look like, making efforts to try and define capex or fixed deadlines up front counter productive.
Likewise, the argument can be made that it's a good strategy to split your systems into modular pieces in such a way that you don't mix different innovation requirements in the same system, or risk having to rebuild parts that work just fine just because it's coupled too closely with something that changes.

### Plotting it on a graph
Since we've now established two different axes of importance, "business value" and "innovation pace", let's plot them in a nice graph and see if we can fit the four different systems we discussed earlier.
![Should you DIY?](/blog/images/should_you_diy.png)
The gradient is meant to convey that the decision is easy in the bottom left and top right corners, and the squiggly line represents the fact that whenever you find yourself close to the dividing line between COTS and DIY, other aspects of your organization may tip the scales in some direction.
* Bottom Left - With low impact on business value and low innovation pace, we find our office suite. Unless making office suites is your core business (in which case it wouldn't be in the bottom left), it's obvious we should buy this off the shelf.
* Top Left - With a very fluid requirement situation, i.e. innovation pace is high but impact on core business is tangential, odds are you're better off sourcing the solution. You won't have much influence on the direction it goes over time, but that's most likely OK. An example might be the ERP needs mentioned earlier. Many ERP suppliers compete to raise efficiency in their offerings by some fraction, and while efficiency is important, this is not where you compete. Then again, building that bespoke plugin or additional feature might still make sense from a business point of view, so it could go either way.
* Bottom Right - Low rate of change, but high impact on your business. Just like top left, this could go either way. If a commercial option is available that ticks ALL your boxes, it's probably a good idea to go for it, but as soon as any potential for evolution comes into play, you're likely better off in a situation where you can have a direct impact without relying on a 3rd party. Say for example the backup solution for your business critical functions. Should be OK to buy off the shelf, but still important enough that it may well justify rolling your own.
* Top Right - If you find yourself here and still have doubts about how to proceed, odds are that you have made a classification error along one or both of the axes. In the aforementioned insurance company, this might be the software that classifies risk and sets prices. You may be able to start your business doing what everyone else does, but it's not a healthy option in the long term.

### Conclusion
Unfortunately, I feel that too often the focus in discussions of this nature focus on short term objectives. How much will it cost? How long will it take? I think that we've established that if you have easy answers to those questions, you're probably in the market for a commercial off-the-shelf solution. If you try to apply the same logic to things that are central to business needs and/or likely to change a lot over time, odds are you'll end up severely disappointed. 

Another limiting factor might be _can_ we do it? This is tricky, because many organizations repeat the same mistakes over and over, especially when it comes to underestimating the innovation needs over time. Most development teams are capable of producing a working first iteration of a system, but the true test comes over time. 

Is the architecture conducive to change? Is the knowledge of the business domain captured in good tests so that you dare change key components after the people who wrote them left the company? In too many cases, code bases spiral out of control, and when the day comes that the business requirements change a little too much it's simply expected that a full rewrite is required. Let's try to be better than that.
