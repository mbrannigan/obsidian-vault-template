<%*
const moment = tp.date.now("YYYY-MM-DD");
const created = `➕ ${moment}`;

let tasksFile = tp.app.vault.getAbstractFileByPath("Tasks.md");
if (!tasksFile) {
    await tp.app.vault.create("Tasks.md", "---\nnote_type: inbox\nexclude_from_tasks: false\n---\n# Tasks\n\n");
    tasksFile = tp.app.vault.getAbstractFileByPath("Tasks.md");
}

const task = await tp.system.prompt("📥 Capture to Tasks", "", true);
if (!task || task.trim() === "") {
    new Notice("No task entered — nothing captured.");
    return;
}

const content = await tp.app.vault.read(tasksFile);
const newTask = `- [ ] ${task.trim()} ${created}`;
await tp.app.vault.modify(tasksFile, content + newTask + "\n");

new Notice(`✅ Captured: ${task.trim()}`);
%>
