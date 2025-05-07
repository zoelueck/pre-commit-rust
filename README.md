# Rust hooks for pre-commit

[Rust](https://www.rust-lang.org) tools package for [pre-commit](https://pre-commit.com).

## Note

this is my private fork of doublify's pre-commit-rust repository with all the pull requests that i found to be useful.

Doublify seems to be defunct, the upstream repository of this repository was supposedly updated on 2024-08-04 but i cant find what was actually changed, their other packages havent been updated in about 4 years (as of 2025-05-08), their website is dead, as such i doubt it will ever get updated.

## Thanks to:

@kajmaj87
@OWissett
@leoleoasd
@tpot
@azat

For their in upstream unmerged pull requests

## Usage

Install pre-commit:
`pip install pre-commit`

Create .pre-commit-config.yaml in your main project dir with the following content:
```yaml
- repo: https://github.com/zoelueck/pre-commit-rust
  rev: v1.1
  hooks:
  - id: fmt
  - id: clippy
  - id: cargo-check
  - id: cargo-test
  - id: update
```
Choose plugins and their order from the above list as needed.

Then run:

```
$ pre-commit install
$ pre-commit run --all-files
```

After that you it will be checked before each commit.

## Passing arguments to rustfmt

```yaml
- repo: https://github.com/zoelueck/pre-commit-rust
  rev: v1.1
  hooks:
  - id: fmt
    args: ['--verbose', '--edition', '2018', '--']
```
