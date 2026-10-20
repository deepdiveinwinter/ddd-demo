# Commit Messages

Write every commit message, including those created with `/commit-commands:commit`, as a [Conventional Commit](https://www.conventionalcommits.org/en/v1.0.0/) in English.

- Format: `<type>(<scope>): <summary>`
- Types: `feat`, `fix`, `docs`, `refactor`, `test`, `build`, `ci`, `chore`
- Scope: the area or bounded context the change touches, e.g. `infra`, `kafka`, `adr`, `claude`
- Summary: imperative mood, lowercase, no trailing period, at most 72 characters
- Body (optional): explain why the change was made when the summary alone does not make it clear; wrap at 72 characters
- Breaking changes: add `!` after the scope and a `BREAKING CHANGE:` footer
