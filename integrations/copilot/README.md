# GitHub Copilot Integration

This integration connects GitHub Copilot's inline coding assistance with The Agency's agent personalities,
so Copilot suggestions stay aligned with your project's established division roles and quality standards.

---

## How It Works

GitHub Copilot reads `.github/copilot-instructions.md` and injects those instructions into every Copilot
Chat session in your repository. The Agency uses this to:

1. Tell Copilot **which agent to behave as** based on context (file type, task type)
2. Enforce **agency-wide quality standards** (handoff format, ethics review, known limitations)
3. Route complex tasks to **named agents** for consistent persona and output style

---

## Setup

### 1. Enable Copilot Instructions in your repo

No additional configuration needed. GitHub Copilot automatically reads `.github/copilot-instructions.md`
when it exists.

### 2. Verify Copilot Chat picks up instructions

Open a Copilot Chat session and ask:
```
What agency division do you belong to for this project?
```

Copilot should respond with the appropriate division based on context.

---

## Agent Routing by Context

| Context | Agent Invoked | Division |
|---------|--------------|---------|
| React/Vue/CSS files | Frontend Developer | engineering |
| API routes / server files | Backend Architect | engineering |
| SQL / migration files | Database Architect | engineering |
| CI/CD / Docker / k8s | DevOps Automator | engineering |
| Prompt / LLM files | Prompt Engineer | engineering |
| Test files | Senior QA Engineer | testing |
| Security-sensitive code | Security Engineer | engineering |
| UI component files | UI Designer | design |
| Product specs / PRDs | Sprint Prioritizer | product |
| Marketing copy | Content Creator | marketing |
| High-level planning | AGI Goal Decomposer | agi-core |
| Post-sprint review | AGI Self Reflector | agi-core |
| Ethics concerns | AGI Ethical Reviewer | agi-core |

---

## Trigger Phrases

Use these in Copilot Chat to explicitly activate an agent:

| Phrase | Activates |
|--------|-----------|
| `/goal [task description]` | AGI Goal Decomposer |
| `/reflect [what happened]` | AGI Self Reflector |
| `/ethics [change description]` | AGI Ethical Reviewer |
| `/schema [description]` | Database Architect |
| `/prompt [task]` | Prompt Engineer |
| `/ux [screen or flow]` | UX Architect |
| `/security [component]` | Security Engineer |
| `/monetize [feature]` | Monetization Strategist |

---

## Files

| File | Purpose |
|------|---------|
| `.github/copilot-instructions.md` | Injected into every Copilot Chat session |
| `agi-core/README.md` | AGI meta-agent docs |
| `integrations/github-actions/` | CI/CD automation workflows |

---

## Limitations

- Copilot instructions are injected as context, not enforced. Copilot may deviate on complex prompts.
- Agent routing is heuristic — Copilot infers context from file paths, not guaranteed.
- Explicit trigger phrases (`/goal`, `/ethics`, etc.) are more reliable than auto-routing.
- The memory system (`memory/`) is not read by Copilot automatically — paste relevant context manually.

---

## Related

- [GitHub Copilot Custom Instructions docs](https://docs.github.com/en/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot)
- [GitHub Actions Integration](../github-actions/README.md)
- [AGI Core Division](../../agi-core/README.md)
