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
| `swap` | Match RAM (e.g. 8 GiB) | Linux Swap |
| `/` | Remaining Space | Ext4 |

Example (8 GB RAM):

| Partition | Size |
| ---------- | ---- |
| EFI | 1 GiB |
| Swap | 8 GiB |
| Root | Remaining Disk |

---

### Alternate Layout (Using zram)

If using **zram**, a dedicated swap partition is unnecessary.

| Mount Point | Size | Filesystem |
| ------------ | ---- | ---------- |
| `/boot` | 1 GiB | FAT32 |
| `/` | Remaining Space | Ext4 |

zram will be configured after installation.

---

## Bootloader

- **Systemd-boot** → Single boot system
- **GRUB** → Dual boot or multi boot system

---

## Hostname

Choose your preferred hostname.

Example:

```
arch
```

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

## Desktop Environment

- None

ML4W will be installed after the base system.

---

# Install

Review all settings.

Select:

```
Install
```

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

Install essential packages.

```bash
sudo pacman -S \
base-devel \
git \
curl \
wget \
zip \
unzip
```

Install Paru.

```bash
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si
```

## Install Essential Applications

Install the applications I use on every fresh installation.

```bash
paru -S \
google-chrome \
visual-studio-code-bin
```

---

# Next

Continue with:

> 02-ml4w-installation.md