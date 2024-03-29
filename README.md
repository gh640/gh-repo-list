⚙️ Simple [GitHub CLI](https://cli.github.com/) extension to list all (own|starred) repositories.

## Requirements

- Python 3 (`python3`)
    - supported versions: `3.12`, `3.11`, `3.10`, `3.9` and `3.8`

## Installation

Install:

```zsh
gh ext install gh640/gh-repo-list
```

Output sample:

```text
Cloning into '/xxx/.local/share/gh/extensions/gh-repo-list'...
remote: Enumerating objects: 41, done.
remote: Counting objects: 100% (41/41), done.
remote: Compressing objects: 100% (27/27), done.
remote: Total 41 (delta 15), reused 30 (delta 8), pack-reused 0
Receiving objects: 100% (41/41), 7.79 KiB | 2.60 MiB/s, done.
Resolving deltas: 100% (15/15), done.
✓ Installed extension gh640/gh-repo-list
```

Uninstall:

```zsh
gh ext remove gh640/gh-repo-list
```

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

## Examples

Search and open a repo in browser:

```zsh
gh repo view -w $(gh repo-list --type=own | fzf | rg -o '^\S+')
```

Search and view the README:

```zsh
gh repo view $(gh repo-list --type=own | fzf | rg -o '^\S+')
```

Archive multiple repositories which starts with `prefix-` (Check the target repositories before running the command):

```zsh
for repo in $(gh repo-list --type=own | rg -o '^username/prefix-\S+'); do
  gh repo archive -y $repo
done
```

## Reference

- [GitHub CLI | Take GitHub to the command line](https://cli.github.com/)
- [gh extension | GitHub CLI](https://cli.github.com/manual/gh_extension)
