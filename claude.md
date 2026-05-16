# PROJECT

Public GitHub repo for PRSN. Dual purpose:

1. Issue tracker for the **PRSN iOS app** (TestFlight beta: <https://testflight.apple.com/join/b58XXvKn>, App Store ID `6761448008`)
2. Public face of the **PRSN Human Verification SDK** — README, changelog, release notes, partner-facing docs. Source is **not** open.

Authoritative product context lives in the marketing site repo (`prsn-web`) at `verification-program-rfp.md` and `src/pages/verification/*`. Don't restate it here; link to <https://prsn.you/verification>.

# WHAT THIS REPO IS NOT

- Not the iOS app source.
- Not the SDK source.
- Not the marketing site (that's `prsn-web` → <https://prsn.you>).
- Not a support inbox — security and partnership inquiries route to email via `.github/ISSUE_TEMPLATE/config.yml`.

# STRUCTURE

- `README.md` — landing page, "where to go" table, integration shape preview, status table
- `LICENSE.md` — proprietary; SDK use requires a partner agreement
- `SECURITY.md` — bypass reports go to <security@fre-studios.com>, see [bounty](https://prsn.you/verification/bounty-program)
- `CHANGELOG.md` — keep in sync with GitHub Releases
- `.github/ISSUE_TEMPLATE/` — `app-bug`, `sdk-bug`, `feature-request`, `config` (redirects security/partnerships out of public issues)

# VOICE & EDITING RULES

- Terse. This is early — less detail beats more. Match the tone of `prsn-web`'s verification pages: short sentences, declarative, no marketing fluff.
- Don't invent SDK API surface. The "Integration shape (preview)" block in README is a sketch; real shape ships with v0.1. If you're tempted to add code samples that imply functionality exists, don't.
- Use `prsn.you/...` URLs for real content. `verify.prsn.you/...` is a planned host — only reference it in the preview snippet, clearly marked as preview.
- Don't add `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, or PR templates. The repo doesn't accept code contributions.
- Don't add a logo, banner image, or badges to the README unless asked.
- Status table in README is the source of truth for component state — update it when status changes.

# CHANGELOG & RELEASES

- Each release ships as a GitHub Release (tag scheme: `ios-app-vX.Y.Z`, `web-sdk-vX.Y.Z`, `ios-sdk-vX.Y.Z`).
- `CHANGELOG.md` mirrors the same notes, newest first. Keep entries one-line where possible.
- iOS app releases here when an App Store version ships; TestFlight builds don't get a release entry.

# ISSUE TRIAGE (when asked to help respond)

- Security / bypass reports filed publicly: thank the reporter, redirect to <security@fre-studios.com>, close the issue. Never confirm or discuss the vulnerability in public comments.
- Verification-fails-for-me reports: ask for device + iOS version + app version if missing, then label `needs-repro`.
- SDK integration questions filed before partner agreement: redirect to <partnerships@fre-studios.com>.

# CONTACTS

- Partnerships: <partnerships@fre-studios.com>
- Security & bounty: <security@fre-studios.com>
