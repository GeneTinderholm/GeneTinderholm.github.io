---
layout: post
title:  "Abstraction as Optimization for Change"
date:   2024-02-04 12:00:00 -0600
categories: development
---
I've been a professional software engineer for a while now, and a hobbyist hacker for a long time. One of the problems that comes up on the professional side that I rarely see on the hobbyist side is every so often I'll go into a project and find that, despite adhering to all best practices, the project is horrible to work with. Each line of code makes sense, but you can flail around for hours without finding anything to grab onto.

I've been thinking recently about why that is. Were these projects made by idiots? Am I the idiot? Is software inherently doomed? I don't really think it's any of these things. Ok, well, I *am* an idiot a lot of the time, but I'm reasonably competent at reading code.

The projects I've been on where making a change is like pulling teeth have, for the most part, been projects where everything is abstracted to high-hell. At a certain level of abstraction, if that abstraction isn't perfect, you have to do this weird puppetry and pull the strings on the abstraction to move the underlying machinery to do the thing you want to do. This, invariably, ends up with the code depending on the implementation details of an interface somewhere. The hacker part of me, the part of me that loves proving my mastery over a system and my ability to bend it to my will, can ride the high after one of these for several days. The part of me that likes software, on the other hand, is usually in a separate room crying.

Alright, so... bad abstractions are bad? Real clever insight there. Thanks for that. Not so fast. Not all of these have been bad abstractions, or at least they didn't all start out that way. They were merely not perfect. And if that's the bar we need, perfect is a lot harder to hit than not bad.

I think to investigate this, we need to back up and go back to why we abstract things. We abstract things when they need to change frequently. From getters and setters to device drivers, what we're really doing is optimizing our system to be able to change easily.

I think this is one of the first lessons a lot of new programmers get in enterprise settings. Wrap your properties in getters and setters, that property might go away, and this will let us change that without updating everywhere in the code that property is used. Similarly, stop for a second and imagine a world where the linux kernel had to be compiled for every possible permutation of hardware, or had to have one giant switch inside it for each possible piece of hardware that could be used. And this is great. Ok, well, we have better ways of doing things than getters and setters this side of 2005, but the idea is great. We program to an interface and the unimportant details are switched out. We can change the behavior in all places that our function is used easily.

So, what about when we only need to change it in 50% of places? Boolean flags. Boolean flags happen. And with them, the problems begin.

```java
void doThing(Object o, boolean shouldSerialize, boolean shouldSync, boolean shouldNotFire, boolean dryRun, boolean isNotRecorded) {
```
<div class="subtitle">
    <p>Oh, good. Today's gonna be one of <em>those</em> days</p>
</div>

Is there anything inherently wrong with boolean flags? No. There are plenty of ways to use them properly, especially if you only have one or two of them. But it never seems to end with one or two of them, and it always ends up the same way. I get why boolean flags happen. People put a system in place to make sure they didn't have to spend days tracking down and changing their code, they're probably not willing to spend several days tracking down half of the uses and change them out. I get it. That's hard to justify to the business, especially when you're on a tight timeline. Plus it's boring.

But boolean flags mean if statements in the implementation, the more boolean flags, the more if statements. You end up with a whole mess inside there that needs to be considered whenever you see this abstraction, compared to the one piece of code you'd have to keep in your head if the abstraction wasn't used. Eventually, you get to the point where the only thing you can do is add more boolean flags, as you can default the flag to false for the old behavior and be sure that the code that runs at the old call sites hasn't really changed.

This would all be fine if abstractions were free, but they aren't. Abstractions, by their nature introduce a new concept into a code base, and concepts have a cost. That's fine sometimes. This profession, by its very nature requires us to grapple with new concepts constantly. But, somewhere between 1 and 100,000 getting into the code base turns into an absolute slog. This is why some of the best abstractions are the ones that let you accomplish some goal without understanding several underlying concepts. The worst ones are the ones that need you to understand everything below them *as well* as the concept behind the abstraction itself. The problem with introducing abstractions is that the people introducing them almost always understand the underlying concepts. They no longer remember what it's like to not understand them.

So, abstractions end up with our code being hard to change, and the people who introduce abstraction are the ones least equipped to judge their quality? We're just screwed? Do we all just never abstract, retreat into a monastery somewhere, write nothing but C, and flog ourselves all day as penance? No. Ok, well, if you want you can. I'm not your boss. But, I don't think that's *required*. I think we're just running into the most overused quote about programming of all time.

> premature optimization is the root of all evil

If the title didn't give it away. I think this is, fundamentally, an optimization problem. We've optimized our code to be able to change it all at once, neglecting that that's not always the area of concern when changing code. Sometimes we want to change a percentage of it. Part of it is experience, but knowing when pieces of code will change together and which ones are just accidentally the same *right now* is an important skill to develop. But even with that, there are times when the business throws a curve-ball at you, and you have to pull apart two things that were linked before. I don't have the perfect answer for this, I don't know your code base, maybe two things really will be linked forever. But if you're writing a greenfield app, maybe let things just be gronky code for a bit until the underlying concepts firm up is a good idea. Opt for module level abstractions instead of global ones if you can for a while until you're really sure that this abstraction is a good idea, things in the same module are much more likely to change together than things in completely separate parts of the project. And most of all, err on the side of getting rid of an abstraction that's not working or creating a new one rather than hacking in a boolean flag into the old one. Some of the worst abstractions I've seen have really needed to be 3 or 4 abstractions.
