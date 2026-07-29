# 🔤 06. Fonts

This guide installs the fonts I use after every fresh installation.

**⏱️ Estimated Time:** 3–5 minutes

---

## Step 1. Install Fonts

Install the required fonts from the official repositories.

```bash
sudo pacman -S \
noto-fonts \
noto-fonts-extra \
noto-fonts-cjk \
noto-fonts-emoji \
ttf-jetbrains-mono-nerd
```

Install Microsoft Core Fonts from the AUR.

```bash
paru -S ttf-ms-fonts
```

---

## Fonts

| Font | Purpose |
| ----- | ------- |
| **Noto Fonts** | Default UI font |
| **Noto Fonts Extra** | Additional Noto font families and weights |
| **Noto CJK** | Chinese, Japanese, and Korean character support |
| **Noto Emoji** | Colored emoji support |
| **JetBrains Mono Nerd Font** | Terminal, VS Code, Waybar, and Hyprland icons |
| **Microsoft Core Fonts** | Better compatibility with Microsoft Office documents |

---

## Verify

Verify that the fonts were installed successfully.

```bash
fc-list | grep "JetBrains"
fc-list | grep "Noto"
fc-list | grep "Arial"
fc-list | grep "Calibri"
```

---

## Notes

> 💡 **JetBrains Mono Nerd Font** is my primary monospace font for the terminal, VS Code, Waybar, and Hyprland.

> 💡 **Noto Fonts** provide excellent multilingual support and are used as the default font family across my system.

> 💡 **Microsoft Core Fonts** improve compatibility with Microsoft Office documents by providing fonts such as Arial, Times New Roman, Verdana, Georgia, Trebuchet MS, and Comic Sans MS.

---

## Useful Commands

List all installed fonts.

```bash
fc-list
```

Search for a specific font.

```bash
fc-list | grep "JetBrains"
```

Rebuild the font cache.

```bash
fc-cache -fv
```

---

## Troubleshooting

### ❌ Fonts are not displayed correctly

Rebuild the font cache.

```bash
fc-cache -fv
```

Verify that the font is installed.

```bash
fc-list | grep "JetBrains"
```

---

## Next

➡️ **07-development-setup.md**