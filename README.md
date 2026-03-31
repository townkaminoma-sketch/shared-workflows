# shared-workflows

Reusable GitHub Actions workflows for the foundation-template ecosystem.

## Workflows

### ci-python

Python CI pipeline: setup Python + uv + pytest + ruff.

```yaml
jobs:
  test:
    uses: townkaminoma-sketch/shared-workflows/.github/workflows/ci-python.yml@main
    with:
      python-version: "3.11"
      runs-on: ubuntu-latest
    secrets: inherit
```

#### Inputs

| Input | Default | Description |
|-------|---------|-------------|
| `python-version` | `"3.11"` | Python version |
| `uv-version` | `"0.10.9"` | uv version |
| `runs-on` | `"ubuntu-latest"` | Runner OS |
| `pre-test-script` | `""` | Optional command before tests (continue-on-error) |

### pr-invariants

PR scope enforcement via `check_pr_invariants.py` in the caller repo.

```yaml
jobs:
  scope:
    uses: townkaminoma-sketch/shared-workflows/.github/workflows/pr-invariants.yml@main
```

#### Inputs

| Input | Default | Description |
|-------|---------|-------------|
| `script-path` | `"scripts/check_pr_invariants.py"` | Path to invariant check script |
