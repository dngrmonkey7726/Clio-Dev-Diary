# ENTRY 003 — Building Neptune — August 10, 2026 — Deciding What Neptune Is Allowed to Become

## What I Set Out to Do

Today was the real beginning of Project Neptune.

The idea sounds simple when I say it quickly: I have a dedicated 2017 iMac, and I want to turn it into a local AI agent.

But I don't just want another chatbot running on a computer in my house. I want Neptune to eventually be able to operate parts of that computer, diagnose problems, manage some of its own services, remember useful information, maintain backups, and eventually interact with other systems I authorize.

That changes the problem quite a bit.

The obvious place to start would have been picking an AI model, installing some software, and seeing what the old iMac could handle.

Instead, most of today's work ended up being about something more fundamental:

**Before I teach Neptune how to control a computer, I need to decide exactly what it is allowed to control.**

And just as importantly, I need to decide what happens when something goes wrong.

## What We Worked Through

The first thing I wanted was a clear definition of what a usable first version of Neptune actually means.

We settled on three jobs.

First, Neptune should be a **local AI assistant**. It should be able to hold useful conversations and eventually maintain its own local memory and history.

Second, it should become a **controlled operator of its own iMac**. That means being able to inspect the machine, launch approved applications, work with approved files, and eventually execute commands and scripts.

Third, Neptune should become a **self-managing agent host**. It should monitor the computer it lives on, recognize problems, maintain logs and backups, recover from ordinary failures, and give me a dashboard where I can see what it is doing.

That third part is where the project started getting interesting.

If Neptune can diagnose its own computer and eventually make changes to it, then I am effectively giving software the ability to work on the machine that controls the software.

That creates a circular problem.

If Neptune is allowed to change its own permissions, rewrite its security rules, alter its audit logs, or decide that its own modified code is trustworthy, then the security system isn't really controlling Neptune anymore. Neptune is controlling the security system.

So we established one of the most important rules of the project:

**Authority should be harder to grant than to remove.**

Neptune can eventually be given more capability as I test it and trust it, but it cannot give that capability to itself.

## Knowing Me Isn't the Same as Having My Permission

Another distinction that became important today was the difference between Neptune recognizing me and Neptune being authorized to act for me.

Those aren't the same thing.

Neptune may eventually recognize that I'm the person sitting in front of it, but that doesn't mean it gets to install software, change security settings, access restricted services, or make a purchase simply because it knows I'm AJ.

For privileged operations, there will be another authorization layer.

That includes MFA for defined high-risk actions, session expiration, trusted-device controls, lockouts after repeated authentication failures, and deliberate confirmation for critical actions.

The idea that finally made this clear for me was pretty simple:

**Recognition answers "Who are you?" Authorization answers "Are you allowed to do this?"**

Neptune needs to know the difference.

## Diagnosing Something Doesn't Mean You Get to Fix It

I also wanted Neptune to have fairly broad diagnostic ability.

If something goes wrong with its host, I want it to be able to look at logs, running processes, network activity, installed software, updates, system resources, configuration, and eventually known vulnerabilities.

But we deliberately separated **diagnostic authority** from **repair authority**.

Neptune being able to discover that something is wrong doesn't automatically give it permission to change the system.

That sounds restrictive at first, but it makes sense.

A mechanic being allowed to inspect my car and tell me the brakes are bad isn't automatically permission to start replacing parts. Diagnosis and repair are two different permissions.

Neptune will work the same way.

When it eventually performs a consequential action, the sequence will be:

**Request → Approval → Checkpoint → Execution → Verification**

That last step matters more than I originally appreciated.

A command saying "success" only tells me the command ran successfully. It doesn't necessarily tell me the problem was actually fixed.

Neptune has to verify the result.

And if it discovers halfway through that another consequential action is required, it doesn't get to quietly add that action to the job. It stops and asks.

## Putting Neptune in Park

One question I raised was whether something called "maintenance mode" could accidentally become a security hole.

Normally, maintenance or developer modes make me think of getting deeper access to a system. That is exactly what I don't want Neptune to have.

So we tightened the definition.

Neptune's Maintenance Mode will give it **less capability, not more authority**.

The way I started thinking about it was like putting a vehicle in Park. The vehicle is still running. I can still look at the dashboard and diagnose what is happening. But it isn't supposed to drive anywhere.

Safe Mode is different.

Safe Mode is Neptune reacting to a security or integrity problem. If Neptune enters Safe Mode because something important has gone wrong, it cannot simply decide everything looks better and turn itself back on normally.

I have to review it and authorize the recovery.

## Watching the Machine Without Becoming the Problem

I also want Neptune to have a browser-based dashboard.

I don't want normal administration of this system to require me to sit at a terminal all the time. I want to be able to see system health, security status, alerts, backups, pending approvals, running tasks, and basic resource information in one place.

Then I realized something slightly ridiculous.

This is an old dual-core iMac with 8 GB of RAM and a mechanical hard drive. I could build a beautiful monitoring system that uses a noticeable amount of the computer's resources just to tell me that the computer is running out of resources.

So the monitoring system itself needs to stay lightweight.

The initial direction is roughly five- to ten-second sampling rather than trying to make everything update continuously. Later we'll measure the actual overhead on the real machine instead of guessing.

