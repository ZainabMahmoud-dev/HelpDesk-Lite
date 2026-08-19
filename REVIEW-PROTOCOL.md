# HelpDesk Lite — Review Protocol

## Purpose

This protocol defines how the team handles pull request review comments
to keep reviews clear, respectful, actionable, and traceable.

## Review Comment Types

### 1. Question

A question is used when the reviewer needs clarification about the
implementation, requirement, or design decision.

**Team response:**
- The author should answer the question clearly.
- If the question reveals a missing requirement or issue, the author
  should address it before approval.
- The discussion should remain focused on the specific implementation.

### 2. Suggestion

A suggestion is an optional improvement that does not block the pull
request.

**Team response:**
- The author evaluates the suggestion against the project requirements.
- The author may implement it, defer it, or explain why it is not needed.
- The reviewer should not treat an optional suggestion as a required change.

### 3. Required Change

A required-change comment identifies a defect, requirement gap, security
issue, usability problem, or other blocking concern.

**Team response:**
- The author must address the comment before merging.
- The author should make the required change and push an update.
- The author should reply to the reviewer explaining what was changed.
- The reviewer re-checks the change and resolves the thread when satisfied.

## Review Workflow

1. Reviewer reads the PR description and linked work item.
2. Reviewer checks the implementation against the stated requirements.
3. Reviewer labels feedback as a question, suggestion, or required change.
4. Author responds to every review comment.
5. Required changes are implemented before merge.
6. Author provides evidence when a change is completed.
7. Reviewer re-checks required changes.
8. Threads are resolved after agreement.
9. PR is merged only after blocking issues are addressed.

## Sample Review Thread

### Reviewer Comment — Question

> Why is authentication listed in the implementation plan if the current
> PR does not contain authentication code?

### Author Response

Authentication is part of the planned HelpDesk Lite implementation, but this
PR only documents the engineering workflow. The authentication work is
planned for a later implementation commit and is explicitly listed in the
commit sequence.

---

### Reviewer Comment — Suggestion

> Consider adding a link from the PR package to the commit sequence file
> to make navigation easier for reviewers.

### Author Response

Good suggestion. I will add a direct link to `COMMIT-SEQUENCE.md` in the
PR documentation so reviewers can navigate between the two documents
more easily.

---

### Reviewer Comment — Required Change

> The PR description should explicitly state that no application behavior
> has changed because this PR only adds documentation.

### Author Response

Agreed. I updated the PR description to explicitly state that there are
no application behavior changes and that the PR only adds documentation.

---

## Review Standards

- Be specific and actionable.
- Separate blocking issues from optional improvements.
- Ask questions when clarification is needed instead of assuming intent.
- Keep comments focused on the code, requirements, or engineering decision.
- Avoid personal or ambiguous feedback.
- Every review comment should receive an author response.
- Required changes must be verified before the thread is resolved.

## Merge Criteria

A pull request can be merged when:

- All required changes are addressed.
- Reviewer questions have been answered.
- Optional suggestions are accepted, deferred, or explained.
- Relevant checks have passed.
- The reviewer is satisfied with the final implementation.