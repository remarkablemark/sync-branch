# sync-branch

[![version](https://badgen.net/github/release/remarkablemark/sync-branch)](https://github.com/remarkablemark/sync-branch/releases)
[![test](https://github.com/remarkablemark/sync-branch/actions/workflows/test.yml/badge.svg)](https://github.com/remarkablemark/sync-branch/actions/workflows/test.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

🤖 Sync local branches with GitHub Actions.

> [!NOTE]
> To use this action, make sure to enable **Settings** > **Actions** > **General** > **Workflow permissions**:
> - [x] **Read and write permissions**
> - [x] **Allow GitHub Actions to create and approve pull requests**

## Quick Start

Merge `master` to `dev`:

```yaml
on:
  push:
    branches:
      - master
jobs:
  sync-branch:
    runs-on: ubuntu-latest
    steps:
      - name: Sync Branch
        uses: remarkablemark/sync-branch@v1
        with:
          base: dev
```

## Usage

Sync `staging` with `production` branch:

```yaml
- uses: remarkablemark/sync-branch@v1
  with:
    base: staging
    head: production
```

See [action.yml](action.yml)

## Inputs

### `base`

**Required**: The base branch.

```yaml
- uses: remarkablemark/sync-branch@v1
  with:
    base: my-base-branch
```

### `head`

**Optional**: The head branch. Defaults to the repository default branch (e.g., `master` or `main`).

```yaml
- uses: remarkablemark/sync-branch@v1
  with:
    base: my-base-branch
    head: my-head-branch
```

### `merge`

**Optional**: The merge method (`merge`, `squash`, `rebase`). Defaults to `merge`.

```yaml
- uses: remarkablemark/sync-branch@v1
  with:
    base: my-base-branch
    merge: squash
```

### `title`

**Optional**: The pull request title.

```yaml
- uses: remarkablemark/sync-branch@v1
  with:
    base: my-base-branch
    title: My PR title
```

### `body`

**Optional**: The pull request body.

```yaml
- uses: remarkablemark/sync-branch@v1
  with:
    base: my-base-branch
    body: My PR body
```

### `delete-branch`

**Optional**: Delete the local and remote branch after merge. Defaults to `false`.

```yaml
- uses: remarkablemark/sync-branch@v1
  with:
    base: my-base-branch
    delete-branch: true
```

### `admin`

**Optional**: Use administrator privileges to merge a pull request that does not meet requirements. Defaults to `false`.

```yaml
- uses: remarkablemark/sync-branch@v1
  with:
    base: my-base-branch
    admin: true
    token: ${{ secrets.PAT }}
```

> [!NOTE]
> The [`token`](https://docs.github.com/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) input must be set for `admin` to work.

### `token`

**Optional**: The GitHub token.

```yaml
- uses: remarkablemark/sync-branch@v1
  with:
    base: my-base-branch
    token: ${{ secrets.GITHUB_TOKEN }}
```

## Examples

- [remarkablemark/sync-branch-demo](https://github.com/remarkablemark/sync-branch-demo)

## License

[MIT](LICENSE)
