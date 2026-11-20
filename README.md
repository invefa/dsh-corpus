# dsh-corpus

Release builds for **Corpus**, a plugin for the DeepSeek Harness desktop app.

The source is not published here. This repository carries the build, this readme and the
[release notes](RELEASE_NOTES.md).

Latest version: **0.19.5**

## Download

| File |
| --- |
| `corpus-0.19.5-single.zip` |

Every release ships one archive: a single-file build that runs as it is.

## Features

- **Command approval.** A rule table decides what may run: a command that matches an allow rule
  passes, one that matches an ask rule waits for you, and one that matches a deny rule is stopped
  before it starts. A master switch turns the whole gate off, and with no rule or no match a command
  behaves exactly as it did before the gate existed.
- **Four answers on a waiting command.** Allow once, allow for this session, allow for good, deny. A
  permanent approval becomes a rule you can see and revoke on the same page.
- **An explanation with every stop.** A stopped command makes the model say what it does and why it
  was stopped, and that answer is kept next to the decision and in the history.
- **Preset rules that match your system.** A minimal set covers destructive and irreversible
  commands, an extended set covers audit-adjacent ones, and each preset is filtered to the platform
  it applies to. Import adds only what is missing, so a rule you edited stays yours.
- **A patch table per host build.** Every rule is listed with its state: waiting to be applied, in
  place, or not applicable to this build. Each rule can be opened to see what it changes before it
  is switched on.
- **Nothing is lost.** Every file is backed up before it is touched, and any change can be reverted
  on its own or in a batch.
- **Prompt injection.** The operator prompt is assembled from Markdown files you own and injected
  into every turn, with its size shown in characters and tokens.
- **Rule sets.** Markdown rules can be written into a workspace so an agent working there reads them.
- **Skills.** Installed skills can be exported and imported, and the list can be refreshed from the
  page.
- **Two ways to look at it.** The panel opens as a page or as a small window beside the chat, and the
  tab shows how many commands are waiting.

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
