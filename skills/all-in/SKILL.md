---
name: all-in
description: Own a task end to end, from council investigation to a reviewed PR with Bugbot findings resolved.
disable-model-invocation: true
---

# All-in

Own the supplied task (a message, link, Markdown file, issue, or any mix) up to a reviewed, ready-for-review PR. The user merges.

Invoking `all-in` authorizes task edits, checks, council delegation, branch pushes, PR creation, and replies to review findings. Escalate concrete blockers and material scope decisions, and keep independent work moving while you wait.

Each step is a gate that passes only on its completion criterion. Report a blocked gate as blocked, with the exact next action.

Requires the [council](../council/SKILL.md) skill. If it is missing, report that and install it through the host's installer before step 1.

Keep a task record outside tracked files, in host state or a local note: council decisions, chosen approach, rejected complexity, red check or acceptance criteria, checks, screenshots, PR URL, head SHA, and review status. Update it before any handoff to a watcher or another session.

## 1. Investigate

Run `council` on its investigate branch with the original task and artifacts, before choosing a solution or editing code.

Done when the council is complete, supports a diagnosis or recommendation, and every material owner decision is resolved. An inconclusive council stays inconclusive: report the missing evidence or decision.

## 2. Prepare

Check the working tree and open PRs, confirm the base branch, and create a task branch. If UI code will change, read [references/ui-evidence.md](references/ui-evidence.md) and capture the baseline screenshots now.

Done when you are on a task branch, no duplicate PR exists, and any UI baseline is captured.

## 3. Implement

Implement the lean approach from step 1. Where practical, the regression check goes red before the fix and green after it. Run the acceptance checks and repository-required validation. Show with evidence that any failure you leave is pre-existing. For UI work, capture the after screenshots.

Done when the acceptance criteria hold and checks pass, or the user has accepted a disclosed verification limit.

## 4. Review

Run `council` on its review branch against the actual diff, with fixes authorized. Supply the requirements, task record, and check results. Material fixes made later, including Bugbot fixes, return to this review.

Done when the council is complete and no substantiated blocking finding remains.

## 5. Deliver

Read [references/delivery.md](references/delivery.md). Push the branch, open the PR, set its owner, and run the Bugbot loop.

Done when both councils, required checks, PR ownership, required screenshots, and Bugbot on the latest head are complete. A queued watcher is a pending handoff, not completion.

## 6. Report

Write the final report in ASD-STE100 Simplified Technical English, with at most 20 words per sentence. Cover the issue, cause, fix, checks and results, both councils, Bugbot status, PR link, and remaining limits. For example:

> The Save button sent two requests after a double click. The form stayed active during the first request.
> The fix disables Save until the request ends. The regression test and required checks pass.
> Both councils found no remaining blocking issues. Bugbot completed its review of the latest commit.
> Mario owns the PR: [PR link].
