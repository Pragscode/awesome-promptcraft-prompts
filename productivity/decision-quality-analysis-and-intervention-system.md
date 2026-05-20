# Decision Quality Analysis and Intervention System

## Prompt (PromptCraft Structured)

Role:
You are a Decision Quality Analyst and System Designer combining organizational behavior science, machine learning, and human-centered design.

Task:
Design a system that identifies patterns of poor decision-making in teams and organizations, analyzes underlying causes, and subtly intervenes to improve decision quality across startups, enterprises, and remote teams.

Context:
- Environments: startups, mid-size enterprises, distributed/remote teams
- Data sources available: meeting transcripts, calendar metadata, chat metadata (Slack/Teams), ticket/issue trackers, commit history, CRM outcomes, pulse surveys, and decision records
- Constraints: privacy-preserving, culturally adaptable, non-punitive, human-in-the-loop
- Stakeholders: team members, managers, people ops, security and compliance

Style:
Professional, collaborative, culturally aware, and operations-focused.

Constraints:
1. Detect patterns over time (not only single mistakes).
2. Analyze root causes including bias, communication gaps, and incentive misalignment.
3. Intervene subtly—improve decisions without making members feel judged or replaced.
4. Adapt to different cultural and behavioral contexts (startup vs enterprise, remote vs co-located).
5. Provide actionable insights to leaders and members with clear explainability.

Output Format:
- A detailed system design document composed of: Executive Summary; Goals & Success Criteria; Metrics & Benchmarks; Data Collection & Privacy; Data Architecture & Flow; ML & Analytics Design; Intervention Strategies; UI/UX & Reporting; Adaptability & Cultural Sensitivity; Implementation Roadmap; Monitoring & Evaluation; Appendices (schemas, sample flows).

---

## Expected AI Output: Detailed System Design Document

### Executive Summary

A Decision Quality Analysis and Intervention System (DQAIS) is a privacy-first, human-centered analytics and intervention platform that detects recurring patterns of suboptimal decisions, diagnoses probable causes (cognitive bias, communication breakdowns, incentive issues), and executes subtle, context-aware interventions. The system augments team autonomy and improves outcomes by providing actionable, explainable insights and lightweight interventions that preserve psychological safety.

### Goals & Success Criteria

Goals:
- Identify recurring decision-quality failure modes across teams and time windows.
- Provide causal and correlational diagnostics for root causes.
- Deliver low-friction interventions that incrementally improve decision outcomes.
- Maintain trust, privacy, and cultural adaptability.

Success criteria (sample):
- 20% reduction in high-regret decisions over 6 months
- 15% increase in documented decision rationale coverage within teams
- Improved post-decision satisfaction scores in pulse surveys (+0.4 on Likert scale)
- No privacy complaints; >90% opt-in within pilot teams

### Decision-Making Metrics & Benchmarks

Define quantitative and qualitative metrics to detect patterns over time.

Core metrics:
- Decision Frequency: count of recorded decisions per team/time window.
- Time-to-Decision (TTD): time from proposal to final decision.
- Decision Reversal Rate: percent of decisions reversed within X time.
- Evidence Coverage Score: proportion of decisions with explicit supporting data and rationale.
- Diversity of Input Index: count & heterogeneity of contributors included in discussion.
- Consensus Quality: measured using semantic alignment of contributors' positions (embedding distance).
- Post-Decision Outcome Metrics: business KPIs tied to decisions (e.g., revenue delta, bug rate, throughput).
- Regret/Correction Cost: estimated downstream cost of reversed or corrective actions.
- Cognitive Bias Signals: proxy scores for anchoring, confirmation bias, overconfidence (see features).
- Communication Health Metrics: meeting participation balance, dominant-speaker ratio, async response latency.

Benchmarks:
- Establish baseline per team for 4-8 weeks before applying thresholds.
- Compare teams by role and maturity stage; use cohort normalization (startup vs enterprise).

### Data Collection & Privacy Framework

Data sources (examples):
- Meeting transcripts (ASR) + speaker diarization
- Calendar metadata (attendees, duration, meeting type)
- Chat metadata (message frequency, threads, reply latency) — not content unless permitted
- Document edit history and decision records (PRs, issues, proposals)
- Ticket/issue outcomes and resolution times
- CRM and product metrics tied to decisions
- Pulse surveys and 360 feedback (anonymized)
- Optional: self-reported decision logs

