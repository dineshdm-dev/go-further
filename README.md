# Go Further

An Agent Skill for discovering and doing useful work you might not think to ask AI to do.

A request often contains our first guess at how to solve a problem. Ask for a document review and an agent can review the document. Give it room to investigate the purpose behind that document, and it may find something more useful to do: reproduce a failure, test an assumption, build an instrument, or fix the workflow itself.

Go Further gives an agent instructions to look for those opportunities and act on a promising one within your scope. You provide the goal, relevant context, and limits. The agent chooses an approach, does what its tools and permissions allow, and checks the result.

## Install

Run this in the project where you want to use the skill:

```bash
npx skills add dineshdm-dev/go-further --skill go-further
```

Choose your agent when prompted. This uses the [Skills CLI](https://github.com/vercel-labs/skills), which currently requires Node.js 22.20 or later. Installation is local to the project by default. Add `-g` to make the skill available across projects:

```bash
npx skills add dineshdm-dev/go-further --skill go-further -g
```

You can select an agent directly with `-a codex` or `-a claude-code`.

### Manual installation

Download or clone this repository. Place the folder containing `SKILL.md` and `references/` in your agent's skills directory, named `go-further`.

| Agent | This project | All local projects |
| --- | --- | --- |
| Codex | `.agents/skills/go-further/` | `~/.agents/skills/go-further/` |
| Claude Code | `.claude/skills/go-further/` | `~/.claude/skills/go-further/` |

Keep the supporting files with `SKILL.md`. Other agents may use different locations; follow their installation instructions. The skill follows the [Agent Skills format](https://agentskills.io/specification).

## Use it

In Codex, start your request with `$go-further`. In Claude Code, use `/go-further`. Then describe what you want to accomplish.

For example, in Codex:

```text
$go-further

Review this SDK's onboarding documentation. New developers should be able
to get their first example running without asking someone for help.
The repository is available here. You can run local checks and edit files,
but don't make paid API calls or publish changes.
```

With a repository and terminal available, a useful response could attempt the setup in a clean environment, run the documented example, locate the obstacle, and repair what it can reproduce. That gives you evidence about whether the instructions work, alongside any writing improvements. It still needs actual developers to establish how usable the experience is.

The response should lead with the result and what you can use. Calculations, commands, and other supporting details belong where they help you understand or check the work.

## Other things to try

Add the invocation for your agent before each request.

**Research**

```text
These two papers seem to disagree. Help me understand what causes the
disagreement and which evidence would matter for my decision.
```

**Learning**

```text
I can follow explanations of conditional probability, but I struggle to
apply it. Help me understand it well enough to solve unfamiliar problems.
I have twenty minutes.
```

**Creative work**

```text
I want a mystery four friends can solve over group chat in about twenty
minutes. No special apps, and everyone should be able to play.
Help me make something we can actually use.
```

Give the agent relevant files or data you already have. State the constraints that matter. You can ask for possibilities only, or authorize it to make a concrete attempt. You remain in control of the goal.

## What to expect

Go Further is most useful when there is room to investigate or choose a different approach. Simple questions and tightly specified edits rarely need it.

It can help an agent pursue the outcome behind a task, investigate more deeply, or apply a useful method from another field. It should preserve your requested deliverable, avoid unnecessary complexity, and explain what remains uncertain.

The skill supplies instructions. Results depend on the model, available information, tools, and permissions. It does not provide additional tool access or background operation.

## Update

If you installed through the Skills CLI, update with:

```bash
npx skills update go-further
```

Choose the installation scope if prompted. For a manual installation, replace the installed folder with the latest version. If your agent does not pick up a change, start a fresh session.

## Files

- [SKILL.md](SKILL.md): the instructions loaded by the agent.
- [references/methods.md](references/methods.md): guidance for choosing a useful method.
- [references/examples.md](references/examples.md): examples of possible approaches and their limits.
- [evals/](evals/): development cases, a review rubric, and an earlier validation record. These are not needed during ordinary use.

Installation details: [Skills CLI](https://github.com/vercel-labs/skills#install-a-skill), [Codex](https://developers.openai.com/codex/skills/), and [Claude Code](https://code.claude.com/docs/en/skills).
