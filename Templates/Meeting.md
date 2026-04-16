---
date: <% tp.date.now('YYYY-MM-DD') %>
attendees:
  - 
type: ad-hoc
project: 
tags:
  - NoteType/Meeting
---

<%*
const date = tp.date.now('YYYY-MM-DD');
const title = await tp.system.prompt('Meeting title (e.g. "Weekly Sync")');
const year = tp.date.now('YYYY');
const month = tp.date.now('MM');
const targetFolder = `Meetings/${year}/${month}`;
const targetFile = `${date} - ${title}`;
await app.vault.createFolder(targetFolder).catch(() => {});
await tp.file.move(`${targetFolder}/${targetFile}`);
%>

# <% tp.date.now('YYYY-MM-DD') %> - <% title %>

## Topic & Objective


## Agenda

- 

## Notes


## Decisions


## Next Steps

> Use the capture hotkey to fire tasks directly to `Tasks.md`. Note any follow-ups here for reference only.
