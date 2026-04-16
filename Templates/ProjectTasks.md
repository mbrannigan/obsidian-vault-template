<%*
const projectName = await tp.system.prompt("Project tag name (e.g. ConsulRetirement)", "", true);
if (!projectName || projectName.trim() === "") {
    new Notice("No project name entered — aborting.");
    const thisFile = tp.app.vault.getAbstractFileByPath(tp.file.path(true));
    if (thisFile) await tp.app.vault.delete(thisFile);
    return;
}

const tag = `#Project/${projectName.trim()}`;
const targetPath = `Projects/${projectName.trim()}/ProjectTasks.md`;

const content = `# ${projectName.trim()} — Task View

> Query view into Tasks.md. Tasks are not stored here — they live in Tasks.md.
> Review this file during weekly review or morning processing.
> Promote one task to 🔺 to surface it in Next.md.
>
> Tag convention: \`Documents/Tags.md\`

---

## All Open Tasks

\`\`\`tasks
not done
tags include ${tag}
sort by priority
sort by due date
sort by scheduled date
\`\`\`

---

## 🔺 Next (this project)

\`\`\`tasks
not done
tags include ${tag}
priority is highest
\`\`\`

---

## ⏳ Waiting (this project)

\`\`\`tasks
status.symbol is ~
tags include ${tag}
group by tags
\`\`\`

---

## Completed

\`\`\`tasks
done
tags include ${tag}
sort by done date
\`\`\`
`;

const folderPath = `Projects/${projectName.trim()}`;
const existingFolder = tp.app.vault.getAbstractFileByPath(folderPath);
if (!existingFolder) {
    await tp.app.vault.createFolder(folderPath);
}

const existing = tp.app.vault.getAbstractFileByPath(targetPath);
if (existing) {
    new Notice(`ProjectTasks.md already exists for ${projectName.trim()}`);
} else {
    await tp.app.vault.create(targetPath, content);
    new Notice(`✅ Created ProjectTasks.md for ${projectName.trim()}`);
}

const thisFile = tp.app.vault.getAbstractFileByPath(tp.file.path(true));
if (thisFile) await tp.app.vault.delete(thisFile);
%>
