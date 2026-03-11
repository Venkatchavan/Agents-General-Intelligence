# 🤖 AGI Core Division

The **AGI Core** division contains meta-agents that reason *about* The Agency itself. These agents don't build features or write copy — they make the entire multi-agent system smarter, more reliable, and self-improving.

## Why AGI Core Exists

Standard domain agents (Engineering, Design, Marketing, etc.) are specialists within their lane. But no standard agent answers:
- *"Which agents do I need for this goal?"*
- *"Why did the last pipeline fail at that handoff?"*
- *"What did we decide in the last session?"*
- *"Is this plan ethically safe to ship?"*
- *"The context window is full — what's actually important?"*

AGI Core agents answer those questions.

---

## The Agents

| Agent | Role | When to Activate |
|-------|------|-----------------|| 👑 [AGI Chief Orchestrator](agi-chief-orchestrator.md) | Supreme authority — conducts Śhāstrārtha debate after every significant output; delivers APPROVED / REVISE / ROLLBACK | After every significant agent output || 🎯 [AGI Goal Decomposer](agi-goal-decomposer.md) | Translates any goal into a ready-to-run agent activation plan | At the very start of any project |
| 🪞 [AGI Self Reflector](agi-self-reflector.md) | Reviews completed pipeline runs and proposes agent improvements | After every pipeline run |
| 🧠 [AGI Memory Manager](agi-memory-manager.md) | Manages shared knowledge base across sessions | On pipeline resume; after retrospectives |
| ⚖️ [AGI Ethical Reviewer](agi-ethical-reviewer.md) | Reviews outputs for ethical risks, bias, privacy violations | Before any launch; on sensitive features |
| 🗜️ [AGI Context Distiller](agi-context-distiller.md) | Compresses conversation history into dense context briefs | When starting new session on existing project || 🪬 [AGI Sakshi Witness](agi-sakshi-witness.md) | Pure witness consciousness — observes the whole pipeline without agenda; surfaces what embedded agents cannot see | When something feels wrong; pipeline stalled; pre-critical-decision; post-failure |
---

## How AGI Core Fits in NEXUS

```
Goal Input
    ↓
AGI Chief Orchestrator ─────── Receives goal; initiates pipeline
    ↓
AGI Goal Decomposer  ──────── Creates activation plan
    ↓
[Agent produces output]
    ↓
AGI Chief Orchestrator ─────── Śhāstrārtha debate
    ├── APPROVED → next pipeline stage
    ├── REVISE   → agent revises → debate repeats
    └── ROLLBACK → return to origin with new framing
    ↓
AGI Context Distiller ──────── Keeps context manageable mid-pipeline
AGI Memory Manager   ──────── Persists knowledge across sessions
AGI Ethical Reviewer ──────── Gates launch on ethical safety
AGI Sakshi Witness   ──────── [On-demand] Observes the whole; surfaces invisible gaps
    ↓
[Pipeline Complete]
    ↓
AGI Self Reflector   ──────── Retrospective + agent improvement proposals
AGI Memory Manager   ──────── Writes learnings to memory
AGI Chief Orchestrator ─────── Final Siddhānta on full pipeline run
```

---

## AGI Core Activation Prompts

### Start a New Project
> Activate AGI Goal Decomposer. My goal is: [one-paragraph description]. Decompose this into an agent activation plan with the minimum viable team, critical path, quality gates, and ready-to-use activation prompts.

### Resume an Existing Project
> Activate AGI Context Distiller. Here is the conversation history from our last session: [paste]. Produce a context brief for [agent name] so they can resume work immediately.

### Post-Pipeline Retrospective
> Activate AGI Self Reflector. The pipeline for [project] just completed. Here are the agent outputs and handoff logs: [attach]. Produce a performance scorecard, root cause analysis for any retries, and proposed agent `.md` file improvements.

### Ethics Check Before Launch
> Activate AGI Ethical Reviewer. Review the following for ethical risks before we proceed to launch: [paste feature spec / code / UX flow]. Flag any Critical or High issues as ship blockers.

### When Something Feels Wrong (No Agenda)
> Activate AGI Sakshi Witness. Something feels off about how this project is going but I can't name it. Here is everything so far: [context]. Observe this without agenda. What is actually happening, and where does our view of ourselves diverge from what you see?

### Before a Critical Irreversible Decision
> Activate AGI Sakshi Witness. We are about to make the following decision: [decision]. Here is the full context: [context]. Before we proceed — witness this. What are we not seeing?

---

## Important: Human Approval Required

AGI Core agents **propose** changes to the system — they never auto-apply them. All proposed agent file diffs, memory writes, and system changes require explicit human review and approval.

This is intentional. The Agency improves through human-in-the-loop iteration, not autonomous self-modification.
