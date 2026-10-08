---
description: "Change code by replacing the old implementation outright, never by layering new code over it"
---

Stop. Don't layer the change on top of the existing code.

Replace the old implementation outright:
- Move or rewrite the code into its proper place, and delete what it replaces: classes, methods, fields, localization keys, CSV rows, tests.
- Update every caller in the same change. No old path kept beside the new one, no flag that switches between them, no adapter that calls another adapter and patches its result.
- The diff should read as if the new design had always been there.

Overlays hide the real behaviour behind two code paths, and every later fix has to reason about both.
