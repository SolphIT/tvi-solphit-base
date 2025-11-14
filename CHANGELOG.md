# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://project adheres to [Semantic Versioning](https://leased]

### Added
- (Planned) Structured logging formatter
- (Planned) JSON log output option
- (Planned) CLI command `solphit-info` for diagnostics

### Changed
- (Planned) Allow configuring multiple handlers via env

### Fixed
- (None)

---

## [0.1.0] - 2025-11-13
### Added
- Base package `tvi-solphit-base` providing `tvi.solphit.base`.
- `SolphitLogger` with:
  - Env-driven config (`TVI_SOLPHIT_LOG_LEVEL`, `TVI_SOLPHIT_LOG_DEST`, `TVI_SOLPHIT_LOG_FILE`, `TVI_SOLPHIT_LOG_FORMAT`).
  - Defaults to stdout, supports file logging.
  - Idempotent setup (no duplicate handlers).
- Initial tests covering stdout and file destination.