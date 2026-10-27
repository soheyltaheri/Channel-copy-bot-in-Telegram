# Telegram Channel Transfer & Cloner Bot

<p align="center">
  <strong>Automated Telegram Channel Content Extraction, Video Watermarking & Migration Daemon</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10%2B-3776AB.svg?logo=python&logoColor=white" alt="Python Version" />
  <img src="https://img.shields.io/badge/Pyrogram-v2.0-2CA5E0.svg?logo=telegram&logoColor=white" alt="Pyrogram" />
  <img src="https://img.shields.io/badge/FFmpeg-Watermarking-007808.svg?logo=ffmpeg&logoColor=white" alt="FFmpeg" />
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="MIT License" />
</p>

---

## 📌 Overview

**Telegram Channel Transfer Bot** is an enterprise-grade channel backup and migration utility engineered with **Pyrogram** and **FFmpeg**. Designed for high-volume content duplication, it safely clones complete channel histories, handles grouped media albums, strips external sponsor links, applies custom font watermarks to video payloads, and queues messages with rate-limit evasion.

---

## 🌟 Key Features

- 🔄 **Full Channel History Migration:** Iterates through thousands of channel messages from origin to destination without message loss.
- 🎬 **Dynamic Video Watermarking:** Integrates directly with `FFmpeg` to embed branded text or logo overlays onto videos on the fly.
- 📦 **Album & Grouped Media Preservation:** Retains Telegram native album structures (multi-photo/video posts) during re-uploading.
- 🧹 **Caption Sanitization & Rebranding:** Automated regex rules to clean unwanted hyperlinks, telegram mentions, and promotional tags before posting.
- ⚙️ **Automated Linux Systemd Daemon:** Includes `setup.sh` and `bootstrap.py` for one-click setup, venv isolation, and background service creation.

---

## 🚀 Quickstart & Server Deployment

### Recommended: Debian / Ubuntu Automated Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/soheyltaheri/Channel-copy-bot-in-Telegram.git
   cd Channel-copy-bot-in-Telegram
   ```

2. **Run the installer:**
   ```bash
   chmod +x setup.sh
   ./setup.sh
   ```
   The installer automatically:
   - Creates a Python virtual environment (`venv`).
   - Installs all Pyrogram & cryptographic dependencies.
   - Interactively requests your `API_ID`, `API_HASH`, and `BOT_TOKEN`.
   - Generates a systemd daemon (`transferbot.service`) and enables autostart on reboot.

---

### Manual Cross-Platform Setup

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Configure environment
cat <<EOF > .env
API_ID=your_api_id
API_HASH=your_api_hash
BOT_TOKEN=your_bot_token
EOF

# 3. Start interactively
python bot.py
```

---

## ⚙️ Service Management

To monitor the background transfer daemon on Linux:

```bash
# Check service status
sudo systemctl status transferbot

# View live streaming logs
sudo journalctl -u transferbot -f
```

---

## 📄 License

This repository is distributed under the [MIT License](LICENSE).

