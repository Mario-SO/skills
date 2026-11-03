# Mario's skills

Agent skills for work I want to delegate from start to finish.

## Install

Install with the [Skills CLI](https://github.com/vercel-labs/skills). Add `-g` to install across projects; the installer lets you choose your agent.

```sh
npx skills@latest add Mario-SO/skills --skill all-in council
```

`council` also installs on its own:

```sh
npx skills@latest add Mario-SO/skills --skill council
```

## all-in

**What it does.** Takes a task, issue link, or Markdown file to a reviewed, ready-for-review PR. It runs a council investigation, implements the lean fix, runs a council review, opens the PR, and resolves Bugbot findings. Merging stays with you.

**When to reach for it.** You invoke it by name; the agent won't reach for it on its own.

```text
Use all-in to fix https://github.com/owner/repo/issues/123
```

**Requirements.** The `council` skill, push and PR access, cross-provider agent delegation, and a Bugbot integration. UI tasks also need browser capture and image upload.

**Common questions.**

- *Who owns the PR?* `Mario-SO` by default. Name another owner when you invoke it. GitHub sets authorship from the authenticated account.
- *What goes in the PR?* At most 200 words of before, after, and verification, plus a before and after visual when behavior changes. UI changes get real screenshots.

**It's working if** the final report names both councils' models, Bugbot has completed on the PR's latest head, and every blocked gate is reported as blocked.

## council

**What it does.** Two independent models from different providers (GPT-6.1 Sol and Opus 5.5 by default, three at most) work blind. The coordinator verifies their claims and reports what the evidence supports. It has two branches: review a change, or investigate an issue before implementation.

**When to reach for it.** Type it, or the agent reaches for it when you ask for a council review or investigation.

```text
Use council to review https://github.com/owner/repo/pull/123
Use council to investigate https://github.com/owner/repo/issues/123
```

**Common questions.**

- *Does it change code?* It reports by default. Ask explicitly for fixes or posted review comments.
- *What if a preferred model is unavailable?* It asks you to approve a specific substitute. Without cross-provider delegation, it reports the council as blocked.

**It's working if** every finding has a location and evidence, a substantiated finding survives even when one member alone raised it, and partial councils say so.

## Writing approach

Written with Matt Pocock's [writing-for-agents](https://github.com/mattpocock/skills/tree/main/skills/productivity/writing-for-agents): context pointers, checkable completion criteria, leading words, and a no-op pass on every sentence.
