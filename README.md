# package-json-sort

💡 Minimal repro to demonstrate a formatting conflict between [Biome](https://biomejs.dev) and [`sort-package-json`](https://github.com/keithamus/sort-package-json).

## What this shows

This project highlights a persistent formatting conflict when using both tools on a `package.json` file:

- [`sort-package-json`](https://github.com/keithamus/sort-package-json) reorders keys and formats short arrays as **multiline**
- [Biome](https://biomejs.dev) rewrites these arrays back to **single-line** when used as a formatter (e.g. on save in VSCode or via `biome check --write`)

This causes diffs to appear constantly in CI or local dev, as each tool reverses the other's output.

Related discussions:

- [sort-package-json Issue #356](https://github.com/keithamus/sort-package-json/issues/356)
- [biome Discussion #5807](https://github.com/biomejs/biome/discussions/5807)