# Changelog

All notable changes to **Spotlight Launcher** are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

> Releases are listed **newest first**. Sections are only ever added: a new version gets a
> new entry on top and the previous ones are kept exactly as they were.

## [Unreleased]

## [0.6.0] - 2026-10-15

Second public release. Adds a built-in calculator, soft interface sounds and a real-time
("live") blur for the background effects, on top of the initial 0.5.11 release.

### Added

- **Built-in calculator.** The search box doubles as a calculator: type an expression
  (`12*8`, `100+15%`, `sqrt(2)+pi`, unit conversions…) and the result is shown as a
  highlighted card at the top of the list, faintly inline right after what you typed, or both.
  Press **Enter** to copy the result.
  - **Calculation history:** recent results are kept so you can reuse them. Navigate with
    **↑/↓**, **Tab** pulls an entry back into the field to edit it, **Enter** adds it to the
    current operation and **Ctrl + Shift + R** removes the highlighted entry (or clears the
    whole history when nothing is selected). History and the last answer survive restarts.
  - Only reacts when the whole text looks like a calculation, so ordinary searches are left
    alone. Locale-aware formatting (thousands separators, decimal comma/point).
  - New settings: **Calculator** (on/off) and **Calculator display** (Card / Inline / Both).
- **Soft interface sounds.** Gentle sounds when the bar opens, a soft rise and fall when the
  details panel opens or closes, and a soft key sound while typing and erasing. They are
  synthesised inside the mod, so there is nothing to download and they work offline.
  - New settings: **Interface sounds** (on/off) and **Sound volume**.
- **Live acrylic (real time).** The **Acrylic**, **Frosted** and **Aurora** effects now use
  the system's real-time blur so they follow whatever is behind the bar, and **Glass** keeps
  refreshing its blur as the background changes. It can be turned off to fall back to a single
  snapshot taken when the bar opens, which is lighter on the CPU and battery.
  - New setting: **Live acrylic (real time)**.

### Changed

- **Clearer, friendlier settings and docs.** Every setting description and both READMEs were
  rewritten in plain language (no jargon, no references to other apps or internal APIs).
- **Details panel animation.** The acrylic/glassy background of the details panel now follows
  the panel while it opens and closes, instead of only fading in place.
- **Subtler effect tints.** The veil/tint values of the Acrylic, Frosted, Aurora and Mica
  effects were toned down so the blur is easier to see through the colour.
- **Shortcut-conflict warning** reworded to describe the system shortcut it clashes with,
  without naming any third-party app.
- **Live acrylic** needs Windows 10 1803 or newer; when it is unavailable the effects fall back
  to a single snapshot automatically.

### Fixed

- The **Glass** effect now respects the **Live acrylic** setting: with it off, Glass uses a
  single static capture instead of continuously re-capturing the desktop.

### Related issue

This release partially addresses
[#1 — Feature suggestions](https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/issues/1).
Of the ideas raised there, the following ship in this version:

- *"a lil click sound when it opens"* → the **interface sounds** (open, details panel, typing).
- *"a quick calculator"* → the **built-in calculator**, with history and display options.
- *"add more settings (…)"* and *"making it configurable would be better"* → several new
  settings (**Live acrylic**, **Calculator**, **Calculator display**, **Interface sounds**,
  **Sound volume**), and the details-panel shortcut is configurable.

Still open from that issue: custom path/command shortcuts, web search, running commands with a
configurable key, per-result hotkeys, monitor selection and deeper theme customisation.

### Removed

- References to other launchers in user-facing text (for example the *PowerToys Run* mention in
  the shortcut note). The mod now describes only what it does itself.

## [0.5.11] - 2026-10-12

First public release, uploaded to Windhawk.

### Added

- **App index** taken from the Start menu: both classic desktop programs and Microsoft Store
  apps, matching what you already see in Windows.
- **Instant, forgiving search:** case- and accent-insensitive, supports multi-word queries
  (`visual code`) and acronyms (the initials of each word, like `vsc`), and highlights the
  matching letters in the results.
- **Keyboard-first navigation:** **↑/↓/Tab** to move, **Enter** to open, **Esc** to close, plus
  mouse support (wheel to scroll, hover to highlight).
- **Actions with shortcuts:** open file location, run as administrator, copy path, properties,
  remove from recents and reindex.
- **Details panel** (**Ctrl + I** / **Ctrl + K** / **Ctrl + Space** / **F4**) with per-app
  actions and technical information.
- **Appearance:** six background effects (**Acrylic**, **Mica**, **Glass**, **Frosted**,
  **Aurora**, **Solid**) and twelve colours, with adjustable panel opacity and blur strength.
- **Index maintenance:** automatic updates when apps are installed or removed, or a fixed
  interval (1 / 3 / 5 / 10 minutes); hides the "Uninstall …" shortcuts and installer
  documentation while keeping genuine tools whose names merely contain "uninstall".
- **Safety touches:** runs as its own Windhawk tool mod, ignores the hotkey while a fullscreen
  window is focused, and warns when the shortcut is already taken.
- **Settings:** configurable keyboard shortcut, vertical position, maximum results, list mode,
  details-panel shortcut and fullscreen handling.
