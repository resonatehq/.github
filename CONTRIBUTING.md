# Contributing to Resonate

Thanks for considering a contribution. This repo hosts the org-level defaults (this file, issue templates, code of conduct, security policy) — the actual code lives in the individual SDK, server, and plugin repos under [github.com/resonatehq](https://github.com/resonatehq). Use this file to figure out **where** to contribute; the repo you land on will have its own specifics.

## Where different kinds of work live

| You want to… | Land on |
|---|---|
| Fix an SDK bug or add an SDK feature | [resonate-sdk-ts](https://github.com/resonatehq/resonate-sdk-ts) · [-py](https://github.com/resonatehq/resonate-sdk-py) · [-rs](https://github.com/resonatehq/resonate-sdk-rs) |
| Work on the server | [resonate](https://github.com/resonatehq/resonate) (current, Rust) |
| Add or fix a FaaS adapter or transport plugin | The specific plugin repo (e.g. [`resonate-faas-aws-ts`](https://github.com/resonatehq/resonate-faas-aws-ts)) |
| Improve the docs | [docs.resonatehq.io](https://github.com/resonatehq/docs.resonatehq.io) |
| Propose a new example app | The [examples org](https://github.com/resonatehq-examples) — see its `CONTRIBUTING.md` |
| Propose a protocol change | This repo — open an RFC issue (template below) |
| Discuss the design of a specification | The spec repo ([DAA](https://github.com/resonatehq/distributed-async-await.io), [Durable Promise](https://github.com/resonatehq/durable-promise-specification), [Async RPC](https://github.com/resonatehq/async-rpc.io)) |

## Contributing code

1. **Open an issue first for anything non-trivial.** A two-line typo fix or a clearly-scoped bug can skip straight to a PR; anything that changes an API surface, protocol, or user-facing behavior should start with an issue so scope is agreed before code is written.
2. **Fork the target repo.** Each SDK / server / plugin repo is a normal open-source workflow — fork, branch, PR.
3. **Match the repo's conventions.** The target repo has its own lint, test, and commit-style rules. The `AGENT.md` (or `AGENTS.md`) at the repo root, if present, summarizes them.
4. **Tests pass before you open the PR.** Every core repo has a CI workflow; a red PR is a slow PR.
5. **Keep PRs scoped.** One concern per PR. If a fix needs cleanup in adjacent code, the cleanup goes in a separate PR unless removing it makes the fix incomprehensible.

## Proposing a protocol or API change (RFC)

Resonate is spec-first. Changes that affect the [Distributed Async Await protocol](https://distributed-async-await.io), the [Durable Promise specification](https://github.com/resonatehq/durable-promise-specification), or any public SDK surface should go through an RFC before code lands.

1. **Open an RFC issue** using the [propose-rfc template](https://github.com/resonatehq/.github/issues/new/choose) here. State the problem, the proposed change, the alternatives considered, and which surfaces the change touches.
2. **Discuss in the issue.** Maintainers will weigh in within a few business days. Expect questions about the wire format, cross-SDK consistency, and migration path.
3. **Prototype once the shape is agreed.** A rough branch on one SDK is often faster than continued prose debate.
4. **Land the spec change + the SDK changes together.** Cross-SDK parity matters — a Python-only change to a protocol-level API is not a protocol change, it's a divergence.

## Reporting a bug

Use the [report-bug template](https://github.com/resonatehq/.github/issues/new/choose) if the bug is cross-cutting (docs mismatch, spec ambiguity, interaction between server and SDK). For SDK-only or server-only bugs, open the issue on the affected repo — maintainers watch those more closely than the org-level tracker.

A good bug report includes: the affected version(s), the exact command you ran, the output you saw, the output you expected, and a minimal reproducer.

## Where to discuss

- **Quick questions:** [Resonate Discord](https://resonatehq.io/discord)
- **Design discussions:** issue threads on the repo where the change would land
- **Security issues:** see [SECURITY.md](./SECURITY.md) — do not file public issues

## Code of conduct

This community follows the [Resonate Code of Conduct](./CODE_OF_CONDUCT.md). By contributing, you agree to its terms.
