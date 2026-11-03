# PR delivery

## Description

Write for a reader who never saw the task conversation, in ASD-STE100 Simplified Technical English with at most 20 words per sentence. Keep non-visual content at or below 200 words, including headings and template text. The visual and its labels, alt text, and short captions sit outside the limit.

Use the repository's PR template with these sections:

- **Before:** the trigger, previous behavior, user impact, and cause.
- **After:** the corrected behavior, how the fix produces it, and the scope of the change.
- **Verification:** checks and results, limits, and both councils with actual models and resolved objections. Link the originating issue or task.
- **Visual:** when behavior changes, a labeled before and after of the same scenario, embedded in the description. UI changes use paired screenshots from [ui-evidence.md](ui-evidence.md). Otherwise pick the simplest fit: a Mermaid flow or sequence diagram for control flow, a state diagram for transitions, or a comparison table for inputs and outputs. Base it on observed evidence or verified code paths, and label a conceptual diagram as conceptual.

If mandatory template content cannot fit in 200 words, report the conflict. After each update, recount the words and confirm the visual renders and matches the latest head.

## Ownership

Assign the PR to `Mario-SO`

Open the PR ready for review. Use issue-closing keywords only when the PR fully resolves the issue.

## Bugbot loop

1. Find the repository's Bugbot trigger. Record the head SHA, and trigger a review if needed.
2. Wait for a completed Bugbot review or check on that head. Completion is an explicit completed status; an empty comment list is not one.
3. Inspect the code behind every new finding. Fix real defects with the smallest correct change. Reply with evidence to false positives. Unfixed real defects stay open.
4. Rerun affected checks, send material fixes back through the council review, and push. Update the task record and PR description, then return to step 2.
5. Done when Bugbot has completed on the latest head, every finding has a documented disposition, no substantiated blocking finding remains, and required checks pass.

Use the host's PR watcher for external waits, ending the turn as pending and resuming on notification.

If Bugbot is absent, cannot be triggered, keeps failing, or exceeds the permitted wait, report the exact status. Ask for access, setup, or an explicit waiver. Report a waiver as "Bugbot skipped". Escalate repeated failures, and preserve the PR and task state so work can resume.
