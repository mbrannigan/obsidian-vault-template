---
tags:
  - learning
created: 2026-04-16
---

# Pandas Fundamentals — Notes

## 2026-04-16

- A `DataFrame` is a 2D labeled data structure — rows and columns, like a spreadsheet but in code
- A `Series` is a single column — a 1D labeled array
- Creating a DataFrame from a dict: `pd.DataFrame({'col1': [1, 2], 'col2': [3, 4]})`
- `.head()` and `.tail()` for quick inspection
- `.info()` gives dtypes and null counts — always run this first on a new dataset
- `.describe()` gives summary statistics for numeric columns

### Indexing

- `.loc[]` — label-based: `df.loc[0, 'col1']`
- `.iloc[]` — position-based: `df.iloc[0, 0]`
- Don't use chained indexing (`df['col'][0]`) — use `.loc` or `.iloc` to avoid the SettingWithCopyWarning

### Loading Data

- `pd.read_csv('file.csv')` — most common
- `pd.read_json()`, `pd.read_parquet()` also useful
- Always check `df.shape` after loading to confirm row/column counts
