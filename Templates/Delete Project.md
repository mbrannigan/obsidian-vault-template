<%*
const rawName = await tp.system.prompt("Project name to delete (PascalCase, e.g. MyCoolProject)", "", true);
if (!rawName || rawName.trim() === "") {
    new Notice("No project name entered — aborting.");
    return;
}

const projectName = rawName.trim();
const projectPath = `Projects/${projectName}`;

const confirm = await tp.system.prompt(`Type DELETE to confirm removal of ${projectPath} and all its tasks`, "", true);
if (confirm !== "DELETE") {
    new Notice("Confirmation failed — aborting.");
    return;
}

const projectFolder = tp.app.vault.getAbstractFileByPath(projectPath);
if (projectFolder) {
    await tp.app.vault.delete(projectFolder, true);
    new Notice(`🗑️ Deleted ${projectPath}`);
} else {
    new Notice(`⚠️ ${projectPath} not found — skipping folder deletion.`);
}

const tasksFile = tp.app.vault.getAbstractFileByPath("Tasks.md");
if (tasksFile) {
    const content = await tp.app.vault.read(tasksFile);
    const tag = `#Project/${projectName}`;
    const lines = content.split("\n");
    const filtered = lines.filter(line => !line.includes(tag));
    const removed = lines.length - filtered.length;
    await tp.app.vault.modify(tasksFile, filtered.join("\n"));
    new Notice(`🧹 Removed ${removed} task(s) tagged ${tag} from Tasks.md`);
} else {
    new Notice("⚠️ Tasks.md not found — skipping task purge.");
}
%>
