# 🐧 01. Arch Linux Installation

This guide covers my standard Arch Linux installation before installing ML4W Dotfiles.

**⏱️ Estimated Time:** 20–40 minutes

---

## Step 1. Boot the Installation Media

Boot the latest Arch Linux ISO in **UEFI mode**.

Verify your internet connection.

```bash
ping archlinux.org
```

For a Wi-Fi connection, use:

```bash
iwctl
```

---

## Step 2. Start the Installer

Launch the Arch Linux installer.

```bash
archinstall
```

---

## Step 3. Configure the Installation

### Language

- English

### Mirrors

- Indonesia

### Disk Layout

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

### Alternative Layout (Using zram)

If you plan to use **zram**, a dedicated swap partition is unnecessary.

| Mount Point | Size | Filesystem |
| ------------ | ---- | ---------- |
| `/boot` | 1 GiB | FAT32 |
| `/` | Remaining Space | Ext4 |

zram can be configured after installation.

### Bootloader

- **systemd-boot** — Single boot system
- **GRUB** — Dual boot or multi boot system

### Hostname

Example:

```text
arch
```

### User

Create your primary user and enable:

- Wheel
- Sudo

### Audio

- PipeWire

### Network

- iwd (Default)

### Timezone

- Asia/Jakarta

### NTP

- Enabled

### Desktop Environment

- None

ML4W will be installed after the base system.

---

## Step 4. Install Arch Linux

Review the configuration.

Select:

```text
Install
```

Wait until the installation is complete.

---

## Step 5. First Boot

- Remove the installation media.
- Boot into your new Arch Linux installation.

---

## Step 6. Post Installation

Update the system.

```bash
sudo pacman -Syu
```

Install the essential packages.

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

## Verify

Verify that the required packages are installed.

```bash
git --version
curl --version
wget --version
```

---

## Notes

> 💡 I use **Manual Partitioning** for better control over the installation.

> 💡 I prefer **systemd-boot** for a single-boot system and **GRUB** only when dual booting.

> 💡 I do not install a desktop environment here because ML4W will configure Hyprland later.

---

## Troubleshooting

### ❌ No internet connection

Verify your network connection.

```bash
ping archlinux.org
```

For Wi-Fi, reconnect using:

```bash
iwctl
```

### ❌ Installation failed

Review your partition layout and ensure the EFI partition is formatted as **FAT32** and mounted at `/boot`.

---

## Next

➡️ **02-ml4w-installation.md**