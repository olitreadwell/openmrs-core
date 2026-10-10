# openmrs/openmrs-core context
> refreshed 2026-10-10 | upstream default: master @ ee18bf341b68364e78adf1e434ce06934e289a10

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
- 2026-09-30 self-found dead-link cleanup pass — outcome: pr-opened (fork PR #26, branch `docs/fix-dead-links`). 7 verified 404 links -> live canonical pages (wiki.openmrs.org short links -> Confluence; help.github.com deep links -> docs.github.com) across CONTRIBUTING.md, .github/PULL_REQUEST_TEMPLATE.md, api/.../module/dtd/README.md. Distinct from PR #1 (different files, links not spellings). Fork GitHub Actions still has zero runs, so no status checks; each old URL re-verified 404 and each replacement 200 with curl at fix time. `x/lwLn` mapped to the archived "Mailing Lists" Confluence page; `x/2RAz` to "Platform Unsupported Releases (EOL)".
- 2026-10-10 self-found Javadoc/comment/docs spelling pass — outcome: pr-opened (fork PR #27, branch `chore/fix-comment-doc-typos`). 15 misspellings in 10 files: Javadoc `@param`/`@return` (Identifer, superceeds, passoword, quanity, specifed, formated), 2 admin global-property descriptions (sql indentifier), `liquibase/README.md` heading + brand (shapshots, OpemMRS), and 5 GZIP exception strings (Asynchonous). Files/lines disjoint from PR #1 and PR #26. Fork master was 3 commits behind upstream and was fast-forwarded to ee18bf341 before branching. Fork Actions still has zero runs (no status checks); local `./mvnw -pl web -am -DskipTests compile` = BUILD SUCCESS and spotless reports the changed Java files clean.

## Mined gaps (discovered, not yet attempted)
- Dead user-facing links left unfixed because no verified-200 canonical replacement was found: `https://wiki.openmrs.org/x/OALpAw` in `UpgradeUtil.java` (3 exception-message strings; no test references found), `https://wiki.openmrs.org/x/0oK5AQ` in the `messages*.properties` locale files (Release Testing Support module page), and a few old `docs.jquery.com/UI/*` links inside the vendored jQuery UI bundle. Do not re-pick these without a confirmed replacement.
- 2026-10-10 verified misspellings not yet attempted (leave for a later pass; no upstream PR found touching them): `api/.../FormRecordable.java` "namepace" x2; web log/comment typos `WebModuleUtil.java` "transorm", `ModuleFilter.java` "Initializating", `WebUtil.java` "separeted", `StartupFilter.java` "varibles", `FilterUtil.java` "retriving"; api Javadoc `Person.java` "atribute"/"matchs", `OpenmrsUtil.java` "randome"/"possiblity"/"Atempting"/"calender". Also a 404 `http://openmrs.org/license` in `liquibase/src/test/resources/file-with-license-header.md` (test fixture — do not touch without checking the test).
