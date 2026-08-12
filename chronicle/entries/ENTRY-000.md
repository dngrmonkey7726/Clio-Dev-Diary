# ENTRY 000 — Building Minerva — Founding Period through August 6, 2026 — The Beginning

## Where This Actually Started

Minerva did not start because I decided I wanted to build a software platform.

It started because I had a much more practical question.

**How much of building a self-paced training course in Articulate Storyline 360 could I automate using ChatGPT and AI agents?**

I was already doing this kind of instructional-development work. I knew how much went into taking source material, figuring out what actually needed to be taught, organizing it, building the slides and interactions, checking everything, and eventually publishing the course.

So the original idea was fairly straightforward: give AI the source material, have it help develop the instruction, and then find some way to automate the actual construction of the course in Storyline.

I wasn't looking for another tool that could just write course text or give me a storyboard. I wanted to see how close we could get to the real finished product.

Ideally, that meant ending up with an actual `.story` project that I could open in Storyline 360, inspect myself, and eventually publish as a SCORM package for the district's learning platform.

That was the idea.

The problem was that the closer we looked at what it would actually take to do that reliably, the bigger the idea became.

## The First Problem Wasn't Storyline

One of the first things that complicated the idea was the source material.

Real projects don't arrive neatly packaged with everything labeled and organized for an AI system.

Sometimes I might get a PowerPoint. Sometimes it is a PDF or a stack of handouts. It could be a video, an existing course, an old Rise course that needs to become Storyline, or something that needs to be updated rather than completely rebuilt.

Sometimes the request might basically amount to, "We need training about this."

That meant the system couldn't just be an automated pair of hands clicking around inside Storyline.

Before it could build anything, it had to figure out **what I had actually given it**.

And even that wasn't enough.

I didn't want it blindly copying old material just because the material had been supplied. Sometimes existing training needs clarification. Sometimes it is outdated. Sometimes the information is correct but the way it teaches the subject isn't very good.

At the same time, I definitely didn't want AI quietly deciding that it knew better and rewriting authoritative information on its own.

That created a line we needed Minerva to understand: preserve what the source actually says, but recognize when something may need improvement. It can question something. It can recommend an improvement. It can research an update. But those things need to stay distinguishable from the original source instead of quietly becoming part of it.

That was one of the first signs that this was going to require more than a clever prompt.

## I Also Didn't Want One Giant ChatGPT Conversation

I had already run into another problem with large ChatGPT projects.

Threads get big.

The more work you pile into one conversation, the more unwieldy it becomes. I didn't want a future Storyline production system to work only because one enormous chat happened to remember everything that had occurred before it.

I wanted to be able to start a fresh production project and still have the system know what mattered.

That eventually led to a principle that became much more important than I realized when I first raised the problem:

**The conversation shouldn't be the record.**

A conversation can help us create something, but anything Minerva actually needs to depend on should be saved somewhere durable.

I think of it a little like working at a counter with a customer. You can have a great conversation and make all kinds of decisions, but if none of those decisions make it onto the work order, the installer who comes in tomorrow has no reliable way of knowing what was agreed to.

Minerva needed the equivalent of the work order.

That became the beginning of separating the conversations we use to develop things from the actual records Minerva trusts.

## Then the Agents Started Creating More Questions

My original thinking also involved multiple AI agents.

I didn't want to spend forever copying information from one ChatGPT conversation into another just so different agents could do different jobs. If we were going to have specialized agents, they needed some way to work together.

That sounds simple until you start asking what "work together" actually means.

What does each agent know?

What is each one allowed to change?

How does one hand something to another?

How does the next agent know that the previous one finished?

What happens if something fails?

When should Minerva stop and ask me?

Those were no longer really Storyline questions.

We were starting to talk about how an entire production process would be controlled.

I also wanted Minerva to guide the person using it instead of requiring them to know the magic prompt for every situation. If there are three reasonable things that can happen next, I would rather the system present those choices than make somebody guess what they should type.

The simple **Approve / Revise / Stop or Handoff** choices we started using while developing Minerva became an early example of what I meant.

I wasn't trying to remove humans from the process.

I was trying to remove unnecessary guessing from the process.

## "Run It 100 Times"

Another idea I kept coming back to was testing.

