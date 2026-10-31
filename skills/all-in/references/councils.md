# Councils

Use this procedure for the solution council and the code review council. Each council has two independent members by default, from different model families and providers. Add a third only when a distinct specialty or unresolved objection warrants it. Never exceed three members per council, including replacements that participate in that council. The coordinator synthesizes the evidence.

## Select and launch

- Discover the host's delegation capabilities and exact model identifiers. Prefer GPT-6.1 Sol and Opus 5.5 in both councils. These are preferences, not proof that either model is available.
- If a preferred model is unavailable, state that fact and ask the user to approve specific available alternatives. Continue investigation or other independent work. Never silently substitute a model or represent repeated calls to one model as a diverse council.
- Use T3 `delegate_task` for cross-provider models when available, following the host's orchestration rules. Call `orchestrator_capabilities` before the first delegation when required. Otherwise use a supported cross-provider delegation mechanism. If none exists, report that the council gate is blocked; do not simulate it yourself.
- Give members read-only tasks. The coordinator owns edits. Require each member to read the relevant repository instructions and source, and to return evidence, objections, and a recommendation. Members must not delegate further.
- Launch members independently before sharing their conclusions. Follow the host's wait or continuation mechanism. Cancel superseded work and preserve pending state across handoffs.

## Solution brief

> Independently investigate this task from the supplied requirements and evidence. Read the relevant source and repository instructions. Propose the smallest complete solution that fits existing conventions. Identify the root cause or feature boundary, affected callers, risks, simpler alternatives, and a verification plan. Cite concrete files or observations. State what would falsify your proposal. Make no edits and launch no agents.

Supply raw reproduction output and source locations. Avoid requiring members to endorse the coordinator's hypothesis.

Compare proposals for correctness, scope, repository fit, and complexity. Investigate disagreements. If a material objection remains, send the evidence and proposed resolution for an independent follow-up. In T3, each new review or re-check is a new delegation. Keep the same council membership and the three-member limit. Ask the user only when the remaining choice changes the task's requirements or needs unavailable authority.

## Code review brief

> Review this diff and the connected code against the task and repository instructions. Independently check behavior, missed callers, regression risk, error handling, security, accessibility where relevant, test quality, and unnecessary complexity. Return actionable findings with file locations, evidence, impact, and a proposed correction. State any verification limits. Make no edits and launch no agents.

Use fresh review contexts after implementation. Give reviewers access to source and checks, not only a summary of the plan. Evaluate findings on evidence. Fix real defects, explain rejected findings, and rerun relevant checks. For material fixes, obtain a fresh review from the relevant council members before closing the review gate.

If two consecutive follow-ups produce no new evidence or cannot resolve the same material objection, record the disagreement and escalate it. Do not exhaust resources by repeating the same debate. Report the gate as incomplete until the objection is resolved.
