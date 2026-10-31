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

## Actions on the selected window

The switcher can also work on a window without switching to it. **All of these leave the bar open**,
so you can act on several windows in a row; nothing is activated behind your back.

| Key | What it does |
| --- | --- |
| **Ctrl + W** | Close the window (asks for a second **Ctrl + W**) |
| **Ctrl + M** | Minimize it |
| **Ctrl + Shift + M** | Maximize it, or restore it if it is already maximized |
| **Ctrl + Shift + T** | Keep it always on top, or stop keeping it |
| **Ctrl + Shift + →** | Move it to the next monitor |
| **Ctrl + Shift + ←** | Move it to the previous monitor |
| **Ctrl + Enter** | Open the folder of its `.exe` |
| **Ctrl + Shift + C** | Copy the path of its `.exe` |

The window keeps its size when it moves between monitors: it is centred on the target screen, and an
edge is never pushed outside it. A maximized window is restored, moved and maximized again.

Both the footer and the panel show the keys, so you do not have to remember them.

> [!TIP]
> Nothing here waits for the window. Each action is posted to its thread and checked a moment later, so
> a window that stopped responding **cannot freeze the launcher** — the very case you open a switcher
> for. If it never reacts, the footer says so instead of leaving you guessing.

## The panel (Ctrl + I)

**Ctrl + I** opens the same card the app list uses, with the actions above and three facts about the
window:

| Row | What it shows |
| --- | --- |
| **Process** | The `.exe` that owns the window |
| **State** | `Normal`, `Minimized`, `Maximized`, plus `· always on top` when it applies |
| **Path** | The full path of that `.exe` |

The card is informational: the actions are triggered with their keys, not with the mouse.

## Closing a window

**Ctrl + W** does not kill anything. It sends the standard *close* request, so the app decides what to
do — most show their "save your changes?" dialog, exactly as if you had clicked the X.

Because of that, it asks for a second press:

1. The footer turns red with **“Ctrl+W again to close”**.
2. A second **Ctrl + W** within four seconds closes the window.
3. Any other key, moving the selection, or waiting cancels it, and holding the key down does not count
   as a confirmation.

The confirmation belongs to **that window**, not to the row: if the list is re-read or the mouse moves
the selection before the second press, the next **Ctrl + W** asks again instead of closing a window you
never picked.

If the app does not answer (a hung window), the request is queued and nothing visibly happens: the
window stays in the list.

## Always on top

**Ctrl + Shift + T** pins the window above the others. Windows itself has no indicator for that state,
so the launcher shows it in three places:

- a small **gold pin** on the window's icon in the list,
- the word **On top** where the list normally says *Window*,
- a green footer notice when you toggle it: *Always on top · Ctrl+Shift+T to undo*.

The state is not remembered: closing the window, or stopping the pin, puts everything back.

## What the launcher cannot do

A window that belongs to a program running **as administrator** cannot be controlled from here: Windows
blocks messages and movement between processes of different integrity levels. The launcher detects it
and says so in amber — *Needs administrator · can't control that window* — instead of failing silently.

That is the same reason a window on a **single-monitor** machine answers *No other monitor in that
direction* when you try to move it.

## Without the prefix

Typing **Open Windows** (also found by *windows manager* or *switcher*) shows the mode as one more
result; **Enter** switches into it and fills in `win:`. See
[Prefixes and commands](prefixes-and-commands.md).

## Focus instead of a second instance

When you launch a classic desktop app that already has a visible window, the launcher focuses that
window instead of starting a second copy. Launches that carry arguments, and packaged (Microsoft
Store) apps, keep their normal behaviour.

---

**Prev:** [File search](file-search.md) | **Next:** [Bookmarks and recent files](bookmarks-and-recent.md) →
