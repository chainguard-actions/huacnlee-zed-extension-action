<!-- markdownlint-disable -->

# Hardening Report: huacnlee--zed-extension-action/v1.0.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **huacnlee--zed-extension-action/v1.0.0** was hardened automatically. 2 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The workflow uses mutable tag-based refs instead of pinned 40-character commit SHAs, making it vulnerable to supply-chain attacks if the referenced tags are moved or overwritten. Failing references: `actions/checkout@v3` and `oven-sh/setup-bun@v1`. Both should be pinned to their full SHA digests (e.g. `actions/checkout@<40-char-sha> # v3`).

Locations:

- `.github/workflows/ci.yml:7`
- `.github/workflows/ci.yml:8`

### missing-permissions (severity: medium)

The workflow file has no top-level `permissions:` key and the only job (`test`) also has no job-level `permissions:` key. Without explicit permissions, the workflow inherits the repository's default token permissions, which may be overly broad. A minimal `permissions:` block (e.g. `contents: read`) should be added at the top level or on each job.

Locations:

- `.github/workflows/ci.yml:1`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses, missing-permissions

**Notes:**

Pinned actions/checkout@v3 to SHA a37ce9120846195fa4ece8f58b268e6043cb2f26 and oven-sh/setup-bun@v1 to SHA f4d14e03ff726c06358e5557344e1da148b56cf7. Added top-level `permissions: contents: read` block to restrict the default GITHUB_TOKEN to the minimum required scope.

