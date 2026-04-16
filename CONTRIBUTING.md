# Contributing

Thanks for wanting to improve this template. This guide covers how to set up the vault locally for development, what to keep out of commits, and how to submit changes.

---

## Local Setup

### 1. Fork and clone

Fork the repo on GitHub, then clone your fork:

```bash
git clone https://github.com/your-username/obsidian-vault-template.git
cd obsidian-vault-template
```

### 2. Open as a vault

Open Obsidian, choose **Open folder as vault**, and select the cloned directory. Obsidian will load the existing `.obsidian/` config — plugins, appearance, and graph settings are all tracked and will be present.

### 3. Install plugins

Community plugins are listed in `.obsidian/community-plugins.json` but their code is not tracked. You'll need to install them manually:

**Settings → Community Plugins → Browse**, then install:

- Dataview
- Tasks
- Templater
- Periodic Notes
- Calendar
- Tag Wrangler
- Omnisearch
- Kanban (optional)

See the README for configuration steps for Templater, Periodic Notes, and the Tasks plugin custom statuses.

### 4. Configure Templater

Point Templater at the `Templates/` folder and set up your capture hotkey before working with any templates. See README Step 4.

---

## What Gets Committed

This repo tracks:

| Path | Why tracked |
|---|---|
| `.obsidian/app.json` | Core editor settings |
| `.obsidian/appearance.json` | Theme selection |
| `.obsidian/community-plugins.json` | Plugin list (not plugin code) |
| `.obsidian/core-plugins.json` | Core plugin toggles |
| `.obsidian/graph.json` | Graph view settings |
| `.obsidian/types.json` | Property type definitions |
| All `.md` files | Vault content and templates |
| `.gitignore` | Exclusion rules |

---

## What Never Gets Committed

### Already excluded by `.gitignore`

- `.obsidian/workspace.json` and `workspace-mobile.json` — your open tabs, pane layout, cursor positions. These are personal state, not config.
- `.obsidian/plugins/*/cache/` and `data-cache/` — plugin runtime caches.
- `.DS_Store`, `Thumbs.db` — OS junk.

### Your personal content — you must handle this

The `.gitignore` excludes workspace state, but it does **not** automatically exclude notes you write while developing. Before committing, check `git status` and make sure you haven't staged:

- Any real tasks, daily notes, or meeting notes you created while testing
- Any real project folders under `Projects/` (other than `_boilerplate` and `TracingRollout`)
- Any personal area or resource notes
- Any edits to `Tasks.md` beyond the example tasks

**The safest approach:** work in a branch, check `git diff --staged` before every commit, and only stage files you intentionally changed.

### Plugin data files

Some plugins write personal config to `.obsidian/plugins/<plugin>/data.json` — for example, Templater stores your hotkey bindings there. These files are not currently gitignored globally because some (like Tasks `data.json`) contain settings worth sharing. If you notice a plugin writing personal data (API keys, personal paths, etc.) to its `data.json`, add it to `.gitignore` and note it in your PR.

---

## Making Changes

### Branches

Work on a branch, not directly on `main`:

```bash
git checkout -b your-branch-name
```

Good branch names: `add-weekly-review-template`, `fix-inbox-query`, `update-contributing-docs`.

### What's in scope

Good contributions:

- New or improved templates in `Templates/`
- Fixes to queries in dashboard files (`Inbox.md`, `Next.md`, `Waiting.md`, `Backlog.md`)
- Improvements to `Documents/` reference docs
- Additions or corrections to `Documents/Tags.md`
- New or improved example content (must be anonymized — no real names, companies, or internal tooling)
- `.obsidian/` config improvements (tracked files only — see table above)
- `.gitignore` additions for files that should be excluded

Out of scope:

- Personal vault content (real projects, real tasks, real meeting notes)
- Changes that break the example project's internal consistency (wikilinks, task tags, etc.)
- New top-level folders without a strong reason — the structure is intentionally minimal

### Anonymization rules

All example content must be free of:

- Real names → use `Your Name`, `SRE Lead`, `Data Team Lead`, `Engineering Director`
- Real company names, internal tool names, or Jira/Confluence URLs → use `example.com` placeholders
- Real project names → use generic but realistic names like `TracingRollout`, `PlatformMigration`
- Real tags containing personal identifiers

When in doubt: would someone reading this on GitHub be able to identify a real person, team, or company? If yes, anonymize it.

### Commit messages

Keep them short and specific:

```
Add weekly review template
Fix Waiting.md query to use status.symbol
Update Tags.md — document NoteType/ root
Add CONTRIBUTING.md
```

No issue numbers required for small fixes. For larger changes, reference the issue if one exists.

---

## Submitting a Pull Request

1. Push your branch to your fork
2. Open a PR against `main` on this repo
3. Describe what changed and why — a sentence or two is fine for small changes, more for significant ones
4. If you changed example content, confirm in the PR description that it's been anonymized

PRs that touch `.obsidian/` config files should explain what the setting change does and why it's an improvement for new users.

---

## Questions

Open an issue if you're unsure whether something is in scope before building it. That's the right place to propose structural changes or new conventions before writing the code.
