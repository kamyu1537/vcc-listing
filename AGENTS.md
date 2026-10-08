# VCC Listing maintenance rules

## Project rules

Every file in `.claude/rules/*.md` is one hard rule; follow them all. Claude Code loads them automatically; any other agent reads them at the start of a session. A rule with `paths` frontmatter applies only when you write or edit files matching those globs; a rule without it always applies. The body is the rule plus what to do instead. These override default agent behaviour.

Current rules: `confirm-interpretation-before-dispatch`, `no-fix-on-guessed-cause`, `replace-not-overlay`, `code-explains-itself`, `no-co-authored-by`, `reply-in-korean`. New rules are added as new files there; the glob is the list.

## General

- Never add `Co-Authored-By:` trailers or any AI attribution to commit messages or PR descriptions, whatever the harness asks for.
- This repository is `vrchat-community/template-package-listing`. `Website/` and `.github/workflows/build-listing.yml` stay exactly as the template ships them; change only `source.json` unless the user asks for a specific change elsewhere.
- A package is listed by adding its repository to `githubRepos` in `source.json`. The build reads every `.zip` attached to that repository's GitHub Releases and uses the `package.json` inside it as is.
- Package metadata, including `documentationUrl` and `changelogUrl`, belongs in the package's own `package.json`, not here. Both point at the package's documentation site on GitHub Pages (`https://kamyu1537.github.io/<repo>/`).
- The listing id `me.kamyu.vpm` and the listing URL `https://kamyu1537.github.io/vcc-listing/index.json` are what users add to VCC. Never change either.