## Drawing Some Very Hard Lines

We also started defining places where Neptune simply should not have normal authority.

Government services and financial services will be restricted at the architecture level.

Password-manager access, if it is ever enabled, will require fresh MFA every time.

Medical and insurance services begin restricted and would require specifically scoped authorization later.

Purchases are another hard boundary.

Neptune may eventually research something for me and prepare a transaction all the way up to the final confirmation, but it cannot complete the purchase without my approval and fresh MFA.

It also will never store my payment-card or banking credentials inside Neptune itself.

Passwords and MFA recovery codes are excluded from Neptune's normal memory, configuration, and logs as well.

That brought the same principle back again: Neptune may become capable of doing something without automatically receiving the authority to do it.

## Preparing for Things to Go Wrong

A lot of today's decisions were really about failure.

Neptune will eventually maintain normal audit logs, separate security-event records, and a record of security-policy changes.

Critical security events don't disappear just because the immediate symptom goes away. I have to acknowledge them.

Trusted code and important configuration will eventually have cryptographic known-good baselines so Neptune can detect unexpected changes without being able to declare those changes trustworthy by itself.

Downloaded files will need malware scanning, and downloaded code won't be allowed to run for the first time without approval.

Backups follow the same philosophy.

The current direction is a dedicated MEGA repository rather than using one of my normal personal cloud accounts. Neptune will encrypt its backup locally before anything is uploaded, and I retain control of the encryption key.

More importantly, a backup isn't considered proven just because the backup software says it succeeded.

Eventually Neptune has to prove it can restore from it.

## The Old iMac Question

There were also two practical hardware questions hanging over everything.

The first was the operating system.

The iMac currently runs macOS Ventura. We considered staying there, extending its life with OpenCore Legacy Patcher, or moving Neptune to Linux.

Linux became the recommended direction.

What changed the way I looked at this was realizing I was asking the wrong question.

This isn't really about finding the newest version of macOS I can squeeze onto an old iMac anymore.

The machine's job has changed.

I'm trying to turn it into a dedicated 24/7 AI appliance. That means I care more about long-term security support, services, permissions, logging, remote administration, recovery, and local AI runtimes than I care about keeping it behaving like a normal Mac desktop.

Linux fits that job better.

We haven't selected a Linux distribution yet, and nothing has been installed.

The second issue was that painfully slow 1 TB 5400-RPM mechanical hard drive.

I already plan to move Neptune to an external SSD, so I asked whether it made sense to stop development until I had the SSD.

The answer was no.

The HDD will be temporary development storage.

We can still work on architecture, code, configuration, security controls, services, and lightweight functional testing.

What we shouldn't do is use the HDD to make serious claims about Neptune's eventual model performance or 24/7 production readiness.

That distinction keeps a hardware upgrade from unnecessarily stopping the project.

## Keeping the Development History Manageable

One other problem I wanted to solve early was how we're going to manage the development process itself.

I don't want Neptune to become one enormous ChatGPT conversation that eventually contains everything we've ever discussed and becomes impossible to navigate.

So Neptune now has a session workflow.

Each development session happens in a new chat.

I start with:

`continue work`

That session resumes from the latest technical handoff and tells me where Neptune stands, what decisions are already locked, what remains unresolved, and exactly what we're working on next.

When I'm finished, I use:

`end session`

That produces two separate records.

One is the technical handoff for continuing engineering work.

The other is the handoff to Clio containing the story behind what happened so the Chronicle can be written separately.

I like that separation.

The technical record needs to tell us how to continue building the system.

The Chronicle needs to explain **why the system became what it became**.

Those aren't the same job.

## Where Things Stand

At the end of today, Neptune isn't running yet.

There is no Linux installation, no local model, no dashboard, no approval system, no automated diagnostics, and no external integrations.

That distinction matters.

What we built today was the control structure that those things will eventually have to live inside.

I started the day thinking about turning an old iMac into a local AI system.

I ended it thinking much more about trust.

How much should Neptune be allowed to do?

Who gets to change those rules?

How do I know an action actually worked?

What happens when Neptune detects something it doesn't understand?

And most importantly, how do I make sure the system can't gradually turn convenience into authority without me deliberately deciding that it should?

Those questions needed answers before installation began.

Now most of those boundaries are defined well enough that we can finally start moving toward implementation.

## Next Time

The next engineering decision is specific:

**Choose the Linux distribution for the 2017 iMac.**

It needs to work reliably with the iMac's Intel hardware, graphics and Wi-Fi while staying lightweight enough for a dual-core processor and 8 GB of RAM. It also needs to support the service management, security, remote administration, recovery, and local AI tools Neptune will eventually depend on.

Once that choice is reviewed and approved, we'll have the operating foundation Neptune will actually be built on.

---

**Entry:** ENTRY 003  
**Date:** August 10, 2026  
**Phase:** Neptune foundation — architecture and trust boundaries  
**Artifact:** Neptune architecture, security, and development-session handoff records  
**Status:** Draft Chronicle entry — awaiting AJ approval  
**Key decision:** Define Neptune's authority, security, approval, recovery, and governance boundaries before granting the agent operational control of its host. Linux is the recommended platform direction, but no distribution has been selected or installed.  
**Next action:** Select and approve the Linux distribution for the Neptune iMac18,1 host.