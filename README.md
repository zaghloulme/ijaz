![Ijaz — Speak less to say more.](assets/header-v3.png)

# Ijaz

**Speak less to say more.**

A writing skill that strengthens the thought, finds its best expression, and gives the reader what they need. Use it on a headline, an email, a proposal, or an essay.

## Install

With [Node.js 22.20+](https://nodejs.org/) installed, run:

```sh
npx skills add zaghloulme/ijaz --skill ijaz
```

Choose your agent when prompted. Add `--global` to use Ijaz across projects.

To install for every agent supported by the installer:

```sh
npx skills add zaghloulme/ijaz --skill ijaz --agent '*' --global
```

Or choose an agent:

| Agent | Install globally |
| --- | --- |
| Claude Code | `npx skills add zaghloulme/ijaz --skill ijaz -a claude-code -g` |
| Codex | `npx skills add zaghloulme/ijaz --skill ijaz -a codex -g` |
| Cursor | `npx skills add zaghloulme/ijaz --skill ijaz -a cursor -g` |
| GitHub Copilot | `npx skills add zaghloulme/ijaz --skill ijaz -a github-copilot -g` |
| Gemini CLI | `npx skills add zaghloulme/ijaz --skill ijaz -a gemini-cli -g` |
| OpenCode | `npx skills add zaghloulme/ijaz --skill ijaz -a opencode -g` |
| Windsurf | `npx skills add zaghloulme/ijaz --skill ijaz -a windsurf -g` |

See the installer's [full agent list](https://github.com/vercel-labs/skills/blob/main/docs/agents.md) and [command reference](https://github.com/vercel-labs/skills/blob/main/docs/commands.md). These are installation targets; behavior depends on the agent and model.

### Manual setup and chat apps

Copy [`skills/ijaz/`](skills/ijaz/) into your agent's documented skills directory. The only required file is [`SKILL.md`](skills/ijaz/SKILL.md); `agents/openai.yaml` adds optional Codex interface metadata.

For agents or chat apps without skill support, paste the body of `SKILL.md` into their instructions or into a conversation before your request. This applies the same guidance without native skill discovery. Use the app's normal upload or instruction feature if available.

## Use

Ask your agent to read Ijaz and apply it:

```text
Use the ijaz skill to edit the text below. Return only the revision.

[paste your draft]
```

You can also use it while drafting:

```text
Use the ijaz skill to write a project update from these notes:

[paste your notes]
```

Native invocation varies by agent. Codex supports `$ijaz`; Claude Code supports `/ijaz` once installed. A plain request to read and apply the skill works wherever the agent can access its file.

## How it works

Ijaz starts with the reader and the purpose. It can rebuild a weak argument, bring a buried benefit forward, gather related ideas into one statement, or add the explanation a reader needs. It also recognizes when writing should stay as it is.

Three choices guide the work: compact expression, omission supported by context, and useful expansion.

**Before**

> Your subscription renews only after you approve the renewal. If you have not approved it, we do not renew it.

**After**

> Your subscription renews only with your approval.

The condition conveys both permission and the consequence of withholding it. There is no need to spell out each implication.

Context matters. Answering “Which plan includes email support?” with “Both” works in a conversation. A standalone page needs “Both plans include email support.”

Names, conditions, uncertainty, and consequences must survive the edit. A full explanation can stay long. Clear writing can stay unchanged.

## Inside

- [`skills/ijaz/SKILL.md`](skills/ijaz/SKILL.md): principles, editorial decisions, writing craft, contrasting examples, and a working process.
- [`skills/ijaz/agents/openai.yaml`](skills/ijaz/agents/openai.yaml): optional Codex interface metadata.
- [`evals/cases.md`](evals/cases.md): prompts and criteria for checking editorial judgment.
- [`evals/2026-10-21.md`](evals/2026-10-21.md): nine trial outputs and the findings. These are limited examples, not a guarantee across models.

The skill needs no tools, API keys, runtime, or dependencies. The optional installer uses Node.js. Instructions are written in English.

## Contribute

Open an issue or pull request with the input, the actual output, and what the edit lost or failed to improve. Keep rules grounded in examples. Run the cases in [`evals/cases.md`](evals/cases.md) after a change.

## Credits and license

Created by [Ahmed Zaghloul](https://github.com/zaghloulme).

The foundation draws on classical accounts of concise expression, context, and useful expansion. See the [research notes](research/ijaz-classical-sources.md) for primary sources, attribution, and the distinction between historical accounts and this modern writing skill.

The early draft drew on Peter Yang’s [No AI Slop](https://github.com/petergyang/no-ai-slop). The plain-language guidance also draws on George Orwell’s *Politics and the English Language* (1946).

[MIT](LICENSE). Peter Yang's copyright notice is retained for the adapted guidance.
