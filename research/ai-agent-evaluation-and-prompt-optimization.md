# AI Agent Evaluation and Prompt Optimization

This pack is for teams running AI agents in production and optimizing prompt performance.

## Prompt 1: AI Agent Evaluation Framework

### Prompt

```text
Role:
You are an AI evaluation lead for production agent systems.

Task:
Create a rigorous evaluation framework for a customer support AI agent that retrieves policy documents and drafts responses.

Context:
- Risks: hallucination, policy non-compliance, wrong escalation decisions
- Data available: historical tickets, internal policy docs, human QA annotations
- Goal: launch with safety and quality confidence

Style:
Methodical, safety-oriented, and measurable.

Constraints:
- Define online and offline evaluation metrics
- Include red-team test categories
- Include pass/fail gates before release
- Include post-launch monitoring plan

Output Format:
1) Evaluation objectives
2) Metric taxonomy
3) Test set design
4) Release gating criteria
5) Monitoring and alerting model
```

### Expected AI Output

- comprehensive metric set (accuracy, grounding, safety, latency)
- clear release readiness gates
- continuous quality monitoring framework

## Prompt 2: Prompt Optimization System

### Prompt

```text
Role:
You are a prompt optimization engineer.

Task:
Design an iterative prompt optimization system to improve response quality of an AI research assistant.

Context:
- Current issues: verbose answers, weak citation discipline, occasional factual drift
- Workflow: prompt changes deployed manually without controlled experiments
- Goal: improve precision and trustworthiness over 6 iterations

Style:
Experimental, rigorous, and reproducible.

Constraints:
- Include hypothesis-driven iteration loop
- Include A/B prompt testing protocol
- Include error taxonomy for failed outputs
- Include prompt versioning and rollback policy

Output Format:
1) Baseline definition
2) Iteration loop design
3) Test and scoring framework
4) Version control strategy
5) Reporting template
```

### Expected AI Output

- reproducible prompt improvement workflow
- robust comparison protocol for prompt variants
- clear governance for versioning and rollback
