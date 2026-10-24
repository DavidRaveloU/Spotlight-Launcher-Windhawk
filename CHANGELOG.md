# Changelog

All notable changes to **Spotlight Launcher** are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

> Releases are listed **newest first**. Sections are only ever added: a new version gets a
> new entry on top and the previous ones are kept exactly as they were.

## [0.7.1] - 2026-10-24

Multiple-drive support in the file browser.

### Added

- **A chip for every drive.** File mode now shows a chip (with a disk icon) for each of your
  drives on a **second row**, kept apart from the location chips so the two groups do not read as
  one list. A chip is added for every fixed and removable drive that is ready; empty card
  readers, optical drives with no disc and network drives are skipped, so nothing ever raises a
  "there is no disk" dialog. The row appears only when you have **two or more** drives (with a
  single drive there is nothing to switch to). The chips are detected automatically, no setup.
- **A "This PC" drives view.** Going up from a drive root — **←** or **Backspace** on an empty
  box, or **Alt + ↑** — now opens a list of all your drives instead of doing nothing, so you can
  move between drives with the arrows alone. **Enter** or **→** opens the highlighted drive; each
  row shows its label and free space.
- **Location chips follow moved folders.** The Home, Downloads, Documents, Pictures, Music and
  Videos chips now resolve to each folder's real location, so they still work when a folder has
  been moved to another drive or redirected (for example a OneDrive-backed Documents).
