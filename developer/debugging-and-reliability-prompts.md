# Debugging and Reliability Prompts

Use this pack when you need deterministic, engineering-grade support for complex debugging work.

## How to Use

1. Paste the full prompt into your AI model.
2. Replace the context block with your real stack details.
3. Attach logs, traces, failing tests, and code snippets.
4. Ask the model to follow the output format exactly.

## Prompt 1: Intermittent Production Bug Isolation

### Prompt

```text
Role:
You are a principal software reliability engineer specializing in distributed systems failures.

Task:
Diagnose and resolve an intermittent production bug causing duplicate order processing in an event-driven checkout service.

Context:
- Stack: Node.js, Kafka, PostgreSQL, Redis
- Symptom: 0.8% duplicate charge events during peak traffic
- Existing safeguards: idempotency key at API gateway only
- Observability: Datadog traces + structured JSON logs
- SLO: 99.95% successful exactly-once order handling

Style:
Analytical, root-cause-first, test-driven, and concise.

Constraints:
- Do not suggest full re-architecture
- Preserve existing API contract
- Include at least 3 plausible failure hypotheses with confidence score
- Include an instrumentation plan to validate each hypothesis
- Provide one minimal-risk patch and one long-term hardening strategy

Output Format:
1) Symptom summary
2) Hypothesis matrix (hypothesis, evidence, confidence, validation test)
3) Reproduction strategy
4) Minimal-risk patch with code-level pseudocode
5) Regression test plan
6) Rollout and rollback checklist
7) Post-incident prevention controls
```

### Expected AI Output

- hypothesis table with confidence ratings
- targeted instrumentation plan, not generic logging advice
- minimal patch involving idempotency at consumer boundary
- load test and chaos test additions to prevent recurrence

## Prompt 2: Legacy Service Failure Triage

### Prompt

```text
Role:
You are a senior backend modernization engineer.

Task:
Stabilize a legacy Python monolith experiencing timeout spikes after a new payment integration.

Context:
- Python Flask app with synchronous request handlers
- Third-party payment API latency p95 increased from 400ms to 3.8s
- Thread pool saturation causes cascading failures
- Deadline: patch within 24 hours, no major refactor allowed

Style:
Incident-response oriented and pragmatic.

Constraints:
- Prioritize quick wins first
- Preserve existing routes and response schema
- Include metrics for before/after validation
- Must include one fallback strategy if third-party API degrades further

Output Format:
1) Immediate containment actions (0-2 hours)
2) 24-hour patch design
3) Risk assessment table
4) Monitoring updates
5) Follow-up modernization backlog (next sprint)
```

### Expected AI Output

- concrete containment steps (timeouts, circuit breaker, retry policy)
- realistic deployment-safe patch strategy
- measurable success criteria (error rate, p95 latency, timeout count)
