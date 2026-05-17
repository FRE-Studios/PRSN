# PRSN

Human-only social network. Human Verification SDK.

- **iOS App** — TestFlight beta: <https://testflight.apple.com/join/b58XXvKn>
- **About** — <https://prsn.you>
- **Human Verification** — <https://prsn.you/verification>

This repo is the public issue tracker, changelog, and release log for both. Source is not open.

## Where to go

| If you're… | …do this |
| --- | --- |
| Reporting an iOS app bug or stuck verification | [Open an issue](../../issues/new/choose) |
| Asking about integrating the SDK | <partnerships@fre-studios.com> |
| Reporting a verification bypass | <security@fre-studios.com> · [bounty](https://prsn.you/verification/bounty-program) |

## Human Verification, in one line

Site shows a QR / deeplink / SDK prompt → user does a brief physical gesture on their phone → your backend gets a signed, single-use token. ([How it works](https://prsn.you/verification/how-it-works))

## Try v0.1.0 & shape what ships

Verification is at **v0.1.0**, under active development. The current flow is testable today inside the [PRSN iOS app](https://testflight.apple.com/join/b58XXvKn) — the full proposed system is at <https://prsn.you/verification>. We want feedback now, while the design is still movable: [open an issue](../../issues/new/choose) with what worked, what didn't, or what you'd need to integrate.

## Integration shape (preview)

Final API ships with v0.1.

```html
<script src="https://verify.prsn.you/v0/widget.js" async></script>
<div data-prsn-verify data-site-key="..."></div>
```

```bash
curl https://verify.prsn.you/v0/siteverify -d "secret=..." -d "token=..."
```

```swift
PRSNVerify.start(siteKey: "...") { result in /* result.token */ }
```

## Status

| Component | Status |
| --- | --- |
| iOS App | TestFlight beta |
| Human Verification | v0.1.0 — testable in iOS app, feedback open |
| Web Widget · iOS SDK · `/siteverify` | In development |

## License & Security

Proprietary — see [LICENSE.md](./LICENSE.md). Disclosure — see [SECURITY.md](./SECURITY.md).
