# workflows

Reusable GitHub Actions workflows for the `midnightntwrk` organization —
label and issue-lifecycle automation shared by consumer repos via thin
dispatcher workflows (`uses: midnightntwrk/workflows/.github/workflows/<name>.yml@<sha>`).

This repo is **public** because GitHub only allows public repositories to call
reusable workflows that live in public repositories. Security-sensitive
automations remain in the private org `.github` repository.

| Workflow | Purpose |
|---|---|
| `default-labels-on-open` | Stamp `status:untriaged` on issues opened without a `status:*` label |
| `default-origin-on-open` | Set the native Origin issue field to `Public` when unset |
| `drop-untriaged-on-assign` | Remove `status:untriaged` once an issue is assigned |
| `ai-assisted-label` | Apply `bot:ai-assisted` to PRs carrying an AI-tooling signature |
| `apply-component-from-form` | Translate the issue form's `Components` answer into `component:*` labels |
| `pr-set-issue-in-progress` | Move PR-referenced issues to In Progress on the org board |
| `pr-merged-set-issue-in-review` | Move issues to In Review when the referencing PR merges |

Dispatchers must pin to a full commit SHA. Labels are IaC-managed
(`midnightntwrk/midnight-iac`); these workflows never create labels.
