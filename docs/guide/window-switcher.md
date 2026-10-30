# Window switcher

Type `win:` to list the windows that are open right now, newest and topmost first, with their title
and the process that owns them. Filter with `win: chrome` or `win: document`.

| Key | Action |
| --- | --- |
| **↑ / ↓** | Move the selection |
| **Enter** | Activate the selected window and close the bar |

A minimized window is restored when it is activated.

> [!NOTE]
> There is no index and nothing runs in the background: the list is read when you use the prefix, so it
> always reflects the windows that exist at that moment.

## Focus instead of a second instance

When you launch a classic desktop app that already has a visible window, the launcher focuses that
window instead of starting a second copy. Launches that carry arguments, and packaged (Microsoft
Store) apps, keep their normal behaviour.

## Without the prefix

Typing **Open Windows** (also found by *windows manager* or *switcher*) shows the mode as one more
result; **Enter** switches into it and fills in `win:`. See
[Prefixes and commands](prefixes-and-commands.md).

---

**Prev:** [File search](file-search.md) | **Next:** [Bookmarks and recent files](bookmarks-and-recent.md) →
