---
tags:
  - resource
  - "#Type/tool"
  - "#Area/Python"
source: https://pandas.pydata.org/docs/
author: Pandas Development Team
published: 
created: 2026-04-16
areas:
  - Python
---

# Pandas

## Summary

Pandas is the standard Python library for data manipulation and analysis. Built on NumPy, it provides DataFrame and Series structures for working with labeled, tabular data — reading CSVs, transforming columns, grouping, merging, and time series analysis.

## Key Ideas

- **DataFrame** — 2D labeled table. Rows have an index, columns have names. Core data structure for almost everything.
- **Series** — 1D labeled array. A single column or row of a DataFrame.
- **Vectorized operations** — operate on entire columns at once, no Python loops needed. Orders of magnitude faster for large data.
- **`loc` vs `iloc`** — `loc` is label-based, `iloc` is position-based. Never mix them on the same operation.
- **GroupBy** — `df.groupby('col').agg(...)` for split-apply-combine patterns. Works with multiple columns and custom aggregation functions.
- **`read_csv` / `to_csv`** — primary I/O for flat files. Use `dtype=` and `parse_dates=` to avoid type inference surprises.

## Notes

- Avoid chained indexing (`df['a']['b']`) — use `.loc[row, col]` instead to avoid SettingWithCopyWarning
- `df.copy()` explicitly when you need a true copy, not a view
- `df.info()` and `df.describe()` are the first two commands on any new dataset
- For large files: use `chunksize=` in `read_csv` or switch to Polars for significant speedups

## Related Areas

- [[Python]]

## Links

- https://pandas.pydata.org/docs/
- https://pandas.pydata.org/docs/user_guide/indexing.html
