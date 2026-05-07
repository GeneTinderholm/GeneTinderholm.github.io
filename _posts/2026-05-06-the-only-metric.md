---
layout: post
title:  "The Only Metric That Matters"
date:   2026-05-06 08:00:00 -0500
categories: development
---

It's been over two years since my last post. Part of this is that my dad died pretty soon after my last post, and I haven't had anything to say that I wanted sent out to the public. The other part is that tech has been changing the past few years, and I didn't feel like I had anything solid to point to. That seems to be over, and I'm going to summarize my thoughts here.

After working with AI coding assistants for the last year, they do seem really impressive, but as far as I can tell, there's only one metric that matters, and it's the same metric that mattered before all of this started. "How many devs on your team actually care?" If that's more than half, there's not much anyone can do to stop you, if it's less than half, there's not much anyone can do to make you succeed. I'm not saying AI is useless. It generates boilerplate very well. The assistants are excellent for learning a new skill or exploring new territory, or for generating something quick. I love them, and use them regularly both at work and on side-projects. The thing is that, on a long-term project, those things amortize to zero.

Let me elaborate, the industry has settled on tickets as a way to describe a unit of dev work. The problem with this is that there's always two ways to complete a ticket.

1. The way the ticket says
2. The way the stakeholder needs

There's not enough specification in the world to constrain an unmotivated engineer to always do 2, and very quickly, specifying it requires more effort than just doing it yourself. The AI, not really caring, and only examining the context, is effectively an unmotivated engineer. We're still in the same situation we were in before. There's a fundamental bottleneck on stakeholder context that has always existed in development work, and getting past it required devs to seek out and internalize the wants and needs of the stakeholders, often by being a stakeholder themselves (this is much more common in open source). That's the main difference between a 10x dev and the median dev.

But, surely coding assistants are transformational? One or two devs can now completely scoop big tech companies. SaaS apocalypse. Everything changed.

No, it didn't. A few motivated people could always completely embarrass the giant tech companies with thousands of employees. Stories of this happening were common in the 90s and 2000s. We developed XP and Agile to deal with the fact that communication overhead (sharing context) was the hard part. It's still the hard part, and having the human not write the code is significantly slower in the long-term for two reasons.

1. The human no longer has an intuitive sense of system behavior. They have to investigate what the behavior of the current system is. (Does a trailing slash cause an error when calling this api? If so, does the config value that was just generated cause problems? How many areas like this are there in the system?)
2. The human still has to get the context, but now they have to distill it simply enough that the AI coding assistant can understand it. This is a monumental task that devs didn't have before, and if you skip it, you're relying on, effectively, roulette that you get lucky enough and the AI generates a good version. This takes, at least as long as writing it yourself.

How exactly did we forgot that two motivated devs could scoop the big boys? How did we forget that behind every software project is a few good engineers who care way more than is healthy? I have a rather cynical take on this. Most managers would rather predictably fail than have a chance to succeed. This isn't completely irrational in the small scale. A project with a 75% chance of failure fails to meet expected value three quarters of the time, and the manager looks bad. It's really easy to manage expectations on a failing project, and the default state of software projects is to fail, by which I mean that they produce a pile of code that doesn't help anyone. And what's the upside for the manager? They have a project that everyone is paying attention to, and a bus factor of one to two people who care, ready to make them look bad as soon as those people move on. In the large scale, however, this destroys the entire point of our industry. There's a very simple test for which ones run your current organization. Have any of the managers who are currently so concerned about dev productivity, ever cared enough to cancel a meeting? If no, it's kabuki theater.

People sold us process. We were sold Jira, agile, XP, TDD, and pairing. Those things are all fine, to some extent, testing is actually great, although I don't have a strong opinion on if it happens before or after. None of these things, however, actually move the needle. All of those things were pioneered by a group of engineers who cared. That's the thing that mattered. Groups of engineers who cared built operating systems way more complex than any web app before any of these things showed up.

The tide is going out. The kind of dev who always does exactly what the ticket says is useless now, but they always were in the long-term. Everything is different, but nothing has changed. Next time you pick up a ticket, ask yourself, am I doing what the ticket says, or what the stakeholder needs?
