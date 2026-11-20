# dsh-corpus

Release builds for **Corpus**, a plugin for the DeepSeek Harness desktop app.

[简体中文](README.zh-CN.md) | English

The source is not published here. This repository carries the build, this readme and the
[release notes](RELEASE_NOTES.md).

Latest version: **0.20.0**

## Download

| File |
| --- |
| `corpus-0.20.0-single.zip` |

Every release ships one archive: a single-file build that runs as it is.

## Features

### Command approval

Before every bash or pwsh call, the plugin runs the command text against a rule table. A command that matches an allow rule runs; one that matches an ask rule waits for your answer; one that matches a deny rule stops before it starts, and the reply carries the rule name and the matched text.

Rules are matched in order but decided by action. When several rules match one command, deny outranks ask and ask outranks allow; between rules with the same action, the earlier one speaks. When an allow and an ask both match, the narrower rule wins, so a small allow can clear a routine case like deleting build output without switching off a broad ask on recursive deletes.

The master switch sits at the top of the page. With it off, the rules stay where they are and every command goes to the host policy, exactly as it did before the gate existed. An empty table or a table with everything disabled behaves the same way, so a missing rule never turns into a blanket stop.

### Waiting and decisions

A command that matches ask joins a queue in arrival order. The page shows the command, the matched rule, the session it came from and its position. The same command from the same session does not queue twice; it returns to the open entry and keeps the first explanation.

There are four answers: allow once, allow for this session, allow for good, deny. Allow once covers that call only. Allow for this session records the rule against the session and ends with it. Allow for good writes an allow rule into the table, where it can be disabled or deleted like any other. Deny and timeout both stop the command and return the reason.

The wait is 120 seconds by default and can be changed in settings, with 0 meaning no limit. The queue holds 20 entries; beyond that a new command is refused rather than silently passed. A call cancelled while waiting is recorded as cancelled instead of leaving a question nobody can answer.

### After a stop

Every stop asks the model to say what the command does, why it was stopped and whether a safer form exists before it goes further; retrying the same command, or an equivalent one, before that explanation is discouraged. The answer is kept with the waiting entry and in the history, and it can be expanded on the page.

If the model retries without explaining, the second judgement runs as usual and that history entry is marked as retried without an explanation. The mark is a record, not a block, so a hurried retry does not turn into a loop.

### Preset rules

The plugin ships a preset list in two tiers. The minimal set has 36 rules and covers nearly irreversible work such as deleting the root, writing to a block device, formatting, piping a download into a shell, reverse shells, reading a private key and dropping a database, along with work worth a look such as installing dependencies, registering scheduled jobs, force-pushing and restarting the machine. The extended set has 8 rules around audit-adjacent work such as clearing shell history, clearing an event log, rewriting commits and changing the firewall, and is not imported by default.

Each preset carries a platform tag and is filtered to the current system: Windows takes the rules about accounts and the registry, other systems take the shell and mount rules. Import adds only what is missing, so a rule you edited keeps your version, while a preset you deleted comes back. The import button reports how many were added, skipped and failed.

### Patch table

Patches are grouped by the host build, because a different build changes in different places. Every rule shows its state: waiting to be applied, in place, or not applicable to this build. Opening a rule shows which files and lines it touches before it is switched on. Each touched file is backed up first, and any change can be reverted on its own or all at once.

### Prompt and rule sets

The operator prompt injected into every turn is assembled from Markdown files you maintain, and the page shows its size in characters and tokens so a runaway file is visible. Rule sets are separate: a Markdown rule file can be written into a chosen workspace, and an agent working there reads the file itself instead of being told the rules again each turn.

### Skills

Installed skills can be exported as a package and imported back, and the list can be re-read from the page. An exported package carries the skill's description and content, so it can be moved to another machine.

### Updates

The About page shows the running version beside the published one, with a button that downloads that build. The download is checked against the version it claims and dropped if it does not match; a good one is kept locally and swapped in at the next start, with the previous files backed up beside it.

An installation running from source is not replaced: the page says to update it with git, so a working tree never turns into a release build.

### Two surfaces

The panel opens as a page or as a small window beside the chat. Both read the same state, so the selected rule and the open blocks survive the switch. The tab shows how many commands are waiting and disappears at zero, and a new command raises a notice that jumps to the page and stays dismissed once closed.

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
