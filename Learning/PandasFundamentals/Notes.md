---
tags:
  - learning
created: 2026-04-14
---

# Pandas Fundamentals — Notes

## 2026-04-14

- `pd.DataFrame` vs `pd.Series` — DataFrame is a 2D labeled structure, Series is a single column
- Index is just a label for rows — can be integers, strings, or DatetimeIndex
- `.iloc[]` for positional access, `.loc[]` for label-based access — don't mix them
- `df.head()`, `df.info()`, `df.describe()` are the first three things you run on any new DataFrame

## 2026-04-15

- Boolean indexing: `df[df['col'] > value]` — returns a filtered DataFrame, not a copy by default
- `.copy()` explicitly when you want a true copy to avoid SettingWithCopyWarning
- `df.dropna()` vs `df.fillna()` — prefer `fillna` with a sensible default unless the row is truly unusable
- Column assignment: `df['new_col'] = df['a'] + df['b']` — vectorized, no loop needed

## 2026-04-16

- `df.groupby('col').agg({'other_col': 'sum'})` — group and aggregate in one step
- Multiple aggregations: `.agg(['mean', 'sum', 'count'])` or a dict for per-column aggregations
- `groupby` returns a GroupBy object — call `.agg()`, `.transform()`, or `.apply()` on it
