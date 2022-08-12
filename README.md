⚙️ Simple [GitHub CLI](https://cli.github.com/) extension to list up (own|starred) repositories.

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

## Reference

- [GitHub CLI | Take GitHub to the command line](https://cli.github.com/)
- [gh extension | GitHub CLI](https://cli.github.com/manual/gh_extension)
