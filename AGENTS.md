# Instructions for coding agents

- Repository: `jasonhorner/jasonhorner-com`. The PR target branch is `master`.
- This is a Jekyll site using the Minimal Mistakes `remote_theme` and the
  `github-pages` gem. Before editing, inspect the relevant repository files,
  existing project conventions, and linked issue; do not invent paths,
  validation results, or site behavior.
- Follow an issue-first workflow. Ordinary contributor branches should use
  `feature/JJH-<issue-number>-<short-description>` when an issue number exists.
  A managed Copilot workspace may require the enforced
  `copilot/feature/JJH-<issue-number>-<short-description>` prefix; keep the
  issue-number convention and do not bypass that prefix. Target pull requests
  at `master` and link the originating issue.
  Keep changes scoped and reviewable.
- Preserve the existing architecture, public URLs, custom domain, and GitHub
  Pages-compatible dependencies unless an issue explicitly approves changing
  them. Do not make unrelated content, theme, or publishing changes.
- Do not autonomously merge, deploy, publish, or modify repository settings.
- Review the diff and run applicable checks before proposing a merge. Clearly
  report failures and untested behavior, and request human review.
- Never disclose secrets, private Teams discussions, or confidential content
  in public issues or pull requests.

## Agent coordination and transparent handoffs

- Use the issue form's problem, scope, exclusions, acceptance criteria, and
  validation expectations as the authoritative implementation contract.
  Clarify material conflicts before expanding scope.
- Keep GitHub Issues and PRs authoritative; a Teams thread is coordination,
  not evidence that a check passed or a change shipped.
- When leaving reviews or comments via the owner's authorized GitHub connection,
  state that assistance was AI-prepared and who authorized submission. Do not
  imply a separate human or agent GitHub identity where none exists.
- End each implementation or review turn with **completed**, **validation
  results**, **blockers**, and **next action owner**, including links to the
  issue, PR, and CI run where available.
- Never treat passing CI or a review comment as permission to merge or deploy.

## Development lifecycle and issue resolution

1. **Proposed:** Read the linked issue, its acceptance criteria, and current files.
   Issue creation or assignment alone does not authorize implementation; follow
   the owner's explicit approval and any authorization recorded in the issue.
2. **In progress:** Implement only approved scope in the issue branch. Keep one
   implementation PR per task, update that PR when reviewers request changes,
   and reply to the review threads with the fix and evidence.
3. **Validation:** Report the actual CI result on the latest PR commit and
   distinguish Passed, Failed, Blocked, and Not run. A successful Jekyll build
   does not establish correct links, visual appearance, or accessibility.
4. **Ready for review:** Confirm intended acceptance criteria, review feedback,
   and remaining blockers. Request human review rather than self-approving.
5. **Owner decision:** Only the owner may authorize merge, deployment, or
   publication. An agent must never interpret a green check as permission.
6. **After merge:** Reconcile the linked issue. A merged PR is not proof that
   every acceptance criterion was met. Note open follow-up work and its owner.

Use `Closes #N` or `Fixes #N` in the PR description **only** when the merged
PR fully satisfies issue N; GitHub can then close the issue on merge to
`master`. Use `Related to #N` when the PR makes partial progress or the issue
is an ongoing audit or umbrella. After merge, verify whether each linked issue
was closed appropriately; do not automatically close unfinished work.

### Review responsibilities

- **Owner:** sets scope, resolves product decisions, approves merge/deployment.
- **Implementer (human or agent):** edits files, records tests, fixes findings.
- **Reviewers (human, ChatGPT, or Copilot):** provide findings and evidence; a
  review alone does not grant merge authority.
- **GitHub Actions:** supplies build results, not content or visual acceptance.

Prefer one primary Teams working thread per issue; use GitHub Issues and PRs
for durable scope, decisions, review findings, and build evidence. Do not infer
an agent's identity from the GitHub account used to submit a comment.

## Changelog requirements

- For **every implementation PR**, inspect the root `CHANGELOG.md`.
- Add a brief human-readable entry under `## [Unreleased]` for each **notable**
  site change, grouped into the appropriate Keep a Changelog category (Added,
  Changed, Deprecated, Removed, Fixed, Security). Explain impact, not commits.
- If the PR makes no notable change (for example a typo-only or internal
  housekeeping edit), do not create noise; instead state **Changelog: N/A**
  with a short reason in the PR description.
- Do not invent past releases, change dates, or version numbers. Leave entries
  under Unreleased unless the owner explicitly designates a release/milestone.
  Link issues or PRs when they improve traceability.
- Confirm changelog status in the PR checklist and update it if the scope
  changes during review. Never substitute a generated git log for an entry.
