# Project State Template

This directory stores live pipeline snapshots for active projects.  
Each project gets its own subdirectory named after the project.

**Structure per project**:
```
project-state/
└── [project-name]/
    ├── current-state.md        # Current phase, active tasks, blockers
    ├── decisions.md            # All locked architectural/product decisions
    ├── constraints.md          # Active constraints (technical, legal, business)
    └── agent-context/          # Per-agent context briefs
        └── [agent-name].md     # Context brief for resuming work
```

---

## current-state.md Template

```markdown
# Project State: [Project Name]
**Last Updated**: [YYYY-MM-DD HH:MM UTC]
**NEXUS Mode**: [Micro / Sprint / Full]
**Current Phase**: [Phase N — Phase Name]

## Overall Status
[GREEN / YELLOW / RED] — [One sentence status]

## Active Sprint
**Sprint**: [N]
**Goal**: [Sprint goal]
**Started**: [Date]
**Target Complete**: [Date]

## Task Status
| Task | Agent | Status | Blockers |
|------|-------|--------|---------|
| [Task 1] | [Agent] | ✅ Complete | |
| [Task 2] | [Agent] | 🔄 In Progress | |
| [Task 3] | [Agent] | ⏳ Queued | Waiting for Task 2 |
| [Task 4] | [Agent] | ❌ Blocked | [Blocker description] |

## Last Agent Action
**Agent**: [Agent name]
**Action**: [What they did]
**Output**: [File/deliverable produced]
**Time**: [YYYY-MM-DD HH:MM]

## Next Agent to Activate
**Agent**: [Agent name]
**Task**: [What they should do]
**Context Needed**: [What they need to know]
```

---

## decisions.md Template

```markdown
# Decisions Log: [Project Name]
**Last Updated**: [Date]

## Locked Decisions (Do Not Re-Litigate)
These decisions were made and confirmed. They are binding unless explicitly overturned with stakeholder approval.

### [Decision Category]

| # | Decision | Rationale | Made By | Date | Status |
|---|----------|-----------|---------|------|--------|
| 1 | [Decision text] | [Why this was chosen] | [Agent/Human] | [Date] | Locked |

## Open Decisions
| # | Question | Options | Decision Criteria | Owner | Target Date |
|---|----------|---------|-----------------|-------|-------------|
| 1 | [Question] | [A / B / C] | [How we'll decide] | [Agent] | [Date] |

## Rejected Options Log
| Decision | Option Rejected | Reason for Rejection |
|----------|----------------|---------------------|
| DB choice | MongoDB | ACID compliance requirement made it unsuitable |
```

---

## constraints.md Template

```markdown
# Active Constraints: [Project Name]
**Last Updated**: [Date]

## Technical Constraints
- Must deploy on [platform]
- Must use [existing tech stack component]
- API response time: <[N]ms at p95
- Must be compatible with [browser/device/OS version]

## Business Constraints
- Budget ceiling: $[N]
- Timeline: Must launch by [Date]
- Team size: [N] agents + [N] human reviewers

## Legal / Compliance Constraints
- [Regulation]: [Specific requirement]
- Data residency: [geographic requirement]
- Accessibility: WCAG [level] minimum

## Design / UX Constraints
- Must use existing brand guidelines
- Mobile-first: [breakpoints]
- Dark mode: [required / optional / not required]

## Things We Are NOT Building (Explicitly Out of Scope)
- [Feature X] — deferred to V2
- [Platform Y] — not in budget
- [Integration Z] — not required by spec
```
