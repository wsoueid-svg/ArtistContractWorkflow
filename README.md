# Contract workflow port bundle

## Identity
- Original clone baseline: `e7774444c8653da22922707c2d0c3423700a1fd6` (2026-10-13, `Cloned from Artist IQ (69220209be31fb12adf8520e)`).
- Exported source: `ca8a6369782cbfd215db27bf23c98569daf09d2b`.
- Scope: current contract editor and workflow, increments 1–3 plus subsequent contract fixes through the exported source. These documentation artifacts do not change runtime behavior.
- The comparison is against the original clone, NOT against the main app's current state. Main-app changes since cloning must be preserved.

## Artifact index
- `manifest.json`: every added/modified/deleted/renamed tracked file versus the original clone, per-file classification, bytes, hashes, snapshot and patch locations.
- `current/`: complete verbatim current contents of EVERY changed file, including every new/changed backend function. Original source paths are retained with a `.source.txt` suffix so these documents cannot execute.
- `baseline/`: complete original contents of modified/deleted files for three-way review.
- `diffs/`: exact Git unified diff for every changed file.
- `patches/all-changes.patch`: complete audit diff, INCLUDING optional and excluded changes; do not apply wholesale.
- `patches/contract-production-review.patch`: contract-related changes proposed for review, including permissions. This is NOT an approved installation script.
- `patches/optional-artist-fix.patch`: independent artist-creation repair, optional and excluded from the contract patch.
- `patches/optional-platform-package-updates.patch`: independent SDK/build-tool version updates; preserve destination versions unless a reviewed compatibility issue requires otherwise.
- `schemas/`: exact current changed schemas, original modified schemas, and machine-computed schema/property/permission deltas, including the eight properties added to Contract.
- `dependencies.json`: local import graph, unchanged dependencies to reuse, source paths, external packages, callable backend dependencies and reference locations.
- `reference/`: verbatim unchanged contract dependencies and host-boundary context. These are reference copies, NOT proposed replacements.
- `configuration.json`: feature-flag findings, required secret NAMES, Gmail requirements, environment-specific identifiers, record configuration prerequisites and existing workflow references.
- `exclusions.json`: staging fixtures and independent changes that must not be blindly imported.
- `evidence/`: verbatim historical contract reports and commit history. Historical reports describe different increments; they do not prove full current acceptance.
- `verification.json`: known acceptance coverage and limits; no live delivery or lifecycle certification is claimed.
- `integrity.json`: export validation results.
- `checksums.sha256`: checksums of all documentation artifacts except itself and the downloadable archive.
- `COPY_TO_MAIN_CHAT.md`: handoff message to paste into the main app chat with the ZIP attached.

## Review boundaries
1. Compare the destination to BOTH baseline and current snapshots. Add missing new files and merge existing files; do not replace destination files wholesale.
2. Review Contract, ContractDraft, ContractRedline, ContractAuditLog AND User field permissions together. Exact source is preserved, including `collaborator_role: editor` rules; compatibility with destination access-management and service-role paths is not certified.
3. Reuse the main app's actual LegalEntity/ContractTemplate records, users, organizations, contacts, mailbox connections and secrets. No database records, generated PDFs, tokens, or secret values are exported.
4. No feature flag was found. This source is wired directly into the workflow; do not describe it as safely disabled by default.
5. Existing milestone and exchange-rate workflow definitions are unchanged from the clone baseline. Review the included reference definitions and their side effects; do not create duplicate automations or activate anything merely by importing the bundle.
6. Gmail dispatch reaches a real external service. There is no new no-send/dry-run switch in this port. Do not invoke dispatch or scan real mail during integration review. `SIGNED` currently records an internal staff confirmation, not a promoter-facing electronic signature service.
7. Keep staging fixtures, sample records, historical test identities and database exports OUT of the main app. The inherited admin-only PDF `smoke_test` is not a new fixture seeder and must not be run as part of import.

All source snapshots and diffs are verbatim. JSON metadata is an index and review boundary, not a rewritten implementation. No main-app integration, deployment, authorization, data migration or email sending has been performed by creating this bundle.