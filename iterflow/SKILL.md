---
name: iterflow
description: >
  Document-driven iterative development workflow. Manage projects through structured iterations
  with PRDs, task tracking, and user requirements. Use when user invokes /iterflow commands:
  /iterflow (resume current iteration work), /iterflow new (create new iteration),
  /iterflow status (show progress), /iterflow req (list unresolved requirements),
  /iterflow init (bootstrap doc structure for a new project).
  Also triggers when user mentions "iteration", "iterflow", or asks about project task status
  in a project that has a docs/iterations/ directory.
---

# Iterflow

Document-driven iterative development. All project knowledge lives in docs. Read docs first, update docs when you make changes.

## Commands

| Command | Action |
|---------|--------|
| `/iterflow` | Resume current iteration — read docs, find current iteration, pick next pending task, work on it |
| `/iterflow new` | Create a new iteration — determine next iter number, create prd.md + tasks.md from templates |
| `/iterflow status` | Show current iteration progress — task completion stats, blocked items, in-progress work |
| `/iterflow req` | List unresolved user requirements from USER_REQUIREMENTS.md |
| `/iterflow init` | Bootstrap the full doc structure for a new project |

## `/iterflow` — Resume Current Iteration

1. Read `docs/iterations/README.md` to find the current iteration
2. Read the current iteration's `tasks.md`
3. Find the first task with "📋 Pending" status and no owner
4. If no pending tasks exist, report iteration complete and suggest `/iterflow new`
5. Claim the task: set Owner, Status to "🔄 In Progress", Start Time to today
6. Read the iteration's `prd.md` for context on what the task is trying to achieve
7. Implement the task, following acceptance criteria
8. On completion, update task status, fill Implementation Notes and Related Files
9. Apply documentation update rules (see [doc-structure.md](references/doc-structure.md))
10. Move to next pending task or report iteration complete

For full task workflow details, see [workflow.md](references/workflow.md).

## `/iterflow new` — Create New Iteration

1. Read `docs/iterations/README.md` to determine the current/latest iteration
2. Read the latest iteration's `tasks.md`, check for unfinished tasks (📋 Pending, 🔄 In Progress, ⛔ Blocked)
3. **If unfinished tasks exist**, present the user with options:
   - **Carry over**: Move unfinished tasks into the new iteration (copy them to the new tasks.md, mark originals as "➡️ Carried to iter-N")
   - **Drop**: Mark unfinished tasks as "🚫 Dropped" in the current iteration and do not carry them forward
   - **Complete first**: Abort new iteration creation, resume current iteration with `/iterflow` instead
   - The user may also mix strategies (e.g., carry some, drop others) — let them pick per task if they choose
4. After resolving unfinished tasks (or if none exist), determine the next iteration number N
5. Ask the user for: iteration name, goals, and which user requirements to address
6. Create `docs/iterations/iter-N/` directory
7. Create `prd.md` and `tasks.md` using templates from [templates.md](references/templates.md)
8. Fill prd.md with goals, user requirements, features, risks, out-of-scope
9. Break features into tasks in tasks.md with priorities, dependencies, acceptance criteria
10. If carrying over tasks, add them to the new tasks.md with a note indicating their origin (e.g., "Carried from iter-M")
11. Update `docs/iterations/README.md`: add row to overview table, update current iteration pointer
12. Present the plan to the user for review before starting work

## `/iterflow status` — Show Progress

1. Read `docs/iterations/README.md` for the overview
2. Read current iteration's `tasks.md`
3. Report:
   - Iteration name and overall completion percentage
   - Tasks by status (completed / in-progress / pending / blocked)
   - Any blocked tasks with their blockers
   - Next available task to pick up

## `/iterflow req` — Unresolved Requirements

1. Read `docs/USER_REQUIREMENTS.md`
2. List all unchecked `[ ]` requirements grouped by category
3. For each, note if it's addressed by any existing iteration (cross-reference prd.md files)

## `/iterflow init` — Bootstrap Project Docs

For a new project that doesn't yet have the iterflow doc structure:

1. Ask the user for: project name, description, tech stack, target users
2. Create the full documentation structure per [doc-structure.md](references/doc-structure.md):
   - `docs/PROJECT.md` — filled with user-provided info
   - `docs/USER_REQUIREMENTS.md` — empty template, ask user for initial requirements
   - `docs/ARCHITECTURE.md` — skeleton with project structure
   - `docs/CONTRIBUTING.md` — standard contribution rules and task workflow
   - `docs/CHANGELOG.md` — initialized with `[Unreleased]` section
   - `docs/iterations/README.md` — iteration management hub
3. Optionally create the first iteration with `/iterflow new`
4. Update root `README.md` with documentation map pointing to all docs

## Key Principles

- **Doc-first**: Never start coding without reading relevant docs. Never finish coding without updating docs.
- **MECE**: Each piece of information lives in exactly one place. No duplication across docs.
- **Iteration-scoped**: All work happens within an iteration. No orphan tasks.
- **Traceable**: Every task links to user requirements via the iteration's prd.md.

## Resources

- [templates.md](references/templates.md) — prd.md and tasks.md templates
- [workflow.md](references/workflow.md) — task claiming, completion, and coordination rules
- [doc-structure.md](references/doc-structure.md) — full project documentation structure and update rules
