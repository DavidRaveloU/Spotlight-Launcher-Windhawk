# Bookmarks and recent files

Two features that put things you already had next to your apps: the bookmarks your browsers hold,
and the files Windows remembers you opening.

## Browser bookmarks

**Browser bookmarks** is **off by default**; turn it on in the mod settings.

> [!IMPORTANT]
> Nothing is read until you turn it on. When it is on, the launcher searches the bookmarks of every
> installed profile of:
>
> - **Chrome**, **Edge**, **Brave**, **Vivaldi**, **Chromium** and **Opera**, including their Beta, Dev,
>   Canary and Nightly builds;
> - **Firefox**, **Waterfox**, **LibreWolf**, **Zen** and **Floorp**.

Bookmark rows carry a gold star and show the folder and the browser they come from. A bookmark saved
in two browsers or profiles is listed once.

| Key | Action |
| --- | --- |
| **Enter** | Open the page |
| **Ctrl + Enter** | Copy the address |

Normal searches add up to three bookmark matches below your app matches, before the Settings and web
rows. Type `bm:` to search only bookmarks — `bm: docs` to filter, or `bm:` on its own to browse them.

Everything is read locally from each profile's bookmark file (Firefox bookmarks come from its own
compressed backups). The mod never reads history, cookies, passwords or favicons, and never touches
the network.

> [!NOTE]
> Chromium changes are picked up the next time the bar opens. Firefox writes its backups on its own
> schedule, so a brand-new Firefox bookmark can take longer to appear.

## Recent files

**Recent files** is **on by default**; turn it off in the mod settings to hide the section and the
prefix.

The empty bar gets a **Recent files** section with the files and folders Windows lists in its Recent
folder, and `recent:` searches that list — `recent: invoice` or `recent: .pdf`, for example.

| Key | Action |
| --- | --- |
| **Enter** | Open the file or folder |
| **Ctrl + Enter** | Open its folder |
| **Ctrl + Shift + C** | Copy the path |

> [!WARNING]
> Windows must be recording recent items, or this feature has nothing to show and the section stays
> empty. On Windows 11, turn on **Settings → Personalization → Start → Show recently opened items in
> Start, Jump Lists, and File Explorer**. On Windows 10, the equivalent **Show recently used files**
> option.

Everything is read locally from the Recent folder; the mod never scans the disk or touches the network.

---

**Prev:** [Window switcher](window-switcher.md) | **Next:** [Custom entries](custom-entries.md) →
