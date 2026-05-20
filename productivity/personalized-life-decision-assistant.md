# Personalized Life Decision Assistant — PromptCraft Prompt

## Prompt (PromptCraft Structured)

```text
Role:
You are an AI System Designer and Behavioral Scientist focused on building responsible, personalized decision-support systems.

Task:
Design a conversational AI system — the Personalized Life Decision Assistant (PLDA) — that provides guidance on major life decisions (career, relationships, finance) tailored to an individual's personality, values, and goals, while avoiding bias and preventing user over-dependence.

Context:
- Target users: adults seeking guidance on career moves, relationship choices, financial planning, and life transitions
- Channels: web chat, mobile app, voice assistant
- Data inputs available: user questionnaire, interaction history, optional linked data (financial accounts, calendar), third-party knowledge sources, expert-curated advice databases
- Constraints: privacy-first, bias mitigation, explainability, encourage critical thinking, allow user control over personalization

Style:
Professional, empathetic, evidence-based, and safety-conscious.

Constraints (explicit):
- Incorporate user's personality, values, and goals into recommendations.
- Use bias-detection and correction mechanisms before presenting advice.
- Prevent over-reliance by encouraging critical reasoning and offering decision scaffolding.
- Support continuous learning from feedback while respecting user consent and data governance.

Output Format:
- A detailed system design document including: Executive Summary; Functional Requirements; System Architecture and Data Flow; Modules (personality assessment, decision framework, bias mitigation, feedback loop, learning module); UX and conversational flows; Safety & ethical safeguards; Evaluation metrics; Implementation roadmap; Sample prompts and API contracts; Appendices (data schemas, consent model).
```

---

## Expected AI Output: System Design Document

### Executive Summary

The Personalized Life Decision Assistant (PLDA) is a conversational AI that helps users make high-stakes personal decisions by combining individualized personality profiles, evidence-backed decision models, and transparent, bias-aware recommendations. PLDA's core goals are to:
- Provide personalized, explainable guidance for career, relationship, and financial decisions.
- Encourage user agency and critical thinking through structured decision scaffolds.
- Continuously improve through user feedback while preserving privacy and fairness.

### Functional Requirements

Core capabilities:
- Onboarding & Personality Assessment: collect personality traits, values, goals, and decision preferences via validated instruments (e.g., Big Five, values inventory) and situational questionnaires.
- Conversational Guidance: multi-turn, context-aware dialogue supporting exploratory questioning and scenario simulation.
- Decision Modeling: scenario comparison, outcome forecasting, tradeoff analysis, risk assessment, and multi-criteria decision analysis (MCDA).
- Bias Mitigation: detect potential biases in user input, model outputs, and data sources; apply correction strategies.
- Feedback & Learning: capture user feedback, decision outcomes, and longitudinal signals to refine personalization.
- Explainability & Transparency: provide rationale, confidence, data sources, and alternative viewpoints.
- Safety & Escalation: detect crisis signals (e.g., suicidal ideation, financial exploitation) and route to human support or emergency resources.

Non-functional requirements:
- Privacy: minimal data collection, client-side storage options, encryption, and user-controlled retention.
- Reliability: resilient, low-latency conversational experience.
- Scalability: modular services to handle increasing user base and data.
- Compliance: GDPR, CCPA where applicable; audit logs for decisions and interventions.

### System Architecture & Data Flow

High-level components:
- Frontend: web/mobile/voice clients
- API Gateway & Conversational Orchestrator
- Dialogue Manager (NLP stack)
- Personalization & Profile Store (encrypted)
- Knowledge Layer (curated expert content, research databases)
- Decision Engine (MCDA, scenario simulators, causal inference models)
- Bias Mitigation Layer (filters, re-rankers, fairness validators)
- Feedback & Learning Pipeline (label collection, offline training)
- Monitoring & Governance Dashboard
- Integrations: optional financial APIs, calendars, professional networks

Data flow:
1. User onboarding -> personality assessment -> profile stored encrypted
2. Conversation input -> NLP parsing -> context state updated
3. Decision request -> Decision Engine queries profile + knowledge layer
4. Bias Mitigation runs on candidate outputs -> re-ranking & explanations
5. Recommendation presented with confidence, rationale, alternatives
6. User provides feedback/records outcome -> feedback pipeline updates models (offline)

Security & privacy:
- Client-side encryption for sensitive profile fields
- Tokenized identifiers for third-party integrations
- Differential privacy aggregation for analytics
- RBAC for internal dashboards; consent-based data release

### Modules

1) Personality Assessment Module
- Purpose: infer stable traits, values, risk tolerance, decision style
- Inputs: validated questionnaires, behavioral signals (language, choices), optional passive signals (activity rhythms)
- Outputs: structured profile with trait scores, uncertainty, calibration notes
- Implementation: combination of psychometric testing + Bayesian updating as users interact

2) Decision-Making Framework
- Core: Multi-Criteria Decision Analysis (MCDA) augmented with scenario simulation and probabilistic forecasting
- Steps:
  a) Problem framing (goals, constraints, timeline)
  b) Option generation (diverse alternatives)
  c) Criteria definition and weighting (user-involved)
  d) Scoring & sensitivity analysis
  e) Outcome projection (probabilistic)
  f) Recommendation with tradeoffs and confidence bands
- Tools: Bayesian networks for causal reasoning; Monte Carlo simulation for outcome distributions

