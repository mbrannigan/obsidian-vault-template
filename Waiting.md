# Waiting

> Tasks blocked on someone else.
> Set the task status to `[~]` and add `#People/FullName` to indicate who is blocking it.
> See `Documents/Tags.md` for full tag reference.

```tasks
not done
filter by function task.status.symbol == '~'
group by tags
sort by due date
show backlink
short mode
```
