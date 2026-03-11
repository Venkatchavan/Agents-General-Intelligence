# 🧠 Memory System

This directory is The Agency's persistent knowledge base. It stores learnings, patterns, failure analyses, project states, and agent performance histories that survive across sessions and pipeline runs.

**Managed by**: AGI Memory Manager  
**Written by**: AGI Self Reflector (retrospectives), AGI Memory Manager (routine writes)  
**Read by**: All agents (via AGI Memory Manager retrieval)  
**Modified by**: AGI Memory Manager only — domain agents do not write here directly

---

## Directory Structure

```
memory/
├── README.md                           # This file
├── patterns/                           # Cross-run success patterns
│   ├── README.md
│   └── [YYYY-MM-DD]-[topic].md        # Individual pattern entries
├── failures/                           # Documented failure modes and root causes
│   ├── README.md
│   ├── index.md                        # Searchable failure index
│   └── [YYYY-MM-DD]-[project].md      # Per-project failure analysis
├── project-state/                      # Live pipeline snapshots (resumable)
│   └── [project-name]/
│       ├── current-state.md           # Current phase, tasks, status
│       ├── decisions.md               # All locked decisions + rationale
│       ├── constraints.md             # Active project constraints
│       └── agent-context/             # Per-agent context briefs
│           └── [agent-name].md
└── agent-performance/                  # Per-agent scoring history
    └── [agent-name]-history.md
```

---

## How to Use This System

### Starting a New Project
1. Create `memory/project-state/[project-name]/`
2. Initialize `current-state.md`, `decisions.md`, `constraints.md`
3. Activate AGI Memory Manager to manage writes

### Resuming an Interrupted Pipeline
1. Activate AGI Context Distiller with `memory/project-state/[project-name]/current-state.md`
2. Request agent-specific briefs for agents that need to resume
3. AGI Memory Manager will provide current context

### After Completing a Pipeline Run
1. Activate AGI Self Reflector to run retrospective
2. AGI Self Reflector + AGI Memory Manager will write:
   - Patterns from this run → `memory/patterns/`
   - Failures from this run → `memory/failures/`
   - Agent performance scores → `memory/agent-performance/`

### Querying Memory
Ask AGI Memory Manager: "What do we know about [topic / agent / failure type]?"

---

## Memory Entry Standards

All memory entries follow the format defined in `agi-core/agi-memory-manager.md`.

**Key rules**:
- All entries are dated and source-attributed
- No entry is written from unverified agent self-reports
- Contradictions are flagged, not silently resolved
- Entries older than 30 days are compressed (kept as summaries)
- Entries older than 1 year are archived unless marked `evergreen: true`

---

## What Belongs Here vs. Not Here

| ✅ Belongs in Memory | ❌ Does Not Belong |
|---------------------|-------------------|
| Decisions made and rationale | Work-in-progress drafts |
| Failure root causes | Raw conversation logs |
| Agent performance scores | Code or implementation files |
| Successful patterns with evidence | Speculative ideas not yet validated |
| Active project state | Superseded decisions |
| User/team preferences | One-off task outputs |
