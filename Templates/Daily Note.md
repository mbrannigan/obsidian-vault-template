---
date: <% tp.date.now('YYYY-MM-DD') %>
day: <% tp.date.now('dddd') %>
tags:
  - NoteType/Daily
note_type: daily
exclude_from_tasks: true
---
<%*
const year = tp.date.now("YYYY");
const month = tp.date.now("MM");
const day = tp.date.now("DD");

const targetFolder = `Daily/${year}/${month}`;
const targetFile = `${year}-${month}-${day}`;
const targetPath = `${targetFolder}/${targetFile}`;

await app.vault.createFolder(targetFolder).catch(() => {});
await tp.file.move(targetPath);
%>
# 📅 <% tp.date.now("dddd, MMMM D, YYYY") %>

---

## 🧠 Strategic Activation

- [ ] Open `Inbox.md` — groom any unprocessed tasks
- [ ] Open `Next.md` — review 🔺 items, fix any stalled projects
- [ ] Tag today's 2–3 commitments with `#Status/Focus`
- [ ] Start one high-impact task

---

## 🎯 Focus

```tasks
short mode
not done
tags include #Status/Focus
sort by priority
```

---

## 🗃️ Scheduled Today

```tasks
short mode
not done
scheduled on <% tp.date.now('YYYY-MM-DD') %>
sort by priority
```

---

## 📝 Notes / Log

> Interruptions, quick captures, decisions, context. Not tasks — those go to `Tasks.md` via the capture hotkey.

