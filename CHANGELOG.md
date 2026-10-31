# Changelog

All notable changes to **Spotlight Launcher** are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

> Releases are listed **newest first**. Sections are only ever added: a new version gets a
> new entry on top and the previous ones are kept exactly as they were.

## [1.1.0] - 2026-10-31

Windows you can act on, and file searches you can narrow by size and date.

### Added

- **Actions on the window switcher.** `win:` no longer only brings a window to the front. **Ctrl + M**
  minimizes it, **Ctrl + Shift + M** maximizes or restores it, **Ctrl + Shift + T** keeps it always on
  top, **Ctrl + Shift + ← / →** moves it to the previous or next monitor, and **Ctrl + W** closes it —
  with a second **Ctrl + W** to confirm, because the app decides whether to ask about unsaved work.
  **Ctrl + Enter** opens the folder of its `.exe` and **Ctrl + Shift + C** copies its path. Every action
  leaves the bar open, so several windows can be handled in a row, and none of them steals the keyboard:
  the bar takes it back. Every action is **posted** to the window's own thread instead of waited on, so a
  window that stopped responding cannot freeze the launcher: the result is checked a moment later and
  reported if the window never reacts. The close confirmation is bound to **that** window — if the
  selection moves before the second press, it asks again instead of closing a window you never picked.
  **Ctrl + I** shows the same card the app list uses, with the actions and the window's process, state
  and path.
- **Always-on-top feedback.** A window kept on top wears a gold pin on its icon, says **On top** in the
  list and reports it in the panel, and toggling it says so in the footer. Windows has no indicator of
  its own, so a forgotten pin is easy to spot and easy to undo.
- **Date and size filters.** The file browser and `find:` both accept `size:>10mb`, `size:<500kb`,
  `size:1mb..10mb`, `modified:today`, `modified:week`, `modified:2026-10-31`, `modified:>2026-06-01` and
  the rest, mixed with the words and the existing filters in any order. Sizes are binary (`1mb` =
  1,048,576 bytes), a lone date covers that whole day in local time, a space after the operator is
  accepted, and a row without a known size or date is left out rather than guessed. The active filters
  are listed in the path bar.

- **Sharp image previews.** The preview panel now decodes the picture at its own size (512 px on the
  long side, aspect preserved) instead of upscaling the 64 px square thumbnail of the row, so an image
  is shown whole and in focus.
- **A copied file keeps its path.** Explorer also publishes a text fallback with only the file name;
  the clipboard history now prefers `CF_HDROP` and stores the full path, which is what you want to paste
  into an address bar, a chat or a terminal.

- **The Quick Look panel belongs to Files.** Leaving the file browser closes it, and a folder is no
  longer previewable: **Ctrl + Q** does nothing on one, moving onto one closes the panel, and the old
  *Cannot open file* is now *A folder has nothing to preview.*

### Changed

- **Everything now answers with size and date.** The query asks its index for both, so file rows from
  Everything show the same metadata as the built-in scan instead of the type alone, and the filters are
  translated to Everything's own syntax (`size:>=1048576`, `datemodified:>=2026-10-31`) instead of
  filtering a handful of arbitrary matches.
- **`find:` shows the full metadata line.** Every result reads *type · size · date · folder*, so the
  folder no longer hides the size when the row is narrow.
- **The footer says “Searching.”** while a `find:` scan is still running, the way Files already did.
- **Icons for packaged apps** come from the tile image the Start menu uses, so Notepad, Terminal, Paint
  and the rest no longer fall back to a blank page.

### Fixed

- **Run as administrator for packaged apps.** A full-trust package (Notepad, Terminal, Paint, Photos,
  Snippets…) now offers the action, resolved from the executable its manifest declares; UWP apps such as
  Calculator or Settings do not, because launching them without their package identity does nothing.
- **Minimizing or closing a window no longer closes the launcher.** The focus the action takes away is
  no longer read as a click outside, and the bar keeps the keyboard.
