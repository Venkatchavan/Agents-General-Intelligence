# Patterns Library

This directory stores validated success patterns from completed pipeline runs.  
Each pattern has been observed across multiple runs before being promoted here.

**Written by**: AGI Memory Manager (after AGI Self Reflector retrospective)  
**Read by**: All agents via AGI Memory Manager retrieval  
**Single observation?** → File in `../failures/` as a note, not here  
**3+ consistent observations?** → Promote to this directory

---

## Pattern Index

| Pattern | File | Domain | Confidence | Runs Observed |
|---------|------|--------|-----------|---------------|
| *(no patterns yet — populate after first pipeline run)* | | | | |

---

## Pattern Entry Format

Each pattern file follows this template:

```markdown
# Pattern: [Descriptive Title]
**Type**: [Handoff / Architecture / Workflow / Quality / Communication]
**Domain**: [Engineering / Design / Marketing / Cross-division]
**Confidence**: [High / Medium] — [evidence basis]
**Runs Observed**: [N]
**First Seen**: [YYYY-MM-DD]
**Last Validated**: [YYYY-MM-DD]
**Evergreen**: [true / false]

## Summary
[2-sentence summary of the pattern]

## Detail
[Full description with specific examples from pipeline runs]

## When to Apply
- Condition 1
- Condition 2

## When NOT to Apply
- Counter-condition 1
- Counter-condition 2

## Which Agents Should Know This
- [Agent A] — how it applies to them
- [Agent B] — how it applies to them

## Evidence
- [Run 1]: [What was observed]
- [Run 2]: [What was observed]
```