Privacy & governance:
- Default to metadata-first approach; content processing requires explicit consent and scoping.
- Onboarding: clear opt-in flows; granular controls (what data, which channels, retention windows).
- Differential privacy or aggregation for cross-team comparisons.
- Role-based access control (RBAC) for insights and raw data.
- Data retention & deletion policies aligned with legal/compliance.

Ethics & fairness:
- Independent review board for high-impact interventions.
- Transparency logs for any automated intervention decisions.

### Data Architecture & Flow

High-level pipeline:
1. Ingest: connectors for calendar, chat, meetings, repos, ticketing, CRM.
2. Pre-process: normalize timestamps, speaker mapping, anonymization, extract metadata.
3. Feature extraction: linguistic, behavioral, network, and outcome features.
4. Storage: time-series store for metrics (e.g., InfluxDB, Timescale) + document store for artifacts.
5. Modeling: analytics and ML layer (real-time and batch).
6. Explainability & decision engine: rule-based logic + ML interpretation layer.
7. Intervention engine: produces nudge events, facilitation cues, or learning module triggers.
8. UI & reporting: dashboards, weekly digests, in-channel micro-messages.

Data flow diagram (simplified):
- Connectors -> Ingest Queue -> ETL -> Feature Store -> Models -> Explainability -> Intervention Engine -> UI / Integrations

### Feature Engineering (Examples)

Linguistic features (from transcripts/content):
- Use of hedges vs assertives
- Sentiment polarity and emotion signals
- Cognitive complexity (syntactic depth)
- Evidence mentions (numbers, citations)
- Question density and interrogative framing

Behavioral features:
- Speaker dominance (talk-time share)
- Response latency distributions
- Meeting attendance regularity
- Proposal–discussion–decision timelines

Network & structural features:
- Cross-functional connectivity (graph centrality)
- Decision approver diversity
- Org-level approval bottlenecks

Outcome features:
- Post-decision KPIs mapped to decision IDs
- Rework/bug counts after technical decisions
- Customer-impact indicators for product decisions

Bias proxy features:
- Anchoring: early message similarity to final decision
- Confirmation: echo-chamber index (repetition among same subgroup)
- Overconfidence: high certainty language with high reversal rate

### ML & Analytics Design

Approach: hybrid — combine unsupervised pattern detection, supervised causal inference, and rule-based explainers.

Model components:
1. Baseline profiling (unsupervised):
   - Time-series anomaly detection (e.g., Prophet + seasonal decomposition) for metrics drift.
   - Clustering of decision patterns with DBSCAN / HDBSCAN.
2. Structural models:
   - Graph Neural Network (GNN) for org/social graph signals (who talks to whom, approval paths).
3. Causal inference and attribution:
   - Causal forests / double machine learning to estimate effect of features (e.g., meeting length) on outcomes.
4. Supervised classification/ranking:
   - Predict probability of high-regret decision using historical labeled examples or proxy labels (reversal, high correction cost).
5. Explainability:
   - SHAP for feature attribution
   - Counterfactual explanations (what minimal change would reduce predicted risk?)
6. Bias detectors:
   - Linguistic-bias classifiers (anchoring, confirmation) trained on labeled corpora and heuristics.

Model training & validation:
- Use time-aware cross-validation for temporal generalization.
- Holdout teams for zero-shot deployment to measure transferability.
- Monitor model drift and retrain triggers.

### Intervention Strategies (Subtle, Human-Centered)

Design principles:
- Minimal intrusiveness: prefer insights over directives.
- Preserve autonomy: suggestions framed as options with rationale.
- Avoid public shaming: deliver personal or private nudges; allow opting out.
- Scaffolded escalation: start with lightweight nudges, increase only when persistent risks detected.

Intervention types:
1. Passive Insights (least intrusive):
   - Weekly digest highlighting decision patterns and suggested experiments.
   - Team-level dashboards with anonymized signals and recommended norms.
2. Micro-Nudges (contextual):
   - In-meeting facilitator cues: "Pause for data—2 minutes" or "Invite a dissenting perspective" shown to meeting host.
   - Pre-meeting prep prompts: remind organizers to attach decision criteria and expected outcome metrics.
3. Decision Templates & Checklists:
   - Provide structured decision templates (problem, options, evidence, tradeoffs, owner, metrics) auto-populated from conversation artifacts.
4. Just-In-Time Training:
   - Short micro-lessons triggered after repeated bias signals (e.g., short 3-minute module on confirmation bias).
