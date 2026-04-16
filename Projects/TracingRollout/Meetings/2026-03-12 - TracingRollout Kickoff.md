---
date: 2026-03-12
attendees:
  - Your Name
  - SRE Lead
  - Platform Engineer
  - Data Team Lead
type: project
project: TracingRollout
tags:
  - NoteType/Meeting
---

# 2026-03-12 - TracingRollout Kickoff

## Topic & Objective

Align on scope, ownership, and initial workplan for distributed tracing rollout across Tier 1 services.

## Agenda

- Review charter and scope
- Walk through Tier 1 service list
- Assign initial workstreams
- Identify blockers and dependencies

## Notes

- Agreed Tier 1 = checkout, auth, payments, catalog. All other services are Phase 2.
- SRE Lead will own sampling strategy. Your Name owns instrumentation and backend selection.
- Data Team raised retention policy question — needs formal approval before backend is stood up. Data Team Lead to own approval process, targeting 2 weeks.
- Jaeger flagged as a candidate by Platform Engineer. Agreed to timebox a spike to 1 week before committing.
- Frontend/RUM tracing explicitly out of scope for this phase.

## Decisions

- Tier 1 service list confirmed (checkout, auth, payments, catalog)
- Data Team Lead owns retention policy approval
- 1-week Jaeger spike approved before backend decision is finalized

## Next Steps

- Your Name: Draft charter and circulate for review by 2026-03-15
- SRE Lead: Draft initial sampling strategy proposal
- Data Team Lead: Start retention policy approval process
- Platform Engineer: Begin Jaeger spike
