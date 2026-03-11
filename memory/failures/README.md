# Failure Library

This directory stores documented failure modes, root causes, and lessons learned from pipeline runs.  
Every retry, quality gate rejection, and escalation from a pipeline run should have an entry here.

**Written by**: AGI Memory Manager (after AGI Self Reflector retrospective)  
**Purpose**: Prevent the same failure from recurring across runs  
**Single observation?** → Still document it here; a single failure can be a warning  
**3+ observations?** → Elevate to systemic issue and propose agent file changes

---

## Failure Index

| Failure Type | Project | Date | Root Cause Category | Status | File |
|-------------|---------|------|--------------------|----|------|
| *(no failures documented yet)* | | | | | |

---

## Failure Categories

| Category | Description | Common Fix |
|----------|-------------|-----------|
| **Handoff Gap** | Context lost between agents at handoff boundary | Update handoff template in source agent |
| **Spec Ambiguity** | Goal specification was unclear, causing misinterpretation | Improve AGI Goal Decomposer clarification prompts |
| **Scope Creep** | Agent added unrequested features | Reinforce "quote exact requirements" rule |
| **Quality Gate Bypass** | Phase advanced without sufficient evidence | Tighten quality gate criteria |
| **Context Loss** | Agent started without relevant prior context | AGI Context Distiller needed at session boundary |
| **Agent Overreach** | Agent worked outside their domain, causing conflicts | Improve division boundary definition |
| **Wrong Agent Chosen** | Task assigned to agent without the right expertise | Improve AGI Goal Decomposer team assembly logic |

---

## Failure Entry Format

```markdown
# Failure: [Failure Description]
**Date**: [YYYY-MM-DD]
**Project**: [Project name]
**Category**: [From category table above]
**Severity**: [Critical / High / Medium / Low]
**Times Occurred Before**: [N — or "First occurrence"]

## What Happened
[Factual description of what went wrong]

## Evidence
[Links or descriptions of evidence — screenshots, retry logs, QA reports]

## Root Cause (5 Whys)
1. Why did [symptom] occur? → [Cause 1]
2. Why did [cause 1] occur? → [Cause 2]
3. Why did [cause 2] occur? → [Root cause]

## Not the Root Cause (Eliminations)
- We ruled out [X] because [reason]

## Proposed Fix
**Change needed in**: [Agent file / NEXUS protocol / Goal Decomposer / Activation process]
**Proposed change**: [Specific diff or instruction change]
**Status**: [Proposed / Approved / Applied]

## Prevention Check
After applying the fix, verify prevention with this test:
[Specific test scenario that would have caught this failure]
```
