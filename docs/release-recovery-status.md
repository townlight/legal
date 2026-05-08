# CivicLegal Release-Recovery Status

Date: 2026-05-07

## Status

CivicLegal `0.1.2` is a published foundation label under suite-wide release-recovery review. It is not product-ready and must not be promoted as production municipal legal software.

## Current Runtime Boundary

The current package provides privilege-aware corpus filtering, cited city-record search, prior-action lookup, attorney-reviewed memo scaffolds, ordinance comparison checklists, litigation-hold candidate flags, optional local legal workpaper persistence, authority citation tracking, and a public sample UI at `/civiclegal`.

It does not provide legal advice, replace Westlaw or Lexis, replace outside counsel, file court documents, manage e-discovery, make autonomous legal conclusions, call live LLMs, ingest live privileged corpora, or integrate with external legal systems.

## Recovery Evidence

- WSL-native release verification passed through `scripts/verify-release.sh`: `23 passed`, docs gate passed, placeholder import check passed, Ruff passed, and build artifacts/checksums were created.
- Fresh install proof resolved CivicCore from the published v0.11.0 release wheel without a hidden CI preinstall: `CivicCore: 0.11.0`, `CivicLegal: 0.1.2`, `WSL platform: linux`.
- Browser QA covered `docs/index.html` at desktop 1440 x 1000 and mobile 390 x 844 with console, overflow, and keyboard-focus checks.
- Documentation gates reject stale product-ready language, shipping badges, and browser mojibake.

## Promotion Rule

Do not call CivicLegal finished, shippable, production-ready, or product-ready until a later active-module sprint implements the full CivicLegal v1.0.0 definition of done and passes the release gate.
