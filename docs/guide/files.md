# Files

A folder button at the right of the search box switches between apps and files (the **Tab** key does
the same, except while a calculation is on screen). The **File browser** setting can turn the whole
mode off, hiding the button and leaving Tab for the app list.

In file mode the bar shows a **Files** chip (folder icon, name and a close button), a row of location
chips (**Home**, **Downloads**, **Documents**, **Pictures**, **Music**, **Videos**) and a **path bar**
with the folder you are in. When the path is long, only the start is shortened (`…\MDG\logs`) so the
last folders stay visible.

## In this page

- [Locations and drives](#locations-and-drives)
- [Browsing](#browsing)
- [Sorting](#sorting)
- [Filters](#filters)
- [Deep search](#deep-search)
- [Preview and the actions menu](#preview-and-the-actions-menu)
- [Editing the path](#editing-the-path)
- [Shortcuts](#shortcuts)

## Locations and drives

- The location chips resolve to each folder's real location, so they keep working when Windows has
  moved or redirected a folder (a OneDrive-backed Documents, for example).
- With two or more ready drives, a **second row of drive chips** (`C:`, `D:`, `X:` …) appears below
  them. One chip per fixed or removable drive that is actually ready: an empty card reader or a
  disconnected network drive is skipped, so nothing pops a *there is no disk* dialog.
- **Ctrl + Tab** / **Ctrl + Shift + Tab** cycle through the drives, **Ctrl + 1…9** jumps to a chip
  (locations first, then drives), and a path such as `D:\` can always be typed.
- Going up from a drive root (**←**, **Backspace** or **Alt + ↑**) opens a **This PC** view listing
  every drive.
- **Start drive** sets which drive the browser opens on the first time in a session; empty (or an
  unavailable drive) opens on Home.

> [!NOTE]
> The drive row only appears with two or more ready drives. With a single drive, the location chips are
> the whole navigation — type a path in the path bar for anything outside your profile.

## Browsing

**Enter** (or **→**) on a folder goes into it; **Enter** on a file opens it. Folders come first, and
each row has a metadata line (type, size, date and the containing folder). Images show a thumbnail;
other files show a type icon based on their extension.

Very large folders stop at 5,000 folders and 5,000 files and the path bar says how many of the total
are listed; typing searches past that cap. Extremely wide or tall images are center-cropped to fill the
square without stretching.

> [!NOTE]
> Previews decode in the background and are skipped for files on network drives and cloud placeholders,
> which could otherwise block the bar while they download. The file still opens normally with **Enter**.

**History**: back and forward through the folders you visited (**Alt + ← / →** or the mouse buttons),
going back highlights the folder you came from.

## Sorting

**Ctrl + S** (or **Sort…** in the actions menu) opens the sort list with the order in use marked:
name A-Z (the default), name Z-A, type, modified date (newest and oldest) and size (largest and
smallest). Folders always stay on top; the order also applies while you filter, and deep-search
results keep their relevance order.

**Remember file sort** keeps the chosen order across closes and restarts.

> [!TIP]
> With **Remember file sort** off (the default), the order you pick still holds while the bar is open —
> navigating, filtering and switching between Files and apps keep it. It only resets to name A-Z the next
> time you open the launcher.

## Filters

Combine them with normal text, in any order; the active filters are shown in the path bar.

| Filter | Meaning |
| --- | --- |
| `*.pdf` or `ext:pdf` | Only that extension (`ext:png,jpg` for several) |
| `type:image` | A category: `image`, `doc`, `audio`, `video`, `archive`, `code` |
| `dir:` / `folder:` | Only folders (`dir:logs` = folders named logs) |
| `file:` | Only files |

For example `report *.pdf` or `dir: projects`.

## Deep search

Whatever you type is searched in the current folder *and all its subfolders*; results show the folder
they live in and appear while the search is still running, closest matches first. Dot-folders such as
`.claude` are included; other hidden/system items and offline or cloud folders are skipped. The scan
stops when the bar closes.

With **File search engine** set to **Everything** this search is answered by the Everything index
instead: instant, still restricted to the current folder, and still applying the active filters. See
[File search](file-search.md).

## Preview and the actions menu

**Ctrl + Q** previews the selected file in the details panel: images, text and code with syntax-free
line numbers, and the usual file details for everything else.

**Ctrl + I** (or your configured details key) opens a menu for the highlighted item: open, show in its
folder, reveal in your file manager, run as administrator, terminal here, rename, copy path / name /
file, new folder, new file, properties, and move to the Recycle Bin (asks for a second Enter). Copying
keeps the bar open and the footer confirms it with *Copied*.

> [!WARNING]
> *Move to Recycle Bin* is the one destructive action here, and it asks for a second **Enter**. Rename,
> new folder and new file act immediately — there is no undo in the bar.

## Editing the path

Click the path bar (or **Ctrl + L** / **Alt + D**) and type or paste a path. It understands `~`,
`%USERPROFILE%`, quotes (Copy as path), `/` slashes, `..` and paths relative to the current folder.
**Tab** completes folder names (Shift + Tab goes back). **Enter** goes there — a file path opens its
folder with the file highlighted — and **Esc** cancels.

## Shortcuts

| Shortcut | Action |
| --- | --- |
| **Enter** / **→** | Open the file / enter the highlighted folder |
| **←** (empty box) | Parent folder (from a drive root, **This PC**) |
| **Backspace** (empty box) | Up one folder |
| **Alt + ← / →** | Back / forward |
| **Alt + ↑** | Parent folder |
| **Alt + Home** | Home |
| **Ctrl + 1…9** / **Ctrl + ←/→** (empty box) | Jump to a location or drive chip |
| **Ctrl + Tab** / **Ctrl + Shift + Tab** | Next / previous drive |
| **Ctrl + L** / **Alt + D** | Edit the path |
| **Ctrl + Q** | Preview the file |
| **Ctrl + S** | Sort the list |
| **Ctrl + I** | Actions menu |
| **Ctrl + Enter** | Show in your default file manager |
| **Ctrl + Shift + Enter** | Run as administrator (programs) |
| **Ctrl + G** | Show the item in its own folder |
| **F2** | Rename |
| **Ctrl + Shift + N** | New folder |
| **Ctrl + T** | Open a terminal in the folder |
| **Ctrl + P** | Properties |
| **Ctrl + Shift + C** | Copy the path |

Switching modes clears the query and file mode is not remembered between opens; the contents are read
live from disk. Deleting, renaming or creating a folder or file keeps the bar open in the same folder.

---

**Prev:** [Prefixes and commands](prefixes-and-commands.md) | **Next:** [Clipboard history](clipboard.md) →
