---
date: 2026-04-03
attendees:
  - Your Name
  - SRE Lead
  - Platform Engineer
type: project
project: TracingRollout
tags:
  - NoteType/Meeting
---

# 2026-04-03 - TracingRollout Weekly Sync

## Topic & Objective

Weekly project sync — status, blockers, next week priorities.

## Agenda

- Jaeger spike readout
- Backend decision
- Instrumentation workplan
- Retention policy status

## Notes

- Platform Engineer presented Jaeger spike findings. Operational complexity (scaling, storage backend) is too high for current team size. Recommendation: eliminate Jaeger.
- Reviewed Honeycomb vs Grafana Tempo. Strong preference for Tempo given existing Grafana stack and cost delta. Your Name to write up decision doc this week.
- Checkout service agreed as first instrumentation target — highest traffic, best test case.
- Retention policy still in progress with Data Team. Data Team Lead not in attendance — Your Name to follow up async.
- OTel collector config: Platform Engineer started Helm chart work. Targeting staging deploy by end of next week.

## Decisions

- Jaeger eliminated from consideration
- Grafana Tempo selected as trace backend (formal decision doc to follow)
- Checkout service is first instrumentation target

## Next Steps

- Your Name: Write OTel Backend Evaluation decision doc
- Your Name: Follow up with Data Team Lead on retention policy timeline
- Platform Engineer: Complete OTel collector Helm chart, deploy to staging
