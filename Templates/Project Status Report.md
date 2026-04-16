---
date: <% tp.date.now('YYYY-MM-DD') %>
project_name: <% tp.file.folder(true).split('/').slice(-2, -1)[0] %>
note_type: project_status
tags:
  - NoteType/ProjectStatus
---
<%*
const projectName = tp.file.folder(true).split('/').slice(-2, -1)[0];
const date = tp.date.now('YYYY-MM-DD');
await tp.file.rename(`${projectName} - ${date}`);
%>
# <% tp.file.folder(true).split('/').slice(-2, -1)[0] %> — Status Report (<% tp.date.now('YYYY-MM-DD') %>)

**Report Date:** <% tp.date.now('MMMM D, YYYY') %>
**Status:** 🟢 `ON TRACK` / 🟡 `AT RISK` / 🔴 `OFF TRACK`
**Health Signal:**
**Owner:** <your name>

---

## Executive Summary

*2–4 sentences on overall project health, what's moving, and what's blocked.*

---

## Task Summary

**In Flight**
```tasks
short mode
not done
tags include #Project/<% tp.file.folder(true).split('/').slice(-2, -1)[0] %>
status.type is IN_PROGRESS
sort by due
```

**To Do**
```tasks
short mode
not done
tags include #Project/<% tp.file.folder(true).split('/').slice(-2, -1)[0] %>
status.type is TODO
sort by due
```

---

## Completed This Period

```tasks
short mode
done
tags include #Project/<% tp.file.folder(true).split('/').slice(-2, -1)[0] %>
done after <% tp.date.now('YYYY-MM-DD', -14) %>
sort by done
```

---

## Next Steps

**Immediate (Next 1–2 Weeks)**
- 

**Upcoming (2+ Weeks)**
- 

---

## Blockers

| # | Description | Impact | Owner | Raised | Status |
|---|-------------|--------|-------|--------|--------|
| B-01 | | `HIGH` / `MEDIUM` / `LOW` | | | `OPEN` / `RESOLVED` |

---

## Risks

| # | Risk | Probability | Impact | Score | Mitigation | Owner |
|---|------|-------------|--------|-------|------------|-------|
| R-01 | | `H/M/L` | `H/M/L` | | | |

*Score = Probability × Impact → HIGH (7–9) MEDIUM (4–6) LOW (1–3)*

---

## Dependencies

| Dependency | Type | Dependent On | Owner | Status | Due | Impact if Delayed |
|------------|------|-------------|-------|--------|-----|-------------------|
| | `Internal` / `External` / `Vendor` | | | | | |

---

## Key Decisions

| Decision | Date | Made By | Notes |
|----------|------|---------|-------|
| | | | |

---

## Decisions Required

| Decision | Priority | Stakeholders | Due | Status |
|----------|----------|-------------|-----|--------|
| | `HIGH` / `MEDIUM` | | | `OPEN` |

---

## Notes

*Additional context, observations, or things that don't fit elsewhere.*

---

## Supporting Documents

- **Charter:** [[Projects/<ProjectName>/Charter]]
- **Architecture / ADRs:** 
- **Confluence:** 
- **Jira Epic:** 

---
*Last Updated: <% tp.date.now('MMMM D, YYYY') %>*
