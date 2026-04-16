# Obsidian Vault Template

An opinionated Obsidian vault for engineers. PARA-inspired structure, GTD-style task management, meeting notes, learning tracking, and resource capture — all wired together with Dataview, Tasks, and Templater.

---

## What's in Here

| Folder / File | Purpose |
|---|---|
| `Areas/` | Ongoing responsibilities — one note per area, no subfolders |
| `Resources/` | Flat reference notes — articles, tools, concepts, books |
| `Projects/` | Active work with a defined outcome — one folder per project |
| `Learning/` | In-progress structured learning — graduates to `Resources/` when done |
| `Daily/` | Daily notes — auto-created by Periodic Notes |
| `Documents/` | Vault reference docs — read these first |
| `Templates/` | Templater templates — don't edit directly, invoke via hotkey |
| `Tasks.md` | Central task pool — all tasks live here |
| `Inbox.md` | Unprocessed captures — groom daily |
| `Next.md` | One committed next action per project |
| `Waiting.md` | Tasks blocked on someone else |
| `Backlog.md` | Parked tasks — not now, not never |

---

## Read These First

Before you start using the vault, read the docs in `Documents/`:

1. **[[Vault Structure Guide]]** — how the folders work, the PARA mental model, when to use tags vs. wikilinks
2. **[[Tags]]** — canonical tag taxonomy, rules, and examples. Never use a tag not defined here.
3. **[[GTD Workflow]]** — how tasks flow from capture through focus. Read this when the system feels off.
4. **[[Meeting Notes]]** — meeting note conventions and which template to use.

---

## Required Plugins

Install all of these via **Settings → Community Plugins → Browse**:

| Plugin | Why |
|---|---|
| [Dataview](https://obsidian.md/plugins?id=dataview) | Powers the Stalled Projects query in `Next.md` |
| [Tasks](https://obsidian.md/plugins?id=obsidian-tasks-plugin) | Task management — status symbols, priorities, queries throughout |
| [Templater](https://obsidian.md/plugins?id=templater-obsidian) | All templates — required for daily notes, meeting notes, and capture |
| [Periodic Notes](https://obsidian.md/plugins?id=periodic-notes) | Auto-creates daily notes in `Daily/YYYY/MM/` |
| [Calendar](https://obsidian.md/plugins?id=calendar) | Sidebar calendar view for navigating daily notes |
| [Tag Wrangler](https://obsidian.md/plugins?id=tag-wrangler) | Rename and manage tags cleanly |
| [Omnisearch](https://obsidian.md/plugins?id=omnisearch) | Full-text search including note contents |
| [Kanban](https://obsidian.md/plugins?id=obsidian-kanban) | Optional — board view for project tracking |

---

## Setup Steps

### 1. Clone and open

```bash
git clone https://github.com/mbrannigan/obsidian-vault-template.git
```

Open the cloned folder as a vault in Obsidian (**Open folder as vault**).

### 2. Install plugins

Go to **Settings → Community Plugins**, enable community plugins, then install and enable each plugin from the table above.

### 3. Configure Templater

In **Settings → Templater**:
- Set **Template folder location** to `Templates`
- Enable **Trigger Templater on new file creation**
- Assign a hotkey to **Open Insert Template modal** (suggested: `Cmd/Ctrl+Shift+T`)
- Assign a hotkey to **Create new note from template** for the Capture to Inbox template (suggested: `Cmd/Ctrl+Shift+C`)

### 4. Configure Periodic Notes

In **Settings → Periodic Notes**:
- Enable **Daily Notes**
- Set **Daily Note Template** to `Templates/Daily Note`
- Set **Daily Note Folder** to `Daily`

### 5. Personalize the templates

A few templates contain placeholder text you should update before use:

- **`Templates/1-1.md`** — replace `Your Name` in the `attendees` frontmatter with your name
- **`Templates/Weekly Alignment.md`** — same as above
- **`Templates/Project Status Report.md`** — replace `<your name>` in the **Owner** field
- **`Templates/Meeting.md`** — add your name to the `attendees` frontmatter default

The manager name in `1-1.md` and `Weekly Alignment.md` is prompted at note creation time — no need to hardcode it.

### 6. Create your first Area

Use **Templater → Templates/Area.md** to create your first area note. Good starting areas for engineers: `Observability`, `Security`, `On-Call`, `Python`, `Platform`, `Vendor`.

### 7. Start capturing

Use your capture hotkey (Step 3) to fire tasks to `Tasks.md` from anywhere in the vault. Groom `Inbox.md` each morning.

---

## Theme

This vault ships with the [GitHub Theme](https://github.com/krios2146/obsidian-theme-github). Install it via **Settings → Appearance → Themes → Manage** and search for "GitHub Theme".

---

## License

MIT. Use it, fork it, make it yours.
