# Settings reference

The mod's **Settings** tab groups its options by what they configure: **Appearance**, **Behavior**,
**Shortcuts**, **Apps**, **Search**, **Files**, **Clipboard**, **Calculator** and **Sounds**.

> [!NOTE]
> The description shown under each option in the app is the authoritative one — it covers the details
> this summary leaves out. Use this page to find an option quickly or to compare defaults.

## In this page

- [Appearance](#appearance)
- [Behavior](#behavior)
- [Shortcuts](#shortcuts)
- [Apps](#apps)
- [Search](#search)
- [Files](#files)
- [Clipboard](#clipboard)
- [Calculator](#calculator)
- [Sounds](#sounds)
- [After an update](#after-an-update)

## Appearance

| Setting | Default | What it does |
| --- | --- | --- |
| List mode | `Expanded` | Compact shows only the search bar until you type; Expanded also shows recent apps and suggestions while the box is empty. |
| Vertical position | `30%` | Where the bar sits, from the top edge (`0`) to just above the taskbar (`100`). |
| Panel opacity | `90%` | How solid the colour is (70–100). Ignored by **Solid**. |
| Background effect | `Acrylic` | Acrylic, Mica, Glass, Frosted, Aurora or Solid. The blurred ones need Windows' **Transparency effects** on; Solid is unaffected. |
| Live acrylic (real time) | `On` | Keeps Acrylic, Glass, Frosted and Aurora updating live. Turn it off to save power. |
| Blur strength | `50` | Applies to **Mica**, and to the other effects only while Live acrylic is off. Ignored by **Solid**. |
| Color | `Midnight blue` | Background, selection highlight and matching letters. 12 options. |

## Behavior

| Setting | Default | What it does |
| --- | --- | --- |
| Open on monitor | `Monitor with the mouse` | The monitor with the mouse, the monitor of the active window, or the primary monitor. |
| Maximum results | `8` | How many apps are shown at once. The bar height does not change; extra rows are reached by scrolling. |
| Disable in fullscreen | `On` | Ignores the shortcut (and closes the bar) while a fullscreen window is focused. |

## Shortcuts

| Setting | Default | What it does |
| --- | --- | --- |
| Keyboard shortcut | `Alt + Space` | Opens and closes the bar. |
| Details panel shortcut | `Ctrl + I` | Shows or hides the actions and details panel. Ctrl + I, Ctrl + K, Ctrl + Space or F4. If you pick Ctrl + Space here, choose a different main shortcut so the two do not clash. |

## Apps

| Setting | Default | What it does |
| --- | --- | --- |
| Hide uninstallers and documentation | `On` | Hides "Uninstall …" shortcuts and readme/help/web-link shortcuts by checking what each one opens, so real tools whose names merely contain "uninstall" are kept. |
| App index updates | `Automatic` | Automatic, every time it opens, or a fixed 1 / 3 / 5 / 10 minutes. Automatic notices apps as they are installed or removed and stays idle otherwise. |

## Search

| Setting | Default | What it does |
| --- | --- | --- |
| Web search | `On` | Shows a "Search the web for …" result for what you type; Enter opens it. A web address opens directly; `?` forces a search. |
| Web search engine | `Google` | Google, Bing, DuckDuckGo, YouTube or Wikipedia. |
| File search engine | `Built-in scan` | **Built-in scan** walks Home and the extra folders live. **Everything (voidtools)** uses the running Everything index: every indexed drive, instant answers, Everything's syntax. Falls back to the built-in scan when Everything is not running. |
| Extra search folders | *(empty)* | Folders searched by `find:`, separated by semicolons. Home is always searched; extra folders inside it are skipped. Not used with the Everything engine. |
| Learn from your choices | `On` | Remembers the app you pick for a few typed words and offers it first next time. Stored locally per user; forgotten after 90 days without a pick. |
| Browser bookmarks | `Off` | Searches the bookmarks of Chrome, Edge, Brave, Vivaldi, Chromium, Opera, Firefox, Waterfox, LibreWolf, Zen and Floorp, and adds the `bm:` prefix. Read locally from the bookmark files only. |
| Recent files | `On` | Shows Windows' Recent files on the empty bar and adds `recent:`. Requires Windows' recent-items option, or the list stays empty. |

## Files

| Setting | Default | What it does |
| --- | --- | --- |
| File browser | `On` | Adds the Files mode (Tab and the folder button). When off, Tab just moves through the app list. |
| Start drive | *(empty)* | Drive letter the file browser opens on the first time in a session (for example `D`). Empty, or an unavailable drive, opens on Home. |
| Remember file sort | `Off` | Keeps the Files order across closes and restarts. Off, the order holds while the bar is open and Files starts again at Name (A-Z); **Ctrl + S** is always available. |

## Clipboard

| Setting | Default | What it does |
| --- | --- | --- |
| Clipboard history | `Off` | Keeps the last 30 things you copied (text and images) and adds the `clip:` prefix. Encrypted for your Windows account before it is written; a copy an app marks as private is skipped. Turning it off erases what was saved. |
| Clipboard retention (days) | `3` | Deletes entries older than this, with their image files. Pinned entries are kept. `0` keeps entries until the 30-entry limit drops them. |

## Calculator

| Setting | Default | What it does |
| --- | --- | --- |
| Calculator | `On` | Shows the result as you type a calculation; Enter copies it. |
| Calculator display | `Card and inline text` | Result card, inline text, or both. |

## Sounds

| Setting | Default | What it does |
| --- | --- | --- |
| Interface sounds | `On` | Soft sounds for opening, the details panel and typing. Generated inside the mod; works offline. |
| Sound volume | `20%` | How loud the interface sounds are. |

## After an update

Options that moved between sections keep their saved values.

> [!IMPORTANT]
> The tab shows the defaults until you save it once, and saving applies what the tab shows — so it is
> worth a look the first time after a big update.

---

**Prev:** [Appearance and sounds](../guide/appearance.md) | **Next:** [Troubleshooting](troubleshooting.md) →
