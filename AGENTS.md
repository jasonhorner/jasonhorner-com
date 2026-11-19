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
