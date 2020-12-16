# Changelog

All notable changes to this project are documented here. The format is based
on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and this project
adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.0] - 2026-08-31

### Added

- **Rust engine (`cairn`)** — content-addressed store with hashing,
  store/restore of output manifests, and integrity verification.
  - `hash`, `key`, `store`, `restore`, `verify`, `show` subcommands.
  - Standard-library-only implementation, including a small canonical JSON
    reader/writer.
- **Go wrapper (`cairn-run`)** — cache-aware command execution.
  - Cache HIT restores declared outputs; MISS runs the command and captures
    outputs. Failed commands are not cached.
  - `hash` and `version` helper subcommands.
- **Shared format v1** — FNV-1a 64-bit content hashing, canonical cache-key
  stream, and canonical manifest JSON, documented in `docs/FORMAT.md` and
  reproduced byte-for-byte by both tools.
- Cross-language reference-vector tests guarding digest and key parity.
- Demo scripts (`examples/demo.sh`, `examples/demo.ps1`), Makefile, and GitHub
  Actions CI (Rust, Go, and an interop job running the demo).

### Notes

- The hash is intentionally **non-cryptographic**; Cairn is a build cache, not
  a security boundary. See `docs/FORMAT.md` for the rationale.

[0.1.0]: https://github.com/example/cairn/releases/tag/v0.1.0

<!-- draft note 121 -->
