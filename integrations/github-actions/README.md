---

# GitHub Actions Integration

Use The Agency agents directly in your GitHub Actions CI/CD workflows. These workflow templates invoke agents at the right moments in your development lifecycle — automatically.

## Available Workflows

| Workflow | Trigger | Agents Invoked |
|----------|---------|---------------|
| [`pr-review.yml`](.github/workflows/pr-review.yml) | Pull Request opened/updated | Evidence Collector, Reality Checker |
| [`security-scan.yml`](.github/workflows/security-scan.yml) | Push to main/PR | Security Engineer |
| [`ethics-review.yml`](.github/workflows/ethics-review.yml) | PR with `ethics-review` label | AGI Ethical Reviewer |
| [`release-gate.yml`](.github/workflows/release-gate.yml) | Release created | Reality Checker, Legal Compliance Checker |
| [`performance-check.yml`](.github/workflows/performance-check.yml) | Deploy to staging | Performance Benchmarker |

## Installation

### Step 1: Copy workflow files to your repo

```bash
cp integrations/github-actions/workflows/*.yml .github/workflows/
```

### Step 2: Set required secrets

```bash
# In your GitHub repo: Settings → Secrets → Actions
ANTHROPIC_API_KEY=your_key_here      # For Claude-based agents
OPENAI_API_KEY=your_key_here         # Optional: OpenAI-based agents
```

### Step 3: Customize agent prompts

Each workflow YAML contains an `AGENT_INSTRUCTIONS` environment variable. Edit it to match your project's conventions, stack, and standards.

## How It Works

These workflows use the [Claude API](https://docs.anthropic.com) directly via `curl` in workflow steps, passing the agent system prompt from the relevant agent `.md` file and the PR diff / build output as context.

You can also adapt these to use:
- OpenAI's Assistants API
- Gemini API
- Any LLM with a REST API

## Important Notes

- These workflows are **advisory by default** — they post comments and create reports, but do not block PRs
- To make agents **required checks**, set `required_status_checks` in your branch protection rules
- Agent API calls cost tokens — estimate usage based on your PR volume before enabling all workflows

---

See individual workflow files in `.github/workflows/` for full implementation.
