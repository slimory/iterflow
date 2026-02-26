# Task & Contribution Workflow

## Task Status Flow

```
📋 Pending → 🔄 In Progress → ✅ Completed
                    ↓
              🚫 Blocked
```

## Priority Levels

- 🔴 **P0**: Critical — blocks other work
- 🟡 **P1**: Important — affects user experience
- 🟢 **P2**: Enhancement — nice to have
- ⚪ **P3**: Future — recorded for later

## Claiming a Task

1. Open current iteration's `tasks.md`
2. Find a task with "📋 Pending" and no owner
3. Set **Owner** to your identifier
4. Set **Status** to "🔄 In Progress"
5. Set **Start Time** to today's date

Conflict rule: if a task already has an owner, pick another.

## Completing a Task

1. Verify ALL acceptance criteria are met
2. Set **Status** to "✅ Completed"
3. Set **Completion Time**
4. Fill **Implementation Notes** (decisions, deviations, issues)
5. Fill **Related Files** (all files created/modified)
6. Update iteration statistics in `tasks.md`
7. Update CHANGELOG.md for user-facing changes
8. Apply documentation update rules (see doc-structure.md)

## Quality Gates

Before marking complete:
- Code compiles/builds without errors
- No regressions in existing functionality
- Acceptance criteria all checked off
- Related documentation updated

## Handling Blockers

1. Set status to "🚫 Blocked" with explanation
2. If blocker needs its own task, create one as dependency
3. Move on to another available task

## Agent Coordination

- One agent per task (no parallel work on same task)
- Multiple agents CAN work on different tasks simultaneously
- If requirements are ambiguous, document interpretation in Implementation Notes before proceeding
- If a task is too large, break into subtasks within the iteration
- If new work is discovered, add as new task in current iteration's `tasks.md`

## Creating a New Iteration

1. Determine next iteration number N (check `docs/iterations/README.md`)
2. Create directory: `docs/iterations/iter-N/`
3. Create `prd.md` from template — fill goals, user requirements, features, risks
4. Create `tasks.md` from template — break features into tasks with priorities and acceptance criteria
5. Update `docs/iterations/README.md` overview table and current iteration pointer
6. Set iteration status to "🔄 In Progress"