5. Facilitation Assistants:
   - Human-in-the-loop facilitation recommendation: if high-risk patterns persist, recommend a neutral facilitator or retrospective session.
6. Incentive Nudges:
   - Recommend changes to meeting invitiation defaults or approval workflows to increase diversity of approvers or slow down risky fast-tracks.
7. Post-Decision Retro Prompts:
   - Automated prompts for a 48-72h reflection: capture rationale, predicted outcomes, and success criteria to be revisited later.

Safety & limits:
- Block interventions for protected or sensitive decisions (HR, legal) unless explicitly authorized.
- Always surface the rationale and data used for the suggestion.

### Adaptability & Cultural Sensitivity

Configuration model:
- Team profile templates: startup, enterprise, distributed, high-regulation.
- Local norms override: allow teams to set cultural parameters (direct vs indirect communication, decision velocity tolerance).
- Language and phrasing adaptation: nudges and training localized to preferred language & tone.
- Threshold tuning: automatically suggest thresholds based on team baseline.

Evaluation per context:
- Use cohort-based A/B trials per context to verify effectiveness and adjust strategies.

### UI/UX & Reporting

Primary interfaces:
- Team Dashboard: timeline of decisions, risk heatmap, participation metrics, trending biases.
- Decision Detail Page: decision artifact, chat/meeting trace, predicted risk score, feature attributions, suggested interventions.
- Leader Insights: high-level summaries, cross-team comparisons (aggregated, anonymized).
- Personal Coach: in-app micro-feedback and learning path for individuals.

Design principles:
- Action-first: every insight should include a recommended next action.
- Explainable: show contributors, signals, and confidence levels.
- Lightweight: short, actionable messages (1–3 lines) with deeper drill-down available.

Example UI flow:
- Weekly digest email -> Click into Team Dashboard -> Open Decision Detail -> Apply Template or Schedule Retro -> Track outcome

### Implementation Roadmap (Phased)

Phase 0: Pilot scoping & consent (2-4 weeks)
- Select pilot teams, define goals, acquire consent, baseline data collection.

Phase 1: Metadata analytics & dashboards (6-8 weeks)
- Implement connectors, baseline metrics, and team dashboards (metadata-only).

Phase 2: Lightweight interventions (8-12 weeks)
- Add meeting nudges, pre-meeting templates, post-decision prompts; measure short-term impact.

Phase 3: Advanced modeling & personalization (12-20 weeks)
- Deploy ML models for risk scoring, causal attribution, and tailored micro-training.

Phase 4: Scale & governance (ongoing)
- Cross-team normalization, RBAC, compliance features, and continuous monitoring.

### Monitoring, Evaluation & Metrics for Success

Operational monitoring:
- Data pipeline health (ingest latency, failure rates)
- Model performance (AUC, precision @k, calibration)
- Feature drift and data quality alerts

Outcome evaluation:
- Decision quality KPI improvements (see success criteria)
- Adoption metrics (nudge acceptance rate, dashboard active users)
- Safety checks (false positive rate for high-risk alerts; user complaints)

A/B testing:
- Randomize interventions across matched teams to measure causal impact.
- Use pre-post and difference-in-differences analysis for robust estimates.

### Explainability, Transparency & Documentation

- Provide model cards and data sheets for each model component.
- Record intervention rationale and logs for auditing.
- Offer an "explain" button on every recommendation showing key contributing signals and counterfactual suggestions.

### Operational Considerations

- Integrations: Slack/Teams, Google/Outlook Calendar, Zoom/MS Teams Recorder, Jira/GitHub, Notion/Confluence, CRM systems.
- Scalability: event-driven architecture with serverless pipelines for pre-processing; separate model serving clusters for real-time scoring.
- Security: encryption at rest/in-transit, SOC2 controls where applicable.

### Appendix: Sample Decision Template

- Decision Title
- Owner
- Date Proposed
- Options Considered
- Evidence & Data (links)
- Success Metrics
- Decision Deadline
- Approvers & Reviewers
- Notes on Uncertainty

---

## Usage Instructions (for contributors and prompt engineers)

1. Copy the structured prompt (top section) into the LLM of choice.
2. When requesting the design doc, include real context values (available connectors, team size, pilot goals).
3. Ask the model to output sections exactly in the "Output Format" order for easier ingestion.
4. Use the resulting system spec as a starting point for architecture, and iterate with engineering and legal teams.

---

## Where to add this file

Category: `productivity/` — this prompt and system design are focused on team decision quality and operational productivity.
