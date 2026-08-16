# Aloud — releases

Signed macOS builds of [Aloud](https://www.aloud.sh). This repository holds the
builds and nothing else: no source, no issue tracker, no history. It exists so
the download has a public URL.

## Download

**[www.aloud.sh](https://www.aloud.sh)** — always points at the current build.

Or take it straight from [Releases](https://github.com/wdobry/aloud-releases/releases/latest).
Apple silicon, macOS 12 or later.

Every build is signed with a Developer ID and notarized by Apple, so it opens
the way any other app does — drag it to Applications and launch it. There is no
warning to click past.

## Verifying a download

Each release lists the SHA-256 of both files in its notes.

```bash
shasum -a 256 ~/Downloads/Aloud-*.dmg
```

You can also ask macOS directly, which checks the signature and the
notarization ticket rather than just the bytes:

```bash
spctl --assess --type execute -vv /Applications/Aloud.app
```

`source=Notarized Developer ID` is the answer you want.

## latest-mac.json

The file at the root of this repository describes the current build. The
landing page reads it; nothing else should depend on its shape.

```json
{
  "version": "0.6.0",
  "url": "https://github.com/wdobry/aloud-releases/releases/download/v0.6.0/Aloud-0.6.0-arm64.dmg",
  "size": 148000000,
  "sha256": "…",
  "publishedAt": "2026-08-16T12:00:00Z"
}
```

It is written by CI when a version is tagged, not by hand.

## Bugs, ideas, questions

The source lives in a private repository, so there is nothing to read here and
issues are closed. Write to [hello@aloud.sh](mailto:hello@aloud.sh) instead.

---

© 2026 wdobry
