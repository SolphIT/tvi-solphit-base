# Timing utilities

Two simple tools to time operations and log durations via `SolphitLogger`:

## `stopwatch(label: str)` (context manager)
```python
from tvi.solphit.base.timing import stopwatch
with stopwatch("indexing"):
    build_index()
```

## `timeit(label: str)` (decorator)
```python
from tvi.solphit.base.timing import timeit
@timeit("scoring")
def score(items):
    return model.score(items)
```

### Notes
- Messages go to logger `tvi.solphit.timing` at `INFO`.
- By default logs use a dedicated handler and do not propagate; see [SolphitLogger](logging-SolphitLogger.md).
