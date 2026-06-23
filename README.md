# 🛡️ Fail2ban Interactive TUI Dashboard

[![GitHub license](https://img.shields.io/github/license/volosatichacker/fail2ban-tui?style=flat-glowing&color=green)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/volosatichacker/fail2ban-tui?style=flat-glowing)](https://github.com/volosatichacker/fail2ban-tui/stargazers)
[![Shell Script](https://img.shields.io/badge/shell-bash-4ea1a3?style=flat-glowing&logo=gnu-bash)](https://www.gnu.org/software/bash/)

A lightweight, high-performance, and visually rich terminal-based dashboard (TUI) to monitor and manage **Fail2ban** directly from your command line.

---

## 🚀 Features

- 📊 **Real-time Service Monitoring**: Instantly check if `fail2ban-server` is running.
- 📂 **Dynamic Jails Detection**: Automatically scans and lists all active jails (e.g. `sshd`, `nginx-http-auth`).
- 🌍 **Geo-IP Integration**: Resolves banned IP locations, countries, and ISPs on the fly using `ip-api.com`.
- 🔨 **Active Control**:
  - **Ban IP**: Manually ban any malicious IP immediately.
  - **Unban IP**: Easily release IPs from the ban list.
- 📜 **Log Viewer**: Live streaming of `/var/log/fail2ban.log`.
- 🎨 **Rich UI/Aesthetics**: Fully styled with curated ANSI color palettes.

---

## 🛠️ Installation & Usage

To install the dashboard on your server, simply run:

```bash
sudo curl -fsSL -o /usr/local/bin/fail2ban https://raw.githubusercontent.com/volosatichacker/fail2ban-tui/main/fail2ban && sudo chmod +x /usr/local/bin/fail2ban
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

## 📋 Screenshot Preview

```text
================================================================
  🛡️ FAIL2BAN INTERACTIVE TUI DASHBOARD  
  Сервер: uhhit | Время: 2026-06-23 15:32:00
================================================================

[+] Статус службы Fail2ban:
    Статус: ACTIVE (Запущена)

[+] Активные Jails:
    • sshd (Забанено сейчас: 6 | Всего банов: 70)

Главное меню:
    1. Подробная статистика и управление Jail: sshd
    2. Просмотр живых логов Fail2ban (/var/log/fail2ban.log)
    3. Выйти
```

---

## 📄 License

Distributed under the MIT License. See [LICENSE](LICENSE) for more info.
