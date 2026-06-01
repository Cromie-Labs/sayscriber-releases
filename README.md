# Say Scriber — Releases

Public host for **Say Scriber** distribution artifacts. This repo is intentionally public so the
`.dmg` files and the Sparkle update feed are reachable without authentication (the app's source
lives in the private `Cromie-Labs/t2t` repo).

## What's here

- **`appcast.xml`** — the Sparkle 2 update feed. The Mac app reads it on launch to detect updates.
  Stable URL: `https://raw.githubusercontent.com/Cromie-Labs/sayscriber-releases/main/appcast.xml`
- **GitHub Releases** — each version's signed, notarized `SayScriber.dmg` is attached to a
  `vX.Y.Z` release. Latest download:
  `https://github.com/Cromie-Labs/sayscriber-releases/releases/latest/download/SayScriber.dmg`

## How releases get here

You don't edit this repo by hand. Running `make release VERSION=x.y.z` in the `t2t` repo builds,
signs, notarizes, packages, EdDSA-signs the `.dmg`, creates the GitHub release here, uploads the
`.dmg`, and commits the updated `appcast.xml`. See `docs/RELEASING.md` in the `t2t` repo.

## Security note

Only the **public** EdDSA key is referenced here (embedded in the app). The **private** signing
key never leaves Kevin's login keychain and is never committed anywhere.
