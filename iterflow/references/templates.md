# Iteration Templates

## prd.md Template

```markdown
# Iteration N: Product Requirements

## Iteration Overview

| Field | Value |
|-------|-------|
| **Iteration** | N |
| **Name** | [Iteration Name] |
| **Status** | 📋 Pending |
| **Duration** | YYYY-MM-DD to TBD |

---

## Goals

[Main goals and objectives for this iteration]

---

## User Requirements

This iteration addresses the following user requirements from [USER_REQUIREMENTS.md](../../USER_REQUIREMENTS.md):

- [ ] Requirement 1
- [ ] Requirement 2

---

## Features to Deliver

### 1. [Feature Name]
**Priority**: 🔴 P0 / 🟡 P1 / 🟢 P2

**Description**
[What this feature does and why]

**Success Criteria**
- [ ] Criterion 1
- [ ] Criterion 2

---

## Technical Requirements

[Technical constraints, architecture decisions]

---

## Out of Scope

[What is explicitly not included]

---

## Risks & Mitigation

| Risk | Impact | Mitigation |
|------|--------|------------|
| [Risk] | High/Medium/Low | [Strategy] |

---

**Created**: YYYY-MM-DD
**Last Updated**: YYYY-MM-DD
```

---

## tasks.md Template

```markdown
# Iteration N: Tasks

## Iteration Information

| Field | Value |
|-------|-------|
| **Iteration Number** | N |
| **Name** | [Iteration Name] |
| **Status** | 📋 Pending |
| **Start Date** | YYYY-MM-DD |
| **End Date** | TBD |
| **Completion** | 0% (0/Y tasks) |

---

## Task List

### TN.1 [Task Name]
- **Status**: 📋 Pending
- **Priority**: 🔴 P0 / 🟡 P1 / 🟢 P2 / ⚪ P3
- **Dependencies**: [Task IDs or None]
- **Depended By**: [Task IDs]
- **Owner**: [Name]
- **Start Time**: -
- **Completion Time**: -
- **Estimated Effort**: Small / Medium / Large

**Description**
[Detailed description of what needs to be done]

**Acceptance Criteria**
- [ ] Criterion 1
- [ ] Criterion 2

**Implementation Notes**
[Fill after completion]

**Related Files**
- [Fill after completion]

---

## Iteration Summary

### Completion Status
- **Total Tasks**: X
- **Completed**: 0
- **In Progress**: 0
- **Pending**: X
- **Blocked**: 0

### Main Achievements
- [Fill after completion]

### Issues Encountered
- [Fill after completion]

### Lessons Learned
- [Fill after completion]

---

**Created**: YYYY-MM-DD
**Last Updated**: YYYY-MM-DD
```

---

## iterations/README.md Template (for new projects)

```markdown
# Iteration Management

## Current Status

**Current Iteration**: [Iteration N: Name](./iter-N/)
**Status**: 📋 Pending
**Last Updated**: YYYY-MM-DD

---

## Iteration Overview

| Iteration | Status | Completion | Directory |
|-----------|--------|------------|-----------|
| 0: [Name] | 📋 Pending | 0% (0/X) | [iter-0/](./iter-0/) |

---

## Task Workflow

See [CONTRIBUTING.md](../CONTRIBUTING.md) for the full task claiming and completion process.

### Status Flow

```
📋 Pending → 🔄 In Progress → ✅ Completed
                    ↓
              🚫 Blocked
```

### Priority Levels

- 🔴 **P0**: Critical — blocks other work
- 🟡 **P1**: Important — affects user experience
- 🟢 **P2**: Enhancement — nice to have
- ⚪ **P3**: Future — recorded for later
```
