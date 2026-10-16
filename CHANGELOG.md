# Changelog

## [Unreleased]

## [v0.2.1] - 2026-10-16

### Changed

- Publish the module under `github.com/cautem/quarshell-proto`; earlier tags keep their original module path.

## [v0.2.0] - 2026-10-16

### Added

- Add workspace quota contract messages and RPCs for reporting and updating workspace limits.
- Add `AttachMainProcess` bidirectional streaming RPC for canonical workload stdin, output, exit status, and TTY resize.
- Add portable CPU, memory, GPU, environment, driver configuration, TTY, PID limit, and CDI device fields to sandbox creation requests.
