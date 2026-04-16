---
tags:
  - resource
  - "#Type/tool"
  - "#Area/Observability"
source: https://opentelemetry.io/docs/
author: OpenTelemetry Authors
published: 
created: 2026-03-15
areas:
  - Observability
---

# OpenTelemetry

## Summary

OpenTelemetry (OTel) is a vendor-neutral observability framework for generating, collecting, and exporting telemetry data — traces, metrics, and logs. It is the CNCF standard for instrumentation and is supported natively by most modern APM and observability backends.

## Key Ideas

- **Three signals:** Traces (request flows across services), Metrics (numeric measurements over time), Logs (structured event records). OTel handles all three under one SDK.
- **Vendor-neutral:** Instrument once, route to any backend (Grafana Tempo, Honeycomb, Datadog, Jaeger, etc.) via the OTel Collector.
- **OTel Collector:** A standalone proxy/agent that receives telemetry from services, processes it (sampling, filtering, enrichment), and exports to one or more backends. Decouples instrumentation from backend choice.
- **Context propagation:** Traces are linked across service boundaries via propagated context (W3C TraceContext standard). Requires all services in a call chain to propagate headers correctly.
- **Sampling:** Head-based (decision at trace start) vs. tail-based (decision after full trace is collected). Tail-based requires a stateful collector and is more complex but more accurate for capturing errors.

## Notes

- Python SDK: `opentelemetry-sdk`, `opentelemetry-api`, auto-instrumentation via `opentelemetry-instrument`
- Collector config lives in `otel-collector-config.yaml` — processors, receivers, exporters
- W3C TraceContext (`traceparent` header) is the propagation standard — ensure all HTTP clients pass it through

## Related Areas

- [[Observability]]

## Links

- https://opentelemetry.io/docs/
- https://opentelemetry.io/docs/collector/
