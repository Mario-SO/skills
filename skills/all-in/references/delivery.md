# PR delivery

## UI evidence

When the task includes UI code, include actual before and after screenshots in the PR description. Capture the baseline on the original revision before edits, and capture the result after verification. Use the same viewport, route, data, and interaction state so the change is comparable. Cover each materially different changed state.

Use the host's authorized browser and screenshot tools. If the baseline was missed, capture it in a separate host-managed workspace on the original revision; preserve current edits. Inspect screenshots for exposed secrets or personal data before upload.

Embed labeled images using uploaded attachments or repository-permitted URLs that PR readers can access. Local file paths are insufficient. Verify that the PR description renders both images. If browser access, a running UI, representative data, or attachment upload is unavailable, state the specific blocker and request the missing capability. Do not fabricate images or mark the screenshot gate complete.

## Ownership and PR content

Default the PR owner to Mario, GitHub login `Mario-SO`. Honor an explicit owner override from the invoking user so other people can install the skill. Assign the PR to that login and verify the assignee.

GitHub attributes PR authorship to the authenticated account. Check that account before creation. If Mario must also be the author and the session uses another account, request authorized account access through the host's credential flow. Do not impersonate Mario or alter commit authorship to fake ownership. If assignment is unavailable, report the failed ownership gate.

Use the repository's PR template. Lead with the user-visible issue and the resulting behavior. Include:

- Cause and scope of the fix, with the originating issue or task link.
- Checks and results, plus any verification limits.
- A concise record of both councils, actual models used, and resolved material objections.
- Labeled before and after screenshots for UI work.

Open a ready-for-review PR once local gates pass. Use issue-closing keywords only when the PR fully resolves the issue. Follow host requirements to link the PR immediately after creation or push. Leave it open for the user to merge.

## Bugbot loop

1. Discover the repository's Bugbot integration and documented trigger. Read PR review summaries, inline review threads, top-level comments, and check runs. Record the head SHA being reviewed. Trigger or request review through the supported mechanism if needed.
2. Wait for an explicit completed Bugbot review or completed Bugbot check associated with that head. An empty comment list does not establish completion. Also wait for required CI checks.
3. Read every new finding and inspect its affected code. Fix supported defects with the smallest correct change. For false positives, reply with evidence. For a code defect that needs no code change, explain why. Keep unresolved real defects open.
4. Rerun affected checks. Obtain council re-review for material changes. Push fixes, update the task record with the new head, and wait for Bugbot and required checks again. Refresh screenshots if UI behavior changes.
5. Finish when Bugbot has completed on the latest head, all findings have a documented disposition, no substantiated blocking findings remain, and required checks pass. Recheck the head before claiming completion.

Use host-provided PR watchers for external waits. In T3, use `watch_pull_request` when checks or reviews remain pending; provide the PR URL and continuation context, then end the turn as pending. Resume the loop on notification. Follow host unwatch rules before final handback. Without a watcher, use the host's supported bounded wait mechanism.

If Bugbot is absent, cannot be triggered, fails repeatedly, or does not finish within the host's permitted wait, report the exact status. Ask for access, integration setup, or an explicit waiver. A waiver must appear in the final report as skipped review, never as Bugbot approval. Escalate repeated external failures instead of retrying indefinitely. Preserve the PR and task state so work can resume.
