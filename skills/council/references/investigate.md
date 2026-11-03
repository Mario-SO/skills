# Investigate branch

## Target

Accept a message, link, issue, Markdown file, logs, or a mix. Read the linked requirements and issue comments. State the expected outcome, scope, and non-goals. Ask the user only for what blocks the investigation.

Record the repository revision and local changes, or the system version and observation time. Trace the affected behavior through source, callers, state, configuration, and tests. Separate reported symptoms, observed facts, and hypotheses.

- **Bug:** build a red check: one command, already run, that reproduces the reported symptom. Keep its exact command, inputs, expected output, and actual output. If it will not go red, record each attempt and keep the cause unconfirmed.
- **Feature or task:** record the current behavior, observable acceptance criteria with a verification method for each, and the decisions only the user can make.

Keep experiments reversible and their files in a temporary location. Experiments on shared systems need explicit authorization.

Done when the question fits in one sentence and you hold a red check, a documented failed attempt, or acceptance criteria with verification methods.

## Brief

> Investigate the issue or task. For a bug, trace the causal path, separate symptoms from causes, and name competing explanations with the evidence that would disprove each. For a feature, identify the affected boundaries, constraints, and viable approaches. Recommend the lean solution: the smallest complete change that follows repository conventions, with its risks and a verification plan. State your confidence and what would change your conclusion. Propose experiments that would discriminate between explanations.

## Reconcile

- Run experiments that share mutable state one at a time. Record each command, input, result, and the hypothesis it supports or contradicts.
- For a bug, document the supported causal path and a regression check that goes red before the fix and green after it.
- For a feature, compare approaches on acceptance criteria, existing patterns, risk, and complexity.
- When the result is inconclusive, name the next discriminating experiment.

## Report

Lead with the diagnosis or recommendation and its confidence. Then include:

- The question, expected outcome, and scope.
- The red check or the acceptance criteria.
- Verified evidence with locations, the causal path, and remaining hypotheses.
- Council agreements, resolved objections, and open disagreements.
- The lean solution, code to reuse, changes to avoid, risks, and verification steps.
- The next action.

Write for an implementer who should not have to repeat the investigation. Mark the proposed fix as untested.
