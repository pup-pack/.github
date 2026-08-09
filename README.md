# pup-pack (.github repo)

[![Version](https://img.shields.io/badge/version-v0.2.2-blue)](https://github.com/toy-gpt/.github/releases)
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/license/MIT)
[![Check Links](https://github.com/toy-gpt/.github/actions/workflows/links.yml/badge.svg)](https://github.com/toy-gpt/.github/actions/workflows/links.yml)
[![Dependabot](https://img.shields.io/badge/Dependabot-enabled-brightgreen.svg)](https://github.com/toy-gpt/.github/security)

<img src="docs/images/pup.png" alt="pup logo" width="110">

> Organization defaults and profile for the **pup-pack** GitHub organization.

This is the organization's special `.github` repository.
It holds the public org profile and the
community-health files GitHub applies across every repo in
the org that doesn't provide its own.

## Repository Contents

- `profile/README.md` - public landing page shown at `github.com/pup-pack`
- `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `SECURITY-POLICY.md` - org-wide community health defaults
- `.github/dependabot.yml` - org default Dependabot configuration
- baseline config (`.editorconfig`, `.gitattributes`, `.gitignore`, linting) synced from [templates](https://github.com/pup-pack/templates)

## Maintenance

Baseline files are managed with `pup-up`,
same as all repositories in the fleet:

```shell
# dry run: show what would change
uvx pup-up

# view differences
uvx pup-up --diff

# apply (CAUTION: DESTRUCTIVE)
uvx pup-up --write
```

## Lint and Save Changes

```shell
npx markdownlint-cli2 --fix

git add -A
git commit -m "update"
git push -u origin main
```

## Conventions

Every supporting file documents its own purpose and decisions inline;
the reason for each decision lives in the associated file.
Repository structure and the layered file conventions are defined in
[templates](https://github.com/denisecase/templates).

## Annotations

[.annotations/annotations.md](./.annotations/annotations.md)

## License

[MIT](./LICENSE)
