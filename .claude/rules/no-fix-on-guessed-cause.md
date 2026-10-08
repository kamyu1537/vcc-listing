Stop. Do not edit code, dispatch a fix, or tell the user "the cause is X" from reading code or guessing.

Before any fix for a reported defect:
1. **Reproduce it**: the same client (VCC, ALCOM or vrc-get), the same listing URL, the same package and version.
2. **Measure**: show the exact `index.json` entry, the HTTP status of its `url`, the SHA-256 of the downloaded zip against `zipSHA256`, the zip's top-level entries, or the workflow log line that failed.
3. Only then name the cause, and fix it at the source.

If you can't reproduce it, say that plainly and state what you measured. Don't write "most likely cause" and then ship a change.
