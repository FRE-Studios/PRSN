# PRSN Bounty Spec

The authoritative terms and scope for the PRSN Human Verification bounty program. The program page at <https://prsn.you/verification/bounty-program> links here. Read with [SECURITY.md](./SECURITY.md).

PRSN is a human-only network. Verification exists to bind **one human** to **one write**. This program pays for breaking that binding.

## What we pay for

A **write bypass**: a technique that creates **new** content on the network **without a human** performing the verification gesture for that content — and keeps working.

That's the whole program. Everything below makes it precise.

## Qualifying criteria

An exploit qualifies only if it meets **all four**:

1. **Write.** It creates content — a new post or a new comment on the network. Read access alone does not qualify (see Out of scope).
2. **New content.** The content is net-new. Editing, deleting, reacting to, reposting, or otherwise mutating content that already exists does not qualify.
3. **No human intervention.** Each write happens without a human completing the verification gesture for it. Defeating the human-per-write binding is the point — including capturing, replaying, forging, or programmatically satisfying the verification signal so that zero or one gesture yields many writes.
4. **Continuous.** It works durably, not in a transient window. It must survive verification token/session expiry and keep producing writes. A method that stops working on its own — e.g. lasts ~5 minutes, dies on the next token rotation — does not qualify.

If any one of the four fails, it is not a qualifying write bypass under this program. It may still be a valid security bug — report it (see [SECURITY.md](./SECURITY.md)), but it is scored separately and outside this bounty.

## Continuity bar

"Continuous" means **sustained and repeatable without human action.** Our standard demonstration:

- Automated writes continue for **≥ 24 hours**, **and**
- The technique survives **at least one** verification token/session expiry and keeps working, **and**
- No human performs a verification gesture during that window.

Equivalent demonstrations are accepted at PRSN's discretion — the test is whether the technique is durable and re-runnable, not transient.

## Out of scope

Not eligible under this program (some may still be valid security reports):

- **Read-only** access: scraping, viewing, enumerating, or exfiltrating content or profiles.
- **Edits / mutations** of existing content: editing, deleting, reacting, reposting, flagging.
- **Transient** bypasses that lapse on their own or with normal token rotation.
- Writes that **require a human gesture** per write (i.e. the verification flow worked as designed).
- Account/auth issues with no path to unattended writes (credential stuffing, session fixation on a single account with no scale, etc.).
- Spam, rate-limit, or content-moderation gaps that do **not** bypass human verification.
- DoS / volumetric attacks, social engineering, and physical attacks.
- Findings in third-party services PRSN does not control.

## Proof of concept

A report must let us reproduce the bypass unattended. Include:

- A working PoC and step-by-step reproduction.
- IDs / permalinks of the posts or comments your PoC created (use test accounts — see Rules).
- Evidence of continuity: timestamps spanning the window and at least one token/session expiry, screen capture or logs showing no human in the loop.
- Affected component and version (e.g. iOS app version, Human Verification version), device, and OS.
- Root cause if known.

Reports we cannot reproduce are not eligible.

## Rules of engagement

- Use your own test accounts. Do not target, post as, or expose other users.
- Do not post real spam, harmful, or illegal content. Keep PoC content benign and clearly marked as a test.
- Do not access, modify, or exfiltrate data that isn't yours.
- No DoS, no degradation of service, no attacks on PRSN infrastructure beyond what's needed to demonstrate the write bypass.
- Stop and report once you've proven the bypass. Do not run it at scale beyond proof.
- Coordinated disclosure only. Do not disclose publicly — including filing a public issue — before PRSN confirms a fix. Acting in good faith under these rules, we treat your research as authorized and will not pursue action against you.

## Reward

Qualifying write bypasses start at **$1,000**. The amount scales with reliability, scale, write throughput, and breadth of the underlying flaw, at PRSN's discretion. One reward per distinct root cause; duplicates are awarded to the first reproducible report.

## How to report

Email <security@fre-studios.com> with the subject `PRSN BOUNTY PROGRAM`. **Do not open a public issue.** We respond within a few days.
