# Agent Performance History

This directory tracks per-agent performance scores across pipeline runs.  
Each agent has their own history file, updated after every retrospective by AGI Memory Manager.

**Written by**: AGI Memory Manager  
**Source data**: AGI Self Reflector retrospective reports  
**Purpose**: Identify trends, improvement areas, and consistently underperforming configurations

---

## Performance File Index

| Agent | File | Total Runs | Avg Score | Trend |
|-------|------|-----------|-----------|-------|
| *(populate after first pipeline run)* | | | | |

---

## Performance Entry Format

Each agent's history file follows this template:

```markdown
# Performance History: [Agent Name]
**Agent File**: [path/to/agent.md]
**Total Pipeline Runs**: [N]
**Average Score**: [Letter grade + numeric average]
**Trend**: [Improving / Stable / Declining]
**Last Updated**: [YYYY-MM-DD]

## Run History

| Date | Project | Score | Retries | Key Issues | Source |
|------|---------|-------|---------|-----------|--------|
| 2026-03-10 | [Project] | B+ | 0 | None | Self Reflector retrospective |

## Recurring Strengths
- [What this agent consistently does well]

## Recurring Issues
- [What this agent consistently struggles with]

## Proposed Improvements (Pending Human Approval)
- [Specific change proposal] — [Status: Proposed / Approved / Applied]

## Applied Improvements Log
- [YYYY-MM-DD]: [Change applied] — [Result]
```

---

## Scoring Rubric

| Grade | Description |
|-------|-------------|
| **A** | Deliverable met all success metrics on first attempt |
| **B** | Deliverable met success metrics with minor gaps; no retry needed |
| **C** | Deliverable required 1 retry or had notable gaps in quality |
| **D** | Deliverable required 2+ retries; significant rework needed |
| **F** | Deliverable was unusable; escalation required |

Grades reflect **first-attempt quality** — a retry that produces an A is still scored based on the retry count.
