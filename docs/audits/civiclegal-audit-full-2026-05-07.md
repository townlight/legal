# CivicLegal Audit-Full Packet

Date: 2026-05-07
Repo: `CivicSuite/civiclegal`
Mode: release-recovery gate
Local commit audited before fixes: `e51efb8`

## 1. Executive Audit

Static audit confidence: High for release-script, docs, dependency, legal-boundary, and tests inspected locally.
Runtime sign-off confidence: High for this release-recovery scope after WSL release verification and browser QA passed.

CivicLegal already used a direct CivicCore v0.11.0 wheel in package metadata, but CI still hid that by preinstalling CivicCore. Public docs also used "Shipping" language instead of provisional release-recovery labels.

## 2. Audit Coverage Ledger

| Area | Status | Evidence |
|---|---|---|
| Engineering | Checked | `pyproject.toml`, workflow, release script, runtime tests |
| Security and authorization | Checked | privilege tiers and legal-boundary tests inspected |
| UI/UX | Checked | docs and public UI updated; Playwright desktop/mobile browser QA passed |
| Product/PM | Checked | provisional foundation label added |
| Documentation | Checked | README/manual/text docs/changelog/docs index/recovery status |
| Install/bootstrap/seeding | Checked | hidden CI preinstall removed |
| Version/release consistency | Checked | version remains `0.1.2`; no v1 promotion |
| Test engineering | Checked | regression tests added for verifier/docs/dependency/status |
| Runtime QA | Checked | WSL release gate passed; browser QA passed |
| Cross-cutting synthesis | Checked | main issue class is release evidence and public claim truth |

## 3. Claim Verification Matrix

| Claim | Result | Evidence |
|---|---|---|
| CivicLegal is not product-ready | Verified static | README/manual/recovery status |
| Version remains `0.1.2` | Verified static | package, pyproject, release script |
| Fresh install can resolve CivicCore | Verified | WSL temp venv installed `civiccore-0.11.0` and `civiclegal-0.1.2` |
| Legal advice is not provided | Verified static/test | README, manual, root payload, tests |
| Browser docs are readable | Verified | Playwright desktop/mobile QA passed with no console/page errors |

## 4. What The Dev Team Needs To Do Now

1. Push the recovery branch.
2. Open a PR.
3. Confirm GitHub CI runs the release gate without a hidden CivicCore preinstall.
4. Merge only after CI is green.

## 5. Next-Sprint Watchlist

- Full CivicLegal v1.0.0 scope remains future active-module work.
- Production claims require real user-flow Playwright tests, runtime install proof, consistency gates, docs-source enforcement, and security scans.

## 6. Engineering Deep Dive

Finding ENG-001
Severity: Critical
Confidence: High
Evidence type: Static
Status: Durable defect
Why it matters: CI must prove the package metadata is installable, not mask it with a manual dependency install.
Evidence: workflow preinstalled CivicCore before `pip install -e .[dev]`.
Blast radius: release trust, new installs, CI evidence.
Fix: remove hidden preinstall and let pyproject resolve the published wheel.

## 7. Security And Authorization Deep Dive

Privilege-tier filtering and legal-boundary tests remain intact. This patch does not expand access surfaces or add external legal-system integrations.

## 8. UI/UX Deep Dive

Finding UX-001
Severity: Major
Confidence: High
Evidence type: Static
Status: Durable defect
Why it matters: First-viewport "Shipping" language overstates release confidence during suite-wide recovery.
Evidence: docs index and public UI used `Shipping v0.1.2` / `Ships Today`.
Blast radius: public trust and status interpretation.
Fix: use "foundation under recovery review" and add browser QA proof.

## 9. Product/PM Deep Dive

CivicLegal is a deterministic legal-record support foundation, not production legal software. Attorneys remain responsible for all legal judgment and corpus access.

## 10. Documentation Deep Dive

Docs now mark the label provisional and retain the no-legal-advice boundary.

## 11. Install / Bootstrap / Seeding Deep Dive

The package metadata already uses the CivicCore v0.11.0 release wheel. Removing CI preinstall makes this verifiable.

## 12. Version And Release Consistency Deep Dive

Version remains `0.1.2`. This patch does not promote CivicLegal to v1.0.0.

## 13. Test Engineering Deep Dive

Regression tests cover Python launcher order, WindowsApps fallback removal, direct CivicCore wheel dependency, docs gate markers, recovery copy, and public UI wording.

## 14. Runtime QA Deep Dive

WSL fresh install resolved CivicCore from the published v0.11.0 wheel and imported `civiclegal==0.1.2` on Linux. WSL `scripts/verify-release.sh` passed with `23 passed`, docs gate passed, placeholder import check passed, Ruff passed, and build artifacts/checksums created. Playwright Chromium verified the recovery docs at desktop and mobile widths with no console errors, page errors, mojibake, stale shipping language, or horizontal overflow; keyboard focus reached the recovery evidence link.

## 15. Cross-Cutting Synthesis

CivicLegal's architecture and boundaries are credible for a foundation module. The recovery need is to stop overconfident presentation and make install evidence repeatable.

## 16. Verification Gaps And Sign-Off Limits

This packet does not certify CivicLegal as product-ready. It certifies only that the current published foundation label is truthfully represented and locally verifiable for the release-recovery scope.