- **A closed window leaves the list** even when the app takes a moment to shut down: Chromium-based
  browsers destroy their window asynchronously, so the list is re-read for up to two seconds instead of
  once.
- **`find:` results** show their size and modified date with either engine.
- **Clipboard history at startup.** With the feature off and nothing stored, the mod no longer creates
  its image folder or writes empty values for accounts that never enabled it. The folder is now created
  only when an image is actually saved, so a preview in Files cannot bring it back either, and turning
  the feature off removes it when nothing is left.
- **A clipboard entry stored as plain text** (only possible in the first 1.0.0 build) is re-encrypted
  when it is loaded instead of being written back unencrypted.
- **The clipboard image folder** is resolved once, thread-safely, so the thumbnail worker and the UI can
  no longer write the same cached path at the same time.

## [1.0.0] - 2026-10-29

Files, the clipboard, your open windows and Everything, in one bar.

### Added

- **Clipboard history.** An opt-in feature (off by default) that keeps the last 30 things you copied
  and adds a `clip:` prefix to search them. **Enter** pastes the selected entry into the window you
  came from, **Ctrl + Enter** copies it, **Ctrl + D** pins it, **Ctrl + Shift + R** removes it, and
  the **Clear Clipboard History** command erases everything. Everything is encrypted for the current
  Windows account (DPAPI) before it is written, turning the feature off erases it, and copies that an
  app marks as private (password managers) are skipped.
- **Images in the clipboard history.** Copied pictures are kept too: each one is saved as a
  compressed PNG inside the mod's own folder (scaled down to 2560 px on its long side when bigger),
  shows its own thumbnail in the list, and pastes back as an image. The file name is a hash of the
  pixels, so copying the same picture twice reuses one file and one entry. `clip: image` narrows the
  list to pictures.
- **Clipboard retention.** A **Clipboard retention (days)** setting (3 by default) deletes entries
  older than that, deleting their image files with them; pinned entries never expire, and `0` keeps
  entries until the 30-entry limit drops them. Files with no entry are cleaned up on load.
- **Pinned clipboard entries.** Pinned entries stay at the top of `clip:` and survive both the
  30-entry trim and the retention.
- **Recent files.** The empty bar gains a **Recent files** section with the files and folders from
  Windows' Recent list, and `recent:` searches them. Enter opens, Ctrl+Enter opens the folder,
  Ctrl+Shift+C copies the path. Read locally from the Recent folder; can be turned off in the
  settings. Windows must be recording recent items (Settings → Personalization → Start), or the list
  stays empty.
- **Global file search.** `find:` searches file and folder names under Home (Documents, Downloads,
  Desktop, Pictures and the rest) and any extra folders configured in the settings. It runs in a
  worker thread, shows partial results while scanning, stops when the bar closes, and builds no
  index. Enter opens, Ctrl+Enter opens the folder, Ctrl+Shift+C copies the path.
- **Window switcher.** `win:` lists the open windows with their title and process; **Enter** activates
  the selected one (restoring it if minimized). Launching a classic desktop app that already has a
  visible window now focuses it instead of starting a second instance; launches with arguments and
  packaged apps keep their normal behaviour.
- **Coloured feedback.** Anything the launcher has to tell you now carries a colour and a small dot
  in the footer: green when something is done (**Copied**), amber when it had to work around a problem
  (**Everything not running · built-in scan**) and red for what needs care (a destructive command
  asking for a second Enter, a path that does not exist, a preview that could not be opened). The
  empty list uses the same language: the accent while it is still searching, amber when a problem is
  the reason it is empty.
- **Everything as an optional index.** With **File search engine** set to **Everything** (voidtools),
  both `find:` and the deep search inside Files go to Everything's IPC instead of scanning: every
  drive (or just the folder you are browsing), answers in milliseconds, and Everything's own syntax
  (`*.pdf`, `"exact phrase"`, `!excluded`). No DLL is shipped or loaded, the built-in scan stays the
  default, and it takes over automatically when Everything is not running or does not answer within a
  second, with the footer saying *Everything not running · built-in scan*.
