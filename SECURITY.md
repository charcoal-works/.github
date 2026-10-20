# Security Policy

## Supported versions

| Version | Supported |
| --- | --- |
| 1.x | ✅ |
| < 1.0 | ❌ |

## Reporting a vulnerability

**Please do not open a public issue for security problems.**

Use GitHub's private vulnerability reporting:

- Go to the affected repository's **Security** tab → **Report a vulnerability**
- Or email `security@charcoal-works.com`

Include, when possible:

- Affected product and version
- macOS / Windows version and architecture
- A minimal reproduction
- Impact assessment
- Any suggested fix

**Never include Apple ID or Google account passwords, 2FA codes, session
tokens, or downloaded account data in a report.** Redact logs before sending.

## What to expect

- Acknowledgement within **3 business days**
- Triage and severity assessment within **7 business days**
- A coordinated disclosure date once a fix is available
- Credit in the advisory, unless you prefer to stay anonymous

## Scope

In scope:

- Credential handling and local storage (Keychain, Credential Manager, session files)
- Update signing and update delivery (Sparkle / electron-updater)
- Download integrity, path traversal, archive handling
- Privilege boundaries between the UI, the embedded engine, and sidecars
- Supply-chain issues in shipped dependencies

Out of scope:

- Apple or Google account restrictions resulting from normal use of the tools
- DRM, FairPlay, or paid-content bypass
- Vulnerabilities in upstream projects that we merely vendor, unless our
  integration makes them exploitable
- Social engineering or physical access

## Safe harbor

We will not pursue legal action for good-faith research that follows this
policy, avoids privacy violations and service disruption, and gives us a
reasonable window to fix the issue before publication.
