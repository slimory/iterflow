# Project Documentation Structure

## Required Files

When initializing a new project with iterflow, create the following documentation structure:

```
docs/
├── PROJECT.md              # Vision, tech stack, milestones
├── USER_REQUIREMENTS.md    # User needs (checkbox format)
├── ARCHITECTURE.md         # Technical design, ADRs
├── CONTRIBUTING.md         # Contribution rules, code conventions
├── CHANGELOG.md            # Version history (Keep a Changelog)
└── iterations/
    ├── README.md           # Current iteration status, overview table
    └── iter-0/
        ├── prd.md          # Product requirements
        └── tasks.md        # Task tracking
```

Root `README.md` serves as the single entry point with a documentation map.

## Documentation Map (read order)

| # | Document | Purpose |
|---|----------|---------|
| 1 | PROJECT.md | Project vision, tech stack, milestones |
| 2 | USER_REQUIREMENTS.md | User needs and feature tracking |
| 3 | ARCHITECTURE.md | Technical design, directory structure, ADRs |
| 4 | CONTRIBUTING.md | Contribution rules, code conventions |
| 5 | iterations/ | Current work: pick tasks, track progress |
| 6 | CHANGELOG.md | Version history |

## USER_REQUIREMENTS.md Format

```markdown
# User Requirements

## Requirements List

### [Category]

[ ] YYYY-MM-DD Requirement description from user perspective
[x] YYYY-MM-DD Completed requirement description
```

## CHANGELOG.md Format

Follow [Keep a Changelog](https://keepachangelog.com/):

```markdown
## [Unreleased]

### Added
- Feature description

### Changed
- Change description

### Fixed
- Fix description
```

## Documentation Update Rules

| When you... | Update... |
|-------------|-----------|
| Add/change a feature | CHANGELOG.md, iteration tasks.md |
| Make an architecture decision | ARCHITECTURE.md (add ADR) |
| Change directory structure | ARCHITECTURE.md |
| Complete a user requirement | USER_REQUIREMENTS.md (check it off) |
| Finish an iteration | iterations/README.md (update table) |
| Change tech stack | PROJECT.md |
