# homebrew-tap — Homebrew tap for `az`

`az` is a fast, small & sane terminal text editor
(<https://github.com/arazgray/az>).

## Install

```sh
brew install arazgray/tap/az
```

Then run `az --version`.

## Upgrade

```sh
brew update && brew upgrade arazgray/tap/az
```

## From source (no tap)

```sh
brew install rust
cargo install --locked --git https://github.com/arazgray/az.git --tag 4.0
```

## Maintainer notes

New `az` release? Bump `url` (short tag, e.g. `4.1`), `version` (full Cargo
version, e.g. `4.1.0`), and `sha256` (of the tag archive) in `Formula/az.rb`,
or `brew bump-formula-pr --version=<ver> arazgray/tap/az`. CI builds the
formula from source on Apple Silicon + Intel and runs `brew test`.

## CI (one-time setup)

This repo has no `.github/workflows` yet (it needs a token with `workflow`
scope to push). To enable it: open
<https://github.com/arazgray/homebrew-tap/new/main?filename=.github/workflows/test.yml>,
paste the contents of
[`test-workflow.yml`](https://github.com/arazgray/az/blob/main/dist/homebrew/test-workflow.yml),
and commit. It installs the formula from source on `macos-15` +
`macos-15-intel` and runs `brew test` + `brew audit`.
