# Release notes

[简体中文](RELEASE_NOTES.zh-CN.md)

## [0.20.0] - 2026-11-20

### Added

- The plugin updates itself. The About page shows the published version and a button that downloads
  it and keeps it ready; the swap happens at the next start, with the previous files kept beside it.
  An installation that is a source checkout is left to git.

### Changed

- Settings labels, form captions, group headers and inactive tabs are readable again; the dimmest
  colour stays with counts and small glyphs.

## [0.19.5] - 2026-11-20

### Changed

- Adding a rule sits at the top of the rules section, so a new rule is written before the list it
  joins instead of after it.
- An open row carries a divider again: a line under its header and one closing the block, while a
  closed row stays bare. The pages therefore read as compact lists until a row is opened.

## [0.19.4] - 2026-11-20

### Changed

- The approval page carries no horizontal dividers. Indentation and spacing already say what belongs
  to what, so the switch row, the sections, the waiting commands and the rules sit in one column
  without rules between them.
- A variable-count entry shows a plus and a minus again: a patch entry and an approval rule fold that
  way, while a fixed section keeps its triangle.

## [0.19.3] - 2026-11-20

### Changed

- A row divider appears only when the row is open. Closed rows sit tight with no line between them,
  and an open block draws a line under its header and closes with one before the next row.
- Folding marks are triangles, turned when the row is open, on the approval page as they already are
  on the patch page.

### Fixed

- The patch page no longer draws a divider between its closed sections. The line arrives with the
  open section, so a list of closed rows reads as one tight list.

## [0.19.2] - 2026-11-20

### Fixed

- An opened rule reads as its own block. Its padding is even on both sides and a quiet hairline marks
  the left, so the fields no longer run to the panel edge with the space all on one side.
- The hover highlight belongs to the rule's header row, not to the opened content: moving over the
  fields no longer lights up the row.

## [0.19.1] - 2026-11-20

### Fixed

- The rule editor no longer stretches its fields down the page. Each field carried the row-sizing
  rule meant for the toolbar, so in a column it turned into a fixed height and one rule filled the
  whole window. Fields are 26 pixels tall again, and they line up in two columns when the window is
  wide and in one column when it is narrow.
- Section actions stay on one line while there is room, instead of dropping one button onto a
  second row.
- The editor keeps a smaller indent in a narrow window, so its fields line up with the rule text.

## [0.19.0] - 2026-11-19

### Added

- A master switch for command approval, at the top of the approval page. Off means the gate steps
  aside and every command goes straight to the host policy; the rules stay where they are.
- Every part of the approval page folds, the same way the patch list does: the queue, the rule
  table, the preset list and the history each open and close, and the preset list folds once more
  per set.
- A rule opens into a form. Name, action, tool, platform, pattern, flags and note are editable in
  place; save writes the rule back, revert discards the edit, and a rule carrying an unsaved change
  does not silently lose it.
- A single preset can be imported from its row, next to the bulk import.

## [0.18.3] - 2026-11-19

### Fixed

- The preset list no longer overlaps its columns. Preset rows are their own shape now: the action,
  the name and the platform read on one line, the note under it, and the state sits at the right
  edge instead of landing on top of the action.
- Every row takes the width it is given. The text column fills the row and the controls keep a fixed
  column at the right, so a narrow window and a wide one both use the space instead of leaving a gap.
- Preset names and notes follow the panel language.

## [0.18.2] - 2026-11-19

### Changed

- The rule switch is smaller and square-cornered. A dense list reads better when the control at the
  right is a compact square instead of a full capsule, and the row keeps its height.

## [0.18.1] - 2026-11-19

The approval page fits a narrow window again: a rule reads as one line with its controls at the
right, and folds the pattern onto a second line when the window is narrow. Moving a rule, enabling
it and deleting it are now a triangle, a switch and a cross.

## [0.18.0] - 2026-11-19

### Added

- Command approval. A rule table decides what may run: a deny rule stops the command, an allow rule
  lets it through, and an ask rule holds it until you answer. With no rule, no match, or an empty
  table, a command runs exactly as it did before.
- Four answers on a waiting command: allow once, allow for this session, allow for good, deny. A
  permanent approval becomes a rule you can see and revoke on the same page.
- Every stopped command makes the model explain what it does and why it was stopped, and that
  explanation is kept beside the decision.
- A presets file ships with the plugin, split into a minimal set for destructive commands and an
  extended set for audit-adjacent ones. Importing adds only what is missing, and a preset is
  filtered to the platform it applies to.
- The approval page shows the waiting queue with the command, the matched rule, the originating
  session and the queue position, beside a reorderable rule table, the preset list and the history.
- The panel tab carries the number of waiting commands, and a new one raises a strip that jumps to
  the page. Both disappear when nothing is waiting.

中文版说明与本节内容相同，见发布页下半部分。

## [0.17.2] - 2026-11-19

The patch page shows the summary bar again.

## [0.17.1] - 2026-11-19

Internal check on the release note; behaviour unchanged.

## [0.17.0] - 2026-11-19

### Added

- Dry run before applying. The plugin lists the files an apply would write, how many changes each
  row carries, and any enabled row that cannot land on the current build; when such a row exists
  the write stops instead of reporting the problem afterwards. The same report is available from
  the command surface.

- Undo from the panel. Two buttons withdraw the last step or the last round into a forked session
  that keeps the earlier context, then open that session. The command entry still works.

- Skill rows export and delete. Export without a destination lands under the plugin folder; delete
  keeps a backup and names it.

- A rule set can be written into the workspace file its target names, so the rule sits where the
  host reads it. Writing the same rule again replaces that block in place and leaves the rest of
  the file alone.

### Changed

- Update checks are on by default. Start-up reads the release feed of the plugin's repository and
  names a newer release on the About page, which also carries a check button.

- The allow list is described as what it is: a register that nothing enforces yet.

### Fixed

- Settings keep one setting per row, with the control on the right rail and the label on the left,
  and the row centres its parts vertically. A narrow panel folds the row instead of squeezing it.

- Round shapes stay round under the host's own corner curvature, so the switch, its knob, the
  status dots and the summary bar no longer render with squared ends.

- A settings switch answers on the click and holds that value until the host confirms, instead of
  flicking back while the request is in flight.

## [0.8.3] - 2026-11-19

Internal cleanup; behaviour unchanged.

## [0.8.0] - 2026-11-19

Internal code refactor; behaviour unchanged.

## [0.4.0] - 2026-11-18

Code refactor; behaviour unchanged.
