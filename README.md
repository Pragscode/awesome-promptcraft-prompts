# awesome-promptcraft-prompts

<p align="center">
  <a href="https://github.com/your-org/awesome-promptcraft-prompts/stargazers"><img alt="GitHub stars" src="https://img.shields.io/github/stars/your-org/awesome-promptcraft-prompts?style=for-the-badge" /></a>
  <a href="https://github.com/your-org/awesome-promptcraft-prompts/network/members"><img alt="GitHub forks" src="https://img.shields.io/github/forks/your-org/awesome-promptcraft-prompts?style=for-the-badge" /></a>
  <a href="https://github.com/your-org/awesome-promptcraft-prompts/blob/main/LICENSE"><img alt="License" src="https://img.shields.io/github/license/your-org/awesome-promptcraft-prompts?style=for-the-badge" /></a>
  <a href="https://github.com/your-org/awesome-promptcraft-prompts/issues"><img alt="Issues" src="https://img.shields.io/github/issues/your-org/awesome-promptcraft-prompts?style=for-the-badge" /></a>
  <img alt="Prompt Engineering" src="https://img.shields.io/badge/prompt-engineering-advanced-success?style=for-the-badge" />
  <img alt="AI Models" src="https://img.shields.io/badge/compatible-ChatGPT%20%7C%20Claude%20%7C%20Gemini-blue?style=for-the-badge" />
</p>

<p align="center">
  <strong>Curated, production-grade structured prompts built with PromptCraft.</strong><br/>
  Turn raw ideas into high-performance prompts for ChatGPT, Claude, Gemini, and modern AI agent stacks.
</p>

---

## Hero

**awesome-promptcraft-prompts** is a premium open-source prompt library for developers, founders, students, creators, and researchers.

This repository demonstrates what professional **prompt engineering** looks like when prompts are designed as reliable systems, not one-line guesses.

Built with PromptCraft: https://promptcraft-genai.netlify.app/

---

## What Is PromptCraft

PromptCraft is an AI prompt engineering platform that transforms rough user intent into optimized, reusable, and model-agnostic prompt assets.

It helps teams:
- standardize prompt quality
- reduce hallucinations through constraints
- improve output consistency
- build prompt libraries that can be versioned and reviewed
- accelerate AI product workflows

---

## Why Structured Prompts Matter

Unstructured prompting often creates:
- inconsistent answers
- vague outputs
- wasted tokens
- weak reasoning traces

Structured prompting adds explicit sections:
- **Role**
- **Task**
- **Context**
- **Style**
- **Constraints**
- **Output Format**

Result: better reliability, better controllability, and better outcomes across all major LLMs.

---

## Before vs After (PromptCraft Example)

### Weak Prompt

> make me a startup plan

### PromptCraft Prompt

```text
Role:
You are a venture strategist and zero-to-one startup operator.

Task:
Design a 90-day launch plan for a B2B SaaS startup that sells AI-powered customer support analytics.

Context:
- Founder is technical, non-sales background
- Budget: $12,000 for 3 months
- Team: 2 people
- Goal: first 10 paying customers
- Region: US + EU

Style:
Action-oriented, metric-driven, concise, and execution-ready.

Constraints:
- No paid ads in first 30 days
- Must include weekly milestones
- Must include customer discovery script
- Must include risks and mitigations

Output Format:
1) Positioning statement
2) ICP definition
3) Weekly execution roadmap (Week 1-12)
4) Sales pipeline design
5) KPI dashboard
6) Risk register with mitigations
```

### Weak AI Output (Typical)

- Build a product
- Do marketing
- Find customers
- Improve based on feedback

### Improved AI Output (PromptCraft-Structured)

- clear ICP with buying triggers
- weekly GTM schedule with deliverables
- outbound script + objections map
- KPI matrix (activation, SQL rate, win rate, churn risk)
- risk controls for runway, low response rate, and scope creep

---

## Repository Structure

```text
awesome-promptcraft-prompts/
├── developer/
├── student/
├── startup/
├── content/
├── design/
├── marketing/
├── productivity/
├── research/
├── CONTRIBUTING.md
├── GITHUB_ASSETS.md
├── LICENSE
└── README.md
```

### Folder Explanations

- **developer/**: advanced prompts for debugging, architecture, AI automation, agent systems, and code quality.
- **student/**: structured prompts for exam prep, study systems, deep understanding, and concept retention.
- **startup/**: startup operating prompts for growth systems, validation, pricing, GTM, and founder execution.
- **content/**: creator-focused prompts for long-form writing, social content, and distribution engines.
- **design/**: UI/UX audits, design critiques, flows, and conversion-focused interface prompts.
- **marketing/**: growth strategy, SEO systems, funnel design, messaging, and campaign optimization.
- **productivity/**: decision frameworks, time architecture, anti-burnout systems, and output optimization.
- **research/**: market, technical, competitor, and literature research prompts with evidence-first structure.

---

## Example Prompt Snippets

### 1) Debugging Complex Code

```text
Role: Senior software reliability engineer.
Task: Isolate and fix an intermittent race condition in a Node.js queue worker.
Context: High-concurrency checkout event processor, duplicate job execution under load.
Style: Diagnostic and test-first.
Constraints: Preserve API contracts, include reproducible test, no broad refactor.
Output Format: Root-cause report + patch + regression tests + rollback plan.
```

### 2) LinkedIn Growth System

```text
Role: B2B personal brand strategist.
Task: Build a 30-day LinkedIn growth engine for an AI consultant.
Context: 1,500 followers, target audience = SaaS founders and product leaders.
Style: Practical, high-signal, anti-generic.
Constraints: 5 posts/week, 2 hours/day max, no engagement bait.
Output Format: Content pillars + weekly schedule + post templates + KPI scorecard.
```

### 3) Research Analysis

```text
Role: Principal research analyst.
Task: Synthesize 15 sources on AI agent evaluation methods.
Context: Need a recommendation for startup implementation in 6 weeks.
Style: Evidence-weighted and decision-driven.
Constraints: Cite source quality, separate facts vs assumptions.
Output Format: Executive brief + comparison table + implementation roadmap.
```

---

## AI Model Compatibility

Designed for:
- ChatGPT (GPT-4.1, GPT-4o, o-series, GPT-5 class)
- Claude (Sonnet, Opus)
- Gemini (1.5 Pro, 2.x class)
- Open-source model stacks (Llama, Mixtral, DeepSeek variants)

Model adaptation tips:
- reduce verbosity constraints for smaller models
- increase explicit schema requirements for deterministic output
- add examples when model has weak tool-use priors

---

## Contribution Guidelines

Contributions are welcome from developers, prompt engineers, founders, and educators.

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting pull requests.

High-value contributions:
- new domain prompt packs with real use cases
- prompt quality improvements with before/after proof
- model-specific optimizations
- benchmarked output comparisons
- multilingual prompt variants

---

## SEO Keywords (Natural Indexing)

AI prompt generator, prompt engineering, ChatGPT prompts, AI prompts, structured prompts, prompt optimization, advanced AI prompting, intelligent prompt builder, AI productivity prompts, LLM prompt templates, prompt framework, AI workflow automation.

---

## Why This Repo Exists

This project is designed to:
- attract GitHub stars through practical value
- rank on search engines through high-signal prompt content
- provide backlink value to PromptCraft
- showcase advanced prompt engineering standards
- become a trusted, community-driven AI prompting resource

---

## Link Back

Explore PromptCraft: https://promptcraft-genai.netlify.app/

---

## License

MIT License. See [LICENSE](LICENSE).
