---
name: council
description: Council of independent models from different providers. Use when the user asks for a council review of a code change, or a council investigation of an issue or task before implementation.
---

# Council

Put one question to a council of blind, independent models. Verify their claims yourself and report what the evidence supports. Pick the branch and read its file now:

- **Review** a change (PR, branch, commit, patch, or local changes): [references/review.md](references/review.md).
- **Investigate** an issue or task before implementation: [references/investigate.md](references/investigate.md).

The output is a report. Edit code, push, or post comments only when the user or a calling workflow authorizes it.

## 1. Pin the target

Follow the branch file's **Target** section. Record the snapshot every member will see: base and head SHAs, the local diff, or the system version and observation time.

Done when the branch file's Target criterion holds.

## 2. Convene the council

Two members from different providers: GPT-6.1 Sol and Opus 5.5. Add a third only for a distinct specialty or a deadlock. Three is the cap, replacements included.

- Look up exact model identifiers through the host. If a preferred model is unavailable, name the gap and get the user's approval for a specific alternative. Keep investigating while you wait.
- Without cross-provider delegation, report the council as blocked. Two runs of one model, or you alone, make no council.
- Give every member the same packet: the snapshot, raw requirements, repository instructions, source locations, and raw evidence or check results. Leave your own hypothesis out.
- Launch members blind, before any member sees another's conclusions. Each is a read-only leaf.

Brief each member with the branch file's **Brief**, followed by:

> Answer "What existing code can solve this?" and "Which proposed changes are unnecessary?" Cite a source location for every claim. Separate verified facts from hypotheses. Report your verification limits. Make no edits, post no comments, and launch no agents.

Done when every member has returned a report.

## 3. Reconcile

- Group claims by root cause or decision. Verify every decisive claim against source yourself, with a focused reproduction or experiment where practical. Apply the branch file's **Reconcile** notes.
- Judge by evidence, not votes. Keep a substantiated claim even when one member alone made it. Dismiss a false one with a concrete reason.
- Settle disagreements with source, a test, or a focused re-check by the same members.
- **Deadlock**: two consecutive re-checks bring no new evidence. Stop, report the disagreement, its evidence, and the missing evidence, access, or decision, and mark the council incomplete.
- Recheck the snapshot before reporting. If it moved, cover the delta, or scope the report to the original snapshot.

Done when every claim is verified, dismissed with a reason, or open with its missing evidence named.

## 4. Report

Follow the branch file's **Report** section. Always state the actual models used, the verification you performed, the limits, and the status: complete, partial, blocked, or inconclusive. Council agreement is evidence, not proof.
