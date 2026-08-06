# 🎥 01. OBS Studio

This guide installs **OBS Studio** with **Virtual Camera** support on Arch Linux.

**⏱️ Estimated Time:** 5–10 minutes

---

## Step 1. Install OBS Studio

```bash
sudo pacman -S obs-studio linux-headers v4l2loopback-dkms
```

---

## Step 2. Reboot

Reboot the system to load the latest kernel.

```bash
sudo reboot
```

---

## Step 3. Build the DKMS Module

```bash
sudo dkms autoinstall
```

---

## Step 4. Enable Virtual Camera

```bash
sudo modprobe v4l2loopback \
    exclusive_caps=1 \
    video_nr=10 \
    card_label="OBS Virtual Camera"
```

---

## Verify

```bash
obs --version
lsmod | grep v4l2loopback
ls /dev/video*
```

---

## Troubleshooting

### ❌ `modprobe: FATAL: Module v4l2loopback not found`

Rebuild the DKMS module.

```bash
sudo dkms autoinstall
```

---
