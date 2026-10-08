---
description: "Code explains itself. A comment is one short line, only where the code cannot say it — in every code file (PowerShell, HTML, JavaScript, CSS, workflow YAML)"
paths:
  - "**/*.ps1"
  - "**/*.html"
  - "**/*.js"
  - "**/*.css"
  - "**/*.yml"
---

The maintainer strongly dislikes code explained through comments. Code must be readable on its own; a comment that walks through complicated code is a sign the code should be simpler.

- **Default is no comment.** Make the code say it: a better name, an extracted well-named helper, a simpler structure.
- **A comment is allowed only for what the code cannot say and a reader would get wrong**: a VPM or VCC gotcha, a GitHub Actions quirk, an invariant, a non-obvious external fact. Example: `# A VPM zip keeps package.json at the archive root, not under Packages/.`
- **One short line.** Two consecutive comment lines or a multi-line block is too long — cut it to the one fact that matters.
- **Never:**
  - narrating what the next statement does, or restating a name;
  - rationale essays or design discussion — those belong in `docs/`;
  - history: what the code used to do, which bug this fixed — that belongs in the commit message.

Before writing a comment, ask: would a competent reader misread this code without it? If not, delete it.
