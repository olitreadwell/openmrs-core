# openmrs/openmrs-core context
> refreshed 2026-09-03 | upstream default: master @ 9d40dd36b85af0eccb780b934c5b8330d03f8f82

## Identity & policies
- upstream: openmrs/openmrs-core, default branch `master`, primary language Java, English-first (yes — docs/CONTRIBUTING all English).
- CLA/DCO: none found (CONTRIBUTING has only a generic GitHub-account/signup link, no contributor agreement).
- AI-assisted PR policy: unstated (no AI mention anywhere in .github/ or CONTRIBUTING).
- signed commits required: no (no branch protection on master; `git blame` shows unsigned merges/dependabot).
- PR template: `.github/PULL_REQUEST_TEMPLATE.md` (TRUNK-format title, issue link `https://issues.openmrs.org/browse/TRUNK-`, checklist with `./mvnw clean package`).
- external tracker: JIRA (`issues.openmrs.org`, TRUNK project — see CONTRIBUTING; the PR template links to `issues.openmrs.org`).

## Conventions (verified from merged PRs)
- branch naming: upstream merged heads use `TRUNK-<issue>-<slug>` (e.g. `TRUNK-6784-logging-advice`, `TRUNK-6705-gzip-filter`) or dependabot-style. Trivial branches: use `docs/*` or `<type>/<desc>` (upstream has no strict trivial convention).
- commit/test command: `./mvnw clean package` (PR template), tests via Maven Surefire; formatting enforced by spotless/license plugins.
- lint/CI: GitHub Actions workflows in `.github/workflows/`.
- how outside PRs get merged: active — 139 external-human-merged PRs in last 60d; dependabot + human contributor merges ongoing (most recent push same-day).

## Maintainer picture
- Active maintainers across core (Java/Spring/Hibernate); heavy dependabot churn alongside human TRUNK ticket work.
- Human PRs are ticket-driven (JIRA). Small doc/typo fixes that follow the template can land but the repo is a Java codebase first.

## Issue-area health
- Issue tracking is external (JIRA TRUNK). GitHub issues exist (287 open) but canonical work flows through JIRA "Ready for Work".
- CONTRIBUTING discourages whitespace/style-only PRs but does NOT ban trivial/doc/link/typo fixes.

## Gap ledger (dedupe — READ FIRST, never re-pick)
- 2026-09-03 self-found trivial cleanup pass — outcome: pr-opened (fork PR #1). 10 spelling fixes (log msgs, Javadoc, messages.properties labels, README Java 8->21). Fork CI not connected; typo-only, no compiled path changed.

## Mined gaps (discovered, not yet attempted)
- see run log for the trivial-fix pass on docs (typos, dead links, stale command references).
