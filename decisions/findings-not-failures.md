---
date: 2026-09-12
nature: technical
status: accepted
---
# Findings, not failures

A content anomaly becomes a finding, never a crash. The build fails only when the configuration says so. Every check is a pure function in a registry shared by the build and the linter, and a test enforces their parity.

## Affects

- [Finding](../objects/finding.md)
- [Build](../processes/build.md)
- [Lint](../processes/lint.md)
