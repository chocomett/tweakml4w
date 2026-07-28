# 01. Arch Linux Installation

This guide covers my standard Arch Linux installation before installing ML4W Dotfiles.

---

# Boot

Boot the latest Arch Linux ISO in **UEFI mode**.

Verify internet connection.

```bash
ping archlinux.org
```

For Wi-Fi:

```bash
iwctl
```

---

# Start Installer

```bash
archinstall
```

---

# Installation Configuration

## Language

- English

## Mirrors

- Indonesia

## Disk Layout

### Recommended Layout

Use **Manual Partitioning**.

| Mount Point | Size | Filesystem |
| ------------ | ---- | ---------- |
| `/boot` | 1 GiB | FAT32 |
| `swap` | Match RAM | Linux Swap |
| `/` | Remaining Space | Ext4 |

Example (8 GB RAM):

| Partition | Size |
| ---------- | ---- |
| EFI | 1 GiB |
| Swap | 8 GiB |
| Root | Remaining Disk |

### Alternate Layout (Using zram)

| Mount Point | Size | Filesystem |
| ------------ | ---- | ---------- |
| `/boot` | 1 GiB | FAT32 |
| `/` | Remaining Space | Ext4 |

zram will be configured later.

---

## Bootloader

- Systemd-boot → Single Boot
- GRUB → Dual Boot / Multi Boot

---

## Hostname

Choose your preferred hostname.

---

## User

Create the primary user.

Enable:

- Wheel
- Sudo

---

## Audio

- PipeWire

---

## Network

- iwd (Default)

---

## Timezone

- Asia/Jakarta

---

## NTP

- Enabled

---

## Desktop

- None

---

# Install

Review all settings.

Select **Install**.

Wait until installation finishes.

---

# First Boot

Remove the installation media.

Reboot into Arch Linux.

---

# Post Installation

Update the system.

```bash
sudo pacman -Syu
```

Install required packages.

```bash
sudo pacman -S \
base-devel \
git \
curl \
wget \
zip \
unzip
```

---

# Next

Continue with:

> 02-ml4w-installation.md