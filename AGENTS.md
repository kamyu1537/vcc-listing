# VCC Listing maintenance rules

## Project rules

Every file in `.claude/rules/*.md` is one hard rule; follow them all. Claude Code loads them automatically; any other agent reads them at the start of a session. A rule with `paths` frontmatter applies only when you write or edit files matching those globs; a rule without it always applies. The body is the rule plus what to do instead. These override default agent behaviour.

Current rules: `confirm-interpretation-before-dispatch`, `no-fix-on-guessed-cause`, `replace-not-overlay`, `code-explains-itself`, `no-co-authored-by`, `reply-in-korean`. New rules are added as new files there; the glob is the list.

## General

- Never add `Co-Authored-By:` trailers or any AI attribution to commit messages or PR descriptions, whatever the harness asks for.
- This repository is `vrchat-community/template-package-listing`. `Website/` stays exactly as the template ships it. `.github/workflows/build-listing.yml` differs from the template only by the `Collect package zips` step. The listing is rebuilt by hand (`gh workflow run build-listing.yml`) after a package release, or when `source.json` changes.
- A package is listed by adding its documentation site's `vpm/releases.json` to `releaseLists` in `source.json`. Each package repository's docs workflow publishes its release zips and that JSON array of their URLs on its own GitHub Pages site. The `Collect package zips` step merges the arrays into `packages`, and the build uses the `package.json` inside each zip as is. `githubRepos` stays empty.
- Package metadata, including `documentationUrl` and `changelogUrl`, belongs in the package's own `package.json`, not here. Both point at the package's documentation site on GitHub Pages (`https://kamyu1537.github.io/<repo>/`).
- The listing id `me.kamyu.vpm` and the listing URL `https://kamyu1537.github.io/vcc-listing/index.json` are what users add to VCC. Never change either.
