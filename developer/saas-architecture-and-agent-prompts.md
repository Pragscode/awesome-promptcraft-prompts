# SaaS Architecture and AI Agent System Prompts

This pack focuses on system design, AI automation, and agent workflows for production SaaS teams.

## How to Use

1. Fill in company stage, traffic profile, and compliance needs.
2. Keep constraints strict to avoid abstract outputs.
3. Request architecture diagrams separately if needed.

## Prompt 1: Multi-Tenant SaaS Architecture

### Prompt

```text
Role:
You are a cloud architect with expertise in multi-tenant SaaS systems.

Task:
Design a secure, scalable architecture for a B2B SaaS analytics platform processing 30M events/day.

Context:
- Product: customer support analytics dashboard
- Tenants: 1,200 companies, usage highly uneven
- Compliance: SOC 2 Type II, GDPR
- Stack preference: AWS or Azure, PostgreSQL + object storage + queue
- Team: 6 engineers, must stay operationally lean

Style:
Systematic, tradeoff-aware, implementation-ready.

Constraints:
- Include tenancy model decision (shared vs isolated components)
- Include cost control strategy
- Include data retention and deletion workflows
- Include disaster recovery RTO/RPO targets
- Include phased rollout by maturity stage

Output Format:
1) Architecture overview
2) Component-level design
3) Security and compliance controls
4) Scalability strategy
5) Cost model assumptions
6) Failure modes and mitigations
7) 90-day implementation roadmap
```

### Expected AI Output

- clear tenant isolation model with rationale
- scalable event ingestion and processing path
- compliance-aware data lifecycle handling
- phased implementation path aligned to team size

## Prompt 2: AI Support Agent Automation System

### Prompt

```text
Role:
You are an AI systems architect specialized in LLM agent orchestration.

Task:
Design an AI support agent system that auto-triages tickets, drafts replies, and escalates high-risk cases.

Context:
- Inputs: Zendesk tickets, internal docs, past ticket history
- Users: support reps and team leads
- Risks: hallucinated policy advice, incorrect refund approvals
- Goal: reduce first-response time by 40% without quality decline

Style:
Safety-first and operationally concrete.

Constraints:
- Include agent boundaries (what it can and cannot do)
- Include human-in-the-loop checkpoints
- Include evaluation metrics and guardrail tests
- Include prompt versioning strategy
- Must define failure handling flows

Output Format:
1) Agent capability map
2) Tool and data integration design
3) Prompt and policy layer
4) Safety and escalation guardrails
5) Evaluation framework
6) Launch plan with staged risk controls
```

### Expected AI Output

- explicit boundaries between autonomous and assisted actions
- policy-aware escalation logic
- measurable quality framework (CSAT proxy, resolution quality, hallucination rate)
