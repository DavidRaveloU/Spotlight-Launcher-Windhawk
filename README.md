<div align="center">

# Spotlight Launcher For Windhawk

A fast, keyboard-driven application launcher for Windows, packaged as a [Windhawk](https://windhawk.net) tool mod.

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

Spotlight Launcher indexes the same applications you see in the Start menu (both classic programs and Microsoft Store apps) and filters them as you type. It runs on its own, as a Windhawk mod, so it never runs inside File Explorer and cannot affect the way Windows works.

---

## Screenshots

### Main

<p align="center">
  <img width="700" alt="Desktop" src="https://github.com/user-attachments/assets/01cd7347-51df-4d22-879e-d44fd35a7ae9" />
</p>

The search bar over the desktop, with the default **Midnight** colour and **Acrylic** effect. A short query already filtered a handful of results, with the matching letters highlighted. This is the launcher's first impression.

### Details panel

<p align="center">
  <img width="700" alt="Details" src="https://github.com/user-attachments/assets/22784b9b-2a83-45f9-bf97-1cd6934d755a" />
</p>

An app selected with the details panel open on the right (**Ctrl + I**): the actions list and the technical info table.

### Look and feel

These are some of the built-in looks (themes): the **Aurora** effect in three colours, plus **Frosted**, **Glass** and **Mica**.

<table align="center">
  <tr>
    <td align="center">
      <img width="250" alt="Aurora Amber" src="https://github.com/user-attachments/assets/863112a5-e583-4050-9eae-c1a03988837a" /><br>
      <b>Aurora</b> &middot; Amber
    </td>
    <td align="center">
      <img width="250" alt="Aurora Emerald" src="https://github.com/user-attachments/assets/6f583ae0-95a4-4759-b172-f9d5e8ca66f2" /><br>
      <b>Aurora</b> &middot; Emerald
    </td>
    <td align="center">
      <img width="250" alt="Aurora Violet" src="https://github.com/user-attachments/assets/0c3c4e1c-ca18-4749-aa8b-d27035d9cf52" /><br>
      <b>Aurora</b> &middot; Violet
    </td>
  </tr>
  <tr>
    <td align="center">
      <img width="250" alt="Frosted" src="https://github.com/user-attachments/assets/a8a61a62-ed41-4f1e-bb8b-01bbb9526d0c" /><br>
      <b>Frosted</b>
    </td>
    <td align="center">
      <img width="250" alt="Glass" src="https://github.com/user-attachments/assets/8df98cf2-112c-4936-8839-7dce259be69b" /><br>
      <b>Glass</b>
    </td>
    <td align="center">
      <img width="250" alt="Mica" src="https://github.com/user-attachments/assets/042c737e-2700-42a4-ae51-96e94e164c77" /><br>
      <b>Mica</b>
    </td>
  </tr>
</table>

The rest (the **Acrylic**, **Mica** and **Solid** effects, and the remaining colours — Midnight blue, Graphite, Black, Teal, Rose, Crimson, Sky, Lavender, White) are described in the [Features](#features) section below.

---

## Features

### Instant, forgiving search
* Filters classic programs, Microsoft Store apps and shortcuts on your Desktop as you type.
* Case- and accent-insensitive.
* Multi-word queries (`visual code`) and acronyms (typing the initials of each word, like `vsc`).
* Matching letters are highlighted in the result.
* Results show a friendly name plus the file or package they open.
* **Frecency**: a recently and frequently used app rises among similar matches (usage decays with a 30-day half-life, so old use counts fade).
* **Pinned apps** stay in a `Pinned` section at the top of the empty bar and get a small boost when they match.
* Each app appears **once**: shortcuts from the Start menu and the Desktop that open the same program are merged, while two different programs that happen to share a name are both kept and labelled so they can be told apart.

### Keyboard-first
Everything is reachable without touching the mouse.

| Shortcut | Action |
| --- | --- |
| **Alt + Space** | Open / close the search bar (configurable) |
| **↑ / ↓** | Move the selection |
| **Tab** | Switch between apps and Files (when the file browser is on) |
| **F1** | Show the shortcut and calculator cheat sheet |
| **Enter** | Open the selected app |
| **Esc** | Close the details panel, then the search bar |
| **Ctrl + Enter** | Open the file location (on a bookmark, copy its address; on a recent file, open its folder) |
| **Ctrl + Shift + Enter** | Run as administrator |
| **Ctrl + Shift + C** | Copy the path |
| **Ctrl + P** | Properties |
| **Ctrl + Shift + R** | Remove from recents (or the selected clipboard entry) |
| **Ctrl + I** | Toggle the details panel (configurable) |
| **Ctrl + D** | Pin / unpin the selected app or clipboard entry |
| **Ctrl + R** | Reindex the app list |
| Mouse wheel | Scroll the list without changing the selection |
| Mouse hover | Highlight the row under the cursor |
| **Ctrl + 1…9** | Jump to a location or drive chip (Home, Downloads, …, `C:`, `D:`) |
| **Ctrl + Tab** / **Ctrl + Shift + Tab** | Switch to the next / previous drive (`C:`, `D:`, `X:`, …) |
| **Ctrl + L** / **Alt + D** | Edit the current folder path |
| **Ctrl + Q** | Preview the highlighted file |
| **Ctrl + S** | Sort the Files list (name, type, modified date, size) |
| **F2** | Rename the highlighted file or folder |
| **Ctrl + Shift + N** | Create a folder |
| **Ctrl + T** | Open a terminal in the current folder |
| **Ctrl + G** | Show the item in its own folder |
| **Alt + ← / →** | Back / forward through visited folders |

Press **F1** at any time (or click **Help** in the footer) for a cheat sheet with every shortcut, prefix and file filter; it scrolls when a page is longer than the card. It has a second **Calculator** page (**Tab** or the tab itself) with the full syntax reference.

> **Note:** **Alt + Space** is also the system shortcut for a window's title-bar menu (Move, Size, Close…). While the mod is enabled with the default shortcut, that menu is not reachable by keyboard, so pick another combination in the settings if you use it.

### Details panel
Press **Ctrl + I** (or **Ctrl + K** / **Ctrl + Space** / **F4**) with an app selected to reveal a right-hand panel with actions and extra details. The actions also work with the panel closed. File actions are only offered for classic programs; Microsoft Store apps offer *open*, *pin* and *remove from recents*.

**Pin to top** (also **Ctrl + D**) keeps the selected app in the `Pinned` section of the empty bar; the same action unpins it. Pins are stored per user and survive restarts and app reindexing.

### Built-in calculator
Type a calculation and the result appears as you go: a highlighted card at the top of the list shows it, and it is also shown faintly next to what you typed. Press **Enter** to copy the result; recent results are kept so you can reuse them. It only reacts when the whole text looks like a calculation, so ordinary searches are left alone.

The full reference is in **F1 → Calculator**; in short:

| You can type | Examples |
| --- | --- |
| Arithmetic, powers, factorials | `(2+3)*4`, `2^10`, `5!` |
| Percentages | `15%`, `100 - 15%`, `20% of 150` |
| Functions | `sqrt`, `cbrt`, `abs`, `round`, `floor`, `ceil`, `trunc`, `sign`, `sin`, `cos`, `tan`, `asin`, `acos`, `atan`, `sinh`, `cosh`, `tanh`, `log`, `ln`, `log2`, `exp`, `fact` |
| Constants and last result | `pi`, `e`, `tau`, `phi`, `ans` |
| Units and bases | `10 km to mi`, `100 f to c`, `255 to hex`, `0xFF`, `0b1010`, `0o17` |

Trigonometry works in radians, `mod` is the remainder (`10 mod 3`), and `%` after a number is a fraction (`15%` = 0.15) except after `+` or `-`, where it applies to the left side (`100 - 15%` = 85).

### Web search
With **Web search** on, a **Search the web for …** result appears at the end of the list for whatever you type (it is not offered while the text is being used as a calculation). Press **Enter** on it to open the search in your default browser. The engine is configurable: **Google** (default), **Bing**, **DuckDuckGo**, **YouTube** or **Wikipedia**. If what you type looks like a web address (for example `gmail.com` or `https://localhost:3000`), the result becomes **Open …** and opens the site directly.

### Windows settings
Searching for a common settings page (for example `bluetooth`, `display`, `sound`, `update`, `wifi`, `storage` or `power`) also offers a **Setting** result that opens the matching page in the Settings app. These need no prefix and appear after your app matches; a valid calculation hides them, just like the web result.

### Learning from your choices
With **Learn from your choices** on (it is on by default), picking an app after typing a few words teaches the launcher exactly that: the next time you type those same words, that app is the first result. One pick is enough, and it works even when the app was matching weakly — typing `ex` and choosing **Firefox** puts Firefox on top from then on, where `Excel` would otherwise win. It only affects those words: `excel`, `explorer` or any other query keeps its normal order, and an app you pick by its full name still opens as expected.

The pairs are stored locally per user, capped at 200, and one you stop picking is forgotten after 90 days. Turn the setting off to search with the plain ranking again.

### Browser bookmarks
**Browser bookmarks** is off by default; turn it on in the mod settings. When it is on, the launcher searches the bookmarks of every installed **Chrome**, **Edge**, **Brave**, **Vivaldi**, **Chromium** and **Opera** profile (including their Beta, Dev, Canary and Nightly builds), plus **Firefox**, **Waterfox**, **LibreWolf**, **Zen** and **Floorp**, next to your apps. Bookmark rows carry a gold star and show the folder and browser they come from; **Enter** opens the page and **Ctrl + Enter** copies the address. A bookmark saved in two browsers or profiles is listed once.

Type `bm:` to search only bookmarks, for example `bm: docs` or `bm:` on its own to browse them. Normal searches add up to three bookmark matches below your app matches, before the Settings and web rows.

Everything is read locally from each profile's bookmark file and its name (Firefox bookmarks come from its own compressed backups). The mod never reads history, cookies, passwords or favicons, and never touches the network. Chromium changes are picked up the next time the bar opens; Firefox writes its backups on its own schedule, so a brand-new Firefox bookmark can take longer to appear.

### Clipboard history
**Clipboard history** is off by default; turn it on in the mod settings. When it is on, the launcher keeps the last 30 things you copied and adds a `clip:` prefix that searches them. Text and images are both kept: an image is saved as a compressed PNG, shows its own thumbnail in the list, and copying the same image twice does not keep two copies.

Everything is **encrypted for your Windows account** (DPAPI) before it is written to the mod's storage, images included; another account on the same PC cannot read it. Turning the feature off erases what was saved, and copies that an app marks as private (password managers do) are skipped, the same way Windows' own clipboard history skips them. Nothing leaves the PC.

Type `clip:` on its own to list the history, or `clip: invoice` to filter it (`clip: image` narrows it to pictures). **Enter** pastes the selected entry into the window you came from; **Ctrl + Enter** copies it and keeps the bar open; **Ctrl + D** pins or unpins it; **Ctrl + Shift + R** removes it. Pinned entries stay at the top, show a small pin badge on the clipboard icon, and survive both the 30-entry trim and the retention. To erase everything, run **Clear Clipboard History** from the `>` menu (it asks for a second Enter); image files are deleted with their entries.

**Clipboard retention (days)** deletes entries older than that many days automatically, together with their image files; the default is 3 days, and 0 keeps entries until the 30-entry limit drops them. Pinned entries are never deleted.

If Windows does not let the launcher restore the previous window (an elevated app, for example), the entry stays on the clipboard so you can paste it yourself.

### Recent files
**Recent files** is on by default; turn it off in the mod settings to hide the section and the prefix. The empty bar gets a **Recent files** section with the files and folders Windows lists in its Recent folder, and `recent:` searches that list (for example `recent: invoice` or `recent: .pdf`).

> **Requirement:** Windows must be recording recent items. In Windows 11, turn on **Settings → Personalization → Start → Show recently opened items in Start, Jump Lists, and File Explorer**. On Windows 10, enable the equivalent **Show recently used files** option. With that off, Windows keeps the Recent folder empty and the section and `recent:` show nothing.

**Enter** opens the file or folder, **Ctrl + Enter** opens its folder, and **Ctrl + Shift + C** copies the path. Everything is read locally from the Recent folder; the mod never scans the disk or touches the network.

### Global file search
Type `find:` followed by words to search the **names** of files and folders under your Home folder (which includes Documents, Downloads, Desktop, Pictures and the rest) and any extra folders configured in **Extra search folders**. Results appear while the scan runs, with the folder each one lives in; the search stops when the bar closes.

**Enter** opens the file or folder, **Ctrl + Enter** opens its folder, and **Ctrl + Shift + C** copies the path. It searches names, not file contents, and it does not build an index: the scan is live and capped, so a very large tree may show partial results.

If **Everything** (voidtools) is installed and running, **File search engine** can send these queries to its index instead: the answers cover every drive Everything has indexed, arrive in milliseconds, and understand Everything's own syntax (`*.pdf`, `"exact phrase"`, `!excluded`). It talks to Everything through its IPC with no DLL or extra download, and if Everything is not running the built-in scan is used automatically, so `find:` keeps working either way; the footer says *Everything not running · built-in scan* while that happens.

### Window switcher
Type `win:` to list the open windows, newest/topmost first, with their title and process. Filter with `win: chrome` or `win: document`. **Enter** activates the selected window (a minimized one is restored), and the launcher closes. There is no index: the list is read when you use the prefix.

When you launch a classic desktop app that already has a visible window, the launcher focuses that window instead of starting a second instance. Launches that carry arguments, and packaged (Store) apps, keep their normal behaviour.

### Custom entries
Your own websites, files, folders and commands can live in the list next to your apps. Open the manager by searching for **Custom Entries** and pressing **Enter** (or from the `>` menu): it creates, edits and deletes entries for you, and no settings page is needed. Give each one a name, a type (**Website**, **File or folder** or **Command**) and a target.

| Type | What the target is | Example |
| --- | --- | --- |
| **Website** | A web address | `https://www.youtube.com/results?search_query={query}` |
| **File or folder** | A path (environment variables work) | `%USERPROFILE%\Projects` |
| **Command** | A program, with optional arguments | `wt.exe` with arguments `-d %USERPROFILE%` |

#### Asking for values
Put placeholders in the target or the arguments and the launcher asks for them when you use the entry. Fields appear in the order they are written (target first, then arguments), up to 16 distinct values.

| Placeholder | Meaning |
| --- | --- |
| `{folder}` | A required value |
| `{folder?}` | An optional value |
| `{branch=main}` | Starts pre-filled with `main`; still required unless written `{branch?=main}` |
| `{query}` | The extra words you type after the entry's name (always optional) |

When you select an entry whose required values are still empty, a small form opens in place of the list instead of launching with something missing:

* **Tab** / **Shift + Tab** and the arrow keys move between the fields, **Enter** runs the entry and **Esc** goes back to the list.
* The form is a normal text field: click a field to put the caret, and use **Ctrl + A**, **Ctrl + C**, **Ctrl + X** and **Ctrl + V** or the usual selection, word and Home/End keys.
* Optional fields carry an **Optional** tag; required ones show *Required* while empty, and the header shows which fields are in view when there are more than fit.
* A line under the fields previews the final address, path or command as you type, and a blocking problem (a missing path, a missing `.exe`, or arguments typed into the target) is reported there before anything opens.
* **Shift + Enter** skips the form and launches with the current values (if a required value is still empty, the form opens anyway); **Enter** opens the form so the values can be reviewed or changed first. The footer offers both for entries that have fields.
* An unknown bare program name is only a warning: it asks for a second Enter, because the shell may still find it through an installed app.

Write `{query}` in the target or the arguments to pass the extra words you type after the entry's name. Because the entry is searched by name, typing **YouTube cats** shows the *YouTube* entry and Enter opens the search for "cats" (URL-encoded for websites); typing just **YouTube** leaves the placeholder empty. A command such as `wt.exe` with `-d {query}` opens Windows Terminal in the folder you typed; put `{query}` in quotes (`-d "{query}"`) so a path with spaces arrives as one argument. Values from other fields are inserted exactly as typed (only `{query}` is URL-encoded for a Website), `{{` and `}}` stand for literal braces, placeholder names are case-insensitive and ignore spaces, `_` and `-` (`{my_folder}`, `{My-Folder}` and `{my folder}` are the same value), and a value used more than once is only asked once.

Entries can also have extra **search keywords**, need no prefix, and appear after the matching apps. They are only offered while you are typing (not on the empty bar), and an entry without a name or a target is ignored. Avoid starting an entry's name with `?` or `>` (or with `g:`, `b:`, `bm:`, `d:`, `y:`, `w:`): those prefixes switch the launcher into another mode.

#### Entry shortcuts
The manager gives every entry two optional shortcuts, so you do not need to remember its name or open the manager again:

| Field | What it does |
| --- | --- |
| **Trigger** | A typed alias: one lowercase word (letters, digits, `-` or `_`, up to 16 characters), unique among your entries. Typing `yt cats` runs the *YouTube* entry straight away, selected at the top of the list, with `cats` passed as its `{query}` (or pre-filling its first required field if it has no `{query}`). The normal app matches stay below, so a trigger never blocks them. |
| **Shortcut** | A key combination you can press while the launcher is open. Focus the field and press the combination (it must include **Ctrl**, **Alt** or **Win**; **Shift** can be added); **Backspace** clears it. Windows and other programs keep their own combinations, and the entry never fires while the bar is closed. If the entry asks for values, its form opens; otherwise it launches directly. |

Both are optional. A trigger or combination already used by another entry or by the launcher's own shortcut is rejected with a message when you save. Windows keeps its own combinations (such as **Win + E** or **Alt + Tab**), so those still go to Windows while the bar is open.

### Files
A folder button at the right of the search box switches between apps and files (the **Tab** key does the same, except while a calculation is on screen). The **File browser** setting can turn the whole mode off, hiding the button and leaving Tab for the app list. In file mode the bar shows a **Files** chip (folder icon, name and a close button), a row of location chips with their own icons (**Home**, **Downloads**, **Documents**, **Pictures**, **Music**, **Videos**) and a **path bar** with the folder you are in. When you have two or more drives, **a second row of drive chips** (`C:`, `D:`, `X:`, … with a disk icon) appears below the location row. When the path is long, only the start is shortened (`…\MDG\logs`) so the last folders stay visible.

* **Other drives**: the location chips live inside your user profile; a **second row of drive chips** below them covers everything else. One chip is added per fixed or removable drive that is ready — an empty card reader or a disconnected network drive is skipped, so nothing ever pops a *there is no disk* dialog — and the row appears only when you have two or more drives. **Ctrl + Tab** cycles forward through the drive chips and **Ctrl + Shift + Tab** backward; **Ctrl + 1…9** jumps straight to a chip (locations first, then drives); and you can always type a path such as `D:\` in the path bar. Going up from a drive root (**←**, **Backspace** or **Alt + ↑**) opens a **This PC** view listing every drive, so you can hop between drives with the arrows alone. Which drive the browser opens on the first time you use it in a session is set by the **Start drive** option (empty opens on Home, and so does an unavailable drive).
* **Moved folders**: the location chips resolve to each folder's real location, so Home, Downloads, Documents, Pictures, Music and Videos keep working even when Windows has moved them to another drive or redirected them (such as a OneDrive-backed Documents).

* **Browse inside the launcher**: **Enter** (or **→**) on a folder goes into it; **Enter** on a file opens it. The list shows folders first, with a metadata line (type, size, date and the containing folder). Images show a **thumbnail preview**; other files show a **type icon** based on their extension (PDF, DOC, XLS, JSON, code, audio, video, archives, …). Very large folders stop at 5,000 folders and 5,000 files, and the path bar shows how many of the total are listed; typing searches past that cap. Previews are decoded in the background (skipped for files on network drives and cloud placeholders, which could otherwise block the bar while they download); extremely wide or tall images are center-cropped to fill the square without stretching.
* **Sort the list**: **Ctrl + S** (or **Sort…** in the actions menu) opens the sort list with the order in use marked: **Name (A-Z)** — the default —, **Name (Z-A)**, **Type**, **Modified (newest first)**, **Modified (oldest first)**, **Size (largest first)** and **Size (smallest first)**. Folders always stay on top, then the files follow the chosen order; the order also applies while you filter, while deep-search results keep their relevance order. With **Remember file sort** on, the order survives closes and restarts, per user. With it off (the default) the order holds while the bar is open — navigating, filtering and switching between Files and apps keep it — and Files starts again at Name (A-Z) the next time you open the launcher.
* **Deep search**: whatever you type is searched in the current folder *and all its subfolders* (results show the folder they live in). Closer matches come first and appear while the search is still running. Dot-folders such as `.claude` are included; other hidden/system items and offline/cloud folders are skipped. The scan stops when the bar closes. With **File search engine** set to **Everything**, this search is answered by the Everything index instead: instant, and it keeps the folder restriction, the active filters and the same "closest match first" order.
* **History**: go back and forward through the folders you visited; going back highlights the folder you came from.
* **Edit the path**: click the path bar (or **Ctrl + L** / **Alt + D**) and type or paste a path. It understands `~`, `%USERPROFILE%`, quotes (Copy as path), `/` slashes, `..` and paths relative to the current folder. **Tab** completes folder names (Shift + Tab goes back). **Enter** goes there (a file path opens its folder with the file highlighted), **Esc** cancels.
* **Actions menu**: **Ctrl + I** (or your configured details key) opens a menu for the highlighted item: open, show in its folder, reveal in your file manager, run as administrator, terminal here, rename, copy path / name / file, new folder, new file, properties and move to the Recycle Bin (asks for a second Enter). Copying keeps the bar open and the footer confirms it with *Copied*.

#### Filters
Combine them with normal text, in any order; the active filters are shown in the path bar.

| Filter | Meaning |
| --- | --- |
| `*.pdf` or `ext:pdf` | Only that extension (`ext:png,jpg` for several) |
| `type:image` | A category: `image`, `doc`, `audio`, `video`, `archive`, `code` |
| `dir:` / `folder:` | Only folders (`dir:logs` = folders named logs) |
| `file:` | Only files |

For example `report *.pdf` or `dir: projects`.

#### Files shortcuts

| Shortcut | Action |
| --- | --- |
| **Enter** / **→** | Open the file / enter the highlighted folder |
| **←** (empty box) | Go to the parent folder (from a drive root, the **This PC** drives view) |
| **Backspace** (empty box) | Go up one folder (a drive root goes to **This PC**; a location root leaves file mode) |
| **Alt + ← / →** | Back / forward in the folder history (mouse back/forward buttons too) |
| **Alt + ↑** | Parent folder |
| **Alt + Home** | Home |
| **Ctrl + 1…9** / **Ctrl + ←/→** (empty box) | Jump to a location or drive chip |
| **Ctrl + Tab** / **Ctrl + Shift + Tab** | Switch to the next / previous drive (`C:`, `D:`, `X:`, …) |
| **Ctrl + L** / **Alt + D** | Edit the path |
| **Ctrl + S** | Sort the list (name, type, modified date, size) |
| **Ctrl + I** | Actions menu |
| **Ctrl + Enter** | Show in your default file manager |
| **Ctrl + Shift + Enter** | Run as administrator (programs) |
| **Ctrl + G** | Show the item in its own folder (handy after a deep search) |
| **F2** | Rename |
| **Ctrl + Shift + N** | New folder |
| **Ctrl + T** | Open a terminal in the folder |
| **Ctrl + P** | Properties |
| **Ctrl + Shift + C** | Copy the path |

Switching modes clears the query and file mode is not remembered between opens; the contents are read live from disk and the chip's close button (or **Backspace** at a location root) leaves file mode. Deleting, renaming or creating a folder or file keeps the bar open in the same folder.

### Prefixes
Start the query with a short prefix to pick a mode; while one is active, a small tag shows it at the left of the search box. Web prefixes keep the bar compact (press **Enter** to search); `>` expands the command list.

| Prefix | Mode |
| --- | --- |
| `?` | Search the web (forces a search even for something that looks like a web address) |
| `>` | Commands |
| `bm:` | Search only browser bookmarks |
| `clip:` | Search the clipboard history |
| `recent:` | Search Windows' recent files |
| `find:` | Search file and folder names in Home and extra folders |
| `win:` | List and switch to open windows |
| `g:` | Search on Google |
| `b:` | Search on Bing |
| `d:` | Search on DuckDuckGo |
| `y:` | Search on YouTube |
| `w:` | Search on Wikipedia |

A prefix only works while its feature is enabled; otherwise the text is treated as a normal query (for example, `bm:` with **Browser bookmarks** off just searches for that text).

You do not have to remember them: typing the name of a mode shows it as one more result, like an app. **Open Windows** (also found by *windows manager* or *switcher*), **Bookmarks**, **Clipboard History**, **Recent Files**, **All Files** and **Commands** switch into their mode on **Enter**, which fills in the prefix for you. They only appear while their feature is enabled, and they do not filter: `win: chrome` is still how you narrow the list.

### Commands
Type `>` to list the built-in commands and narrow them as you type (for example `>task`). Press **Enter** to run the selected one. Destructive commands (**Hibernate**, **Shut Down**, **Restart**, **Sign Out**, **Empty Recycle Bin**) ask for a second **Enter** first: the footer turns red and shows an "again to confirm" warning, and pressing any other key, moving the selection or waiting a few seconds cancels it.

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
| Terminal | Opens Windows Terminal (PowerShell if not installed) |
| File Explorer | Opens File Explorer |
| Empty Recycle Bin | Empties the Recycle Bin (two-step) |
| Clear Clipboard History | Erases the clipboard history (two-step) |

### Soft interface sounds
Gentle sounds play as you use the launcher: one when the bar opens, a soft rise and fall when the details panel opens and closes, and a soft, deep key sound as you type. Everything is generated inside the mod, so it needs no extra files and no internet connection. You can turn the sounds off or change their volume in the settings.

### Appearance
* Six background effects (**Acrylic**, **Mica**, **Glass**, **Frosted**, **Aurora**, **Solid**) and 12 colours.
* Each effect is built from a blurred view of whatever is behind the bar, finished with a colour tint, subtle grain and light highlights, so the bar looks the same on Windows 10 and 11.
* The blurred effects (every one except **Solid**) need Windows' **Transparency effects** turned on (**Settings → Personalization → Colours → Transparency effects**). Windows draws no blur when it is off, so these effects fall back to a flat colour; switch to **Solid** or turn Transparency effects back on for the intended look.
* **Live acrylic**: Acrylic, Glass, Frosted and Aurora follow what is behind the bar in real time. Turning it off uses a single snapshot taken when the bar opens, which helps performance and saves battery.
* Adjustable panel opacity, blur strength and layout. Blur strength applies to Mica, and to the other effects while Live acrylic is off; with it on, Windows sets their blur strength.
* Looks sharp on every monitor, even high-resolution ones or a mix of several.
* The bar can sit anywhere from against the top edge to against the bottom edge of the screen.

### Fresh without fuss
* **Automatic** index updates watch the Start menu folders and re-read the list when an app is installed or removed, with a light periodic fallback for Store apps.
* Can also re-index on every open or on a fixed interval (1 / 3 / 5 / 10 minutes).
* Installers write an "Uninstall …" shortcut for everything they install; the mod inspects what each shortcut actually runs and hides the uninstallers and documentation, while keeping real tools whose names merely contain "uninstall".

### Safe by design
* Runs as a Windhawk **tool** mod on its own, separate from File Explorer, so it cannot affect Windows itself.
* **Disable in fullscreen**: the hotkey stays quiet while a fullscreen window (a game, a video player, a fullscreen browser) is focused.
* If another app already owns the shortcut, the mod warns you instead of fighting over it.
* Bookmarks are read from the browsers' local bookmark files (Chromium) and compressed backups (Firefox) only; history, cookies, passwords, favicons and the network are never touched.
* Clipboard history is opt-in and text-only: no images, no network, and the `>` command erases it.

---

## Installation

1. Install [Windhawk](https://windhawk.net) (Windows 10 or 11).
2. In Windhawk, open **Mods** and search for **Spotlight Launcher**, then click **Install**.
3. Press **Alt + Space** to open it. Change the shortcut, position, effect and colour from the mod's **Settings** tab.

### From source
1. Download [`spotlight-launcher.wh.cpp`](https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/blob/main/spotlight-launcher.wh.cpp).
2. In Windhawk, choose **Create a new mod**, replace the editor contents with the file and **Save**.
3. Install it from your local mods list.

---

## Settings reference

The settings page groups the options into **Appearance**, **Behavior**, **Shortcuts**,
**Apps**, **Features** and **Sounds**.

### Appearance

| Setting | Default | What it does |
| --- | --- | --- |
| List mode | `Expanded` | Compact = bar only; Expanded = recents and suggestions when empty. |
| Vertical position | `30%` | Where the bar sits, from the top edge (0) to the bottom edge (100). |
| Panel opacity | `90%` | How solid the colour is (70–100). Ignored by **Solid**. |
| Background effect | `Acrylic` | Acrylic, Mica, Glass, Frosted, Aurora or Solid. The blurred ones need Windows' **Transparency effects** on (Settings → Personalization → Colours); with it off they fall back to a flat colour. Solid is unaffected. |
| Live acrylic (real time) | `On` | Keeps Acrylic, Glass, Frosted and Aurora updating live. Turn it off to save power. |
| Blur strength | `50` | How strong the blur is. Applies to **Mica**, and to the other effects only while Live acrylic is off. Ignored by **Solid**. |
| Colour | `Midnight blue` | Background, selection highlight and matching letters. 12 options. |

### Behavior

| Setting | Default | What it does |
| --- | --- | --- |
| Open on monitor | `Monitor with the mouse` | Which monitor the bar appears on: the one with the mouse, the one with the active window, or the primary monitor. |
| Maximum results | `8` | How many apps are shown at once. Extra rows are reached by scrolling. |
| Disable in fullscreen | `On` | Ignores the shortcut (and closes the bar) while a fullscreen window is focused. |

### Shortcuts

| Setting | Default | What it does |
| --- | --- | --- |
| Keyboard shortcut | `Alt + Space` | Key combination that opens and closes the bar. |
| Details panel shortcut | `Ctrl + I` | Ctrl + I, Ctrl + K, Ctrl + Space or F4. |

### Apps

| Setting | Default | What it does |
| --- | --- | --- |
| Hide uninstallers and documentation | `On` | Hides "Uninstall …" and readme/help shortcuts by checking what they open. |
| App index updates | `Automatic` | Automatic, every time it opens, or a fixed 1/3/5/10-minute interval. |

### Search

| Setting | Default | What it does |
| --- | --- | --- |
| Web search | `On` | Shows a "Search the web for …" result for what you type; Enter opens it in your browser. A web address opens directly. |
| Web search engine | `Google` | Google, Bing, DuckDuckGo, YouTube or Wikipedia. |
| File search engine | `Built-in scan` | How file searching works, for `find:` and the deep search inside Files. **Built-in scan** walks Home and the extra folders live (no index). **Everything (voidtools)** uses the running Everything index: every indexed drive, instant answers, Everything's own syntax. Falls back to the built-in scan when Everything is not running. |
| Extra search folders | *(empty)* | Folders searched by `find:`, separated by semicolons. Home is always searched; extra folders inside it are skipped. Not used with the Everything engine. |
| Learn from your choices | `On` | Remembers the app you pick for a few typed words and offers it first next time. Only reorders apps that match equally well, stored locally, forgotten after 90 days without a pick. |
| Browser bookmarks | `Off` | Searches the bookmarks of every Chrome, Edge, Brave, Vivaldi, Chromium, Opera, Firefox, Waterfox, LibreWolf, Zen and Floorp profile next to your apps, and adds the `bm:` prefix. Read locally from the bookmark files only. |
| Recent files | `On` | Shows Windows' Recent files on the empty bar and adds the `recent:` prefix. Read locally from the Recent folder. Requires Windows' recent-items option (Personalization → Start), or the list stays empty. |

### Files

| Setting | Default | What it does |
| --- | --- | --- |
| File browser | `On` | Adds the Files mode (Tab and the folder button). When off, Tab just moves the selection. |
| Start drive | *(empty)* | Drive letter the file browser opens on the first time it is used in a session (e.g. `D`). Empty, or a drive that is not available, opens on Home. |
| Remember file sort | `Off` | Keeps the Files order you pick across closes and restarts. Off, the order holds while the bar is open and Files starts again at Name (A-Z); the sort menu (**Ctrl + S**) is always available. |

### Clipboard

| Setting | Default | What it does |
| --- | --- | --- |
| Clipboard history | `Off` | Keeps the last 30 things you copied, text and images, and adds the `clip:` prefix. Enter pastes into the previous window, Ctrl+Enter copies, Ctrl+D pins, Ctrl+Shift+R removes, and the `>` command clears everything. Encrypted for your Windows account (DPAPI); a copy an app marks as private is skipped. |
| Clipboard retention (days) | `3` | Deletes clipboard entries older than this, together with their image files. Pinned entries are kept. `0` keeps entries until the 30-entry limit drops them. |

### Calculator

| Setting | Default | What it does |
| --- | --- | --- |
| Calculator | `On` | Shows the result as you type a calculation; Enter copies it. |
| Calculator display | `Card and inline text` | Card, inline text, or both. |

### Sounds

| Setting | Default | What it does |
| --- | --- | --- |
| Interface sounds | `On` | Soft sounds for opening, the details panel and typing. Works offline. |
| Sound volume | `20%` | How loud the interface sounds are. |

---

## Contributing

Contributions are welcome — bug reports, fixes, new features and translations alike.

### Reporting a bug
Open an [issue](https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/issues) and include:
* Windows build (`winver`) and Windhawk version.
* The mod version (shown in the README header / settings).
* Steps to reproduce it and what you expected instead.
* A screenshot or short clip when the problem is visual.

### Sending a pull request
1. Fork the repository and create a branch from `main`, e.g. `fix/acrylic-on-win10`.
2. Make your change in `spotlight-launcher.wh.cpp` (C++23, Windhawk tool mod).
3. Bump `@version` in the mod header when behaviour changes.
4. Confirm it compiles and test it on the Windows versions you can reach.
5. Open a pull request against `main` describing **what** changed and **why**.

Keep pull requests focused: one bug or feature per PR is much easier to review and merge.

---

## License

Released under the **MIT License**. See [`LICENSE`](https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/blob/main/LICENSE).

Copyright (c) 2026-present David Ravelo.
