# Custom entries

Your own websites, files, folders and commands can live in the list next to your apps. Open the
manager by searching for **Custom Entries** and pressing **Enter**, or from the `>` menu. It creates,
edits and deletes entries for you; no settings page is involved.

Every entry has a **name**, a **type** and a **target**.

| Type | What the target is | Example |
| --- | --- | --- |
| **Website** | A web address | `https://www.youtube.com/results?search_query={query}` |
| **File or folder** | A path (environment variables work) | `%USERPROFILE%\Projects` |
| **Command** | A program, with optional arguments | `wt.exe` with arguments `-d %USERPROFILE%` |

Entries appear after the matching apps, need no prefix, and are only offered while you are typing —
not on the empty bar. They can have extra **search keywords**. An entry without a name or a target is
ignored.

> [!NOTE]
> Avoid starting an entry's name with `?` or `>` (or with `g:`, `b:`, `bm:`, `d:`, `y:`, `w:`): those
> prefixes switch the launcher into another mode instead of matching your entry.

## Asking for values

Put placeholders in the target or the arguments and the launcher asks for them when the entry is used.
Fields appear in the order they are written (target first, then arguments), up to 16 distinct values.

| Placeholder | Meaning |
| --- | --- |
| `{folder}` | A required value |
| `{folder?}` | An optional value |
| `{branch=main}` | Starts pre-filled with `main`; still required unless written `{branch?=main}` |
| `{query}` | The extra words you type after the entry's name (always optional) |

When you select an entry whose required values are still empty, a form opens in place of the list
instead of launching with something missing:

- **Tab** / **Shift + Tab** and the arrow keys move between fields, **Enter** runs the entry and
  **Esc** goes back to the list.
- The form is a normal text field: click a field to put the caret, and use **Ctrl + A**, **Ctrl + C**,
  **Ctrl + X**, **Ctrl + V** or the usual selection, word and Home/End keys.
- Optional fields carry an **Optional** tag; required ones show *Required* while empty, and the header
  shows which fields are in view when there are more than fit.
- **Shift + Enter** skips the form and launches with the current values (a required value that is
  still empty opens the form anyway); **Enter** opens the form so the values can be reviewed first.
  The footer offers both for entries that have fields.
- An unknown bare program name is only a warning: it asks for a second Enter, because the shell may
  still find it through an installed app.

> [!TIP]
> A line under the fields previews the final address, path or command as you type, and a blocking
> problem — a missing path, a missing `.exe`, or arguments typed into the target — is reported there
> before anything opens.

### `{query}`

Write `{query}` in the target or the arguments to pass the extra words typed after the entry's name.

- Because the entry is searched by name, typing **YouTube cats** shows the *YouTube* entry and Enter
  opens the search for "cats" (URL-encoded for websites).
- Typing just **YouTube** leaves the placeholder empty.
- A command such as `wt.exe` with `-d {query}` opens Windows Terminal in the folder you typed; put it
  in quotes (`-d "{query}"`) so a path with spaces arrives as one argument.

Values from other fields are inserted exactly as typed (only `{query}` is URL-encoded for a Website).
`{{` and `}}` stand for literal braces. Placeholder names are case-insensitive and ignore spaces, `_`
and `-` (`{my_folder}`, `{My-Folder}` and `{my folder}` are the same value), and a value used more than
once is only asked once.

## Entry shortcuts

The manager gives every entry two optional shortcuts, so you do not need to remember its name or open
the manager again.

| Field | What it does |
| --- | --- |
| **Trigger** | A typed alias: one lowercase word (letters, digits, `-` or `_`, up to 16 characters), unique among your entries. Typing `yt cats` runs the *YouTube* entry straight away, selected at the top of the list, with `cats` passed as its `{query}` (or pre-filling its first required field if it has no `{query}`). The normal app matches stay below, so a trigger never blocks them. |
| **Shortcut** | A key combination you can press while the launcher is open. Focus the field and press the combination (it must include **Ctrl**, **Alt** or **Win**; **Shift** can be added); **Backspace** clears it. If the entry asks for values, its form opens; otherwise it launches directly. |

Both are optional. A trigger or combination already used by another entry, or by the launcher's own
shortcut, is rejected with a message when you save.

> [!IMPORTANT]
> The entry shortcut only works **while the bar is open**. It is not a Windows-wide hotkey: it never
> fires while the launcher is closed, and Windows keeps its own combinations (such as **Win + E** or
> **Alt + Tab**).

---

**Prev:** [Bookmarks and recent files](bookmarks-and-recent.md) | **Next:** [Calculator](calculator.md) →
