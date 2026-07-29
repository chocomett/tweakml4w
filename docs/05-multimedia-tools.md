# 🎬 05. Multimedia Tools

This guide installs the multimedia applications I use on every fresh installation.

**⏱️ Estimated Time:** 3–5 minutes

---

## Step 1. Install Multimedia Applications

Install the multimedia applications.

```bash
sudo pacman -S \
gwenview \
mpv \
obs-studio \
ffmpeg
```

---

## Applications

| Application | Purpose |
| ------------ | ------- |
| **Gwenview** | Image Viewer |
| **mpv** | Video Player |
| **OBS Studio** | Screen Recording & Streaming |
| **FFmpeg** | Audio & Video Processing |

---

## Verify

Verify that the applications were installed successfully.

```bash
gwenview --version
mpv --version
obs --version
ffmpeg -version
```

You can also launch the applications from the application launcher.

---

## Notes

> 💡 **FFmpeg** is a powerful command-line tool used for converting, recording, and processing audio and video. It is also required by many multimedia applications.

---

## Useful Commands

Display FFmpeg version.

```bash
ffmpeg -version
```

Convert a video.

```bash
ffmpeg -i input.mov output.mp4
```

Extract audio from a video.

```bash
ffmpeg -i input.mp4 output.mp3
```

Display media information.

```bash
ffprobe input.mp4
```

---

## Next

➡️ **06-fonts.md**