# 04. Custom Keybinds

This guide covers the keybinding changes I always apply after installing ML4W.

---

# 1. Open Terminal

Move the terminal shortcut from **Super + Enter** to **Super + Q**.

Replace:

```lua
hl.bind(mainMod .. " + RETURN", hl.dsp.exec_cmd("~/.config/ml4w/settings/terminal.sh"), {
    description = "Open the terminal"
})
```

With:

```lua
hl.bind(mainMod .. " + Q", hl.dsp.exec_cmd("~/.config/ml4w/settings/terminal.sh"), {
    description = "Open the terminal"
})
```

---

# 2. Kill Active Window

Move the shortcut from **Super + Q** to **Super + C**.

Replace:

```lua
hl.bind(mainMod .. " + Q", hl.dsp.exec_cmd("killactive"), {
    description = "Kill active window"
})
```

With:

```lua
hl.bind(mainMod .. " + C", hl.dsp.exec_cmd("killactive"), {
    description = "Kill active window"
})
```

---

# 3. Toggle Spotlight Search

Add a new keybinding.

```lua
hl.bind(mainMod .. " + D", hl.dsp.exec_cmd([[sh -c 'pgrep -x rofi >/dev/null && pkill -x rofi || rofi -show combi -combi-modes "drun,run,window" -modi "drun,run,window" -show-icons']]), {
    description = "Toggle Spotlight Search"
})
```

---

# 4. Custom Screenshot

Replace the default screenshot keybindings.

```lua
hl.bind(mainMod .. " + PRINT", hl.dsp.exec_cmd("~/.config/hypr/scripts/custom-screenshot.sh"), {
    description = "Copy Fullscreen Screenshot"
})

hl.bind(mainMod .. " + SHIFT + F", hl.dsp.exec_cmd("~/.config/hypr/scripts/custom-screenshot.sh --instant"), {
    description = "Copy Fullscreen Screenshot"
})

hl.bind("ALT + S", hl.dsp.exec_cmd("~/.config/hypr/scripts/custom-screenshot.sh --instant-area"), {
    description = "Copy Area Screenshot"
})
```

Script:

```text
~/.config/hypr/scripts/custom-screenshot.sh
```

---

# Next

Continue with:

> 05-multimedia-tools.md