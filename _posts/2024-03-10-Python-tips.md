---
layout: post
title: Python Tips & Tricks
subtitle: Snippets I use almost every day
tags: [python, dev, tools]
comments: true
---

A collection of Python patterns I keep coming back to.

## Quick file reading with pathlib

```python
from pathlib import Path

text = Path("data.txt").read_text(encoding="utf-8")
lines = Path("data.txt").read_text().splitlines()
```

Much cleaner than `open()` + `read()` for simple cases.

## Flatten a nested list

```python
nested = [[1, 2], [3, 4], [5]]
flat = [x for sub in nested for x in sub]
# [1, 2, 3, 4, 5]
```

## Default dict for grouping

```python
from collections import defaultdict

grouped = defaultdict(list)
for item in items:
    grouped[item["category"]].append(item)
```

## Run a quick HTTP server

```bash
python -m http.server 8080
```

Useful when you need to serve local files fast.

{: .box-note}
**Note:** These snippets target Python 3.10+.
