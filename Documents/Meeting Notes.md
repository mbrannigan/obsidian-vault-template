# Meeting Notes

> How to create and structure meeting notes in this vault.
> Read this before creating a new meeting type.

*Last updated: 2026-04-16*

---

## Where Meeting Notes Live

All meeting notes go in `Meetings/YYYY/MM/`. Templates handle folder creation automatically.

**Filename pattern:** `YYYY-MM-DD - Person or Group Name.md`

Examples:
```
Meetings/2026/04/2026-04-16 - Your Manager.md
Meetings/2026/04/2026-04-16 - Your Manager - Weekly Alignment.md
Meetings/2026/04/2026-04-16 - Security Tabletop Exercise.md
```

---

## Creating a Meeting Note

Use the Templater hotkey and select the appropriate template:

| Meeting | Template |
|---|---|
| Bi-weekly 1:1 with your manager | `Templates/1-1.md` |
| Weekly alignment with your manager | `Templates/Weekly Alignment.md` |
| All other meetings | `Templates/Meeting.md` |

Both `1-1.md` and `Weekly Alignment.md` prompt for the manager name at creation.

---

## Note Structure

| Section | Purpose |
|---|---|
| **Topic & Objective** | Why this meeting exists. One line. Pre-filled for recurring meetings. |
| **Agenda** | Items on the agenda going in. |
| **Notes** | Free-form capture during the meeting. |
| **Decisions** | Explicit decisions made. Omit if none. |
| **Next Steps** | Reference only — tasks fire to `Tasks.md` via the capture hotkey mid-meeting. |

---

## Frontmatter Fields

```yaml
date: YYYY-MM-DD           # Meeting date
attendees:                 # List of attendees (First Last format)
  - Your Name
type: 1-1                  # See meeting types below
project:                   # Optional — link to Projects/<Name> if relevant
tags:
  - NoteType/Meeting
```

---

## Meeting Types

| Type | Description | Template |
|---|---|---|
| `1-1` | Bi-weekly 1:1 with your manager | `1-1.md` |
| `alignment` | Weekly alignment — week plan, status, updates | `Weekly Alignment.md` or `Meeting.md` |
| `ad-hoc` | Unscheduled or informal sync | `Meeting.md` |
| `security` | Security team meetings, tabletops, monthly status | `Meeting.md` |
| `project` | Project kickoff, working session, status review | `Meeting.md` |
| `cross-team` | Meetings with other teams that don't fit above | `Meeting.md` |

---

## Action Items

Do **not** write action items into the meeting note as tasks. Use the capture hotkey during the meeting to fire tasks directly to `Tasks.md`. The **Next Steps** section is for reference notes only.

---

## Standup

The daily standup does **not** get a meeting note. Log your standup update in the **Notes / Log** section of your daily note instead.
