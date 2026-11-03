# Review branch

## Target

Accept a PR, branch, commit, commit range, patch, or local changes. With no target, review staged, unstaged, and relevant untracked changes. Resolve the intended base and record the base and head SHAs, or the diff and file state for local edits.

Read the task or issue and the PR description. Trace the connected code: callers, interfaces, tests, configuration, and dependencies.

Done when the base resolves, the diff is non-empty, and you can state the intended behavior in one sentence. Ask for a target when none of these hold. Report missing context as missing context, not as a defect.

## Brief

> Review the change and its connected code against the requirements and repository instructions. Check correctness, missed callers, regressions, error handling, test quality, and unnecessary complexity, plus security, accessibility, and performance where the change touches them. Prioritize defects the change introduces or exposes. For each finding, give the location, triggering condition, user impact, evidence, and smallest correction.

## Reconcile

- Confirm each finding applies to the snapshot. A pre-existing defect counts when the change makes it reachable or worse.
- Style counts only when it breaks a documented convention or causes a material maintenance cost.
- When fixes are authorized, apply the smallest correction that fits repository patterns, rerun affected checks, and send material fixes to a fresh blind review.

## Report

Lead with findings in severity order: critical, high, medium, or low, by impact and likelihood. For each finding:

- **Severity and problem.**
- **Location:** a clickable file and line, or the smallest changed range.
- **Evidence and effect:** the triggering condition, the observed behavior, and why it matters.
- **Correction:** the smallest fix.

Then state the reviewed scope and snapshot. With no actionable findings, say so directly and list the remaining risks.
