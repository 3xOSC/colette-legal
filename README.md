# colette-legal

Public legal and support pages for **Colette** (iOS app, App Store Apple ID `6763777428`).
Served as a static site via GitHub Pages; the app itself lives in a separate private repository.

| Page | URL | Used by |
|------|-----|---------|
| `index.html` | `/` | App Store Connect → **Support URL** |
| `privacy.html` | `/privacy.html` | App Store Connect → **Privacy Policy URL**; RevenueCat paywall footer |
| `terms.html` | `/terms.html` | RevenueCat paywall footer (Terms link); subscription disclosure per App Store Review 3.1.2 |

## Keeping content in sync

`privacy.html` is a mirror of the in-app Privacy Policy screen — `Sources/Carusel/Settings/PrivacyPolicyView.swift`
in the app repository. The two must say the same thing: App Review compares the in-app text, this page, and the
App Privacy nutrition label. When one changes, change all of them and bump the "Last updated" date in both.

`terms.html` lists subscription prices and what Pro unlocks. Those come from the app's gate sites and the
App Store Connect subscription group — if pricing or the set of Pro features changes, this page changes too.

No build step, no dependencies: plain HTML with inline CSS, light and dark themes via `prefers-color-scheme`.
