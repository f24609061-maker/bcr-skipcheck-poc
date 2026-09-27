# PoC — missing authorization in `@bazel-io skip_check`

Mirrors bazelbuild/bazel-central-registry `.github/workflows/skip_check.yml` (the job gate)
and `actions/bcr-pr-reviewer` `runSkipCheck()` (the handler). The workflow job runs whenever
a comment starts with `@bazel-io skip_check `, with **no check on who commented**, and adds a
`skip-*-check` label — the same label BCR's presubmit reads to bypass a validation.

Trigger: comment `@bazel-io skip_check unstable_url` on any issue/PR here.
