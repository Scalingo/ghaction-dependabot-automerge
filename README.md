# Usage

```yaml
uses: scalingo/ghaction-dependabot-automerge@v1
```

# ghaction-dependabot-automerge

GitHub action to automatically merge the Dependabot PRs. It merges the dependency upgrade if it upgrades a minor or patch version.

## Workflow Example

```yaml
name: Dependabot auto-merge
on: pull_request

permissions:
  # Mandatory for both the auto-merge enabling and approval steps
  pull-requests: write
  # Mandatory for the auto-merge enabling step
  contents: write

jobs:
  dependabot:
    runs-on: ubuntu-latest
    steps:
      - name: Automatically merge Dependabot PRs
        uses: scalingo/ghaction-dependabot-automerge@v1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