3) Bias Mitigation Module
- Detection strategies:
  - Input-level: flag framing effects, loaded language, missing perspectives
  - Model-level: check for disparate impact across demographic slices
  - Data-level: source provenance, recency, representativeness checks
- Correction strategies:
  - Counterfactual augmentation (present alternative framings)
  - Re-weighting or re-sampling of training data
  - Re-ranking suggestions to boost underrepresented options
  - Human-in-the-loop expert review for ambiguous cases
- Explainability: annotate which bias detectors fired and what corrective action was taken

4) Feedback Loop & Outcome Capture
- Mechanisms:
  - In-conversation feedback prompts (thumbs up/down, reasoning notes)
  - Post-decision follow-ups (check-ins at user-specified intervals)
  - Outcome reporting (user-entered or integrated via APIs)
- Use cases:
  - Train supervised models to predict helpfulness
  - Calibrate personalization weights
  - Identify systematic misrecommendations

5) Learning & Improvement Module
- Offline training pipeline:
  - Aggregate anonymized feedback and outcomes
  - Use counterfactual evaluation methods to estimate policy value
  - Retrain components with fairness constraints
- Online personalization:
  - Lightweight bandit algorithms for UI-level choices (nudge phrasing)
  - Bayesian preference updating for user weights

6) Safety & Over-Dependence Prevention
- Pattern detection for over-reliance:
  - Frequency of advice-seeking for similar trivial choices
  - Reduction in user-expressed agency language
- Interventions:
  - Explicit prompts encouraging reflection: "How would you weigh these options?"
  - Decision scaffolds: show reasoning templates and ask user to input priorities
  - Limit recommendations: provide range/options rather than directives
  - Promote human consultation for major decisions (legal, medical, mental health)

### UX & Conversational Flows

Onboarding flow:
- Welcome -> brief mission statement -> consent + privacy controls -> personality questionnaire (short form)
- Offer optional integrations and set check-in cadence

Typical decision flow:
1. User states decision problem
2. System asks clarifying questions to frame the problem
3. System proposes candidate options and suggests criteria
4. User adjusts weights and preferences
5. System runs MCDA and scenario simulations
6. System presents ranked options with rationale and sensitivity analysis
7. User selects an action plan and schedule follow-ups

Explainability UI:
- Each recommendation includes: summary, top contributing signals, confidence, alternative options, and suggested next steps
- "Explain more" expands into a visualization of tradeoffs and simulation distributions

Feedback and reflection:
- After decision, scheduled prompts ask for outcome and user's retrospective: what changed, new evidence

### Bias & Fairness Strategies (Detailed)

- Auditable data lineage: log sources and transformations for every knowledge item used
- Fairness constraints in objective functions (e.g., ensure options do not systematically disadvantage groups)
- External expert panels to review contentious domains (e.g., career advice for protected classes)
- Transparently communicate limits of training data and model scopes

### Evaluation Metrics

Model & system metrics:
- Recommendation usefulness (user-rated)
- Decision outcome alignment with user goals (quantitative outcomes where applicable)
- Over-dependence index (frequency of low-value queries)
- Bias detection rates and correction success
- Calibration metrics for confidence scores
- Retention and engagement for long-term value

Safety metrics:
- Number of escalations to human support
- False positive/false negative rates in crisis detection

### Implementation Roadmap

Phase 0: Research & Ethics Setup (4-6 weeks)
- Ethical review board, expert advisory group, initial data policy and consent model

Phase 1: MVP — Core Conversational Engine + Personality Assessment (8-12 weeks)
- Lightweight personality instrument, basic MCDA engine, explainability UI, privacy baseline

Phase 2: Bias Mitigation & Feedback Integration (10-14 weeks)
- Add bias detectors, outcome capture, offline training pipelines

Phase 3: Personalization & Advanced Forecasting (12-20 weeks)
- Bayesian personalization, scenario simulation, causal models

Phase 4: Scale & Governance (ongoing)
- Compliance, audits, multi-lingual support, domain expansions

### Privacy, Compliance & Ethics

- Explicit consent: fine-grained consents for profile fields and integrations
- Data minimization: store only data necessary for personalization
- Right to forget: deletion and export tools
- Human oversight: audit logs and reviewer tools
- Documentation: model cards, data sheets, and user-facing limitations page

### Sample Prompts & API Contracts

Sample user prompt:
"I'm offered two job roles: A (startup, higher equity) and B (corporate, stable). I value autonomy and financial security. Help me decide."

System API (simplified):
- POST /decisions
  - body: {user_id, problem_text, context, constraints, preferred_horizon}
  - returns: {decision_id, options:[{id,title}], suggested_steps, confidence, explanation}

- POST /feedback
  - body: {decision_id, user_feedback, outcome}

### Appendix: Data Schemas (excerpt)

UserProfile:
- user_id
- traits: {openness, conscientiousness, extraversion, agreeableness, neuroticism}
- values: array
- goals: array
- preference_weights: map
- consent_flags

DecisionRecord:
- decision_id
- user_id
- timestamp
- problem_text
- options
- criteria_weights
- model_version
- recommendation
- feedback
- outcome

---

## Usage Instructions

1. Copy the structured prompt at the top into your LLM and specify available integrations and pilot goals.
2. Use the returned system design as a blueprint; iterate with domain experts (legal, ethics, clinical if needed).
3. Implement in phases, starting with a metadata-first MVP and opt-in users.

---

## Where to add this file

Category: `productivity/` — this prompt supports personal productivity and life decision support systems.
