# Appearance and sounds

## Background effects

Six effects and twelve colours. Each effect is built from a blurred view of whatever is behind the
bar, finished with a colour tint, subtle grain and light highlights, so the bar looks the same on
Windows 10 and Windows 11.

| Effect | Look |
| --- | --- |
| **Acrylic** | Blurred, with a light grain (the default) |
| **Mica** | Blurred, closer to the desktop wallpaper's tone |
| **Glass** | Blurred and clearly see-through |
| **Frosted** | Blurred and soft |
| **Aurora** | Blurred with a coloured gradient |
| **Solid** | A plain colour, no blur |

> [!IMPORTANT]
> The blurred effects (every one except **Solid**) need Windows' **Transparency effects** turned on:
> **Settings → Personalization → Colours → Transparency effects**. With it off, Windows draws no blur
> and those effects fall back to a flat colour — which is the single most common reason the bar "looks
> wrong".

**Live acrylic** keeps Acrylic, Glass, Frosted and Aurora following what is behind the bar in real
time.

> [!TIP]
> Turning **Live acrylic** off uses a single snapshot taken when the bar opens. It still blurs, but it
> stops updating in real time, which helps performance and battery on laptops.

**Panel opacity** sets how solid the colour is (70–100). **Blur strength** applies to Mica, and to the
other effects while Live acrylic is off; with it on, Windows sets their blur strength. **Solid** is
always fully opaque and ignores both.

## Colours

Midnight blue (the default), Graphite, Black, Violet, Emerald, Teal, Rose, Crimson, Amber, Sky,
Lavender and White. Each colour sets the background, the selection highlight and the colour of the
matching letters.

## Layout

- **List mode**: **Compact** shows only the search bar until you type; **Expanded** also shows your
  recent apps and suggestions while the box is empty.
- **Vertical position**: where the bar sits, as a percentage of the screen height. `0` sticks it to
  the very top, `50` centres it, `100` sits it just above the taskbar. In Compact mode only the search
  box appears at that height; in Expanded mode the bar grows downward from there.
- The bar looks sharp on every monitor, including high-resolution ones and a mix of several.
- **Open on monitor** chooses which screen it appears on: the one with the mouse, the one with the
  active window, or the primary monitor.

## Sounds

Gentle sounds play as you use the launcher: one when the bar opens, a soft rise and fall when the
details panel opens and closes, and a soft, deep key sound as you type. Everything is generated inside
the mod, so it needs no extra files and no internet connection.

**Interface sounds** turns them off and **Sound volume** sets how loud they are (20% by default).

## Feedback colours

Anything the launcher has to tell you uses the same small language, with a dot in the footer:

| Colour | Meaning | Example |
| --- | --- | --- |
| Green | Something is done | **Copied** |
| Amber | It had to work around a problem | *Everything not running · built-in scan* |
| Red | It needs care | A destructive command asking for a second Enter, a path that does not exist, a preview that could not be opened |

The empty list uses the same tones: the accent while it is still searching, amber when a problem is
the reason it is empty.

---

**Prev:** [Calculator](calculator.md) | **Next:** [Settings reference](../reference/settings.md) →
