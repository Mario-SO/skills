# Mario's skills

Reusable agent skills for work I want to delegate from start to finish.

## Install

Install `all-in` with the [Skills CLI](https://github.com/vercel-labs/skills):

```sh
npx skills@latest add Mario-SO/skills --skill all-in
```

Add `-g` to install across projects. The installer lets you choose your agent.

To install the standalone council review skill:

```sh
npx skills@latest add Mario-SO/skills --skill council-review
```

## council-review

```text
Use council-review to review https://github.com/owner/repo/pull/123
```

Reviews a PR, branch, commit, patch, or local changes with independent models. It checks the connected code, verifies findings, and reports defects in severity order. It prefers GPT-6.1 Sol and Opus 5.5, with at most three council members. Cross-provider delegation is required; unavailable model substitutions need your approval.

The skill produces a report by default. Ask explicitly if you also want fixes or posted review comments. It installs independently of `all-in`.

## all-in

Give your agent a task, issue link, or Markdown file and ask it to use `all-in`:

```text
Use all-in to fix https://github.com/owner/repo/issues/123
```

The skill investigates the task, runs a solution council, implements a lean fix, runs a review council, opens a PR, and resolves Bugbot findings. UI changes require before and after screenshots in the PR. The final report uses ASD-STE100 writing principles. The skill leaves merging to you.

Requirements: repository access, permission to push and open PRs, cross-provider agent delegation, and a Bugbot integration. UI tasks also need browser capture and image upload. Councils prefer GPT-6.1 Sol and Opus 5.5, with at most three members each. The agent asks before substituting unavailable models and reports blocked gates.

PRs are assigned to `Mario-SO` by default. To use your own account, specify an owner when invoking the skill. GitHub sets authorship from the authenticated account.

## Writing approach

Written with guidance from Matt Pocock's [writing-for-agents](https://github.com/mattpocock/skills/tree/main/skills/productivity/writing-for-agents) and earlier [write-a-skill](https://github.com/mattpocock/skills/blob/e7f0b58a4b8ad0764d9478b069fe6e48b99c320f/write-a-skill/SKILL.md): a concise entrypoint, clear completion criteria, and conditional reference files.