If we eventually had an AI deciding what needed to be built and then handed those instructions to something operating Storyline on a Windows computer, I didn't want our standard for reliability to be, "Well, it worked when I tried it."

My early way of putting it was basically:

**Run it 100 times first.**

The number itself wasn't really the point.

The point was that AI can produce something convincing once and still be unreliable.

We needed to know what happened when the same process was repeated. Did important source information disappear? Did assumptions start appearing? Did the meaning change? Did the output vary too much? How often did validation fail? How long did it take? What did it cost?

That simple idea eventually grew into Minerva's approach to testing.

It also helped clarify something else that became important later: giving generative AI the exact same inputs does **not** guarantee that it will produce the exact same result.

That was an assumption we had to correct as the architecture developed.

Minerva can record exactly what went into a production run. That doesn't mean the AI itself suddenly becomes perfectly repeatable.

## The Agent Shouldn't Be the One Clicking the Buttons

Another distinction gradually became important: **Agents and Workers are not the same thing.**

This took the idea of automation and split it into two very different jobs.

An Agent reasons about what should happen.

A Worker carries out approved instructions.

For Storyline, that means an instructional Agent might determine what a slide needs to teach, what should appear on it, and how the interaction should behave.

The Windows Worker operating Storyline shouldn't suddenly decide that it has a better instructional idea halfway through the build.

It should build what it was told to build.

A useful way of thinking about it is the difference between somebody creating the plans and somebody following those plans on the job site. Both jobs matter, but you don't want the person installing something casually changing the plans because they felt like doing it differently.

And between those two, there are places where a human still needs to approve what is happening.

That separation made the system safer, but it also made it easier to imagine changing the technology underneath Minerva later. The reasoning doesn't have to be permanently tied to whatever tool happens to be controlling Storyline today.

## Somewhere Along the Way, We Weren't Just Automating Storyline Anymore

This was probably the biggest change in the project.

At some point, the questions Daedalus and I were working through stopped being mainly about how to automate Storyline.

We were talking about projects, agents, workflows, source material, templates, approvals, versions, testing, workers, finished products, and how Minerva would remember what happened.

That was when I made the decision to treat this as a real software product.

We paused the production workflow.

Instead of immediately creating agents and trying to automate Storyline, we started designing the system that would control all of it.

For a while, we called that idea the **Factory Operating System**.

That name made sense for what I thought we were building at the time. It was the machinery behind the factory—the thing coordinating all the individual parts.

But the more we worked through it, the more obvious it became that the idea was bigger than a Storyline factory.

It needed to take information in different forms, understand it, preserve what mattered, help turn it into effective instruction, coordinate the work required to produce something, check the result, keep a history of what happened, and ultimately produce learning products.

That became **Minerva**.

Storyline didn't disappear from the plan.

It became the first place where Minerva has to prove that all of this actually works.

## Where Daedalus Fit Into This

My role in all of this has been pretty consistent.

I know what I want Minerva to accomplish.

I know the practical problems I want it to solve, how I want someone to be able to work with it, and what I don't want the experience to become.

What I didn't come into this knowing was how to architect a software platform.

That is where Daedalus became important.

As the project grew, I started using Daedalus less as "ChatGPT, make the next thing" and more as someone whose job was to challenge what I was proposing.

Sometimes that meant catching a consequence I hadn't considered. Sometimes it meant telling me that we were trying to build something too early. Sometimes it meant explaining why an idea that sounded simple to me required another layer underneath it.

We eventually formalized that relationship.

I'm the Product Owner. I define the vision, requirements, outcomes, and final decisions.

Daedalus is the Chief Systems Architect. His job is to challenge assumptions, find structural problems, recommend what needs to happen first, and help turn what I'm trying to accomplish into something that can actually hold together.

Then the Minerva Workshop is where those decisions get turned into the formal documents Minerva will eventually depend on.

That gave us a much better rhythm: I bring the problem or idea, Daedalus and I work through what it really means, the Workshop documents it, Daedalus checks the result, and I decide whether to approve it or send it back.

## Building the Foundation Instead of the Machine

This led to another course correction that I probably wouldn't have made at the beginning.

We deliberately slowed down.

I wanted to build the automation.

Instead, we started building the rules the automation would eventually have to live by.

