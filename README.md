<div align="center">

# Spotlight Launcher For Windhawk

A fast, keyboard-driven application launcher for Windows, packaged as a [Windhawk](https://windhawk.net) tool mod.

Press **Alt + Space**, type a few letters, press **Enter**. That is the whole idea.

<br>

<a href="https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/blob/main/LICENSE">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="License: MIT">
</a>
<a href="https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/blob/main/version.json">
  <img src="https://img.shields.io/badge/dynamic/json?url=https://raw.githubusercontent.com/DavidRaveloU/Spotlight-Launcher-Windhawk/main/version.json&query=%24.version&label=version&prefix=v&color=informational" alt="Version">
</a>
<a href="https://www.microsoft.com/windows">
  <img src="https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0078D6" alt="Platform: Windows 10/11">
</a>
<a href="https://windhawk.net">
  <img src="https://img.shields.io/badge/Windhawk-mod-orange" alt="Windhawk mod">
</a>

</div>

Spotlight Launcher indexes the same applications you see in the Start menu (both classic programs and Microsoft Store apps) and filters them as you type. It runs on its own, as a Windhawk mod, so it never runs inside File Explorer and cannot affect the way Windows works.

---

## Screenshots

### Main

<p align="center">
  <img width="700" alt="Desktop" src="https://github.com/user-attachments/assets/01cd7347-51df-4d22-879e-d44fd35a7ae9" />
</p>

The search bar over the desktop, with the default **Midnight** colour and **Acrylic** effect. A short query already filtered a handful of results, with the matching letters highlighted. This is the launcher's first impression.

### Details panel

<p align="center">
  <img width="700" alt="Details" src="https://github.com/user-attachments/assets/22784b9b-2a83-45f9-bf97-1cd6934d755a" />
</p>

An app selected with the details panel open on the right (**Ctrl + I**): the actions list and the technical info table.

### Look and feel

These are some of the built-in looks (themes): the **Aurora** effect in three colours, plus **Frosted**, **Glass** and **Mica**.

<table align="center">
  <tr>
    <td align="center">
      <img width="250" alt="Aurora Amber" src="https://github.com/user-attachments/assets/863112a5-e583-4050-9eae-c1a03988837a" /><br>
      <b>Aurora</b> &middot; Amber
    </td>
    <td align="center">
      <img width="250" alt="Aurora Emerald" src="https://github.com/user-attachments/assets/6f583ae0-95a4-4759-b172-f9d5e8ca66f2" /><br>
      <b>Aurora</b> &middot; Emerald
    </td>
    <td align="center">
      <img width="250" alt="Aurora Violet" src="https://github.com/user-attachments/assets/0c3c4e1c-ca18-4749-aa8b-d27035d9cf52" /><br>
      <b>Aurora</b> &middot; Violet
    </td>
  </tr>
  <tr>
    <td align="center">
      <img width="250" alt="Frosted" src="https://github.com/user-attachments/assets/a8a61a62-ed41-4f1e-bb8b-01bbb9526d0c" /><br>
      <b>Frosted</b>
    </td>
    <td align="center">
      <img width="250" alt="Glass" src="https://github.com/user-attachments/assets/8df98cf2-112c-4936-8839-7dce259be69b" /><br>
      <b>Glass</b>
    </td>
    <td align="center">
      <img width="250" alt="Mica" src="https://github.com/user-attachments/assets/042c737e-2700-42a4-ae51-96e94e164c77" /><br>
      <b>Mica</b>
    </td>
  </tr>
</table>

The rest (the **Acrylic**, **Mica** and **Solid** effects, and the remaining colours — Midnight blue, Graphite, Black, Teal, Rose, Crimson, Sky, Lavender, White) are described in the [Features](#features) section below.

---

## Features

### Instant, forgiving search
* Filters classic programs and Microsoft Store apps as you type.
* Case- and accent-insensitive.
* Multi-word queries (`visual code`) and acronyms (typing the initials of each word, like `vsc`).
* Matching letters are highlighted in the result.
* Results show a friendly name plus the file or package they open.

### Keyboard-first
Everything is reachable without touching the mouse.

| Shortcut | Action |
| --- | --- |
| **Alt + Space** | Open / close the search bar (configurable) |
| **↑ / ↓ / Tab** | Move the selection |
| **Enter** | Open the selected app |
| **Esc** | Close the details panel, then the search bar |
| **Ctrl + Enter** | Open the file location |
| **Ctrl + Shift + Enter** | Run as administrator |
| **Ctrl + Shift + C** | Copy the path |
| **Ctrl + P** | Properties |
| **Ctrl + Shift + R** | Remove from recents |
| **Ctrl + I** | Toggle the details panel (configurable) |
| **Ctrl + R** | Reindex the app list |
| Mouse wheel | Scroll the list without changing the selection |
| Mouse hover | Highlight the row under the cursor |

> **Note:** **Alt + Space** is also the system shortcut for a window's title-bar menu (Move, Size, Close…). While the mod is enabled with the default shortcut, that menu is not reachable by keyboard, so pick another combination in the settings if you use it.

### Details panel
Press **Ctrl + I** (or **Ctrl + K** / **Ctrl + Space** / **F4**) with an app selected to reveal a right-hand panel with actions and extra details. The actions also work with the panel closed. File actions are only offered for classic programs; Microsoft Store apps only offer *open* and *remove from recents*.

### Built-in calculator
Type a calculation and the result appears as you go: a highlighted card at the top of the list shows it, and it is also shown faintly next to what you typed. Press **Enter** to copy the result; recent results are kept so you can reuse them. It only reacts when the whole text looks like a calculation, so ordinary searches are left alone.

### Soft interface sounds
Gentle sounds play as you use the launcher: one when the bar opens, a soft rise and fall when the details panel opens and closes, and a soft, deep key sound as you type. Everything is generated inside the mod, so it needs no extra files and no internet connection. You can turn the sounds off or change their volume in the settings.

### Appearance
* Six background effects (**Acrylic**, **Mica**, **Glass**, **Frosted**, **Aurora**, **Solid**) and 12 colours.
* Each effect is built from a blurred view of whatever is behind the bar, finished with a colour tint, subtle grain and light highlights, so the bar looks the same on Windows 10 and 11.
* **Live acrylic**: Acrylic, Frosted and Aurora follow what is behind the bar in real time, and Glass keeps refreshing its blur as the background changes. Turning it off uses a single snapshot taken when the bar opens, which helps performance and saves battery.
* Adjustable panel opacity, blur strength and layout.
* Looks sharp on every monitor, even high-resolution ones or a mix of several.
* The bar can sit anywhere from against the top edge to against the bottom edge of the screen.

### Fresh without fuss
* **Automatic** index updates watch the Start menu folders and re-read the list when an app is installed or removed, with a light periodic fallback for Store apps.
* Can also re-index on every open or on a fixed interval (1 / 3 / 5 / 10 minutes).
* Installers write an "Uninstall …" shortcut for everything they install; the mod inspects what each shortcut actually runs and hides the uninstallers and documentation, while keeping real tools whose names merely contain "uninstall".

### Safe by design
* Runs as a Windhawk **tool** mod on its own, separate from File Explorer, so it cannot affect Windows itself.
* **Disable in fullscreen**: the hotkey stays quiet while a fullscreen window (a game, a video player, a fullscreen browser) is focused.
* If another app already owns the shortcut, the mod warns you instead of fighting over it.

---

## Installation

1. Install [Windhawk](https://windhawk.net) (Windows 10 or 11).
2. In Windhawk, open **Mods** and search for **Spotlight Launcher**, then click **Install**.
3. Press **Alt + Space** to open it. Change the shortcut, position, effect and colour from the mod's **Settings** tab.

### From source
1. Download [`spotlight-launcher.wh.cpp`](https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/blob/main/spotlight-launcher.wh.cpp).
2. In Windhawk, choose **Create a new mod**, replace the editor contents with the file and **Save**.
3. Install it from your local mods list.

---

## Settings reference

| Setting | Default | What it does |
| --- | --- | --- |
| Keyboard shortcut | `Alt + Space` | Key combination that opens and closes the bar. |
| Vertical position | `30%` | Where the bar sits, from the top edge (0) to the bottom edge (100). |
| Maximum results | `8` | How many apps are shown at once. Extra rows are reached by scrolling. |
| Panel opacity | `90%` | How solid the colour is (70–100). Ignored by **Solid**. |
| Background effect | `Acrylic` | Acrylic, Mica, Glass, Frosted, Aurora or Solid. |
| Live acrylic (real time) | `On` | Keeps Acrylic, Frosted and Aurora updating live and Glass refreshing. Turn it off to save power. |
| Blur strength | `50` | How strong the blur is. Ignored by **Solid**. |
| Colour | `Midnight blue` | Background, selection highlight and matching letters. 12 options. |
| Hide uninstallers and documentation | `On` | Hides "Uninstall …" and readme/help shortcuts by checking what they open. |
| App index updates | `Automatic` | Automatic, every time it opens, or a fixed 1/3/5/10-minute interval. |
| List mode | `Expanded` | Compact = bar only; Expanded = recents and suggestions when empty. |
| Details panel shortcut | `Ctrl + I` | Ctrl + I, Ctrl + K, Ctrl + Space or F4. |
| Disable in fullscreen | `On` | Ignores the shortcut (and closes the bar) while a fullscreen window is focused. |
| Calculator | `On` | Shows the result as you type a calculation; Enter copies it. |
| Calculator display | `Card and inline text` | Card, inline text, or both. |
| Interface sounds | `On` | Soft sounds for opening, the details panel and typing. Works offline. |
| Sound volume | `20%` | How loud the interface sounds are. |

---

## Contributing

Contributions are welcome — bug reports, fixes, new features and translations alike.

### Reporting a bug
Open an [issue](https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/issues) and include:
* Windows build (`winver`) and Windhawk version.
* The mod version (shown in the README header / settings).
* Steps to reproduce it and what you expected instead.
* A screenshot or short clip when the problem is visual.

### Sending a pull request
1. Fork the repository and create a branch from `main`, e.g. `fix/acrylic-on-win10`.
2. Make your change in `spotlight-launcher.wh.cpp` (C++23, Windhawk tool mod).
3. Bump `@version` in the mod header when behaviour changes.
4. Confirm it compiles and test it on the Windows versions you can reach.
5. Open a pull request against `main` describing **what** changed and **why**.

Keep pull requests focused: one bug or feature per PR is much easier to review and merge.

---

## License

Released under the **MIT License**. See [`LICENSE`](https://github.com/DavidRaveloU/Spotlight-Launcher-Windhawk/blob/main/LICENSE).

Copyright (c) 2026-present David Ravelo.
