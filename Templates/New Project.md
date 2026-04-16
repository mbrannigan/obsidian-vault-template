<%*
const rawName = await tp.system.prompt("Project name (PascalCase, e.g. MyCoolProject)", "", true);
if (!rawName || rawName.trim() === "") {
    new Notice("No project name entered — aborting.");
    return;
}

const projectName = rawName.trim();
const today = tp.date.now("YYYY-MM-DD");
const projectPath = `Projects/${projectName}`;

const reserved = ["Inbox", "Tasks", "Waiting", "Next", "Backlog", "Templates", "Daily", "Documents", "Projects", "Backup"];
if (reserved.includes(projectName)) {
    new Notice(`⚠️ "${projectName}" is a reserved name — aborting.`);
    return;
}

if (tp.app.vault.getAbstractFileByPath(projectPath)) {
    new Notice(`⚠️ Projects/${projectName} already exists — aborting.`);
    return;
}

function substitute(content) {
    return content
        .replaceAll("ProjectName", projectName)
        .replaceAll("Project Name", projectName)
        .replace(/^project_name: $/m, `project_name: ${projectName}`)
        .replace(/^start_date: $/m, `start_date: ${today}`);
}

const subdirs = [
    projectPath,
    `${projectPath}/Documents`,
    `${projectPath}/Meetings`,
    `${projectPath}/Status`,
    `${projectPath}/Archive`,
];
for (const dir of subdirs) {
    await tp.app.vault.createFolder(dir);
}

const charterBoilerplate = tp.app.vault.getAbstractFileByPath("Projects/_boilerplate/Charter.md");
if (charterBoilerplate) {
    const raw = await tp.app.vault.read(charterBoilerplate);
    await tp.app.vault.create(`${projectPath}/Charter.md`, substitute(raw));
}

const tasksBoilerplate = tp.app.vault.getAbstractFileByPath("Projects/_boilerplate/Project Tasks.md");
if (tasksBoilerplate) {
    const raw = await tp.app.vault.read(tasksBoilerplate);
    await tp.app.vault.create(`${projectPath}/Project Tasks.md`, substitute(raw));
}

const emptyDirs = ["Documents", "Meetings", "Status", "Archive"];
for (const dir of emptyDirs) {
    await tp.app.vault.create(`${projectPath}/${dir}/.gitkeep`, "");
}

new Notice(`✅ Created project: ${projectName}`);

const charterFile = tp.app.vault.getAbstractFileByPath(`${projectPath}/Charter.md`);
if (charterFile) {
    await tp.app.workspace.getLeaf().openFile(charterFile);
}
%>
