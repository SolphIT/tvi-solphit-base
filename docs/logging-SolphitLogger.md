# SolphitLogger

`SolphitLogger` provides a simple, env‑configurable logger with stdout or file destination. It is idempotent: calling `get_logger` multiple times for the same name will not add duplicate handlers.

## Import
```python
from tvi.solphit.base.logging import SolphitLogger
```

## Usage
```python
log = SolphitLogger.get_logger("tvi.solphit.demo")
log.info("message")
```

## Configuration
- `TVI_SOLPHIT_LOG_LEVEL` (default: `INFO`)
- `TVI_SOLPHIT_LOG_DEST`  (default: `stdout`, set to `file` for file logging)
- `TVI_SOLPHIT_LOG_FILE`  (default: `solphit.log`)
- `TVI_SOLPHIT_LOG_FORMAT` (default: `%(asctime)s %(levelname)s %(name)s %(message)s`)

## API
```python
class SolphitLogger:
    @classmethod
    def get_logger(
        cls,
        name: str = "tvi.solphit",
        *,
        level: str | None = None,
        dest: str | None = None,
        file_path: str | None = None,
        fmt: str | None = None,
        propagate: bool = False,
    ) -> logging.Logger: ...
```

## Notes
- Handlers are attached once per logger name (idempotent pattern).
- `propagate=False` by default to avoid duplicate logs in applications that configure the root logger.
