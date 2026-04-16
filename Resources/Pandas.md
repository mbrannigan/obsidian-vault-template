---
tags:
  - resource
  - "#Type/tool"
source: https://pandas.pydata.org/docs/
author: 
published: 
created: 2026-04-16
areas:
  - "[[Python]]"
---

# Pandas

Python library for data manipulation and analysis. Built on NumPy. Core data structures are `DataFrame` (2D tabular) and `Series` (1D).

## Summary

The go-to tool for working with structured data in Python — loading, cleaning, transforming, and exploring tabular datasets.

## Key Ideas

- `DataFrame` is the primary object — think of it as a spreadsheet in code
- Most operations return a new DataFrame rather than mutating in place
- Indexing has two main flavors: `.loc[]` (label-based) and `.iloc[]` (position-based)
- Method chaining is idiomatic — prefer `df.pipe()` for complex transformations
- Watch out for chained assignment (`df[...][...] = ...`) — use `.loc` instead

## Notes

<!-- Patterns, gotchas, useful snippets -->

## Related Areas

- [[Python]]

## Links

- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Pandas User Guide](https://pandas.pydata.org/docs/user_guide/index.html)
