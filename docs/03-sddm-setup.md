# 🖥️ 03. SDDM Setup

This guide installs and enables SDDM as the display manager.

**⏱️ Estimated Time:** 2–5 minutes

---

## Step 1. Install SDDM

Install the SDDM package.

```bash
sudo pacman -S sddm
```

---

## Step 2. Enable SDDM

Enable SDDM to start automatically at boot.

```bash
sudo systemctl enable sddm.service
```

---

## Step 3. Reboot

Restart the system.

```bash
sudo reboot
```

---

## Verify

After rebooting:

- ✅ The **SDDM** login screen appears.
- ✅ You can log in to **Hyprland** successfully.

---

## Notes

> 💡 **Tip**
>
> If you already have another display manager installed (such as GDM or LightDM), disable it before enabling SDDM to avoid conflicts.

---

## Useful Commands

Check SDDM status.

```bash
systemctl status sddm
```

Start SDDM manually.

```bash
sudo systemctl start sddm
```

Stop SDDM.

```bash
sudo systemctl stop sddm
```

Restart SDDM.

```bash
sudo systemctl restart sddm
```

Disable SDDM.

```bash
sudo systemctl disable sddm
```

---

## Troubleshooting

### ❌ SDDM does not appear after reboot

Check whether the service is enabled.

```bash
systemctl is-enabled sddm
```

View the service logs.

```bash
journalctl -u sddm
```

Verify that your graphics driver and Hyprland session are installed correctly.

---

## Next

➡️ **04-custom-keybinds.md**