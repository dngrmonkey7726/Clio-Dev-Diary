# Chronicle Entry and Processing Register

This public register is the authoritative control record for Chronicle entry continuity and processed handoffs in `dngrmonkey7726/Clio-Dev-Diary`.

## Entry Continuity

Next Available Entry ID: ENTRY 004

| Entry ID | Work Date | Title | Status | Source Handoffs |
|---|---|---|---|---|
| ENTRY 000 | Historical founding period | Founding entry preserved in ARCHIVE — Original Clio Setup | Approved | Legacy entry created before the handoff inbox |
| ENTRY 001 | See approved entry | Preserved in ARCHIVE — Original Clio Setup | Approved | Legacy entry created before the handoff inbox |
| ENTRY 002 | See approved entry | Preserved in ARCHIVE — Minerva Project Registry Discussion | Approved | Legacy entry created before the handoff inbox |
| ENTRY 003 | 2026-08-10 | Deciding What Neptune Is Allowed to Become | Approved | Legacy entry created before the handoff inbox |

## Processed Handoffs

No handoffs have been processed through the combined Chronicle workflow yet.

After AJ approves a combined Chronicle entry, add one row for each source handoff:

| Entry ID | Work Date | Exact Source Filename | Source Project | Date Processed | Status |
|---|---|---|---|---|---|

## Control Rules

- ENTRY 000–003 are permanent approved records.
- ENTRY 004 is the next available ID.
- Drafts do not consume an Entry ID until approved.
- Each approved entry must be added to the Entry Continuity table.
- Each source handoff must be added to the Processed Handoffs table after approval.
- A processed handoff cannot be reused unless AJ explicitly authorizes a correction or revision.
- Drafts are never added to this register.
- After AJ selects `[1] Approve entry`, Clio publishes the approved entry, updates this register, and moves the exact source handoffs from `handoffs/inbox/[Project]/` to `handoffs/processed/[Project]/` as one linked publication transaction.
- Publication failures must be reported and must not be represented as completed.
