---
tags:
  - area
created: 2026-03-01
---

# Observability

## Purpose

Own the observability posture for Tier 1 services — distributed tracing, metrics, and log correlation. Ensure on-call engineers have the tools and runbooks to triage incidents without guesswork.

## Standards

- All Tier 1 services emit traces, metrics, and structured logs
- Every new service gets OTel instrumentation before it ships
- On-call runbooks cover trace-based triage for all P1/P2 alert types
- SLO dashboards are reviewed monthly and thresholds adjusted as traffic patterns change

## Notes

- Grafana Tempo selected as trace backend (April 2026) — see [[Projects/TracingRollout/Documents/OTel Backend Evaluation]]
- Jaeger evaluated and eliminated — operational overhead too high for current team size

## Related Projects

- [[Projects/TracingRollout/Charter]]

## Related Resources

- [[OpenTelemetry]]
