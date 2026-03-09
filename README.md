<p align="center">
  <img src="./assets/uniapp-icon.webp" alt="UniApp icon" width="120" height="120">
</p>

<h1 align="center">UniApp Upstream</h1>


<p align="center">
  <img alt="Beta build" src="https://img.shields.io/static/v1?label=&message=CHANNEL%20BETA&color=d97706&style=for-the-badge">
</p>


<p align="center">
  Distribution repository for the Android release channel of <strong>UniApp</strong>.
  This repository hosts the current APK, the update manifest consumed by the app, and the published release metadata.
</p>

<p align="center">
  <a href="https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/androidApp-release.apk"><img alt="Stable APK" src="https://img.shields.io/static/v1?label=&message=STABLE%20APK&color=1f6f5f&style=for-the-badge"></a>
  <a href="https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/beta/androidApp-release.apk"><img alt="Beta APK" src="https://img.shields.io/static/v1?label=&message=BETA%20APK&color=d97706&style=for-the-badge"></a>
  <a href="./update.json"><img alt="Update Manifest" src="https://img.shields.io/static/v1?label=&message=UPDATE%20JSON&color=cb5a2e&style=for-the-badge"></a>
</p>

## Overview

This is the deploy repository for UniApp Android builds.
It is intended to stay small, stable, and machine-friendly:

- `src/release/stable/` contains stable APKs and metadata
- `src/release/beta/` contains beta APKs and metadata
- `update.json` exposes channel-specific manifests under `channels`
- `README.md` summarizes the current public release

## Current Release

| Field | Value |
| --- | --- |
| App | UniApp |
| Repository | `Anto426-Project/UniappUpstream` |
| Current version | `1.3.4-beta` |
| Release channel | `beta` |
| Version code | `1` |
| Published at | `2026-03-08` |
| Minimum supported version | `1.1.0` |
| Mandatory update | `false` |
| App enabled | `true` |
| Package name | `com.anto426.uniapp` |
| Min SDK | `31` |
| APK file | `src/release/beta/androidApp-release.apk` |
| APK size | `97.8 MB` |

## Quick Links

- [Download current APK](https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/beta/androidApp-release.apk)
- [Current channel metadata](./src/release/beta/output-metadata.json)
- [Current channel APK path](./src/release/beta/androidApp-release.apk)
- [Stable APK](https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/androidApp-release.apk)
- [Beta APK](https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/beta/androidApp-release.apk)
- [Open update manifest](./update.json)

## Release Notes

Add support for 2 update channels: stable and beta.

## Repository Layout

```text
assets/
  uniapp-icon.webp
src/
  release/
    stable/
      ...
    beta/
      ...
update.json
README.md
```

## Update Feed

The application reads `update.json` to decide whether a newer build is available.
The most relevant fields are:

- `channels.stable.release`
- `channels.beta.release`
- `latestVersion`
- `downloadUrl`
- `publishedAt`
- `buildCommit`

`downloadUrl` currently points to:

`https://raw.githubusercontent.com/Anto426-Project/UniappUpstream/main/src/release/beta/androidApp-release.apk`

## Publish Flow

This repository is updated automatically by the GitHub Actions workflow in the main UniApp repository.
Each publish refreshes:

1. the APK under `src/release/stable/` or `src/release/beta/`
2. the channel-specific `output-metadata.json`
3. `update.json`
4. this `README.md`

## Notes

- This repository is a release endpoint, not the main development repository.
- Published files can change on every new release.
