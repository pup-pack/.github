# pup-pack

<img
src="https://raw.githubusercontent.com/pup-pack/pup-up/main/docs/images/pup.png"
alt="pup logo" width="110">

> Opinionated tooling for keeping professional Python repositories on a consistent baseline.

The **PUP** tools keep a fleet of Python repositories
on a shared professional standard:
syncing infrastructure files, checking structure, and preparing
instructor repos for release.
Each runs with no install via `uvx`.
Dry run is always the default;
nothing is changed without an explicit flag.

## The Pack

| Tool          | What it does                                                                 | Repo                                            | PyPI                                        |
| ------------- | ---------------------------------------------------------------------------- | ----------------------------------------------- | ------------------------------------------- |
| **pup-up**    | Syncs repo infrastructure from maintained templates                          | [repo](https://github.com/pup-pack/pup-up)    | [pypi](https://pypi.org/project/pup-up/)    |
| **pup-check** | Checks repo structure and configuration for consistency                      | [repo](https://github.com/pup-pack/pup-check) | [pypi](https://pypi.org/project/pup-check/) |
| **pup-clean** | Prepares instructor repo for student release by removing generated artifacts | [repo](https://github.com/pup-pack/pup-clean) | [pypi](https://pypi.org/project/pup-clean/) |
| **pup-core**  | Shared inspection, metadata, and path-safety primitives (library)            | [repo](https://github.com/pup-pack/pup-core)    | [pypi](https://pypi.org/project/pup-core/)  |

Templates: [denisecase/templates](https://github.com/denisecase/templates)

## Use

Run any tool from inside a target repository.
All default to a dry run.

| Command                  | What happens                                   |
| ------------------------ | ---------------------------------------------- |
| `uvx pup-up`             | Show what infrastructure files would change    |
| `uvx pup-up --diff`      | Show the exact line-by-line changes            |
| `uvx pup-up --write`     | Apply the changes (**destructive**)            |
| `uvx pup-check`          | Report structure and configuration issues      |
| `uvx pup-clean`          | Show what generated artifacts would be removed |
| `uvx pup-clean --delete` | Remove them (**destructive**)                  |

Add `@latest` to any command to force the newest published version
(e.g. `uvx pup-up@latest`).

## Safety

- Dry run is the default for every tool.
- Only explicitly managed files are changed.
- `--write` / `--delete` are required to modify anything.
- Selected paths must be safe, repository-relative, and managed.

## Conventions

Every supporting file documents its own purpose and decisions inline;
the reason for each decision lives in the associated file.
Repository structure and the layered file conventions are defined in
[templates](https://github.com/denisecase/templates).

## Annotations

[.annotations/annotations.md](./.annotations/annotations.md)

## License

[MIT](https://opensource.org/license/MIT)
