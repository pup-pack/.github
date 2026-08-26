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

| Tool | PyPI | Purpose |
| --- | --- | --- |
| [pup-up](https://github.com/pup-pack/pup-up) | [PyPI](https://pypi.org/project/pup-up/) | Syncs repo infrastructure from maintained templates |
| [pup-down](https://github.com/pup-pack/pup-down) | [PyPI](https://pypi.org/project/pup-down/) | Reports repo infrastructure changes that may belong in canonical templates |
| [pup-check](https://github.com/pup-pack/pup-check) | [PyPI](https://pypi.org/project/pup-check/) | Checks repo structure and configuration for consistency |
| [pup-clean](https://github.com/pup-pack/pup-clean) | [PyPI](https://pypi.org/project/pup-clean/) | Cleans repo by removing generated artifacts |
| [pup-core](https://github.com/pup-pack/pup-core) | [PyPI](https://pypi.org/project/pup-core/) | Shared inspection, metadata, and path-safety primitives (library) |

Default Templates: [pup-pack/templates](https://github.com/pup-pack/templates)

## Use

Run any tool from inside a target repository.
All default to a dry run.

| Command                  | What happens                                   |
| ------------------------ | ---------------------------------------------- |
| `uvx pup-up`             | Show what infrastructure files would change    |
| `uvx pup-up --diff`      | Show the exact line-by-line changes            |
| `uvx pup-up --write`     | Apply the changes (**destructive**)            |
| `uvx pup-down`           | Report infrastructure changes for templates   |
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
[templates](https://github.com/pup-pack/templates).

## Annotations

[.annotations/annotations.md](./.annotations/annotations.md)

## License

[MIT](https://opensource.org/license/MIT)
