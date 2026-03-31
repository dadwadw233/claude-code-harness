# Claude Code Harness

Design the harness, not just the prompt.

`claude-code-harness` is a public skill and plugin package for developers who want to design real harnesses for agentic systems: request assembly, execution loops, tools, memory, permissions, transcript, recovery, and extension planes.

It is inspired by Claude Code’s harness design, but written as a generalized pattern language that other builders can apply to their own agentic products.

This project is unofficial. It is not affiliated with Anthropic.

## Why this project exists

Many agent projects stop too early. They have:

- prompts without runtime boundaries
- tools without governance
- memory without layers
- retries without stop conditions
- “autonomy” without visibility or recovery

This project exists to close that gap.

The goal is to help developers move from “an agent idea” to “a harness blueprint.”

## What you get

This repository currently ships one skill:

- `claude-code-harness`

That skill helps you design:

- request assembly
- turn loops
- tool and capability planes
- memory and context layers
- permission and safety boundaries
- transcript and recovery strategy
- extension surfaces

## What makes it different

This is not a general “agent design” skill.

Its center of gravity is the **harness**: the runtime that turns a model into a durable, governable, usable system.

In particular, it pushes users to specify:

- how a request is assembled
- how a turn progresses
- how power is bounded
- how state survives failure
- how humans steer the system

## Quick install

### Codex: install the skill directly

Inside Codex, run:

```text
$skill-installer install https://github.com/dadwadw233/claude-code-harness/tree/main/skills/claude-code-harness
```

Then restart Codex.

### Claude Code: install through the repository marketplace

Inside Claude Code, run:

```text
/plugin marketplace add dadwadw233/claude-code-harness
/plugin install claude-code-harness@claude-code-harness
```

Then invoke the installed skill with:

```text
/claude-code-harness:claude-code-harness
```

## Installation details

### Codex: direct skill install

```text
$skill-installer install https://github.com/dadwadw233/claude-code-harness/tree/main/skills/claude-code-harness
```

After installation, restart Codex.

### Codex: local plugin install

Clone the repo:

```bash
git clone git@github.com:dadwadw233/claude-code-harness.git
```

Copy it into your local plugin area:

```bash
mkdir -p ~/.codex/plugins
cp -R /absolute/path/to/claude-code-harness ~/.codex/plugins/claude-code-harness
```

Create or update `~/.agents/plugins/marketplace.json`:

```json
{
  "name": "personal-plugins",
  "interface": {
    "displayName": "Personal Plugins"
  },
  "plugins": [
    {
      "name": "claude-code-harness",
      "source": {
        "source": "local",
        "path": "./.codex/plugins/claude-code-harness"
      },
      "policy": {
        "installation": "AVAILABLE",
        "authentication": "ON_INSTALL"
      },
      "category": "Productivity"
    }
  ]
}
```

Restart Codex. The plugin should appear in the plugin directory.

### Claude Code: marketplace install

This repository includes a Claude Code marketplace manifest at `.claude-plugin/marketplace.json`.

Register the marketplace:

```text
/plugin marketplace add dadwadw233/claude-code-harness
```

Install the plugin:

```text
/plugin install claude-code-harness@claude-code-harness
```

After installation, the explicit slash command is:

```text
/claude-code-harness:claude-code-harness
```

### Claude Code: manual skill install

Copy the skill directory:

```bash
mkdir -p ~/.claude/skills
cp -R skills/claude-code-harness ~/.claude/skills/claude-code-harness
```

For a manually installed standalone skill, invoke:

```text
/claude-code-harness
```

## What the skill outputs

When the skill is working well, it should produce a **harness blueprint** with:

- system goal and delegation boundary
- harness layers
- request assembly design
- turn loop design
- tool runtime and permission boundaries
- memory and context strategy
- transcript and recovery model
- extension surfaces
- build order

## Example prompts

### Codex

- `Use $claude-code-harness to design a harness for this coding agent.`
- `Use $claude-code-harness to turn this vague operator idea into a real runtime blueprint.`

### Claude Code plugin install

- `/claude-code-harness:claude-code-harness`
- `/claude-code-harness:claude-code-harness Design a harness for a repo-writing agent with request assembly, permissions, and recovery.`

### Claude Code standalone skill install

- `/claude-code-harness`
- `/claude-code-harness Review whether this agent idea really needs a harness and design the smallest one that works.`

## Repository structure

```text
.
├── .claude-plugin/
│   ├── marketplace.json
│   └── plugin.json
├── .codex-plugin/
│   └── plugin.json
├── .agents/plugins/
│   └── marketplace.json
└── skills/
    └── claude-code-harness/
        ├── SKILL.md
        ├── LICENSE.txt
        ├── agents/
        │   └── openai.yaml
        └── references/
            ├── claude-code-derived-insights.md
            ├── harness-blueprint-template.md
            ├── harness-pattern-language.md
            └── harness-principles.md
```

## Reference files

The repository keeps the skill concise and moves depth into references:

- `harness-principles.md`: what a harness is and why it matters
- `harness-pattern-language.md`: reusable runtime patterns
- `harness-blueprint-template.md`: the default output shape
- `claude-code-derived-insights.md`: generalized lessons distilled from Claude Code

## Inspiration

This project is strongly informed by:

- Claude Code’s request assembly and runtime design
- Claude Code’s turn loop, memory maintenance, and transcript/recovery model
- official OpenAI/Codex skill and plugin conventions
- Claude Code plugin and marketplace conventions

## Non-goals

This project is not trying to:

- clone Claude Code
- provide an all-purpose agent framework
- turn every workflow into an autonomous system
- replace real implementation work with architecture theater

It is trying to help developers design stronger harnesses.

