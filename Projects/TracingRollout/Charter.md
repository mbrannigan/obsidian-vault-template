---
project_name: TracingRollout
owner: Your Name
status: active
start_date: 2026-03-10
target_date: 2026-05-30
sponsor: Engineering Director
stakeholders:
  - Platform Team
  - Data Team
  - SRE
jira_epic: PLAT-4421
confluence: https://confluence.example.com/display/PLAT/TracingRollout
tags:
  - NoteType/ProjectCharter
---

# TracingRollout — Charter

> This is the index file for this project. Keep it current.
> All project context lives here or is linked from here.

---

## Objective

Instrument all Tier 1 services with OpenTelemetry distributed tracing, route traces to a centralized backend, and establish SLO-aligned observability dashboards. Done when all Tier 1 services are emitting traces, a backend is selected and operational, and on-call engineers have runbooks covering trace-based triage.

---

## Scope

**In Scope**
- OTel SDK instrumentation for Tier 1 services (checkout, auth, payments, catalog)
- Trace backend selection and deployment (Honeycomb vs Grafana Tempo)
- Sampling strategy and retention policy
- SLO threshold definition and alerting
- Runbook authorship for trace-based triage

**Out of Scope**
- Non-Tier-1 services (Phase 2)
- Metrics and log correlation (future iteration)
- Frontend/RUM tracing

---

## Stakeholders

| Name | Role | Involvement |
|---|---|---|
| Your Name | Owner | Accountable |
| Engineering Director | Sponsor | Approvals, escalation |
| SRE Lead | Partner | Sampling strategy, on-call runbooks |
| Data Team Lead | Dependency | Retention policy approval |

---

## Success Criteria

- All Tier 1 services emitting traces to centralized backend
- P95 trace ingestion latency < 200ms
- Retention policy approved and enforced
- At least one runbook published and reviewed by SRE
- On-call team can triage a Tier 1 incident using traces alone

---

## Key Links

- **Jira Epic:** PLAT-4421
- **Confluence:** https://confluence.example.com/display/PLAT/TracingRollout
- **Slack Channel:** #platform-tracing
- **Status Reports:** [[Projects/TracingRollout/Status/]]
- **Meeting Notes:** [[Projects/TracingRollout/Meetings/]]

---

## Notes

- Jaeger backend spike was abandoned 2026-04-09 — operational overhead too high for team size.
- Data team approval on retention policy is the current blocking dependency.
- Checkout service instrumentation is in flight as of 2026-04-14.
