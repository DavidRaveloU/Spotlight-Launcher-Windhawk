# Clipboard history

**Clipboard history** is **off by default**; turn it on in the mod settings.

> [!IMPORTANT]
> It is opt-in on purpose. When it is on, the launcher keeps the last 30 things you copied and adds a
> `clip:` prefix that searches them. Everything stays on this PC — nothing is sent anywhere.

Both **text and images** are kept. An image is stored compressed, shows its own thumbnail in the list,
and copying the same image twice does not keep two copies.

**A copied file is kept as its path.** Explorer puts the file itself on the clipboard plus a text
fallback with only its name; the launcher stores the full path, so **Enter** pastes something usable —
the path — into an address bar, a chat or a terminal.

## Using it

Type `clip:` on its own to list the history, or `clip: invoice` to filter it. `clip: image` narrows the
list to pictures.

| Key | Action |
| --- | --- |
| **Enter** | Paste the entry into the window you came from |
| **Ctrl + Enter** | Copy the entry and keep the bar open |
| **Ctrl + D** | Pin or unpin the entry |
| **Ctrl + Shift + R** | Remove the entry |

> [!TIP]
> Pinned entries stay at the top, show a small pin badge on the clipboard icon, and survive both the
> 30-entry trim and the retention. Pin the ones you paste all day and let the rest expire.

To erase everything, run **Clear Clipboard History** from the `>` menu.

> [!WARNING]
> There is no undo: every entry is deleted, and image files are deleted with their entries. That is
> exactly why it asks for a second **Enter**.

## Retention

**Clipboard retention (days)** deletes entries older than that many days, together with their image
files. The default is 3 days; `0` keeps entries until the 30-entry limit drops them. Pinned entries are
never deleted.

> [!NOTE]
> Retention runs while the launcher is in use, so `0` does not mean "keep forever" — the 30-entry limit
> still applies. Pin what you want to keep.

## Privacy

- Everything is **encrypted for your Windows account** before it is written to the mod's storage, so
  another account on the same PC cannot read it. Nothing leaves the PC.
- Copies that an app marks as private are **skipped** — password managers set that flag, and Windows'
  own clipboard history honours it the same way.
- Turning the feature off **erases** what was saved, images included.
- Very large copies are ignored (text over about 8,000 characters), and images are scaled down on
  their long side (to 2,560 px) so the history stays small.

If Windows does not let the launcher restore the previous window (an elevated app, for example), the
entry stays on the clipboard so you can paste it yourself.

Where this lives, and how to delete it, is in
[Troubleshooting](../reference/troubleshooting.md#what-the-mod-stores).

---

**Prev:** [Files](files.md) | **Next:** [File search](file-search.md) →
