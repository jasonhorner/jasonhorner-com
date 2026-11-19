# Contributing

## Start with an issue

Open or identify a GitHub issue before making tracked changes. Describe the
problem, scope, and acceptance criteria so the change can be reviewed against
an agreed outcome.

## Branches and pull requests

- Work on a feature branch, not directly on `master`. When an issue number
  exists, use `feature/JJH-<issue-number>-<short-description>`.
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
