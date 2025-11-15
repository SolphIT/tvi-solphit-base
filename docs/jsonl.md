# JSONL helpers

Thin wrappers for newline‑delimited JSON datasets.

## Import
```python
from tvi.solphit.base.jsonl import write_jsonl, read_jsonl
```

## Usage
```python
from pathlib import Path
records = [{"id": 1, "txt": "hello"}, {"id": 2, "txt": "world"}]
write_jsonl(Path("records.jsonl"), records)
rows = list(read_jsonl(Path("records.jsonl")))
```

## Notes
- Uses UTF‑8.
- Skips empty lines on read.
