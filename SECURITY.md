# Security Policy

The `resonatehq` org hosts production code — SDKs, the server, plugins, and the protocol spec. Security issues here can affect anyone running Resonate, so we take them seriously and ask that you report them privately.

## Reporting a vulnerability

**Do not file a public issue for a security vulnerability.** Public disclosure before a fix lands puts users at risk.

Use one of these private channels, in order of preference:

1. **GitHub private vulnerability reporting** on the affected repo:
   - [`resonatehq/resonate`](https://github.com/resonatehq/resonate/security/advisories/new) (server)
   - [`resonatehq/resonate-sdk-ts`](https://github.com/resonatehq/resonate-sdk-ts/security/advisories/new)
   - [`resonatehq/resonate-sdk-py`](https://github.com/resonatehq/resonate-sdk-py/security/advisories/new)
   - [`resonatehq/resonate-sdk-rs`](https://github.com/resonatehq/resonate-sdk-rs/security/advisories/new)
   - For other repos (plugins, transports, observability), open a private advisory on the specific repo — every public Resonate repo has the feature enabled.
2. **If you don't know which repo is affected** — or the issue spans multiple — DM a Resonate maintainer on the [Resonate Discord](https://resonatehq.io/discord). The team is small and a DM reaches us within a day. We'll triage to the right private advisory.
3. **If the issue is cross-cutting and affects the protocol itself** (Distributed Async Await, Durable Promise, or Async RPC), use the Discord path above — protocol-level issues need coordinated remediation across every SDK that implements the spec.

## What to include

- **Affected repo and version.** A specific SDK version and server version beats "the latest."
- **Reproducer.** Minimal steps that demonstrate the issue.
- **Impact.** What can an attacker do? Read data, execute code, deny service, escalate privileges, corrupt durable state, replay operations?
- **Suggested fix** if you have one.

## Response timeline

- **Acknowledgment:** within 2 business days.
- **Triage decision** (accept, decline, route to a specific repo): within 7 days of acknowledgment.
- **Fix or mitigation** for accepted reports: timeline depends on severity. Critical issues get priority; non-critical issues land in the next normal release cycle of the affected repo.

## Disclosure

We follow **coordinated disclosure with a 90-day default window** from acknowledgment. If you need a different window — shorter for active exploitation, longer for complex remediation — say so in the original report and we'll agree on a schedule. We'll request an extension in writing if a fix needs more time; we won't sit on a report past 90 days without coordinating with you.

Once a fix has shipped, we publish a security advisory on the affected repo and — for cross-cutting issues — link the advisories from the relevant SDK repos together. If you want credit for the report, tell us in the original message — we default to anonymous attribution unless asked.

## What's in scope

- Vulnerabilities in published SDK packages (`@resonatehq/sdk`, `resonate-sdk` on PyPI, `resonate-sdk` on crates.io).
- Vulnerabilities in the `resonate` server binary or its HTTP / gRPC / wire protocols.
- Vulnerabilities in a plugin or transport adapter that affect code running Resonate.
- Protocol-level issues in [Distributed Async Await](https://distributed-async-await.io), [Durable Promise](https://github.com/resonatehq/durable-promise-specification), or [Async RPC](https://github.com/resonatehq/async-rpc.io) that have implementation impact.

## What's out of scope

- **Vulnerabilities in transitive dependencies** that Resonate consumes but doesn't actively expose. Dependabot covers transitive CVEs automatically; file a security report only if Resonate's usage pattern actively exposes the dependency's vulnerable surface.
- **Theoretical vulnerabilities** without a concrete exploit path. Useful context, but not actionable security issues until someone shows the impact.
- **Issues in the [`resonatehq-examples`](https://github.com/resonatehq-examples) org** — those are demonstration repos; report vulnerabilities there via the examples org's SECURITY.md.
- **Issues in private forks** of these repos. We can only address what's in the public org.
