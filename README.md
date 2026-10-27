# Emsai releases

[Emsai](https://emsai.app) runs every coding agent on your Mac in one native
window, and puts the Mac around them in the same app. This repository holds
its releases: one per version, each with a disk image signed with Apple's
Developer ID and notarized. Nothing else of Emsai is here.

## Install

Download the latest disk image and drag Emsai to Applications:

**[Emsai.dmg](https://github.com/emsai-org/emsai-releases/releases/latest/download/Emsai.dmg)**
(always the latest release) or pick a version under
[Releases](https://github.com/emsai-org/emsai-releases/releases).

Or with Homebrew, from the tap
[emsai-org/homebrew-emsai](https://github.com/emsai-org/homebrew-emsai):

```sh
brew install emsai-org/emsai/emsai
```

Requires macOS 26 (Tahoe) or later. The first launch starts a 7-day trial:
every feature, no card, no account.

## What each release holds

| File | What |
|---|---|
| `Emsai-<version>.dmg` | The disk image of that version |
| `Emsai.dmg` | The same file, so `releases/latest/download/Emsai.dmg` always serves the latest release |
| `latest.json` | What the app's updater reads: version, build, the DMG's URL, sha256 and size, the minimum macOS |

Emsai checks `latest.json` once a day and offers the update from the island;
a release can be offered to a share of Macs first (`rollout` in the feed).

## Checking a download

Every disk image is notarized by Apple. To check one yourself:

```sh
spctl -a -t open --context context:primary-signature -v Emsai.dmg
shasum -a 256 Emsai.dmg   # compare with sha256 in latest.json
```

Questions or problems: [hello@emsai.app](mailto:hello@emsai.app).
