# PR1668 abandonment boundary hardening

## Objective and rationale
Complement PR #1668 with fail-closed controller checks and registered-tool regression coverage. Fresh inventory acquisition and post-consent drift detection already exist; require authority and unambiguous lineage selection at both reads, and prevent dispatch after cancellation.

## Baseline and authorization
- Branch: `dnlrsls/issue1159-pr1668-hardening`.
- Baseline: `3a966451643d3f8a5393ba71d8cfa5368f125448`.
- Previous fix remains on `dnlrsls/issue1159` at `4562fb2b8f2432eab1251323efbaf994fac2d92f`.
- Authorized: local scoped implementation, focused tests and, subsequently, explicit local work-unit commit plus separate completion bookkeeping.
- Not authorized: push, PR changes, publication, real native abandonment, or destructive operations.
- One writer. Respect the existing 400 authored additions-plus-deletions budget; surface an overage before expanding scope. Do not compress code or omit tests to fit it.

## Scope
- `extensions/gentle-ai.ts`, only abandonment controller boundaries.
- `tests/review-controller-native-recovery.test.ts`, abandonment fixtures and registered-tool coverage.
- `docs/native-authority-architecture.md`, stale binding description.
- `tests/review-authority-recovery-docs.test.ts`, only if needed to lock the corrected wording.

## Work unit
- [x] **T1 (completed): Harden abandonment inventory and cancellation boundaries with actual-adapter registered-tool tests and aligned documentation.**
  - Require complete authoritative inventory on both reads.
  - Count all entries matching the lineage before checking eligibility/completeness; reject ambiguity.
  - Check cancellation after both inventory awaits, after approval, and immediately before dispatch.
  - Preserve strict caller-key rejection, input/top-level lineage conflict checks, post-approval drift reread, exact eight-line consent/dispatch binding and one dispatch without replay.
  - Exercise the registered tool with `NativeReviewCliV216` and encoded adapter responses, not only cast mocks.
  - Correct obsolete evidence-record-presence wording.
  - Observe meaningful RED before controller changes, then GREEN and focused regression checks.
  - Complete independent verification/review according to the native assessment and user-owned RDD switch.
  - Explicit local commit permission received; work unit committed as `2e36627c68229f84406616607bf1f60b6f6ded5d`.

## Acceptance and verification
Commands authorized for the writer, synchronously:
- `node --experimental-strip-types --test tests/review-controller-native-recovery.test.ts`
- `node --experimental-strip-types --test tests/review-authority-recovery-docs.test.ts`
- `node --experimental-strip-types --test tests/native-review-cli.test.ts`
- `node --experimental-strip-types --test tests/review-contract-prompt.test.ts`
- `git diff --check`

Cases: non-authoritative/incomplete inventory and hidden duplicates at each read; cancellation during each inventory and approval; strict rejected caller facts and top-level lineage acceptance; drift; exact displayed/dispatched binding; failed inventory; headless/declined UI; single dispatch/no retry. Reuse the real adapter's repository decoding and canonical Windows handling without asserting an unproven foreign-repository bypass. Tests must not invoke real abandonment.

## Evidence and limits
- Read-only explorer `mur7l75l-a-g2x8` mapped the existing registered-tool harness and narrow surfaces. No tests executed during exploration.
- PR baseline generated runtime is already synchronized; remote CI run `37035365123` succeeded. These are baseline remote observations, not validation of this patch.
- Prior local branch's 82 passing tests are not verification of this new work unit.
- No claim of real native eligibility, CAS, or post-dispatch mutation proof.
- Writer `mur7sqf2-b-yx8i` completed the four scoped files: 125 additions + 24 deletions = 149 authored lines, within budget.
- Observed RED on unchanged controller: 35 passed, 9 failed for authority, hidden duplicates and cancellation. GREEN: recovery 54, docs 3, native CLI 40, prompt contract 9 = 106 passed; `git diff --check` passed.
- Registered-tool tests use actual `NativeReviewCliV216` decoding/argv; no new canonical Windows regression was added. No real native operations ran.
- Parent controller diff readback confirms both authoritative reads/all-lineage counting and four cancellation guards; only scoped files plus this tracking document changed.
- RDD mode: on (global), clone-local unset. Native ASSESS returned unassessable because intended-untracked scope was undeclared; candidate outcome unknown, so its exact plan requires independent verification (treat as high risk).
- Independent verifier `mur85ooj-c-coua`: PASS, same four-file candidate preserved; recovery 54, docs 3, native CLI 40, prompt 9 = 106 passed, 0 failed/skipped; `git diff --check` passed.
- Verification nits/limits: an existing missing-discarded-work cast fixture lacks `authoritative: true` and now blocks earlier; inventory-failure cases exercise malformed JSON, not injected process failures; immediate predispatch guard is inspected without a dedicated trigger; no new Windows canonicalization test or executed Windows symlink branch proof. These were nonblocking; no post-review source changes were made.
- Native review `review-1a5e64d30351be04`: medium, one reliability lens, approved and exactly acknowledged; authority burned for target `sha256:06caa65ce3ae78781e191e50c8cca90e629ec2c29216183326cd416631c14ac9`, reviewed tree `dd42a24e86a35fdb232173e00406224f55a60db4`.
- Acknowledgement succeeded, but candidate-view cleanup was deferred with `candidate-view-git-failure`; inspect that candidate state before any new START. No cleanup, recovery, or post-burn STATUS was attempted.
- Parent post-review spot check: documentation command rerun, 3 passed / 0 failed / 0 skipped; `git diff --check` passed and scope unchanged.
- Work-unit commit: `2e36627c68229f84406616607bf1f60b6f6ded5d`, `fix(review): harden audited abandonment inventory boundaries`. Both staged tree and committed tree exactly matched the approved `dd42a24e86a35fdb232173e00406224f55a60db4`. No source changes after approval. This passive completion document is committed separately.
- Engram mirror: pending until save/readback is confirmed.

## Rollback and next action
Rollback only this work unit's controller checks, abandonment tests and architecture wording, retaining the PR baseline and its existing drift reread/runtime synchronization. T1 is complete locally. Next: decide the coordinated contribution/publication route with the PR author before any push or PR modification; refresh PR head before integration. Deferred review candidate-view cleanup is a separate follow-up and remains pending.
