# Life-Experimentalist/homebrew-tap

A Homebrew tap carrying one formula: [**dev-prune**](https://github.com/Life-Experimentalist/dev-prune),
a universal, lockfile-safe workspace pruner.

```bash
brew tap Life-Experimentalist/tap
brew install dev-prune
```

That installs both names — `dev-prune` and `devp` — and generates your shell completions
from the binary itself.

To upgrade:

```bash
brew update && brew upgrade dev-prune
```

## What is in here

`Formula/dev-prune.rb`, and nothing else. It is not written by hand: the formula is
rendered by `scripts/render-packaging.sh` in the
[dev-prune repository](https://github.com/Life-Experimentalist/dev-prune/tree/main/packaging/homebrew)
against the assets each release actually publishes, and
[`.github/workflows/sync.yml`](.github/workflows/sync.yml) copies it here. Every download
URL is matched by a `sha256` that Homebrew verifies before unpacking, so a tampered
archive fails the install rather than reaching your machine.

**Open issues and pull requests against
[Life-Experimentalist/dev-prune](https://github.com/Life-Experimentalist/dev-prune/issues),
not here.** A change made in this repository is overwritten by the next sync.

## You do not have to tap anything

The formula can be installed straight from its URL, which needs no tap and is reviewed by
nobody either way — Homebrew still checks the archive against the `sha256` in the file:

```bash
brew install https://raw.githubusercontent.com/Life-Experimentalist/dev-prune/main/packaging/homebrew/dev-prune.rb
```

The tap exists so that `brew upgrade` keeps working afterwards, which the URL form does
not do.

## Licence

Apache-2.0, the same as dev-prune itself.
