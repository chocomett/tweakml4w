# 06. Fonts

This guide installs the fonts I use after every fresh installation.

---

# Install

Official Repository

```bash
sudo pacman -S \
noto-fonts \
noto-fonts-cjk \
noto-fonts-emoji \
ttf-jetbrains-mono-nerd
```

AUR

```bash
paru -S ttf-ms-fonts
```

---

# Fonts

| Font | Purpose |
| ----- | ------- |
| **Noto Fonts** | Default UI font |
| **Noto CJK** | Chinese, Japanese, Korean characters |
| **Noto Emoji** | Colored emoji support |
| **JetBrains Mono Nerd Font** | Terminal, VS Code, Waybar, Hyprland icons |
| **Microsoft Core Fonts** | Better compatibility with Microsoft Office documents |

---

# Verify

```bash
fc-list | grep "JetBrains"
fc-list | grep "Noto"
fc-list | grep "Arial"
fc-list | grep "Calibri"
```

---

# Next

Continue with:

> 07-development-setup.md