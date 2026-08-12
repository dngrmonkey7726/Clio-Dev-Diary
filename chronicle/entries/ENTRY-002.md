`2026-08-10 — Entry 002 — Defining the Project Registry`

# Minerva Chronicle — Entry 002

**Date:** August 10, 2026

With the Registry Definition Standard in place, today’s work moved from deciding how all Minerva registries should be built to defining the first actual registry: the Project Registry.

We started with Projects because nearly everything Minerva does will need to belong to or relate back to one. Before Minerva can manage sources, workflows, artifacts, validation, or publishing, it needs a dependable way to know which project it is working on. Conversation memory and scattered notes might work while Minerva is still small, but they are not a reliable foundation for a real platform.

I started thinking about it like setting up an organized filing system. Before putting documents into folders, you need a consistent way to label each folder so you can tell what it represents, who is responsible for it, whether it is active, and how it relates to everything around it. The Project Registry gives Minerva that stable project identity.

The frozen Registry Definition Standard, `MIN-FA-REGDEFSTD-001 v1.0.0`, supplied the blueprint. Because that structure had already been reviewed, approved, and frozen, we did not have to invent a new format for the Project Registry. We could concentrate on what Minerva actually needs to know about a project while following the same structure that future registries will use.

A major part of the work was deciding what the Project Registry should not control. It identifies a project, records its purpose, ownership, lifecycle, version history, security, quarantine history, and relationships to the rest of Minerva. It does not absorb the internal responsibilities of future Source, Artifact, Workflow, Approval, or other registries.

That boundary matters. Without it, the Project Registry could easily become the place where every piece of project-related information gets dumped. It might appear convenient at first, but it would eventually become one overloaded record trying to manage the whole platform. Instead, the Project Registry acts as the project’s official identity and connecting point while allowing other registries to manage their own information.

Several details were tightened during review. A blocked project may return to `intake_pending`, but being released from a blocked condition cannot let it skip validation or approval requirements. Quarantine remains separate from the project’s normal lifecycle so Minerva can preserve both the project’s operating status and the complete history of why it was quarantined, who authorized it, what evidence supported it, and how it was released.

The definition also separates routine record edits from meaningful project versions. A mutable `record_revision` can track ordinary corrections, while an immutable Project Version preserves material changes as part of the project’s history. The first immutable version is created when the project is durably established, and `current_version_id` becomes required once that creation is complete.

We also preserved Minerva’s broader platform boundary. The Project Registry contains no Storyline-specific fields. Storyline 360 may be Minerva’s first production use, but the general meaning of a project cannot be built around one application.

One dependency remains intentionally unresolved. The Project Registry includes `source_baseline_version_id`, which will eventually point to the exact approved source baseline governing one or more Sources and their specific versions. We did not invent that future entity inside the Project Registry or make assumptions about its ownership, lifecycle, or internal structure. That work must be defined later through the proper architecture.

The recovered Project Registry Markdown file was also reopened and checked before final review. Its critical tables passed their structural validation. That confirmed that the controlled artifact had been produced correctly and that the earlier table-format concerns were not problems with the underlying architecture.

The completed Project Registry Definition, `MIN-REG-PROJECT-001 v1.0.0`, passed final architectural review and was approved and frozen. Its handoff record, `MIN-HANDOFF-PROJECTREG-001 v1.0.0`, was completed and returned to Daedalus for sequencing. The Registry Framework and Registry Definition Standard also remain approved and frozen, although their previously created handoff records still need to be reconciled with approved Minerva storage if they are not already available to Clio.

No database, API, storage system, implementation schema, software framework, or other technology was selected during this work. We defined what Minerva must know and the rules that information must follow, not how programmers will physically store or retrieve it.

At the end of this increment, Minerva had moved beyond a general registry blueprint and gained its first authoritative individual registry. The Project Registry now gives Minerva a stable way to identify and distinguish projects while keeping neighboring responsibilities properly separated. The Source Registry Definition is sequenced next because Sources are foundational to Minerva’s work, but that work has not begun and must not begin until Daedalus sequences it.
