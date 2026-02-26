# Iterflow

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill for document-driven iterative development.

Iterflow turns your project docs into the single source of truth. Every iteration has a PRD and a task list — Claude reads them before coding, updates them after. No context lost between sessions.

## Why

AI coding agents forget context between conversations. Iterflow solves this by keeping all project knowledge in structured Markdown files that the agent reads on every session start. You get:

- Persistent project context across conversations
- Structured iteration planning with PRDs and task tracking
- Traceable requirements → features → tasks pipeline
- Multi-agent coordination support

## Quick Start

### Install

Copy the `iterflow/` directory into your Claude Code skills location:

```
~/.claude/skills/iterflow/
```

Or add it to a project-level `.claude/skills/` directory.

### Usage

| Command | What it does |
|---------|-------------|
| `/iterflow init` | Bootstrap doc structure for a new project |
| `/iterflow new` | Plan and create a new iteration |
| `/iterflow` | Resume work — pick up the next pending task |
| `/iterflow status` | Show iteration progress |
| `/iterflow req` | List unresolved user requirements |

### Typical Workflow

```
/iterflow init        ← set up project docs
/iterflow new         ← plan first iteration
/iterflow             ← start working on tasks
/iterflow status      ← check progress anytime
/iterflow new         ← next iteration when done
```

## How It Works

Iterflow generates and maintains a `docs/` directory in your project:

```
docs/
├── PROJECT.md              # Vision, tech stack, milestones
├── USER_REQUIREMENTS.md    # User needs (checkbox format)
├── ARCHITECTURE.md         # Technical design, ADRs
├── CONTRIBUTING.md         # Contribution rules
├── CHANGELOG.md            # Version history
└── iterations/
    ├── README.md           # Iteration overview & status
    └── iter-0/
        ├── prd.md          # What to build and why
        └── tasks.md        # Granular task tracking
```

Each iteration follows a clear lifecycle:

1. Define goals and requirements in `prd.md`
2. Break down into tasks with priorities and acceptance criteria in `tasks.md`
3. Claude claims tasks, implements them, and updates docs as it goes
4. When all tasks are done, start the next iteration

## Key Principles

- **Doc-first** — Read docs before coding. Update docs after coding.
- **MECE** — Each piece of information lives in exactly one place.
- **Iteration-scoped** — All work happens within an iteration. No orphan tasks.
- **Traceable** — Every task links back to user requirements.

## License

[MIT](LICENSE)
