# find_files

Glob‑based file discovery with include/exclude patterns.

## Import
```python
from tvi.solphit.base.discovery import find_files
```

## Usage
```python
from pathlib import Path
paths = list(find_files(Path("."), includes=["**/*.py"], excludes=["dist/*"]))
```

## Behavior
- Deduplicates results across patterns.
- Returns files sorted by resolved path.
