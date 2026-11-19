# GitHub Copilot repository instructions

This repository is the personal website at https://jasonhorner.com/, built with Jekyll, GitHub Pages, and the Minimal Mistakes remote theme. The default branch and PR target are `master`.

## Source of truth

- Read and follow the root [AGENTS.md](../AGENTS.md) for agent responsibilities, issue authorization, the implementation lifecycle, review handling, issue resolution, and merge/deployment restrictions.
- Read [CONTRIBUTING.md](../CONTRIBUTING.md) for branch conventions, validation, and the Definition of Done.
- Use the linked GitHub issue and the actual repository files as the implementation contract. Do not invent missing files, URLs, tests, approvals, or accomplishments.
- Treat GitHub issues and PRs as the durable record; Teams is for coordination.

## Working on this site

- Preserve Jekyll front matter, existing links and public URLs, SEO metadata, the custom domain, and theme architecture unless an approved issue expressly changes them.
- Use GitHub Pages-compatible dependencies and minimal scoped HTML/Markdown/SCSS. Avoid unnecessary plugins, frameworks, global CSS overrides, and unrelated reformatting.
- The site build is `bundle install` followed by `bundle exec jekyll build`; CI uses Ruby 3.1. Report exact check outcomes and link to the most recent CI run. A green Jekyll build alone does not validate appearance, accessibility, or outbound links.
- For review feedback, update the **existing PR**, reply to review threads, and clearly identify blockers and the next action owner.
- Use `Closes #N` only when the PR fully resolves that issue; otherwise use `Related to #N`. Verify issue closure after merge.

## Approval and reporting

Do not autonomously merge, deploy, publish, change repository settings, or close unfinished issues. Explicit owner approval is required.

End handoffs with: **Completed**, **Validation**, **Blockers**, and **Next action owner**. Disclose when comments or reviews are AI-prepared through the owner's GitHub connection, and never include private Teams conversations, client data, or secrets in public GitHub artifacts.
