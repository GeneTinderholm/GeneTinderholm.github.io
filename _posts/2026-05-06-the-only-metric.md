---
layout: post
title:  "The Only Metric That Matters"
date:   2026-05-06 08:00:00 -0600
categories: development
---

It's been over two years since my last post. Part of this is that my dad died pretty soon after my last post, and I haven't had anything to say that I wanted sent out to the public. The other part is that tech has been changing the past few years, and I didn't feel like I had anything solid to point to. That seems to be over, and I'm going to summarize my thoughts here.

After working with AI coding assistants for the last year, they do seem really impressive, but as far as I can tell, there's only one metric that matters, and it's the same metric that mattered before all of this started. "How many devs on your team actually care?" If that's more than half, there's not much anyone can do to stop you, if it's less than half, there's not much anyone can do to make you succeed.

Let me elaborate, the industry has settled on tickets as a way to describe a unit of dev work. The problem with this is that there's always two ways to complete a ticket.

    1. The way the ticket says
    2. The way the stakeholder needs

There's not enough specification in the world to constrain an unmotivated engineer to always do 2, and very quickly, specifying it requires more effort than just doing it yourself. There's a fundamental bottleneck on stakeholder context that has always existed in development work, and getting past it required devs to seek out and internalize the wants and needs of the stakeholders, often by being a stakeholder themselves. That's the main difference between a 10x dev and the median dev.

But, surely coding assistants are transformational? One or two devs can now completely scoop big tech companies. SaaS apocalypse. Everything changed.

No, it didn't. A few motivated people could always completely embarrass the giant tech companies with thousands of employees. Stories of this happening were common in the 90s and 2000s. We developed XP and Agile to deal with the fact that communication overhead (sharing context) was the hard part. It's still the hard part, and having the human not write the code is significantly slower in the long-term for two reasons.

    1. The human no longer has an intuitive sense of system behavior. They have to investigate what the behavior of the current system is. (Does a trailing slash cause an error when calling this api? If so, does the config value that was just generated cause problems? How many areas like this are there in the system?)
    2. The human still has to get the context, but now they have to distill it simply enough that the AI coding assistant can understand it. This is a monumental task that devs didn't have before, and if you skip it, you're relying on, effectively, roullette that you get lucky enough and the AI generates a good version.

Somehow we forgot that two motivated devs could scoop the big boys. I have a rather cynical take on this. Agile was so obviously dominating that managers had to adopt it, but they didn't want to risk succeeding. They wanted to fail predictably. This is, on one hand, very easy, because the default state of software projects is to fail, but on the other hand saps the entire point of even doing a software project. There's a very simple test for which ones run your current organization. Have any of the managers who are currently so concerned about dev productivity, ever cared enough to cancel a meeting? If no, it's kabuki theater.

The tide may be going out. The kind of dev who always does exactly what the ticket says is useless now. But they always were in the long-term. Next time you pick up a ticket, ask yourself, am I doing what the ticket says, or what the stakeholder needs?
