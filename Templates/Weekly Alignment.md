---
date: <% tp.date.now('YYYY-MM-DD') %>
attendees:
  - Your Name
type: alignment
project: 
tags:
  - NoteType/Meeting
---
<%*
const date = tp.date.now('YYYY-MM-DD');
const manager = await tp.system.prompt('Manager name (e.g. "Your Manager")');
const year = tp.date.now('YYYY');
const month = tp.date.now('MM');
const targetFolder = `Meetings/${year}/${month}`;
const targetFile = `${date} - ${manager} - Weekly Alignment`;
await app.vault.createFolder(targetFolder).catch(() => {});
await tp.file.move(`${targetFolder}/${targetFile}`);
%>
# <% tp.date.now('YYYY-MM-DD') %> - <% manager %> - Weekly Alignment

> Weekly alignment. Week plan, blockers, and updates from manager.

## What I'm Working On This Week

- 

## Blockers


## Things They Need to Know


## Updates from Manager


## Notes


## Next Steps

> Use the capture hotkey to fire tasks directly to `Tasks.md`. Note any follow-ups here for reference only.
