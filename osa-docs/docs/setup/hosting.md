# Installation & Hosting

OSA Bot is hosted on **Oracle Cloud Always Free** (Ubuntu 22.04) and managed via GitHub. This page covers the full setup from scratch.

---

## Prerequisites

- A Discord application and bot token from the [Discord Developer Portal](https://discord.com/developers/applications)
- An Oracle Cloud account (free tier is sufficient)
- A GitHub account with access to the [osa-bot repository](https://github.com/CaptainBHH/osa-bot)

---

## Server setup

### 1. Connect via SSH

```bash
ssh -i /path/to/ssh-key.key ubuntu@YOUR_SERVER_IP
```

### 2. Install dependencies

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install python3 python3-pip git sqlite3 -y
pip3 install discord.py aiosqlite aiohttp
```

### 3. Clone the repository

```bash
cd ~
git clone https://github.com/CaptainBHH/osa-bot.git
cd osa-bot
```

### 4. Create the config file

```bash
nano config.json
```

Add your bot token:

```json
{
  "token": "YOUR_BOT_TOKEN_HERE"
}
```

---

## Running as a systemd service

This keeps the bot running in the background and auto-restarts it on failure or reboot.

### Create the service file

```bash
sudo nano /etc/systemd/system/osa-bot.service
```

```ini
[Unit]
Description=OSA Discord Bot
After=network.target

[Service]
Type=simple
User=ubuntu
WorkingDirectory=/home/ubuntu/osa-bot
ExecStart=/usr/bin/python3 main.py
Restart=always
RestartSec=5

[Install]
WantedBy=multi-user.target
```

### Enable and start

```bash
sudo systemctl daemon-reload
sudo systemctl enable osa-bot
sudo systemctl start osa-bot
```

### Check status

```bash
sudo systemctl status osa-bot
sudo journalctl -u osa-bot -n 30 --no-pager
```

---

## Updating the bot

All updates are pushed via GitHub. To deploy:

```bash
cd ~/osa-bot
git pull
sudo systemctl restart osa-bot
sudo journalctl -u osa-bot -n 20 --no-pager
```

---

## Firewall notes

Oracle Cloud has two firewall layers — the OS firewall (`iptables`) and the cloud security list. If you host the transcript web viewer, you'll need to open port 5000 on both.

```bash
# OS firewall
sudo iptables -I INPUT -p tcp --dport 5000 -j ACCEPT
```

The security list is configured in the Oracle Cloud console under **Networking → Virtual Cloud Networks → Security Lists**.
