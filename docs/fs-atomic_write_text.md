# atomic_write_text

Atomic, safe writes to a target file. Uses a temporary file in the same directory and `os.replace` for atomicity on POSIX.

## Import
```python
from pathlib import Path
from tvi.solphit.base.fs import atomic_write_text
```

## Usage
```python
target = Path("out/data.txt")
atomic_write_text(target, "payload")
```

## Behavior
- Creates parent directories automatically.
- Overwrites the target atomically (no partial files on crash).