- **Sort the Files list.** **Ctrl + S** (or **Sort…** in the actions menu) opens a sort list with the
  order in use marked: name (A-Z and Z-A), type, modified date (newest and oldest) and size (largest
  and smallest). Folders stay on top, the order also applies while filtering, and deep-search results
  keep their relevance order. **Remember file sort** (off by default) keeps the chosen order across
  closes and restarts; while it is off the order only lives while the bar is open and Files starts
  again at Name (A-Z).
- **Learning from your choices.** Picking an app after typing a few words puts that app first the next
  time you type those same words — even when it was a weak match (`ex` + **Firefox** puts Firefox
  above Excel). One pick is enough, only those words are affected, the pairs live in the mod storage
  (capped at 200, forgotten after 90 days without a pick), and **Learn from your choices** in the
  settings turns it off.
- **Modes as results.** Typing the name of a mode (for example **Open Windows** — also found by
  *windows manager* or *switcher* — **Bookmarks**, **Clipboard History**, **Recent Files**, **All
  Files** or **Commands**) shows it as one more result, like an app; **Enter** switches into that mode
  and fills in its prefix, so the prefixes are optional. A mode row only appears while its feature is
  enabled, and it never filters: `win: chrome` is still how a list is narrowed.

### Changed

- **The Settings tab is grouped by what each option configures**: Appearance, Behavior, Shortcuts,
  Apps, Search (web search, bookmarks, recent files, learning and the file search engine), Files
  (browser, start drive, remembered sort), Clipboard, Calculator and Sounds. Options that moved
  between sections keep their saved values; the tab shows the defaults until you save it once, so it
  is worth a look the first time.
- **The F1 sheet** lists every shortcut, prefix and filter (including the newer ones: sort, preview,
  pin, the clipboard keys and the mode names) and scrolls with the wheel or the arrow keys when a
  page is taller than the bar.
- **Feedback has a colour**: green when something is done, amber when a problem had to be worked
  around and red for what needs care, with a small dot in the footer and the same tones in the empty
  list and the error bands.

### Fixed

- Disabled features no longer claim their prefixes: `bm:`, `clip:` and the web prefixes (`?`, `g:`,
  `b:`, `d:`, `y:`, `w:`) are only recognized while the matching feature is enabled; otherwise the
  text is searched as a normal query.

## [0.10.0] - 2026-10-28

A launcher that learns which apps you actually use.

### Added

- **Pinned apps.** **Ctrl + D** (or **Pin to top** in the details panel) keeps the selected app in a
  new `Pinned` section at the top of the empty bar; the same action unpins it. Pins are stored per
  user and survive restarts and app reindexing, and a pinned app gets a small boost when it matches.
- **Frecency ranking.** Usage is now weighted by recency: a recently and frequently used app rises
  among similar matches, with a 30-day half-life so old counts fade. The bonus stays below the next
  match tier, so exact, prefix and word-start name matches still win.

### Changed

- Suggestions are ordered by frecency instead of the raw use count.

## [0.9.0] - 2026-10-28

Your bookmarks and your own shortcuts, next to your apps.

### Added

- **Browser bookmarks.** An optional feature (off by default) that adds the bookmarks of every
  Chrome, Edge, Brave, Vivaldi, Chromium and Opera profile (Beta, Dev, Canary and Nightly builds
  included), plus Firefox, Waterfox, LibreWolf, Zen and Floorp, to the search. Rows carry a gold
  star and show the folder and browser they come from; **Enter** opens the page and
  **Ctrl + Enter** copies the address. The same URL saved in two profiles is listed once, up to
  three matches appear below your app matches, and `bm:` searches bookmarks alone. Only each
  profile's bookmark file (Firefox's compressed backups for the Firefox family) and its name are
  read, locally: no history, cookies, passwords, favicons or network. Chromium changes are picked up
  the next time the bar opens; Firefox follows its own backup schedule.
