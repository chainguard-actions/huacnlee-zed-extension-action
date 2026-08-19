<!-- markdownlint-disable -->

# Hardening Report: huacnlee--zed-extension-action/v2.0.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **huacnlee--zed-extension-action/v2.0.0** was hardened automatically. 2 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The workflow uses mutable tag-based refs instead of pinned full SHA commit hashes, making it vulnerable to supply-chain attacks if the referenced tags are moved or overwritten. Failing references: `actions/checkout@v3` (line 7) and `oven-sh/setup-bun@v1` (line 8). These should be pinned to their full 40-character commit SHAs.

Locations:

- `.github/workflows/ci.yml:7`
- `.github/workflows/ci.yml:8`

### missing-permissions (severity: medium)

The workflow file `.github/workflows/ci.yml` has no top-level `permissions:` key, and the single job `test` also has no job-level `permissions:` key. Without explicit permissions, the workflow inherits the default repository token permissions (which may include write access), violating the principle of least privilege. A `permissions: {}` or specific minimal scopes block should be added.

Locations:

- `.github/workflows/ci.yml:1`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses, missing-permissions

**Notes:**

Fixed .github/workflows/ci.yml: (1) Pinned actions/checkout@v3 to full SHA a37ce9120846195fa4ece8f58b268e6043cb2f26 and oven-sh/setup-bun@v1 to full SHA f4d14e03ff726c06358e5557344e1da148b56cf7, with original tag names preserved as inline comments. (2) Added top-level `permissions: {}` block to enforce least privilege across the workflow.

