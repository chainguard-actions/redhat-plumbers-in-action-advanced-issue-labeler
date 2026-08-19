<!-- markdownlint-disable -->

# Hardening Report: redhat-plumbers-in-action--advanced-issue-labeler/v3.2.3

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **redhat-plumbers-in-action--advanced-issue-labeler/v3.2.3** was hardened automatically. 7 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

All `uses:` references in check-dist.yml use mutable version tags instead of pinned 40-character SHA commit hashes, making the workflow vulnerable to supply-chain attacks if the referenced action tags are moved or compromised. Unpinned references: `actions/checkout@v4`, `actions/setup-node@v4`, `actions/upload-artifact@v4`.

Locations:

- `.github/workflows/check-dist.yml:26`
- `.github/workflows/check-dist.yml:29`
- `.github/workflows/check-dist.yml:52`

### unpinned-uses (severity: high)

All `uses:` references in codeql-analysis.yml use mutable version tags instead of pinned 40-character SHA commit hashes. Unpinned references: `actions/checkout@v4`, `github/codeql-action/init@v3`, `github/codeql-action/autobuild@v3`, `github/codeql-action/analyze@v3`.

Locations:

- `.github/workflows/codeql-analysis.yml:26`
- `.github/workflows/codeql-analysis.yml:29`
- `.github/workflows/codeql-analysis.yml:34`
- `.github/workflows/codeql-analysis.yml:37`

### unpinned-uses (severity: high)

All `uses:` references in issue-labeler.yml use mutable version tags instead of pinned 40-character SHA commit hashes. Unpinned references: `actions/checkout@v4`, `stefanbuck/github-issue-parser@v3`.

Locations:

- `.github/workflows/issue-labeler.yml:19`
- `.github/workflows/issue-labeler.yml:22`

### unpinned-uses (severity: high)

All `uses:` references in lint.yml use mutable version tags instead of pinned 40-character SHA commit hashes. Unpinned references: `actions/checkout@v4`, `actions/setup-node@v4`.

Locations:

- `.github/workflows/lint.yml:19`
- `.github/workflows/lint.yml:22`

### unpinned-uses (severity: high)

All `uses:` references in publish-release.yml use mutable version tags instead of pinned 40-character SHA commit hashes. Unpinned references: `actions/checkout@v4`, `Actions-R-Us/actions-tagger@v2`. The third-party `Actions-R-Us/actions-tagger@v2` is particularly risky as it has write access to repository contents.

Locations:

- `.github/workflows/publish-release.yml:18`
- `.github/workflows/publish-release.yml:21`

### unpinned-uses (severity: high)

The `uses:` reference in release-drafter.yml uses a mutable version tag instead of a pinned 40-character SHA commit hash. Unpinned reference: `release-drafter/release-drafter@v6`. This action runs with write access to contents and pull-requests.

Locations:

- `.github/workflows/release-drafter.yml:16`

### unpinned-uses (severity: high)

All `uses:` references in unit-tests.yml use mutable version tags instead of pinned 40-character SHA commit hashes. Unpinned references: `actions/checkout@v4`, `actions/setup-node@v4`, `codecov/codecov-action@v5`.

Locations:

- `.github/workflows/unit-tests.yml:18`
- `.github/workflows/unit-tests.yml:21`
- `.github/workflows/unit-tests.yml:37`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all `uses:` references across 7 workflow files to full 40-character SHA commit hashes:

- check-dist.yml: actions/checkout@v4 → @34e114876b0b11c390a56381ad16ebd13914f8d5, actions/setup-node@v4 → @49933ea5288caeca8642d1e84afbd3f7d6820020, actions/upload-artifact@v4 → @ea165f8d65b6e75b540449e92b4886f43607fa02
- codeql-analysis.yml: actions/checkout@v4 → @34e114876b0b11c390a56381ad16ebd13914f8d5, github/codeql-action/init@v3, autobuild@v3, analyze@v3 → @b7351df727350dca84cb9d725d57dcf5bc82ba26
- issue-labeler.yml: actions/checkout@v4 → @34e114876b0b11c390a56381ad16ebd13914f8d5, stefanbuck/github-issue-parser@v3 → @cb6e97157cbf851e3a393ff8d57c93a484cc323f
- lint.yml: actions/checkout@v4 → @34e114876b0b11c390a56381ad16ebd13914f8d5, actions/setup-node@v4 → @49933ea5288caeca8642d1e84afbd3f7d6820020
- publish-release.yml: actions/checkout@v4 → @34e114876b0b11c390a56381ad16ebd13914f8d5, Actions-R-Us/actions-tagger@v2 → @330ddfac760021349fef7ff62b372f2f691c20fb
- release-drafter.yml: release-drafter/release-drafter@v6 → @6a93d829887aa2e0748befe2e808c66c0ec6e4c7
- unit-tests.yml: actions/checkout@v4 → @34e114876b0b11c390a56381ad16ebd13914f8d5, actions/setup-node@v4 → @49933ea5288caeca8642d1e84afbd3f7d6820020, codecov/codecov-action@v5 → @0fb7174895f61a3b6b78fc075e0cd60383518dac

All original version tags are preserved as inline comments (e.g. `# v4`). check-dist.yml was rewritten entirely to fix a corruption that occurred during the initial edit.

