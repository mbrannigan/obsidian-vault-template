# GTD Workflow

> How tasks move through the system. Read this when the system feels off.

*Last updated: 2026-04-16*

---

## The Flow

```
Capture → Inbox → Groom → Project Review → Next → Focus → Work
```

---

## Step 1 — Capture

- Hit the Templater hotkey from anywhere in the vault
- Type the task, hit Enter
- Task lands in `Tasks.md` with a `➕ YYYY-MM-DD` created date and nothing else
- **No decisions at capture time**

---

## Step 2 — Groom (Inbox Processing)

- Open `Inbox.md` — shows all tasks with no metadata beyond created date
- For each task, open it in the Tasks modal and add:
  - `#Project/Name` — required, gets it out of Inbox
  - Due date or scheduled date if known
  - `#People/FullName` if someone is involved
  - `#Area/Name` if it belongs to a cross-cutting area
- Task drops out of Inbox automatically once it has a project tag
- **No priority decisions yet** — that happens in Step 3

---

## Step 3 — Project Review

- Open each active project's `ProjectTasks.md`
- Review all open tasks sorted by priority and date
- Set 🔺 on the single most important task — **one per project only**
- Set 🔼 / 🔽 on others to mark sequence
- Set due or scheduled dates on upcoming tasks
- Do this during weekly review or whenever a project's 🔺 gets completed

---

## Step 4 — Next

- Open `Next.md`
- See one 🔺 task per project — your committed action queue
- Check the **Stalled Projects** section — any project with tasks but no 🔺
- Fix stalled projects by going back to that project's `ProjectTasks.md` and setting a 🔺
- This is your daily starting point

---

## Step 5 — Focus

- From `Next.md`, pick 2–3 tasks you're committing to today
- Open each in the Tasks modal and add `#Status/Focus`
- These are today's commitments — not a wish list

---

## Step 6 — Daily Note

- Open today's daily note (created automatically via Periodic Notes)
- The Focus section queries `#Status/Focus` tasks
- The Scheduled Today section surfaces tasks with today's scheduled date
- This is your cockpit for the day

---

## Step 7 — Working

As you work through tasks, update their status using Tasks plugin symbols:

| Status | Symbol | What to do |
|---|---|---|
| Starting a task | `[/]` | Mark in progress |
| Finished | `[x]` | Mark done — falls out of all views automatically |
| Blocked | `[~]` | Mark on hold + add `#People/FullName` for who's blocking it — surfaces in `Waiting.md` |
| Dropped | `[-]` | Mark cancelled — falls out of all views |

---

## Step 8 — Backlog

- For tasks you want to park but not lose: add `#Status/Someday` in the Tasks modal
- Task disappears from all active views (Inbox, Next, Focus)
- Task surfaces in `Backlog.md` for monthly review
- To resurrect: remove `#Status/Someday`, set a project tag and priority

---

## Warning Signs the System is Drifting

- Inbox has items older than 2 days — groom it
- Stalled Projects section in `Next.md` has entries — fix them
- `#Status/Focus` items from yesterday still open — decide: reschedule or backlog
- A project has no `ProjectTasks.md` — spin one up from the template
- `Waiting.md` has items with no `#People/` tag — add context

---

## File Reference

| File | Purpose |
|---|---|
| `Tasks.md` | Central task pool. All tasks live here. |
| `Inbox.md` | Unprocessed tasks. No metadata beyond created date. |
| `Next.md` | One 🔺 per project + stalled project alerts. |
| `Waiting.md` | Blocked tasks (`[~]` status). |
| `Backlog.md` | Parked tasks (`#Status/Someday`). |
| `Daily/YYYY/MM/YYYY-MM-DD.md` | Daily note. Focus query, scheduled today, log. |
| `Meetings/YYYY/MM/` | Non-project meeting notes. |
| `Projects/<Name>/ProjectTasks.md` | Per-project query view. Review and promote here. |
| `Documents/Tags.md` | Canonical tag reference. Read before tagging. |
| `Documents/Meeting Notes.md` | Meeting note conventions and type reference. |
