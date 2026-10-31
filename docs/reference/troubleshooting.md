# Troubleshooting

> [!TIP]
> Read the footer before searching this page. It carries the reason with a colour: **amber** when a
> problem is the cause, **red** when something needs care. The same tones appear in the empty list and in
> the error bands.

## In this page

- [The bar and the shortcut](#the-bar-and-the-shortcut)
- [Missing results](#missing-results)
- [Clipboard](#clipboard)
- [Files and previews](#files-and-previews)
- [Windows and other programs](#windows-and-other-programs)
- [After an update](#after-an-update)
- [What the mod stores](#what-the-mod-stores)
- [Reporting a problem](#reporting-a-problem)

## The bar and the shortcut

### The shortcut does nothing

- **Another program owns the combination.** Windows and some apps reserve theirs (input-method
  editors, utilities, games). The launcher warns you instead of fighting over it; pick a different
  combination in the settings.
- **A fullscreen window is focused.** With **Disable in fullscreen** on (the default), the shortcut
  stays quiet while a game, video player or fullscreen browser is in front. Leave fullscreen or turn
  the option off.
- **Windhawk is not running the mod.** Check the mod is enabled in Windhawk's **Installed mods**.

### Alt + Space does not open it, or the window menu is gone

**Alt + Space** is also the system shortcut for a window's title-bar menu (Move, Size, Close…). While
the mod uses it, that menu is not reachable by keyboard. Choose another combination in the settings if
you use it.

### The bar looks flat, with no blur

The blurred effects (every one except **Solid**) need Windows' **Transparency effects**:
**Settings → Personalization → Colours → Transparency effects**. With it off, Windows draws no blur and
those effects fall back to a flat colour.

## Missing results

### Recent files is empty

Windows must be recording recent items:

- **Windows 11:** Settings → Personalization → Start → **Show recently opened items in Start, Jump
  Lists, and File Explorer**.
- **Windows 10:** the equivalent **Show recently used files** option.

With that off, Windows keeps its Recent folder empty and `recent:` has nothing to show.

### Bookmarks do not appear

- **Browser bookmarks** is off by default. Turn it on in the settings.
- Chromium bookmarks are read when the bar opens, so a change made a second ago may need a reopen.
- Firefox writes its bookmark backups on its own schedule; a brand-new Firefox bookmark can take
  longer to appear.
- A bookmark saved twice (two browsers, or two profiles) is listed once.

### `find:` is slow, or misses files

- The built-in scan walks your folders live and stops at its cap, so a very large tree may show partial
  results. Narrow the query, or add the folder to **Extra search folders**.
- Setting **File search engine** to **Everything (voidtools)** answers from its index in milliseconds,
  as long as Everything is installed and running.
- `find:` searches **names**, not file contents.

### The footer says "Everything not running · built-in scan"

Everything was chosen as the file search engine but is not answering (not installed, not running, or
slower than a second). The built-in scan took over so the search keeps working. Start Everything, or
switch the engine back to **Built-in scan**.

## Clipboard

### Clipboard history stays empty

- **Clipboard history** is off by default; turn it on in the settings.
- Copies that an app marks as private are skipped on purpose. Password managers set that flag, and
  Windows' own clipboard history skips them the same way.
- Very large text copies (over about 8,000 characters) are ignored.

### Pasting went to the wrong place

The launcher pastes into the window you came from. If Windows does not allow restoring that window (an
elevated app, for example), the entry stays on the clipboard so you can paste it yourself.

## Files and previews

### File previews are blank

Previews are skipped for files on network drives and for cloud placeholders, which could otherwise
block the bar while they download. The file still opens normally with **Enter**.

## Windows and other programs

### A window stays above everything else

It was pinned with **Ctrl + Shift + T** in `win:`. That state belongs to the window, not to the
launcher, so it survives closing the bar. Open `win:`, find the row — it wears a **gold pin** on its
icon and says **On top** — and press **Ctrl + Shift + T** again.

### I cannot close or move a window

Windows blocks cross-process work between programs of different integrity levels. A window whose
program runs **as administrator** cannot be closed, minimized or moved from the launcher, and the
footer says *Needs administrator · can't control that window* in amber.

The same message frame covers the other cases: *No other monitor in that direction* on a single-monitor
setup, nothing at all when the window has already closed (the row is re-read and disappears), and the
same amber notice when a window that stopped responding never reacts to the action — the launcher stays
usable the whole time.

### `find:` shows folders Explorer does not

With **File search engine** set to **Everything**, the answers come from its index, which includes
hidden folders such as `AppData` or `ProgramData`. The built-in scan skips them. Switch the engine
back to **Built-in scan** if you only want what Explorer would show you.

### The bar closes when I minimize a window

That was a bug before 1.1.0: minimizing took the focus away and the launcher treated it as a click
outside. From 1.1.0 the bar stays open for every window action, and gives itself the keyboard back.

## After an update

### The Settings tab shows values I did not choose

After a release that regroups options, the tab shows the defaults until you save it once. Saving applies
what the tab shows, so review it the first time after a big update.

## What the mod stores

Everything the mod saves stays on this PC and never leaves it.

| What | Where | How to delete it |
| --- | --- | --- |
| Settings, pinned apps, app usage, learned pairs, custom entries | Windhawk's storage for the mod, per user | Reset the mod's settings in Windhawk, or remove the mod |
| Clipboard history, text and images | Windhawk's storage and the mod's own folder, encrypted for your Windows account | **Clear Clipboard History** in the `>` menu, turn the feature off, or remove the mod |

> [!CAUTION]
> Removing the mod deletes the folder Windhawk gives it, clipboard images included. Erase the history
> from the `>` menu first if you want to keep anything.

Turning **Clipboard history** off erases what it saved, image files included. Bookmarks, recent files
and window titles are read live and never stored.

## Reporting a problem

Open an [issue](https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/issues) with:

- your Windows build (`winver`) and Windhawk version;
- the mod version (shown in Windhawk's mod page);
- the steps that reproduce it and what you expected instead;
- a screenshot or short clip when the problem is visual.

---

**Prev:** [Settings reference](settings.md) | **Next:** [Documentation index](../index.md) →
