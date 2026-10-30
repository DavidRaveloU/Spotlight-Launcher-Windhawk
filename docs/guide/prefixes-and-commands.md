# Prefixes and commands

Start the query with a short prefix to pick a mode. While one is active, a small tag shows it at the
left of the search box. Web prefixes keep the bar compact (press **Enter** to search); `>` expands the
command list.

| Prefix | Mode |
| --- | --- |
| `?` | Search the web (forces a search even for something that looks like a web address) |
| `>` | Commands |
| `bm:` | Search only browser bookmarks |
| `clip:` | Search the clipboard history |
| `recent:` | Search Windows' recent files |
| `find:` | Search file and folder names in Home and the extra folders |
| `win:` | List and switch to open windows |
| `g:` | Search on Google |
| `b:` | Search on Bing |
| `d:` | Search on DuckDuckGo |
| `y:` | Search on YouTube |
| `w:` | Search on Wikipedia |

> [!IMPORTANT]
> A prefix only works while its feature is enabled. With **Browser bookmarks** off, `bm:` is not a mode —
> the text is searched as a normal query.

## You do not have to remember them

Typing the name of a mode shows it as one more result, like an app — **Open Windows** (also found by
*windows manager* or *switcher*), **Bookmarks**, **Clipboard History**, **Recent Files**, **All Files**
and **Commands**. **Enter** switches into that mode and fills in the prefix. They only appear while
their feature is enabled, and they do not filter by themselves.

> [!TIP]
> Prefixes are for narrowing a list you are already in (`win: chrome`). The mode names are for getting
> there without remembering the syntax.

## Commands

Type `>` to list the built-in commands and narrow them as you type (for example `>task`). **Enter**
runs the selected one.

| Command | What it does |
| --- | --- |
| Lock | Locks the PC |
| Sleep | Puts the PC to sleep |
| Hibernate | Hibernates the PC (two-step) |
| Shut Down | Shuts the PC down (two-step) |
| Restart | Restarts the PC (two-step) |
| Sign Out | Signs the current user out (two-step) |
| Task Manager | Opens Task Manager |
| Control Panel | Opens the classic Control Panel |
| Device Manager | Opens Device Manager |
| Services | Opens Services |
| Registry Editor | Opens the Registry Editor |
| Network Connections | Opens the network adapters |
| Settings | Opens the Settings app |
| Windows Update | Opens Windows Update |
| Installed Apps | Opens Apps & features |
| Display Settings | Opens Display settings |
| Sound Settings | Opens Sound settings |
| Bluetooth | Opens Bluetooth settings |
| Printers & Scanners | Opens Printers & scanners |
| Terminal | Opens Windows Terminal (PowerShell if it is not installed) |
| File Explorer | Opens File Explorer |
| Empty Recycle Bin | Empties the Recycle Bin (two-step) |
| Clear Clipboard History | Erases the clipboard history (two-step) |

### Two-step commands

The destructive ones — **Hibernate**, **Shut Down**, **Restart**, **Sign Out**, **Empty Recycle Bin**,
**Clear Clipboard History**, and *Move to Recycle Bin* in the file actions — ask for a second **Enter**:
the footer turns red and shows an "again to confirm" warning.

> [!WARNING]
> The second **Enter** is the only confirmation: there is no undo for these. Pressing any other key,
> moving the selection or waiting a few seconds cancels the command, and holding the key down does not
> count as the confirmation.

---

**Prev:** [Search](search.md) | **Next:** [Files](files.md) →
