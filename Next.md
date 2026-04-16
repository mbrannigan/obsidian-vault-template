# Next

> One committed next action per project.
> Promote a new 🔺 when you complete one. Clear stalled projects during weekly review.

---

## 🔺 Next Actions

```tasks
not done
priority is highest
group by tags
show backlink
```

---

## ⚠️ Stalled Projects

> Projects with open tasks but no 🔺 identified.

```dataview
TABLE WITHOUT ID "[[Projects/" + tag + "/Project Tasks|" + tag + "]]" AS "Project", length(rows) AS "Tasks Waiting"
FROM "Tasks.md"
FLATTEN file.tasks AS T
WHERE !T.completed AND any(T.tags, (t) => startswith(t, "#Project/"))
FLATTEN replace(filter(T.tags, (t) => startswith(t, "#Project/"))[0], "#Project/", "") AS tag
GROUP BY tag
WHERE none(rows.T.priority, (p) => p = "highest")
```
