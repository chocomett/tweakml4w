# 03. SDDM Setup

This guide installs and enables SDDM as the display manager.

---

# Install SDDM

```bash
sudo pacman -S sddm
```

---

# Enable SDDM

```bash
sudo systemctl enable sddm.service
```

---

# Reboot

```bash
sudo reboot now
```

---

# Verification

The SDDM login screen should appear.

Log in to **Hyprland**.

---

# Next

Continue with:

> 04-custom-keybinds.md