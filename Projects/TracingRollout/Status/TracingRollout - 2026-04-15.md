---
date: 2026-04-15
project_name: TracingRollout
note_type: project_status
tags:
  - NoteType/ProjectStatus
---

# TracingRollout — Status Report (2026-04-15)

**Report Date:** April 15, 2026
**Status:** 🟡 `AT RISK`
**Health Signal:** Retention policy approval is blocking backend standup. Risk is timeline, not technical.
**Owner:** Your Name

---

## Executive Summary

Instrumentation work is progressing well — the OTel collector is deployed to staging and checkout service SDK work is in flight. The backend decision (Grafana Tempo) is made and documented. The primary risk is the data team retention policy approval, which has been pending for 3 weeks and is required before Tempo can be stood up in production. If unblocked this week, the project remains on track for the May 30 target.

---

## Task Summary

**In Flight**
```tasks
short mode
not done
tags include #Project/TracingRollout
status.type is IN_PROGRESS
sort by due
```

**To Do**
```tasks
short mode
not done
tags include #Project/TracingRollout
status.type is TODO
sort by due
```

---

## Completed This Period

```tasks
short mode
done
tags include #Project/TracingRollout
done after 2026-04-01
sort by done
```

---

## Next Steps

**Immediate (Next 1–2 Weeks)**
- Resolve retention policy approval — escalate to Engineering Director if not resolved by 2026-04-18
- Complete checkout service OTel SDK instrumentation
- Review SLO thresholds with SRE team

**Upcoming (2+ Weeks)**
- Deploy Grafana Tempo to production
- Instrument auth and payments services
- Write trace triage runbook

---

## Blockers

| # | Description | Impact | Owner | Raised | Status |
|---|-------------|--------|-------|--------|--------|
| B-01 | Data team retention policy approval pending | HIGH — blocks Tempo production deploy | Data Team Lead | 2026-03-28 | `OPEN` |

---

## Risks

| # | Risk | Probability | Impact | Score | Mitigation | Owner |
|---|------|-------------|--------|-------|------------|-------|
| R-01 | Retention policy approval slips past 2026-04-18 | M | H | HIGH | Escalate to Engineering Director | Your Name |
| R-02 | Checkout service instrumentation reveals unexpected OTel SDK compatibility issue | L | M | LOW | Spike available, Platform Engineer on standby | Platform Engineer |

---

## Key Decisions

| Decision | Date | Made By | Notes |
|----------|------|---------|-------|
| Grafana Tempo selected as trace backend | 2026-04-11 | Your Name + SRE Lead | See [[Projects/TracingRollout/Documents/OTel Backend Evaluation]] |
| Jaeger eliminated | 2026-04-03 | Your Name | Operational overhead too high for team size |
| Checkout service as first instrumentation target | 2026-04-03 | Your Name | Highest traffic, best test case |

---

## Supporting Documents

- **Charter:** [[Projects/TracingRollout/Charter]]
- **Backend Decision:** [[Projects/TracingRollout/Documents/OTel Backend Evaluation]]
- **Confluence:** https://confluence.example.com/display/PLAT/TracingRollout
- **Jira Epic:** PLAT-4421

---
*Last Updated: April 15, 2026*
