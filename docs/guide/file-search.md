# File search

There are two ways to find a file by name without opening Files: the `find:` prefix, and the deep
search inside [Files](files.md). Both use the same engine, set by **File search engine**.

## `find:`

Type `find:` followed by words to search the **names** of files and folders under:

- your **Home** folder, which already covers Documents, Downloads, Desktop, Pictures, Music, Videos
  and the rest;
- any folder added to **Extra search folders** (separated by semicolons; environment variables such
  as `%USERPROFILE%` work).

Results appear while the scan runs, showing the folder each one lives in, and the search stops when
the bar closes. It searches names, not contents, and builds no index.

| Key | Action |
| --- | --- |
| **Enter** | Open the file or folder |
| **Ctrl + Enter** | Open the containing folder |
| **Ctrl + Shift + C** | Copy the path |

> [!NOTE]
> The scan is live and capped, so a very large tree may show partial results. Narrow the query, or add
> the folder to **Extra search folders**.

## With Everything (optional)

[Everything](https://www.voidtools.com) is a free file indexer for Windows. If it is installed and
running, set **File search engine** to **Everything (voidtools)** and both `find:` and the deep search
inside Files are answered by its index instead of a live scan:

- the answers cover **every drive** Everything has indexed, not only Home;
- they arrive in milliseconds;
- Everything's own syntax works: `*.pdf`, `"exact phrase"`, `!excluded`.

> [!IMPORTANT]
> Everything is **optional**. The built-in scan is the default, no DLL is shipped or loaded, and nothing
> extra is downloaded. You only need Everything if you want the speed and the drive-wide coverage.

If Everything is not running, or does not answer within a second, the built-in scan takes over
automatically.

> [!TIP]
> When that happens the footer says *Everything not running · built-in scan* in amber, so the search
> keeps working and still tells you why it is slower.

While the engine is Everything, **Extra search folders** is not used and the deep search inside Files
is restricted to the folder you are browsing, keeping the active filters.

## Which one to pick

| | Built-in scan | Everything |
| --- | --- | --- |
| Setup | Nothing | Install Everything and keep it running |
| Coverage | Home plus the extra folders | Every index from Everything |
| Speed | Depends on the size of the tree | Milliseconds |
| Syntax | Plain words | Everything's syntax (wildcards, quotes, exclusions) |
| If the other one is unavailable | Always works | Falls back to the built-in scan |

---

**Prev:** [Clipboard history](clipboard.md) | **Next:** [Window switcher](window-switcher.md) →
