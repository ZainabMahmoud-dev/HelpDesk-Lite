# HelpDesk Lite — Merge Readiness Checklist

## Purpose

This checklist defines the conditions that must be satisfied before a
pull request is approved and merged into `main`.

## Merge Readiness Checklist

### 1. Approvals

- [ ] Required reviewer approval has been received.
- [ ] At least one qualified reviewer has reviewed the PR.
- [ ] All blocking review comments have been addressed.

### 2. Checks

- [ ] Required CI checks have passed.
- [ ] No required check is failing.
- [ ] No required check is missing or skipped.

### 3. Tests

- [ ] Relevant automated tests have passed.
- [ ] Relevant manual checks have been completed.
- [ ] No known regression has been introduced.
- [ ] Test results or evidence are available in the PR when applicable.

### 4. Conflicts

- [ ] The branch is up to date with the target branch.
- [ ] No merge conflicts are present.
- [ ] Any conflicts have been resolved and re-checked.

### 5. Review Comments

- [ ] No unresolved blocking comments remain.
- [ ] All reviewer questions have been answered.
- [ ] Suggestions have been accepted, deferred, or explained.
- [ ] Required changes have been implemented and verified.

### 6. Risk Review

- [ ] Potential risks have been identified.
- [ ] Security or data-impact risks have been reviewed when applicable.
- [ ] Performance or usability risks have been considered when applicable.
- [ ] Known limitations are documented.
- [ ] Rollback or mitigation considerations are understood for risky changes.

### 7. Owner Confirmation

- [ ] The PR owner confirms that the implementation matches the intended
      work item.
- [ ] The PR owner confirms that the evidence and checks are accurate.
- [ ] The PR owner confirms that no known blocking issue remains.
- [ ] The PR owner confirms the PR is ready to merge.

## Final Merge Decision

The PR is **Ready to Merge** only when all applicable blocking checklist
items are satisfied.

If any required item is incomplete, the PR should remain open until the
issue is resolved or explicitly accepted by the responsible reviewer.

## Owner Confirmation

**Owner:** ____________________

**Date:** ____________________

**Confirmation:**

> I confirm that the applicable approvals, checks, tests, conflict review,
> comment resolution, risk review, and implementation verification have
> been completed and that this PR is ready to merge.

**Status:** ☐ Ready to Merge