# Search

Type into the bar and the list narrows as you go. This page explains how that list is built and the
extras that appear in it.

## In this page

- [How matching works](#how-matching-works)
- [Result order](#result-order)
- [Where the app list comes from](#where-the-app-list-comes-from)
- [Pinned apps](#pinned-apps)
- [Learning from your choices](#learning-from-your-choices)
- [The details panel](#the-details-panel)
- [Web results](#web-results)
- [Windows Settings](#windows-settings)
- [Modes as results](#modes-as-results)

## How matching works

- Case- and accent-insensitive: `cafe` finds *Café*.
- Multi-word queries match words anywhere in the name, in any order: `visual code` finds
  *Visual Studio Code*.
- Acronyms work too: `vsc` finds *Visual Studio Code* by the initials of its words.
- The letters that matched are highlighted in the result.

## Result order

Apps are ranked by match quality first, then by how you actually use them:

| Signal | Effect |
| --- | --- |
| Exact name | An app whose name is exactly what you typed always comes first. |
| Prefix, word start, substring | The closer the match, the higher the row. |
| **Frecency** | A recently and frequently used app rises among similar matches. Usage decays with a 30-day half-life, so old counts fade. |
| **Pinned apps** | A pinned app gets a small boost when it matches, and lives in its own `Pinned` section on the empty bar. |
| **Learning** | An app you picked for the same words wins next time (see below). |

Merged duplicates: shortcuts from the Start menu and the Desktop that open the same program are
listed once; two different programs that happen to share a name are both kept and labelled so they can
be told apart.

## Where the app list comes from

- The list is the same one the Start menu uses: classic programs, Microsoft Store apps and shortcuts
  sitting on your Desktop.
- **App index updates** (*Automatic* by default) notices apps as they are installed or removed and
  stays idle when nothing changes. It can also refresh every time the bar opens, or on a fixed
  interval (1, 3, 5 or 10 minutes).
- Installers add an "Uninstall …" shortcut for everything they install. The launcher looks at what
  each shortcut actually runs and hides the uninstallers, readmes and help links, while keeping real
  tools whose names merely contain "uninstall".
- **Ctrl + R** rebuilds the list by hand if something looks out of date.

## Pinned apps

**Ctrl + D** (or **Pin to top** in the details panel) keeps the selected app in the `Pinned` section at
the top of the empty bar; the same action unpins it.

> [!TIP]
> Pins are stored per user and survive restarts and app reindexing — they are not tied to the app's
> position in the Start menu.

## Learning from your choices

With **Learn from your choices** on (the default), picking an app after typing a few words makes the
launcher offer it first for exactly those words next time. One pick is enough, and it works even when
the app was matching weakly: typing `ex` and choosing Firefox puts Firefox on top from then on, where
*Excel* would otherwise win.

- It only affects those words: `excel`, `explorer` or any other query keeps its normal order.
- The pairs are stored locally per user, capped at 200, and one you stop picking is forgotten after
  90 days.
- Turn the setting off to get the plain ranking back.

> [!NOTE]
> Learning only reorders apps that already match. It never makes an app appear for a query it would not
> match otherwise.

## The details panel

**Ctrl + I** (or **Ctrl + K** / **Ctrl + Space** / **F4**) opens a right-hand panel for the selected
app with its actions and technical details. The actions also work with the panel closed. File actions
are offered for classic programs; Microsoft Store apps offer *open*, *pin* and *remove from recents*.

## Web results

With **Web search** on, a **Search the web for …** result appears at the end of the list for whatever
you type (never while the text is being used as a calculation). **Enter** opens it in your default
browser. The engine is configurable: Google (default), Bing, DuckDuckGo, YouTube or Wikipedia.

If what you type looks like a web address (`gmail.com`, `https://localhost:3000`), the row becomes
**Open …** and opens the site directly.

> [!TIP]
> Prefix the text with `?` to force a search when the address is what you actually wanted to search for.
> The shortcut engines work too: `g:`, `b:`, `d:`, `y:` and `w:`.

## Windows Settings

Typing the name of a common settings page — `bluetooth`, `display`, `sound`, `update`, `wifi`,
`storage`, `power` — also offers a **Setting** result that opens the matching page in the Settings app.
These need no prefix, appear after your app matches, and a valid calculation hides them.

## Modes as results

Typing the name of a mode shows it as one more row, like an app: **Open Windows**, **Bookmarks**,
**Clipboard History**, **Recent Files**, **All Files** and **Commands**. **Enter** switches into that
mode and fills in the prefix for you.

> [!TIP]
> This is the answer to "I do not remember the prefix". Type *clipboard*, press **Enter**, and the bar
> is already in `clip:`.

A mode row only appears while its feature is enabled, and it never filters: `win: chrome` is still how
a list is narrowed. See [Prefixes and commands](prefixes-and-commands.md).

---

**Prev:** [Keyboard shortcuts](../get-started/shortcuts.md) | **Next:** [Prefixes and commands](prefixes-and-commands.md) →
