---
tags:
  - resource
  - "#Type/tool"
source: https://opentelemetry.io/docs/
author: 
published: 
created: 2026-04-16
areas:
  - "[[Observability]]"
---

# OpenTelemetry

Vendor-neutral observability framework for instrumenting, generating, collecting, and exporting telemetry data (metrics, logs, traces).

## Summary

The emerging standard for instrumentation across languages and platforms. OTel gives you a single consistent API regardless of which backend (Datadog, Honeycomb, Jaeger, Prometheus, etc.) you send data to.

## Key Ideas

- Three pillars: traces (request flow), metrics (numeric measurements), logs (events)
- The Collector is a standalone proxy that receives, processes, and exports telemetry — decouple your app from your backend
- Auto-instrumentation libraries exist for most major frameworks — start there before writing custom spans
- Context propagation is the mechanism that ties distributed traces together across service boundaries
- Semantic conventions define standard attribute names — use them for consistent querying across services

## Notes

<!-- Patterns, gotchas, integration notes -->

## Related Areas

- [[Observability]]

## Links

- [OpenTelemetry Docs](https://opentelemetry.io/docs/)
- [OTel Collector](https://opentelemetry.io/docs/collector/)
