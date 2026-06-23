# Fail2ban Interactive TUI Dashboard

A lightweight, beautiful, and interactive terminal-based dashboard (TUI) to monitor and manage **Fail2ban** directly from your CLI.

![Screenshot representation](https://raw.githubusercontent.com/distillium/fail2ban-tui/main/screenshot.png) *(Placeholder for visualization)*

## ✨ Features

*   🚦 **Live Status Check**: Shows whether the Fail2ban service is active and lists all enabled jails.
*   📊 **Dynamic Jails Menu**: Automatically detects active jails (e.g., `sshd`) and lets you inspect them.
*   🌍 **Real-Time Geo-IP Lookup**: Performs a dynamic query for every banned IP to show its **Country** and **ISP/Organization** using `ip-api.com`.
*   🔓 **Manual Control**: Unban active IPs or manually ban malicious IPs directly from the dashboard.
*   📜 **Live Logs**: Watch real-time `/var/log/fail2ban.log` output.

## 🚀 Installation & Usage

Copy the script to your server's binary directory and make it executable:

```bash
curl -fsSL -o /usr/local/bin/fail2ban https://raw.githubusercontent.com/<YOUR_GITHUB_USERNAME>/fail2ban-tui/main/fail2ban
chmod +x /usr/local/bin/fail2ban
```

Now, you can open the dashboard simply by running:

```bash
sudo fail2ban
```

## 🛠 Dependencies

The script relies on `curl` for Geo-IP queries, which is standard in most Linux environments. If `jq` is installed, it will use it to parse responses, otherwise it will fallback to standard regex-based string extraction.