- **Entry triggers.** Every custom entry can have a typed alias in the manager: typing `yt cats`
  runs the *YouTube* entry at once, selected at the top of the list, passing `cats` as its
  `{query}` (or pre-filling its first required field when it has no `{query}`). The app matches
  stay below, so an alias never blocks them.
- **Per-entry shortcuts.** An entry can own a key combination (Ctrl+Alt+T, for example) that runs it
  while the launcher is open. The launcher matches it in its own window, so it never takes a
  combination away from Windows or another application and never fires while the bar is closed.
  Entries that ask for values open their form; the rest launch directly.

### Changed

- **Custom entries are managed in the launcher itself.** The editor now has seven fields (name,
  type, target, arguments, keywords, trigger and shortcut), sized so all of them fit at once.
- The docs and the settings reference now point to the in-app **Custom entries** manager instead of
  a settings list that never existed.

## [0.8.1] - 2026-10-25

Custom entries now ask for their values.

### Added

- **A form for custom entries.** When an entry's required values are still empty, selecting it opens a
  keyboard-first form instead of launching with something missing: **Tab** and the arrows move
  between fields, **Enter** runs, **Esc** goes back, and **Shift + Enter** opens the form even when
  every value is already filled (so a pre-filled one can be changed). The form previews the final
  address, path or command as you type and keeps the usual text-editing keys.
- **Placeholders beyond `{query}`.** Any name can be used in a target or its arguments: `{folder}`
  (required), `{folder?}` (optional), `{branch=main}` (pre-filled, `{branch?=main}` for optional and
  pre-filled) and `{query}` (the extra words typed after the entry's name). Names are
  case-insensitive and ignore spaces, `_` and `-`, `{{` and `}}` are literal braces, and a value
  used twice is only asked once.
- **Problems are reported before launching.** A missing path, an unknown program, or arguments typed
  into the target now show up in the form with a clear message instead of the entry silently doing
  nothing. A bare program name that the shell may still resolve through an installed app only asks
  for a second Enter.

### Changed

- **Only `{query}` is URL-encoded** in a Website target; values from other fields are inserted
  exactly as typed, so a field can carry a path, a `user/repo` value or a whole base address without
  its slashes and colons being escaped.

## [0.8.0] - 2026-10-25

A smarter app list and your own entries next to it.

### Added

- **Desktop shortcuts in the app list.** The index now also reads the two Desktop folders (yours
  and the shared one), so portable programs and shortcuts that installers only put on the Desktop
  are found like any other app. Only shortcuts that really start a program are used; documents,
  missing targets and Windows' Store-app aliases are left out. The automatic index notices
  shortcuts added to or removed from the Desktop as well.
- **Custom entries.** The launcher gains its own keyboard-first **Custom entries** manager for your
  own websites, files, folders and commands (open it by searching for *Custom Entries*). Each entry
  has a name, a type (**Website**, **File or folder**, **Command**), a target, optional arguments
  and optional search keywords. Entries are searched like apps (no prefix) and appear after the
  matching apps. `{query}` in the target or arguments is replaced with the extra words you type
  after the entry's name — for websites it is URL-encoded — so an entry named *YouTube* with the
  target `https://www.youtube.com/results?search_query={query}` turns **YouTube cats** into a
  YouTube search for "cats", and a command such as `wt.exe -d {query}` opens Windows Terminal where
  you typed.

### Changed

- **Nothing is listed twice.** Apps are now identified by what they actually run (the program and
  its arguments, or the packaged app id) instead of by their display name. A shortcut that exists
  in both the Start menu and the Desktop, or one installed for all users and for one user, shows
  up once. Two different programs that happen to share a name are both kept and get a short
  suffix (the program's folder, or **Store**) so the rows can be told apart.

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
