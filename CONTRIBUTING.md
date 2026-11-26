# Contributing

Thanks for helping. These rules apply to every abnormalhq repository; a repository's own README or CONTRIBUTING file adds to them and wins where they differ.

Everyone taking part is expected to follow the [Code of Conduct](CODE_OF_CONDUCT.md).

## Before you start

- For anything larger than a small fix, open an issue first so the approach can be agreed before code is written.
- Never put secrets, customer data or mailbox contents in an issue, pull request, commit or test fixture. Security problems go through [SECURITY.md](SECURITY.md), not a public issue.

## Making a change

1. Branch from `main`. Keep one pull request to one change.
2. Run the repository's checks before pushing; in most repositories that is `pnpm check` (lint, typecheck and tests), with the Node.js version from `.node-version` and pnpm from the `packageManager` field. CI runs the same checks on every pull request.
   JavaScript and TypeScript projects are managed with pnpm only: install, run scripts and one-off tools with `pnpm`, `pnpm exec` and `pnpm dlx` (not `npm`, `npx` or `yarn`), commit `pnpm-lock.yaml` and never a `package-lock.json`, and set up pnpm in CI with `pnpm/action-setup`.
3. Update the README or `docs/` in the same pull request when behavior, configuration or an API changes. Documentation and code comments are written in English.
4. Open the pull request against `main` and fill in the template: what changed, why, and how it was tested.

`main` deploys automatically in the repositories that deploy, so a pull request is merged only once it is ready to ship.

## Commit messages

Commits follow [Conventional Commits](https://www.conventionalcommits.org/), enforced by commitlint where a repository has it:

```
<type>(<optional scope>): <summary in the imperative, lower case>

<optional body: why the change was made and what it affects>
```

Types: `build`, `chore`, `ci`, `docs`, `feat`, `fix`, `ops` (servers, DNS, Ansible), `perf`, `refactor`, `revert`, `style`, `test`. The body may be written in English or Chinese and is not wrapped to a fixed width. Husky and lint-staged format staged files on commit.
