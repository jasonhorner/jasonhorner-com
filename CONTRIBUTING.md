# Contributing

## Start with an issue

Open or identify a GitHub issue before making tracked changes. Describe the
problem, scope, and acceptance criteria so the change can be reviewed against
an agreed outcome.

## Branches and pull requests

- Work on a feature branch, not directly on `master`. Ordinary contributor
  branches should use `feature/JJH-<issue-number>-<short-description>` when an
  issue number exists. A managed Copilot workspace may require the enforced
  `copilot/feature/JJH-<issue-number>-<short-description>` prefix; keep the
  issue-number convention and do not bypass that prefix.
- Open pull requests against `master` and link the originating issue.
- Keep each change scoped and reviewable. Explain what changed, the validation
  performed, and any limitations.
- Review the diff and ensure applicable checks pass before proposing a merge.
- Do not merge, deploy, or change publishing configuration without explicit
  owner approval.

## Preserve the site

Unless an issue explicitly approves a change, preserve current public URLs,
front matter, SEO metadata, the Minimal Mistakes remote theme architecture,
and GitHub Pages-compatible dependencies. Avoid unrelated site-content,
configuration, and publishing changes.

## Build and CI validation

The site dependencies are declared in the existing `Gemfile`. This repository
does not commit a `Gemfile.lock`, so `bundle install` resolves the declared
dependencies and may create an ignored local lock file. With a compatible Ruby
and Bundler installed, run:

```sh
bundle install
bundle exec jekyll build
```

Jekyll writes the generated site to `_site/`. For local preview, run
`bundle exec jekyll serve` and open the local address printed by Jekyll.

The **Jekyll CI** check runs `bundle exec jekyll build` for pull requests
targeting `master` and can also be started manually. Wait for the check to
pass and review its logs if it fails; dependency installation or build errors
fail the check. Report local checks you could not run as limitations. CI does
not deploy or publish the site.

## Issue types and ownership

Use **New issue** and choose the form that best fits the work:

- **Bug report** for broken behavior, accessibility defects, or build failures.
- **Improvement or technical task** for features, maintenance, and architecture.
- **Content or navigation change** for personal-site copy, links, metadata, and visitor journeys.
- **Blank issue** for investigations or work that does not yet fit a form.

Before assigning implementation, agree on the outcome and testable acceptance
criteria. Keep GitHub Issues and PRs as the source of truth; Teams discussions
can coordinate the work but should link to the relevant issue and PR. Do not
copy private Teams or client details into this public repository.

## Reviews and handoffs

For each implementation PR, record what changed, related issue, actual checks
and their results, any untested behavior, and whether AI was used. Explicitly
request human diff review; a green CI build does not prove visual or content
correctness. After addressing review feedback, report a short handoff:

- **Completed:** the work or review response and links.
- **Validation:** checks that passed, failed, or could not run.
- **Blockers:** unresolved findings or decisions.
- **Next action owner:** person or agent expected to act next.

When submitting a GitHub comment or review drafted by an AI assistant through
the owner's connected account, include a short attribution such as:
"Prepared with ChatGPT at the repository owner's request; submitted via the
owner's authorized GitHub connection." This clarifies authorship without
pretending the GitHub account is a separate reviewer. The owner retains
approval authority for merging and deployment.

## Definition of Done and closing issues

Before recommending a merge:

1. The implementation addresses the issue's approved acceptance criteria or
   explicitly identifies what remains incomplete.
2. CI has passed for the latest relevant PR commit; failed, blocked, or
   unexecuted checks are reported accurately.
3. Content claims and external destinations are verified where applicable.
   Visual changes receive a browser review, or that limitation is disclosed.
4. Open review findings have been addressed or explicitly accepted by the owner.
5. The PR includes evidence, AI-assistance attribution, remaining risks, and
   the next action owner.
6. A human has reviewed the diff and the repository owner has explicitly
   approved merging. Deployment or publishing changes also require approval.

Use `Closes #N` (or `Fixes #N`) in a PR description only when merging to
`master` fully resolves that issue. GitHub uses closing keywords to close
the issue automatically on merge. Use `Related to #N` for partial changes,
ongoing audits, or work with outstanding acceptance criteria.

After merging, confirm the linked issue was closed if fully completed. If it
remains open unexpectedly, reconcile it with evidence of completion. Do not
close larger issues simply because one related PR merged. If work is partial,
record the next step, owner, and any follow-up issue rather than claiming done.

## Work authorization and roles

Issue templates include an optional authorization field: a proposed issue
does **not** itself authorize an agent to implement it. Approval should be
explicit from the owner; record it in the issue or working handoff.

The owner controls scope and merges. Implementers make scoped changes and fix
review feedback in the existing PR. Independent reviewers provide findings.
GitHub Actions provides build evidence, not acceptance or deployment approval.
