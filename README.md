# Piplosion for Android

Android releases of **[Piplosion](https://piplosion.app)** – a retro dice puzzle in 16-bit style:
chain matching pips or straights, set off bombs, freeze time and keep the board clear.
Plays fully offline; optional global hi-score list.

**Download:** [Zapstore](https://zapstore.dev) · or the APK from the
[latest release](https://github.com/cleuenberg/piplosion-android/releases/latest)

This repository only hosts signed release builds and the Zapstore listing
(`zapstore.yaml`). Play in the browser: <https://piplosion.app>

---

## Publishing to Zapstore (maintainer)

1. Install `zsp`: <https://github.com/zapstore/zsp/releases>
2. **First time:** in a local clone of this repo run `zsp publish --wizard`.
   - It adds your `pubkey` to `zapstore.yaml` → commit and push it.
     Zapstore reads this file from this public repo to whitelist you.
   - It links the APK signing certificate to your Nostr identity once
     (needs `piplosion-release.jks`).
3. **Every new release** (after the `vX.Y.Z` release appears here):
   `zsp publish zapstore.yaml`
