# 🎨 02. ML4W Installation

This guide installs ML4W Dotfiles on a fresh Arch Linux installation.

**⏱️ Estimated Time:** 15–30 minutes

---

## Step 1. Run the Installer

Execute the official ML4W installer.

```bash
bash <(curl -s https://raw.githubusercontent.com/mylinuxforwork/dotfiles/main/setup.sh)
```

---

## Step 2. Select Package Helper

Choose:

```text
paru
```

> 💡 **Tip**
>
> Always choose **paru**. The installer will automatically install and configure it.

---

## Step 3. Reboot

```bash
reboot
```

---

## Step 4. First Login

- ✅ Log in to **Hyprland**
- ✅ Complete the initial setup
- ✅ Open a terminal

---

## Step 5. Install Essential Applications

```bash
paru -S \
google-chrome \
visual-studio-code-bin
```

---

## Verify

```bash
google-chrome-stable --version
code --version
```

---

## Notes

> 📝 Install additional applications only after the ML4W setup is complete.

---

## Troubleshooting

### ❌ `paru: command not found`

Run the installer again and select **paru**.

---

## Next

➡️ **03-sddm-setup.md**