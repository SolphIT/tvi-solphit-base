# Changelog
All notable changes to this project will be documented in this file.  
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).  
This project adheres to [Semantic Versioning](https://semver.org/).

## [0.2.0] - 2025-11-15

### Added
- **Utility modules**
  - `fs.py`: `atomic_write_text` for safe, atomic file writes (creates parent directories).
  - `jsonl.py`: `write_jsonl`, `read_jsonl` for newline-delimited JSON.
  - `discovery.py`: `find_files` with include/exclude glob patterns.
  - `timing.py`: `stopwatch` context manager and `timeit` decorator for execution timing.
- **Argument parsing base**
  - Enhanced `arg_parsed.py` base (`ArgParsed` with hooks: `register_arguments`, `validate_args`, `from_args`, plus helpers: `comma_list`, `key_value_pair`, `existing_path`).
- **Tests**
  - Comprehensive pytest suite for `fs`, `jsonl`, `discovery`, `logging`, `timing`, `arg_parsed` using `tmp_path`, `monkeypatch`, and targeted log capture patterns.
- **Docs**
  - New `docs/` with per-feature pages linked from the README.
- **Tooling**
  - `pytest.ini` for `src/` layout; optional GitHub Actions CI workflow (see `.github/workflows/ci.yml`).

### Changed
- Clarified logging usage patterns in tests vs. production; `SolphitLogger` remains idempotent, non-propagating by default, with stdout/file handlers.

### Fixed
- N/A

---

## [0.1.0] - 2025-11-13

### Added
- Base package `tvi-solphit-base` providing `tvi.solphit.base`.
- `SolphitLogger` with:
  - Env-driven config (`TVI_SOLPHIT_LOG_LEVEL`, `TVI_SOLPHIT_LOG_DEST`, `TVI_SOLPHIT_LOG_FILE`, `TVI_SOLPHIT_LOG_FORMAT`).
  - Defaults to stdout; supports file logging.
  - Idempotent setup (no duplicate handlers).
- Initial tests covering stdout and file destinations.
