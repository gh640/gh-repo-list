⚙️ Simple GitHub CLI extension to list up repositories.

## Requirements

- Python 3

## Usage

```zsh
gh repo-list --help
usage: List up all repositories. [-h] --type {viewer-status,own,starred}

options:
  -h, --help            show this help message and exit
  --type {viewer-status,own,starred}
```

The option `--type` is required.

List up own repositories:

```zsh
gh repo-list --type=own
```

List up starred repositories:

```zsh
gh repo-list --type=starred
```
