# Kitty Theme Loading Guide

## Where to put your theme files
Anywhere you want. Suggested spots:
```
~/.config/kitty/themes/       # tidy, kitty-adjacent
~/Music/ArchRice/Kitty/       # your current setup
~/.themes/kitty/              # alongside other rice files
```

---

## Method 1 — include in kitty.conf (recommended)
Edit `~/.config/kitty/kitty.conf` and add one line:
```
include ~/Music/ArchRice/Kitty/bastard.conf
```
- Use the **full path** from `~` or `/home/youruser/`
- Only one theme active at a time — comment out the others with `#`
- Reload: **Ctrl+Shift+F5**

---

## Method 2 — append via terminal (one-liner)
```bash
echo "include ~/Music/ArchRice/Kitty/bastard.conf" >> ~/.config/kitty/kitty.conf
```
Then reload with **Ctrl+Shift+F5**.

> ⚠️ Run this once per theme. Running it again adds a duplicate line.
> To remove old theme lines: `nano ~/.config/kitty/kitty.conf` and delete them.

---

## Method 3 — switch themes on the fly (no restart)
```bash
kitty @ set-colors --all ~/Music/ArchRice/Kitty/bastard.conf
```
- Takes effect **immediately** in all open kitty windows
- Does **not** persist after restart
- Useful for previewing before committing

---

## Method 4 — launch a one-off kitty window with a specific theme
```bash
kitty --config ~/Music/ArchRice/Kitty/bastard.conf
```
- Opens a new kitty instance with only that config
- Your main kitty.conf is ignored for this window
- Good for testing

---

## Switching between themes cleanly

Keep your `kitty.conf` like this:
```
# ── Active theme ─────────────────────────
include ~/Music/ArchRice/Kitty/bastard.conf
# include ~/Music/ArchRice/Kitty/hurejaesik.conf
# include ~/Music/ArchRice/Kitty/hurejaesik-abyss.conf
```
Comment/uncomment the one you want, then **Ctrl+Shift+F5**.

---

## Reload shortcut reference
| Action | Shortcut |
|---|---|
| Reload kitty.conf | Ctrl+Shift+F5 |
| Open kitty.conf in editor | Ctrl+Shift+F2 |
| Debug config (check for errors) | `kitty --debug-config` in terminal |
