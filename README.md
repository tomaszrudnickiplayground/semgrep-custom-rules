# semgrep-custom-rules

Custom Semgrep rules for staging tests. Each file in `rules/` is one custom Semgrep policy; create it in
Cycode with the file's public raw link.

| File | Language | Matches | Used for |
|---|---|---|---|
| `rules/js-express-app-listen.yaml` | javascript | `js-sast-playground/src/app.js`, `app.listen(3000)` (1 finding) | CM-76747: custom-rule languages are counted in the zip manifest |
| `rules/generic-findings-total.yaml` | generic | `c-sast-playground/README.md`, `Total: 41 findings ...` (1 finding) | CM-76747: a language-agnostic rule keeps Semgrep running on every repo |

The generic rule makes Semgrep count every file for the whole tenant while it exists, so add it only for the
test that needs it and delete the policy afterwards.