We established the overall Minerva Architecture. Then the Data Dictionary, which started defining the information Minerva needs to understand and preserve. Then the Core Design Principles, which captured the rules we don't want to accidentally abandon later when we're focused on getting something to work.

Some of the ideas that came out of that now seem obvious, but they weren't necessarily obvious when we started.

Important information needs to survive beyond a chat.

Original source meaning needs to be protected.

Important decisions should be visible rather than hidden inside AI behavior.

Versions matter.

Humans remain accountable.

Automation should follow the design of the system rather than dictate it.

And Minerva shouldn't be built so tightly around today's technology that changing a tool later means rebuilding everything.

We also kept coming back to instruction itself.

Successfully preserving source material isn't enough if Minerva produces terrible training from it.

The goal isn't just accurate content.

It has to teach.

## Storyline Still Has to Be Real

There was a danger in all this architecture work that Minerva could become a very elaborate idea that never actually produced anything.

I didn't want that.

So Storyline 360 stayed anchored as the first measurable production target.

Eventually, the path needs to start with source material and end with something that can become a real Storyline course, be opened and checked by a human, published as SCORM, placed into the learning platform, and tested there.

One part of that remains unresolved.

I would like Minerva to generate a complete `.story` file directly.

We do **not** currently know that we can do that reliably.

Rather than design everything around the assumption that we will figure it out, we classified direct `.story` generation as an unproven capability.

If we prove it works, great.

If Version 1 instead needs to produce a controlled build package or a partially automated Storyline project, that is still a valid path.

That decision is a good example of how Minerva has changed from the original idea. We're trying to separate what we **want** the system to do from what we have actually **proven** it can do.

## The Latest Pause

Just as we were getting ready to start defining Minerva's individual registries, Daedalus caught another issue.

We could start building them one at a time, but then we'd be making the same basic decisions over and over.

How does this one identify a record?

Who owns it?

How does this one handle history?

What about security?

What happens when something changes?

How does it point to something stored somewhere else?

Instead of answering those questions twenty different times and hoping all twenty answers matched, we paused again.

That's what led to the **Registry Framework**.

I think of it like establishing the building code before constructing the individual buildings. The buildings can have completely different purposes, but there are certain rules you don't want every construction crew reinventing independently.

That framework also established another rule I think will become increasingly important as Minerva starts connecting to outside systems:

**There needs to be one place where the official version of each kind of Minerva record lives.**

Other systems can have copies. They can synchronize information. They can display it.

But having a copy doesn't make something the original.

## Where Minerva Stands at the Beginning of This Chronicle

That brings me to August 6, 2026, and the reason this is **ENTRY 000** instead of ENTRY 001.

The Chronicle didn't exist while all of this was happening.

By the time I decided we needed to start documenting Minerva's development as a story instead of only preserving the technical records, the project had already changed substantially.

What started as:

**Can I use AI to automate building Storyline courses?**

had gradually become:

**What kind of system would I need to build so AI could do this reliably, safely, repeatedly, and eventually across more than just Storyline?**

We didn't know the answer to that when we started.

A lot of the foundation came from discovering that the simple version of the idea wasn't enough, stopping, figuring out what was missing, and then moving forward again.

As of August 6, the Minerva Architecture, Data Dictionary, and Core Design Principles are approved and frozen.

The Registry Framework is structurally complete, but I still need to review and approve it before it becomes part of that frozen foundation.

We haven't started the individual registry schemas or artifact schemas. We haven't established the naming standards. We haven't written implementation code.

And we still haven't proven that Minerva can reliably generate a `.story` file directly.

So there is an enormous amount left to build.

But the thing that exists now is very different from the thing I originally imagined.

I started out trying to automate Storyline.

Before I could do that properly, I had to start figuring out how to build Minerva.

And this is where the Chronicle begins.

---

**Entry:** ENTRY 000  
**Date:** Founding Period through August 6, 2026  
**Phase:** Founding / Foundational Architecture  
**Artifact:** Minerva Founding Chronicle Entry  
**Status:** Draft Chronicle entry; Architecture, Data Dictionary, and Core Design Principles approved and frozen; Registry Framework awaiting human approval  
**Key decision:** Treat Minerva as a real instructional-production software product, with Storyline 360 as its first measurable proving ground rather than the permanent boundary of the system  
**Next action:** Review and either approve or revise the proposed Minerva Registry Framework before beginning individual registry design