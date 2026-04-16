# Tag Taxonomy

> Canonical tag reference for this vault.
> Read this before writing or suggesting any tags.
> Never use a tag not defined here.
> If an unknown tag appears, add it here first or ask before using it.

*Last updated: 2026-04-16*

---

## Tag Roots

| Root | Purpose |
|---|---|
| `#Type/` | What kind of note this is |
| `#NoteType/` | System classification for structured note types |
| `#Project/` | Discrete work with an end state |
| `#People/` | A person associated with a task or note |
| `#Area/` | Ongoing responsibility with no end state |
| `#Status/` | Task state beyond what the Tasks plugin tracks natively |

---

## `#Type/` — Note Classification

Format: `#Type/name`

Describes what kind of note this is. Used on Resource notes. Not used on tasks.

| Tag | Meaning |
|---|---|
| `#Type/clipping` | Article or web page captured for reference |
| `#Type/book` | Book notes or summary |
| `#Type/concept` | A concept, mental model, or framework |
| `#Type/tool` | A specific tool, library, or technology |
| `#Type/reference` | General reference material that doesn't fit the above |

**`#Type/` and `#Area/` stack.** A note can be both `#Type/clipping` and `#Area/Python` — type describes what the note is, area describes what responsibility it informs.

**Topics are wikilinks, not tags.** Don't create tags for subjects like `#pandas` or `#kafka`. Instead, link to the relevant Resource note (e.g., `[[Pandas]]`) in the note body. The graph and backlinks handle topic connections.

---

## `#NoteType/` — System Note Classification

Format: `#NoteType/name`

Used internally by templates to classify structured note types. Applied automatically — do not add manually.

| Tag | Applied by | Meaning |
|---|---|---|
| `#NoteType/Meeting` | All meeting templates | Any meeting note |
| `#NoteType/ProjectCharter` | Charter boilerplate | Project charter / index |
| `#NoteType/ProjectStatus` | Project Status Report template | Status report note |
| `#NoteType/Daily` | Daily Note template | Daily note |

---

## `#Project/` — Active Projects

Format: `#Project/PascalCaseName`

Every task in `Tasks.md` must have exactly one `#Project/` tag.
Project names must match the folder name under `Projects/`.

Examples:
- `#Project/ProjectAlpha`
- `#Project/PlatformMigration`
- `#Project/VendorEvaluation`

---

## `#People/` — People

Format: `#People/FirstNameLastName`

Use on tasks to indicate a person is associated — blocked on them, delegated to them, or relevant to the work.
Pair with the Tasks plugin `[~]` on-hold status when a task is blocked on that person.

Examples:
- `#People/FirstLast`

---

## `#Area/` — Areas of Responsibility

Format: `#Area/PascalCaseName`

Ongoing responsibilities with no end state. Cross-cutting themes that span multiple projects.
Use on tasks and notes to indicate the area they belong to.

Examples:
- `#Area/Security`
- `#Area/Observability`
- `#Area/Vendor`
- `#Area/Python`

---

## `#Status/` — Task Status

Format: `#Status/Name`

Only two status tags are used. All other task states (done, in progress, on hold/waiting) are handled
natively by the Tasks plugin status symbols — do not create tags for those.

| Tag | Meaning | Query file |
|---|---|---|
| `#Status/Focus` | Hand-picked for today's work. Set during morning processing. | Daily note |
| `#Status/Someday` | Not committed, not forgotten. Review monthly. | `Backlog.md` |

---

## Tasks Plugin Status Symbols

These are **not tags** — they are Tasks plugin native statuses. Documented here for reference.

| Symbol | Meaning | Notes |
|---|---|---|
| `[ ]` | Open | Default. Unstarted task. |
| `[x]` | Done | Completed. Falls out of all active queries. |
| `[/]` | In Progress | Actively being worked. |
| `[~]` | On Hold / Waiting | Blocked. Pair with `#People/FullName` to indicate who. Surfaces in `Waiting.md`. |
| `[-]` | Cancelled | Dropped. Falls out of all active queries. |

---

## Priority Symbols (Tasks Plugin)

These are **not tags** — Tasks plugin native priority flags.

| Symbol | Meaning | Usage |
|---|---|---|
| `🔺` | Highest | The **Next** item for this project. One per project at a time. |
| `🔼` | High | Second in line. Will become Next when 🔺 is done. |
| `🔽` | Medium | Third priority and below. |
| `⏬` | Low | Backlog-level priority. |
| (none) | Normal | Ungroomed. Will appear in Inbox query. |

---

## Rules

- Every task in `Tasks.md` must have exactly one `#Project/` tag
- `#People/` is optional but required when a task is set to `[~]` on hold
- `#Status/Focus` is set during morning processing, removed (or task completed) by end of day
- `#Status/Someday` removes a task from all active views — it will only appear in `Backlog.md`
- Never stack two `#Status/` tags on the same task
- Tag names are PascalCase after the `/` — no spaces, no abbreviations
- `#Type/` is for Resource notes only — not for tasks
- `#NoteType/` is applied by templates automatically — do not add manually
- Topics (pandas, kafka, etc.) are wikilinks, not tags
