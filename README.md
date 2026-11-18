# dsh-corpus

Release builds for **Corpus**, a plugin for the DeepSeek Harness desktop app.

The source is not published here. This repository carries the build, this readme and the
[release notes](RELEASE_NOTES.md).

Latest version: **0.4.0**

## Download

| File |
| --- |
| `corpus-0.4.0-single.zip` |

Every release ships one archive: a single-file build that runs as it is.

## What it does

- Keeps a set of patch rules that adjust how the desktop app behaves.
- Lists every rule and shows its state: not applied yet, in place, or not applicable to this build.
- Shows what each rule changes before you turn it on.
- Backs up each file it touches, and reverts any change in one click.
- Manages the operator prompt that is injected into every turn.

## Install

1. Unpack the archive.
2. Put the unpacked folder in the profile directory of your DSH installation.
3. Add the plugin to the profile and restart the host once.
4. The panel opens from the sidebar entry named 规范库.

## Update

Unpack the new archive over the old folder and restart the host. Configuration and rule state
are kept outside the plugin folder, so they survive the replacement.

## Uninstall

Remove the plugin from the profile, delete its folder, and restart the host.

## Requirements

- Windows.
- A DeepSeek Harness desktop installation the release targets.

## Release notes

See [RELEASE_NOTES.md](RELEASE_NOTES.md); the Chinese edition is
[RELEASE_NOTES.zh-CN.md](RELEASE_NOTES.zh-CN.md).

## License

MIT.
