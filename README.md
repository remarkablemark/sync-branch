# sync-branch

[![version](https://badgen.net/github/release/remarkablemark/sync-branch)](https://github.com/remarkablemark/sync-branch/releases)
[![test](https://github.com/remarkablemark/sync-branch/actions/workflows/test.yml/badge.svg)](https://github.com/remarkablemark/sync-branch/actions/workflows/test.yml)

⚙️ GitHub Actions Composite Template. Inspired by [remarkablemark/hello-world-composite-action](https://github.com/remarkablemark/hello-world-composite-action).

## Quick Start

```yaml
on: push
jobs:
  sync-branch:
    runs-on: ubuntu-latest
    steps:
      - name: GitHub Actions Composite Template
        uses: remarkablemark/sync-branch@v1
```

## Usage

See [action.yml](action.yml)

**Basic:**

```yaml
- uses: remarkablemark/sync-branch@v1
```

## Inputs

### `version`

**Optional**: The version. Defaults to `1.2.3`:

```yaml
- uses: remarkablemark/sync-branch@v1
  with:
    version: 1.2.3
```

## Contributions

Contributions are welcome!

## License

[MIT](LICENSE)
