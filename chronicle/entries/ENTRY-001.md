# ENTRY 001 — Building Minerva — August 6, 2026 — Setting the Rules Before Building the Registries

Today’s work was about something I originally wanted to get past pretty quickly: the rules every Minerva registry is going to have to follow.

I was ready to get into the individual registries themselves. Projects, users, agents, workflows, artifacts, versions—all the different places Minerva is eventually going to keep track of what it knows.

Daedalus caught something I hadn’t really thought through yet.

If we started building those one at a time, we would keep answering the same questions over and over.

How does a record get its identity?

Who owns it?

What happens when it changes?

How do we keep its history?

How does it point to something in another part of Minerva?

How does security follow it?

What happens when another system has a copy of the same information?

I could see the problem once he explained it. We were about to start building the rooms before deciding how the house itself was supposed to be wired.

So instead of defining the first registry, we stepped back and worked on the **Registry Framework**.

That framework is basically the common rulebook every future Minerva registry will inherit from.

The individual registries can still be different. A Project record is obviously not the same thing as an Agent or an Artifact. But they shouldn’t each invent their own way of handling identity, ownership, versions, history, security, and relationships.

That is what we spent this session sorting out.

One of the most important pieces was the idea that each kind of record needs one authoritative home inside Minerva.

Minerva will eventually connect to outside platforms. Some of them may store copies of Minerva information or synchronize with it. That is fine.

What we do not want is a situation where two systems both think they are the original.

I think of it like having a master file and photocopies. The photocopies can be useful. They can be passed around, displayed, or updated from the master. But having a photocopy does not suddenly make it the master document.

That became the **One Source of Truth Rule**.

For each record class, Minerva needs one place that gets to say, “This is the official version.”

We also worked through how Minerva should remember change over time.

Records need stable Minerva identifiers so something can remain the same thing even after it has been updated. Historical references also need to stay intact. If an older production run used Version 3 of something, Minerva cannot quietly point that old record at Version 5 later just because Version 5 is newer.

The history has to mean what it meant when the work actually happened.

That same thinking carries into security and audit history. The system needs to be able to show what existed, what changed, what was used, and what happened to it without relying on somebody remembering the conversation where the decision was made.

Storyline 360 was another major part of the discussion.

Storyline is still Minerva’s first real production target. That has not changed.

What we had to be careful about was letting Storyline shape Minerva so much that Minerva eventually becomes useless anywhere else.

This is one of those areas where I can see how easy it would be to make a short-term decision that becomes a long-term problem.

We need Minerva to understand `.story` files, SCORM packages, Storyline build jobs, integrations, testing, deployment, QA, and rollback.

But that does **not** mean Storyline-specific fields should start appearing everywhere in Minerva.

So we kept that information contained in the parts of the system that actually need it.

The way I understand it is that Minerva should have a general structure, and Storyline should plug into that structure where necessary. Storyline gets what it needs without becoming part of the foundation itself.

That matters because Storyline is the first proving ground, not the permanent limit of the system.

We also preserved both possible production paths for Storyline.

The ideal path is still a complete `.story` file that Minerva can eventually produce and that I can open in Storyline, inspect, and verify.

But we still have not proven that reliable direct `.story` generation is possible.

So we are not treating it like a solved problem.

Minerva also needs to support a controlled build package that can be handed to the Storyline production process if direct generation does not work reliably enough.

That keeps us from building the entire system around something we hope will work.

Human verification remains part of the process either way.

If Minerva produces a Storyline project, we still need to know exactly what version was built, what was tested, what was approved, and how to get back to the last approved `.story` file and published package if something goes wrong.

By the end of the session, the Registry Framework covered the common ground we needed: identity, ownership, metadata, relationships, indexing, security, versioning, audit history, and the rules that should keep future registries consistent even as Minerva grows.

We checked it against the Minerva Architecture, Data Dictionary, Core Design Principles, and the requirements for the first Storyline deployment.

Those checks passed.

But the important part is that passing those checks does **not** mean the framework is finished.

I have not approved it yet.

It has not been frozen.

We also did not start designing a database, an API, implementation schemas, or any of the individual registries.

And no durable Minerva artifact was created from this work. Right now, the proposed framework still exists only in the conversation.

So this is another deliberate stopping point.

The next move is not to start building the first registry.

The next move is for me to review the Registry Framework and decide whether these are really the rules I want everything else built on.

If something needs to change, this is the time to change it.

If it holds up, I approve it, we freeze it, and then the individual registry work can begin.

---

**Entry:** ENTRY 001  
**Date:** August 6, 2026  
**Phase:** Foundational Architecture — Registry Framework Design  
**Artifact:** Proposed Minerva Registry Framework  
**Status:** Structurally complete; alignment checks passed; human approval pending; not frozen  
**Key decision:** Establish one common framework for all future Minerva registries while keeping Storyline-specific requirements isolated so Storyline does not become Minerva’s permanent boundary  
**Next action:** Review the proposed Registry Framework and either approve it as the frozen baseline or request revisions before defining any individual registry