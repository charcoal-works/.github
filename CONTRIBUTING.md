# Contributing to Charcoal Works

Thanks for helping. This guide covers both products and the organization-level
conventions.

By participating, you agree to follow the [Code of Conduct](CODE_OF_CONDUCT.md).

## Repositories

| Repository | Stack | Notes |
| --- | --- | --- |
| `charcoal-ipa` | Swift 6 / SwiftUI + embedded Node 24 engine | Fork of [Pastel](https://github.com/EEliberto/Pastel-macOS) |
| `charcoal-apk` | TypeScript / Electron + Rust sidecar | In design |
| `.github` | Markdown / YAML | Organization profile and templates |

## Development

### Charcoal IPA

Requirements:

- macOS 26 or later, Apple silicon
- Xcode 26 or later (Xcode beta is fine)
- Node.js 24 (the repository also carries a bundled runtime for release builds)

```bash
cd NodeProject
npm install
npm test
cd ..
open Pastel.xcodeproj
```

Build from the command line:

```bash
xcodebuild -project Pastel.xcodeproj \
  -scheme Pastel \
  -configuration Debug \
  -derivedDataPath "$TMPDIR/CharcoalIPA-DerivedData" \
  build
```

Release packaging (ad-hoc signed DMG):

```bash
sh Scripts/BuildAdHocDMG.sh
```

> The Xcode target and project are still named `Pastel` while the rebrand is
> being finished. See `BRANDING.md` in `charcoal-ipa`.

### Charcoal APK

The repository is not published yet. Once it is, this section will list the
Electron/Rust build commands and the APK sidecar verification steps.

## Pull requests

1. Open an issue first for non-trivial changes.
2. Branch from `main`: `feat/...`, `fix/...`, `docs/...`, `chore/...`.
3. Keep commits focused and use the imperative mood
   (`Add version picker`, not `Added ...`).
4. Run the relevant build and tests before pushing.
5. Fill in the pull request template, including what you tested.
6. CI must pass. A maintainer will review.

Do not include:

- Apple ID / Google credentials, session tokens, or Keychain exports
- Downloaded IPA/APK files or other user data
- Generated build products (`dist/`, `DerivedData/`, `node_modules/`)

## Code style

- Swift: follow the existing structure and Swift 6 strict concurrency settings.
- TypeScript: keep modules small and typed; no `any` unless justified.
- Do not log credentials, tokens, or full request bodies.
- New user-visible strings must be added to `Localizable.xcstrings` (IPA) or the
  equivalent i18n catalog (APK).

## Security

Never report vulnerabilities in a public issue. See [SECURITY.md](SECURITY.md).

## Licensing

Contributions are accepted under the Apache License 2.0. There is no CLA;
submitting a pull request means you agree to license your contribution under the
same terms.

## Upstream policy (Charcoal IPA)

Charcoal IPA is a fork. Keep the upstream attribution and `NOTICE` intact, and
prefer small, reviewable patches so upstream fixes can be rebased cleanly.

```bash
git remote add upstream https://github.com/EEliberto/Pastel-macOS.git
git fetch upstream
git rebase upstream/main
```

After a rebase, re-check the brand-specific files listed in `BRANDING.md`.
