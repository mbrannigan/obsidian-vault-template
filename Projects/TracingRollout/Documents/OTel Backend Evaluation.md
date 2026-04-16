# OTel Backend Evaluation

*Created: 2026-03-28 | Author: Your Name*

> Decision document for distributed trace backend selection.
> Outcome: **Grafana Tempo** selected. See Decision section.

---

## Options Evaluated

### Honeycomb

| Attribute | Notes |
|---|---|
| Type | SaaS |
| Cost | ~$2,400/mo at current trace volume estimate |
| Retention | Configurable, up to 90 days on paid tier |
| Query | BubbleUp + Heatmaps — strong for anomaly investigation |
| Ops burden | Minimal — fully managed |
| Integration | Native OTel support |

**Pros:** Zero operational overhead. Excellent query UX. Best-in-class for high-cardinality analysis.

**Cons:** Cost. Data leaves the perimeter (relevant for compliance review). Vendor lock-in on query layer.

---

### Grafana Tempo

| Attribute | Notes |
|---|---|
| Type | Self-hosted (existing Grafana stack) |
| Cost | Infrastructure cost only — est. $180/mo additional EBS/S3 |
| Retention | S3-backed object storage — configurable |
| Query | TraceQL — powerful, lower UX polish than Honeycomb |
| Ops burden | Moderate — team already operates Grafana/Loki |
| Integration | Native OTel support |

**Pros:** Integrates with existing Grafana/Loki/Prometheus stack. No data egress. Low incremental cost.

**Cons:** Team owns operations. TraceQL learning curve.

---

### Jaeger *(eliminated early)*

Spike completed 2026-04-09. Eliminated due to operational overhead (no built-in S3 backend in open-source tier, complex scaling model). Not a fit for current team size.

---

## Decision

**Selected: Grafana Tempo**

**Rationale:** Team already operates the Grafana stack. Incremental cost is minimal vs. Honeycomb SaaS. Data residency is cleaner for future compliance requirements. Operational burden is acceptable given existing Grafana expertise.

**Decided:** 2026-04-11
**Decided by:** Your Name + SRE Lead

---

## Follow-on Actions

- [ ] Tempo deployment config (Helm chart) — tracked in Tasks.md `#Project/TracingRollout`
- [ ] Retention policy approval from Data Team — currently blocked, tracked in Tasks.md
