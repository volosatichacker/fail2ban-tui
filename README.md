# 🛡️ Fail2ban Interactive TUI Dashboard

🇷🇺 [Русская версия здесь](README_RU.md)

[![GitHub license](https://img.shields.io/github/license/volosatichacker/fail2ban-tui?style=flat-glowing&color=green)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/volosatichacker/fail2ban-tui?style=flat-glowing)](https://github.com/volosatichacker/fail2ban-tui/stargazers)
[![Shell Script](https://img.shields.io/badge/shell-bash-4ea1a3?style=flat-glowing&logo=gnu-bash)](https://www.gnu.org/software/bash/)

A lightweight, high-performance, and visually rich terminal-based dashboard (TUI) to monitor and manage **[Fail2ban](https://github.com/fail2ban/fail2ban)** (the official repository) directly from your command line.

---

## 🚀 Features

- 📊 **Real-time Service Monitoring**: Instantly check if `fail2ban-server` is running.
- 📂 **Dynamic Jails Detection**: Automatically scans and lists all active jails (e.g. `sshd`, `nginx-http-auth`).
- 🌍 **Geo-IP Integration**: Resolves banned IP locations, countries, and ISPs on the fly using `ip-api.com`.
- 🔨 **Active Control**:
  - **Ban IP**: Manually ban any malicious IP immediately.
  - **Unban IP**: Easily release IPs from the ban list.
- 📡 **Banned IP Collector**: Automatically logs every banned IP (both manual bans and automatic background bans) to a centralized endpoint (`https://banned.norkn.ru/api/ban`) using a custom Fail2ban action.
- 📜 **Log Viewer**: Live streaming of `/var/log/fail2ban.log`.
- 🗣️ **Localization**: Full English and Russian language support.
- 🎨 **Rich UI/Aesthetics**: Fully styled with curated ANSI color palettes.

---

## 🔥 Latest Updates (v1.3.0)

*   📡 **Banned IP Collector Integration**: Configures Fail2ban with a custom action (`norkn-ban`) to report all banned IP addresses automatically to `banned.norkn.ru`.
*   🌐 **Multi-language TUI**: Interactive choice of English/Russian on the first launch, with the ability to switch languages directly from the dashboard menu.
*   ⚙️ **Jail Settings Manager**: Dynamically adjust parameters like `bantime`, `findtime`, and `maxretry` in memory and write them persistently to `/etc/fail2ban/jail.local` using an automated INI configuration updater.
*   📦 **Automated Dependency Installer**: If Fail2ban is missing on the system, the script prompts the user to auto-install it and configures a secure default jail settings profile.
*   🎨 **Visual Alignment Fixes**: Fixed ANSI escape code evaluation in tables to ensure columns align perfectly.

---

## 🛠️ Installation & Usage

To install the dashboard on your server, simply run:

```bash
sudo curl -fsSL -o /usr/local/bin/fail2ban https://raw.githubusercontent.com/volosatichacker/fail2ban-tui/main/fail2ban && sudo chmod +x /usr/local/bin/fail2ban && sudo fail2ban
```

Once installed, open the dashboard from any terminal directory:

```bash
sudo fail2ban
```

---

## ⚙️ Configuration & Requirements

> [!IMPORTANT]
> The script must be run with **root** privileges (`sudo`) to interact with `fail2ban-client` and read logs.

### Dependencies
- `curl` — for real-time Geo-IP API queries.
- `jq` (Optional, recommended) — for clean JSON parsing (falls back to regex string manipulation if `jq` is absent).

---

## 📄 License

Distributed under the MIT License. See [LICENSE](LICENSE) for more info.
