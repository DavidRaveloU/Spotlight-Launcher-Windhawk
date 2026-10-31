# File search

There are two ways to find a file by name without opening Files: the `find:` prefix, and the deep
search inside [Files](files.md). Both use the same engine, set by **File search engine**, and both
understand the same [filters](#filters).

## `find:`

Type `find:` followed by words to search the **names** of files and folders under:

- your **Home** folder, which already covers Documents, Downloads, Desktop, Pictures, Music, Videos
  and the rest;
- any folder added to **Extra search folders** (separated by semicolons; environment variables such
  as `%USERPROFILE%` work).

Results appear while the scan runs, showing the folder each one lives in, and the search stops when
the bar closes. It searches names, not contents, and builds no index.

Each row shows the file type, its **size** and its **modified date**, then the folder it lives in:

```
report-final.pdf
File · 1.2 MB · 30/10/2026 16:02 · C:\Users\you\Documents\work
```

| Key | Action |
| --- | --- |
| **Enter** | Open the file or folder |
| **Ctrl + Enter** | Open the containing folder |
| **Ctrl + Shift + C** | Copy the path |

> [!NOTE]
> The scan is live and capped, so a very large tree may show partial results. While it runs, the footer
> says **Searching.**; when it finishes, the footer goes back to the usual hints.

## Filters

The same filters as Files work here, mixed with the words in any order:

| Filter | Examples |
| --- | --- |
| Size | `size:>10mb`, `size:<500kb`, `size:1mb..10mb` |
| Date | `modified:today`, `modified:week`, `modified:2026-10-31`, `modified:>2026-06-01` |
| Type | `*.pdf`, `ext:png,jpg`, `type:image`, `dir:`, `file:` |

```
find: report size:>1mb modified:week
find: *.pdf modified:today
find: size:<1kb
```

- A size is in binary units (`1mb` = 1,048,576 bytes). A bare value means "at least".
- A lone date covers that whole day; `>2026-06-01` starts the next day, `<2026-06-01` ends before it.
- A space after the operator is fine: `size:> 1mb` and `modified: today` are read the same way.
- Filters combine with **AND**: the row has to match the words *and* every filter.

See [Files → Filters](files.md#filters) for the complete semantics.

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

Filters are translated to Everything's own syntax (`size:>=1048576`, `datemodified:>=2026-10-31`), so
the index does the work instead of the list. That also gives every row its size and date, the same as
the built-in scan.

If Everything is not running, or does not answer within a second, the built-in scan takes over
automatically.

> [!TIP]
> When that happens the footer says *Everything not running · built-in scan* in amber, so the search
> keeps working and still tells you why it is slower.

> [!NOTE]
> The two engines do not see exactly the same files. Everything indexes folders the file browser hides,
> so results from `AppData`, `ProgramData` and other hidden locations can appear with Everything and
> never with the built-in scan. The Recycle Bin and the volume metadata folders are dropped from both.
> While the engine is Everything, **Extra search folders** is not used and the deep search inside Files
> is restricted to the folder you are browsing, keeping the active filters.

## Which one to pick

| | Built-in scan | Everything |
| --- | --- | --- |
| Setup | Nothing | Install Everything and keep it running |
| Coverage | Home plus the extra folders | Every index from Everything |
| Hidden folders | Skipped | Included |
| Speed | Depends on the size of the tree | Milliseconds |
| Syntax | Plain words plus the filters | Everything's syntax plus the filters |
| If the other one is unavailable | Always works | Falls back to the built-in scan |

---

**Prev:** [Clipboard history](clipboard.md) | **Next:** [Window switcher](window-switcher.md) →
