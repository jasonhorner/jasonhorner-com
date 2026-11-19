# JasonHorner.com

Source for [jasonhorner.com](https://jasonhorner.com/), Jason Horner's personal website for professional background, speaking, personal interests, and links to related work.

Consulting offerings and business inquiries belong on [Empty Cup Consulting](https://emptycupconsulting.com/). Technical articles are published separately at [blog.jasonhorner.com](https://blog.jasonhorner.com/).

## Technology

- Jekyll, hosted on GitHub Pages
- [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) as a `remote_theme`
- Ruby dependencies defined by `Gemfile` using the `github-pages` gem
- Default branch and pull request target: `main`
- Custom domain maintained through `CNAME`

## Repository layout

| Path | Purpose |
| --- | --- |
| `_pages/` | Pages and Jekyll front matter |
| `_data/navigation.yml` | Main navigation |
| `_config.yml` | Jekyll configuration and site metadata |
| `assets/` | Site styles and media |
| `.github/workflows/jekyll-ci.yml` | Pull-request Jekyll build check |
| `.github/ISSUE_TEMPLATE/` | Issue reporting and planning forms |
| `.github/pull_request_template.md` | Pull request checklist |

Some pages and paths may change as approved content issues are implemented; inspect the current files before modifying them.

## Local development

Use a compatible Ruby installation and Bundler. The current CI workflow uses Ruby 3.1; newer local Ruby versions may not work with this site's existing dependencies.

```sh
bundle install
bundle exec jekyll build
bundle exec jekyll serve
```

The build outputs to `_site/`; `jekyll serve` prints a local preview address. The repository currently does not commit a `Gemfile.lock`, so dependency resolution may vary across environments.

GitHub Actions runs the Jekyll build for pull requests targeting `main`. A passing build does not verify page appearance, external links, or accessibility.

For notable changes to the website and development workflow, see the [changelog](CHANGELOG.md).

## Contributing and AI-assisted development

Start with a [GitHub issue](https://github.com/jasonhorner/jasonhorner-com/issues/new/choose) that defines the problem, scope, and acceptance criteria. Read [CONTRIBUTING.md](CONTRIBUTING.md) for the contributor workflow and definition of done. Coding agents should also follow [AGENTS.md](AGENTS.md).

Submit proposed changes in a feature branch and PR targeting `main`. Record validation results, review findings, AI assistance, and outstanding work. Merge, publishing, and repository setting changes require explicit owner approval.

The authoritative instructions are in those two files; this README is a repository overview, not a replacement for them.
