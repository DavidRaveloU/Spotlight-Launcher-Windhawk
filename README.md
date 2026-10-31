<div align="center">

# Spotlight Launcher For Windhawk

A fast, keyboard-driven launcher for Windows, packaged as a [Windhawk](https://windhawk.net) tool mod.

Press **Alt + Space**, type a few letters, press **Enter**. That is the whole idea.

<br>

<a href="https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/blob/main/LICENSE">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="License: MIT">
</a>
<a href="https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/blob/main/version.json">
  <img src="https://img.shields.io/badge/dynamic/json?url=https://raw.githubusercontent.com/DavidRaveloU/Spotlight-Launcher-Windhawk/main/version.json&query=%24.version&label=version&prefix=v&color=informational" alt="Version">
</a>
<a href="https://www.microsoft.com/windows">
  <img src="https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0078D6" alt="Platform: Windows 10/11">
</a>
<a href="https://windhawk.net">
  <img src="https://img.shields.io/badge/Windhawk-mod-orange" alt="Windhawk mod">
</a>

</div>

Spotlight Launcher indexes the same applications you see in the Start menu, classic programs and
Microsoft Store apps alike, and filters them as you type. From there it reaches further: your files and
folders, the clipboard, browser bookmarks, Windows' recent files, open windows, a calculator and a set of
built-in commands. It runs as its own Windhawk **tool** mod, so it never runs inside File Explorer and
cannot affect the way Windows works.

## Screenshots

<p align="center">
  <img width="700" alt="Spotlight Launcher over the desktop" src="https://github.com/user-attachments/assets/01cd7347-51df-4d22-879e-d44fd35a7ae9" />
</p>

The search bar over the desktop with the default **Midnight** colour and **Acrylic** effect. A short
query already filtered a handful of results, with the matching letters highlighted.

<p align="center">
  <img width="700" alt="Details panel" src="https://github.com/user-attachments/assets/22784b9b-2a83-45f9-bf97-1cd6934d755a" />
</p>

An app selected with the details panel open on the right (**Ctrl + I**): the actions list and the
technical info table.

Some of the built-in looks — the **Aurora** effect in three colours, plus **Frosted**, **Glass** and
**Mica**:

<table align="center">
  <tr>
    <td align="center"><img width="230" alt="Aurora Amber" src="https://github.com/user-attachments/assets/863112a5-e583-4050-9eae-c1a03988837a" /><br><b>Aurora</b> &middot; Amber</td>
    <td align="center"><img width="230" alt="Aurora Emerald" src="https://github.com/user-attachments/assets/6f583ae0-95a4-4759-b172-f9d5e8ca66f2" /><br><b>Aurora</b> &middot; Emerald</td>
    <td align="center"><img width="230" alt="Aurora Violet" src="https://github.com/user-attachments/assets/0c3c4e1c-ca18-4749-aa8b-d27035d9cf52" /><br><b>Aurora</b> &middot; Violet</td>
  </tr>
  <tr>
    <td align="center"><img width="230" alt="Frosted" src="https://github.com/user-attachments/assets/a8a61a62-ed41-4f1e-bb8b-01bbb9526d0c" /><br><b>Frosted</b></td>
    <td align="center"><img width="230" alt="Glass" src="https://github.com/user-attachments/assets/8df98cf2-112c-4936-8839-7dce259be69b" /><br><b>Glass</b></td>
    <td align="center"><img width="230" alt="Mica" src="https://github.com/user-attachments/assets/042c737e-2700-42a4-ae51-96e94e164c77" /><br><b>Mica</b></td>
  </tr>
</table>

## Highlights

- **Instant, forgiving search.** Case- and accent-insensitive, multi-word and acronym matching, with the
  letters that matched highlighted. Results are ranked by match quality, then by how often and how
  recently you use them, and an app you pick after typing a few letters comes first next time.
- **Files, without a second window.** Browse your drives and folders in the bar: locations and drive
  chips, sorting, previews, and rename, copy, terminal and Recycle Bin actions. Narrow the list with
  `*.pdf`, `type:image`, `dir:`, and now by size and date too: `size:>10mb`, `modified:today`.
- **Global file search.** `find:` searches file and folder names under Home and any extra folders, with
  no index to build, using the same filters: `find: report size:>1mb modified:week`. Point it at
  **Everything** (optional) and the same queries are answered from its index in milliseconds, with size
  and date for every row.
- **Window switcher.** `win:` lists your open windows; **Enter** brings the selected one to the front.
  It can also **close**, **minimize**, **pin on top** or **move to another monitor** the selected
  window without switching to it, and a panel shows its process, state and path. Launching an app that
  is already open still focuses it instead of starting a second copy.
- **Clipboard history (opt-in, encrypted).** Off by default. When on, it keeps the last 30 things you
  copied, text and images, and `clip:` searches them. Everything is encrypted for your Windows account,
  copies an app marks as private are skipped, and turning the feature off erases what it saved.
- **Browser bookmarks (off by default).** Chrome, Edge, Brave, Vivaldi, Chromium, Opera, Firefox,
  Waterfox, LibreWolf, Zen and Floorp, read locally from the bookmark files — `bm:` searches only
  bookmarks.
- **Recent files.** The empty bar shows the files and folders from Windows' Recent list, and `recent:`
  searches them. Windows must be recording recent items (Settings → Personalization → Start), or the
  list stays empty.
- **Custom entries.** Your own sites, folders and commands, with placeholders that ask for the values
  they need, plus an optional typed trigger or in-launcher shortcut per entry.
- **A calculator, commands and settings pages.** Type a calculation and the result appears as you go;
  `>` reaches lock, sleep, Task Manager, Settings pages and more, destructive ones asking for a second
  Enter.
- **Built to look right.** Six effects, twelve colours, live blur, adjustable opacity and position, and
  soft interface sounds generated inside the mod.

## Install

1. Install [Windhawk](https://windhawk.net) (Windows 10 or 11).
2. In Windhawk, open **Mods**, search for **Spotlight Launcher** and click **Install**.
3. Press **Alt + Space** to open it.

From source: download [`spotlight-launcher.wh.cpp`](spotlight-launcher.wh.cpp), choose **Create a new
mod** in Windhawk, paste it in place of the editor contents and save.

## The first five keys

| Key | Action |
| --- | --- |
| **Alt + Space** | Open and close the bar (configurable) |
| **↑ / ↓**, **Enter** | Move the selection, open it |
| **Tab** | Switch between apps and Files |
| **Ctrl + I** | Actions and details panel |
| **F1** | The cheat sheet: every shortcut, prefix and filter |

## Documentation

**[Read the documentation →](docs/index.md)** — installation, every prefix and command, the file
browser and its filters, the window actions, the clipboard, custom entry placeholders, the full
calculator syntax, every setting and troubleshooting.

## Contributing

Bug reports, fixes, new features, translations and documentation corrections are welcome. Open an
[issue](https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/issues) with your Windows build,
the mod version, the steps to reproduce it and, when it is visual, a screenshot or a short clip.

For a pull request: fork, branch from `main`, change `spotlight-launcher.wh.cpp`, confirm it compiles
and open the PR describing **what** changed and **why**. One bug or feature per PR is much easier to
review.

Leave `@version` in the mod header and `version.json` alone: the maintainer sets both when a release is
published on Windhawk, so they always agree with what the store shows.

If the change adds, edits or removes a feature, update its page in [`docs/`](docs/index.md) in the same
pull request. Documentation corrections are welcome too — keep the existing structure (one page per
area, `docs/index.md` as the entry point) and describe what a user does and sees, not how it is
implemented.

## License

Released under the **MIT License**. See [`LICENSE`](LICENSE).

Copyright (c) 2026-present David Ravelo.