- **Switch drives with Ctrl + Tab.** **Ctrl + Tab** cycles forward through the drive chips and
  **Ctrl + Shift + Tab** backward (the six location chips are left out, since they are a separate
  idea). **Ctrl + 1…9** now jumps to any chip — locations first, then drives — and typing a path
  such as `D:\` in the path bar still works.
- **Start drive setting.** A new **Start drive** option (a single drive letter) chooses which
  drive the file browser opens on the first time you use it in a session. Empty — or a drive that
  is not available, such as an unplugged USB stick — opens on Home, as before.

The F1 cheat sheet and the README shortcut tables list the new keys.

### Fixed

- **The F1 help sheet no longer resets the bar.** It now overlays the current view and closing it
  returns exactly where you were — the same folder and selection in the file browser, or the
  calculation you were working on — instead of starting over as if the launcher had just opened.

## [0.7.0] - 2026-10-20

> **Updating from 0.6.0 or earlier resets the settings.** They moved into groups, so their
> stored names changed; every option returns to its default once and has to be set again.

Third public release. Adds a full file browser with deep search, web search with selectable
engines, Windows settings results and monitor selection, on top of the calculator, sounds and
live blur from 0.6.0.

### Added

- **Files.** A folder button in the search box (or **Tab**) switches between apps and files.
  The bar shows a **Files** chip, a row of location chips (**Home**, **Downloads**,
  **Documents**, **Pictures**, **Music**, **Videos**) and a **path bar** that keeps the last
  folders visible when the path is long.
  - **Browse in place:** **Enter** or **→** on a folder opens it in the launcher; **Enter** on
    a file opens it. **Backspace** on an empty box goes up a folder and leaves file mode at a
    location root. Image files show thumbnails; every file shows a type icon and a metadata
    line (type, size, date and folder).
  - **Deep search:** typing searches the current folder and all its subfolders, closest
    matches first, with results appearing while the search is still running. A background
    thread keeps the bar responsive and stops early once the result limit is reached. It runs
    below normal priority, skips offline/cloud folders and stops when the bar closes.
  - **History:** back and forward through visited folders (**Alt + ←/→**, mouse back/forward
    buttons), including the folder you came from.
  - **Path editing:** click the path bar (or **Ctrl + L** / **Alt + D**) and type or paste a
    path. `~`, environment variables, quoted paths, `/`, `..` and relative paths work; **Tab**
    completes folder names and **Enter** navigates (a file path opens its folder with the file
    highlighted). A missing path shows an inline error instead of doing anything.
  - **Actions menu** (**Ctrl + I**): open, show in its folder, reveal in the file manager,
    run as administrator, terminal here, rename, copy path / name / file, new
    folder, new file, properties and move to the Recycle Bin (needs a second **Enter**). Copying
    keeps the bar open and the footer confirms it with *Copied*.
  - **Filters:** `*.pdf`, `ext:png,jpg`, `type:image` (also `doc`, `audio`, `video`,
    `archive`, `code`), `dir:` / `folder:` and `file:`, combinable with normal text. The
    active filters are shown in the path bar.
  - **Shortcuts:** **Ctrl + 1…6** or **Ctrl + ←/→** jump to a location chip, **F2** renames,
    **Ctrl + Shift + N** creates a folder, **Ctrl + T** opens a terminal in the folder,
    **Ctrl + G** shows the item in its own folder, **Ctrl + P** opens properties and
    **Ctrl + Shift + C** copies the path.
- **Web search.** A **Search the web for …** result for what you type, or **Open …** when it
  looks like a web address. The engine is configurable: Google, Bing, DuckDuckGo, YouTube or
  Wikipedia. Web prefixes (`?`, `g:`, `b:`, `d:`, `y:`, `w:`) force a search or a specific
  engine.
- **Windows settings.** Common settings pages (**bluetooth**, **display**, **sound**,
  **update**, **wifi**, **storage**, **power**, ...) appear as a **Setting** result that opens
  the matching page in the Settings app.
- **Open on monitor** setting: show the bar on the monitor with the mouse, the one with the
  active window, or the primary monitor.
- **Help sheet.** **F1** (or the **Help** button in the footer) shows a two-column cheat sheet
  with the shortcuts, prefixes and file filters, plus a **Calculator** page (**Tab**) that
  documents operators, functions, constants and conversions. **Esc**, **F1** or a click closes
  it.
- **File browser** setting: turns the whole Files mode off. The folder button is hidden and
  **Tab** goes back to moving through the app list.

### Changed

- **Settings are grouped** into **Appearance**, **Behavior**, **Shortcuts**, **Apps**,
  **Features** and **Sounds**, so every option is easier to find. Grouped settings have new
  key names (`Appearance.Opacity` instead of `Opacity`), so **updating resets the settings**:
  options customized in 0.6.0 or earlier fall back to their defaults and must be set again.
- **Live acrylic** now also drives **Glass** in real time. With it on, **Blur strength** only
  changes **Mica**; with it off it applies to every effect again.
- **Files performance:** the folder listing no longer formats every file's metadata up front
  (it is built only for the rows that are shown), names are folded once per listing instead
  of on every keystroke, and sorting uses a fast ordinal comparison. Very large folders are
  capped at 5,000 folders and 5,000 files, and the path bar shows how many of the total are
  listed; typing searches past that cap. Image previews now decode on a background thread
  into a small LRU cache (reused by the partial deep-search updates through a single drawing
  brush), so large image folders no longer stall the bar; previews are skipped for files on
  network drives and cloud placeholders. Panoramas and long screenshots are center-cropped
  instead of being skipped, and HEIC, HEIF, AVIF and JPEG XR previews are recognized when the
  codec is installed.
- **Open with** was removed from the Files actions menu.

### Fixed

- **Deleting a file or folder** no longer closes the bar: the shell briefly takes the
  foreground while the item goes to the Recycle Bin, which used to count as a focus loss.
  The bar now keeps the folder you were browsing and takes the focus back.
- The **background effect** (acrylic and friends) no longer stays on screen as a floating
  rectangle after the bar closes. The hide animation has a fallback that completes it if it
  is ever interrupted, and the acrylic is switched off before the backdrop windows are hidden.

## [0.6.0] - 2026-10-15

Second public release. Adds a built-in calculator, soft interface sounds and a real-time
("live") blur for the background effects, on top of the initial 0.5.11 release.

### Added

- **Built-in calculator.** The search box doubles as a calculator: type an expression
  (`12*8`, `100+15%`, `sqrt(2)+pi`, unit conversions…) and the result is shown as a
  highlighted card at the top of the list, faintly inline right after what you typed, or both.
  Press **Enter** to copy the result. The copied value is the plain number (no thousands
  separators, unit or alternative data-size reading), so it pastes cleanly into other apps.
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
- **Live acrylic (real time).** The **Acrylic**, **Glass**, **Frosted** and **Aurora** effects
  now use the system's real-time blur so they follow whatever is behind the bar. It can be
  turned off to fall back to a single snapshot taken when the bar opens, which is lighter on
  the CPU and battery.
  - New setting: **Live acrylic (real time)**.
  - While it is on, the blur strength of those four effects is set by Windows, so **Blur
    strength** only changes **Mica** (and every effect again once Live acrylic is off). With
    Glass this means a heavier blur than its snapshot look.

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

- The **Glass** effect no longer re-captures the desktop about 60 times per second on the CPU
  while the bar is open: it uses the same live blur as the other effects (or a single snapshot
  with **Live acrylic** off). It also no longer hides the bar from screenshots, screen
  recordings and screen sharing.
- **Interface sounds** recover after the audio device goes away (for example, unplugging a
  headset while the bar is closed): the sound engine is rebuilt the next time the bar opens.

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
