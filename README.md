<p align="center">
  <br>
  <h1 align="center">Nexus Ultimate Control Center</h1>
  <p align="center">
    <b>Your servers. Your sites. Your universe. All inside VS Code.</b>
  </p>
  <p align="center">
    <img src="https://img.shields.io/badge/VS%20Code-1.109%2B-007ACC?logo=visualstudiocode&logoColor=white" alt="VS Code 1.109+">
    <img src="https://img.shields.io/badge/TypeScript-Strict-3178C6?logo=typescript&logoColor=white" alt="TypeScript">
    <img src="https://img.shields.io/badge/Three.js-r128-000000?logo=threedotjs&logoColor=white" alt="Three.js">
    <img src="https://img.shields.io/badge/SSH2-Secure-4EAA25?logo=gnubash&logoColor=white" alt="SSH2">
  </p>
</p>

---

**Stop juggling SSH terminals, web panels, and monitoring dashboards.**

Nexus puts full server administration, real-time 3D infrastructure visualization, and visual site editing into a single VS Code extension. One click to connect. Zero browser tabs. Total control.

If you've ever dreamed of HestiaCP + Webmin + Portainer + Grafana fused into your editor &mdash; this is it.

---

## Server Control &mdash; 10-Panel Admin Suite

Connect to any Linux server via SSH (key or password) and manage everything through a modern glassmorphic UI. No browser needed.

| Panel | Capabilities |
|-------|-------------|
| **Docker** | Containers, images, networks, volumes, compose stacks. Start/stop/restart/exec/logs/stats/pull/prune &mdash; full lifecycle management |
| **Nginx** | View and edit site configs, enable/disable sites, reload, create new sites, one-click Let's Encrypt SSL |
| **Database** | MySQL + PostgreSQL. Create/drop databases, user management, run SQL queries, backup & restore |
| **Services** | systemd services: start, stop, restart, enable, disable, journal logs |
| **Security** | UFW firewall rules, fail2ban status, SSH hardening, port management |
| **Files** | Dual-pane WinSCP-style file manager. Upload/download via SFTP, rename, delete, create folders |
| **Backup** | Full server snapshots, MySQL/PG dumps, S3 sync, cron-scheduled backups |
| **Metrics** | Real-time CPU, RAM, Disk, Network, Load Average, top processes |
| **Deploy** | Git pull + build + restart, PM2 process management, Docker Compose deploy, webhook auto-deploy |
| **Logs** | Live-tail any log file (syslog, nginx, auth, custom), search, filter, export |

**Dual connection model:** interactive VS Code Terminal for hands-on SSH *plus* programmatic `ssh2` connection for data fetching &mdash; running simultaneously on a single Connect click.

---

## Server Universe 3D &mdash; See Your Infrastructure

A real-time Three.js visualization that turns your server fleet into a living cosmos.

**Visual mapping:**

| Server metric | 3D representation |
|--------------|-------------------|
| RAM capacity | Planet size |
| CPU load | Core glow intensity (pulsating) |
| Health status | Planet color: green / yellow / red / gray |
| Docker containers | Saturn-like rings (blue=running, red=stopped, yellow=paused) |
| systemd services | Orbiting satellites (green=active, red=failed) |
| Network | Particle streams flowing between servers |

**Automatic cosmic events:**
- Server offline &rarr; a **black hole** forms (accretion disk + spiraling particles)
- CPU > 90% &rarr; **supernova** explosion (shockwave + particle burst + flash)
- VPN tunnel &rarr; **wormhole** between two server planets

**4 view modes:** Galaxy (spiral overview) &middot; Solar System (central server focus) &middot; Network (grid topology) &middot; Matrix (column layout)

**6 color schemes:** Cosmos &middot; Nebula &middot; Matrix &middot; Synthwave &middot; Ice &middot; Fire

Independent SSH connections poll metrics every 10 seconds. Custom orbit controls (Ctrl+click rotate, scroll zoom), no external dependencies.

---

## Site Builder &mdash; Visual Constructor

Drag-and-drop website builder powered by **GrapesJS**. Component library, responsive design preview, CSS/JS editing, and project export.

## Site Editor &mdash; Edit Existing Sites

Connect to a **live website** by URL or server path. Move blocks, edit text, add and remove elements visually &mdash; changes save directly to the server via SSH.

## Atomic Clock &mdash; Productivity Widget

Clock + calendar with a local **SQLite** notes database. Pin notes to dates, search your history, stay organized without leaving the editor.

---

## Getting Started

```
1. Install from VS Code Marketplace
2. Click "Servers" in the status bar
3. Click "+ Add Server" — enter host, username, SSH key or password
4. Hit "Connect" — done
5. Navigate any panel: Docker, Nginx, Database, Files...
```

For 3D mode: click **Universe 3D** in the top bar, status bar, sidebar, or Command Palette.

---

## Extension Logging

Full OutputChannel logging for transparency and debugging:

```
[2026-02-20T12:34:56.789Z] [ServerControl] SSH connected to Production Server successfully
[2026-02-20T12:34:57.123Z] [ServerControl] SSH exec [prod-1]: docker ps -a --format ...
[2026-02-20T12:35:06.456Z] [Universe3D] Collecting metrics from Production Server (10.0.0.1)
```

Open via the **Logs** button in the panel, or `Ctrl+Shift+U` &rarr; channel "Nexus Server Control".

---

## Security

| Measure | Implementation |
|---------|---------------|
| Credential storage | VS Code **SecretStorage** (OS-level keychain) |
| SSH key encryption | AES-256-GCM with master password + scrypt key derivation |
| Database passwords | `--defaults-extra-file` (invisible in process list) |
| Command injection | Input validation on all SSH parameters (SQL names, IPs, ports, Docker names) |
| Compose deploy | YAML written via SFTP (no shell injection through heredoc) |
| XSS prevention | HTML escaping on all user-visible data |

---

## Tech Stack

| Technology | Purpose |
|-----------|---------|
| VS Code Extension API | WebView panels, commands, status bar, sidebar views, SecretStorage |
| ssh2 | Programmatic SSH and SFTP |
| Three.js r128 | 3D visualization (CDN-loaded, zero bundling) |
| GrapesJS | Visual site builder engine |
| SQLite3 | Local notes database |
| TypeScript | Strict types across all modules |

---

## Requirements

- **VS Code 1.109+**
- SSH access to target servers (key-based or password)
- Docker on target servers (for Docker panel features)
- systemd (for Services panel)
- Nginx (for Nginx panel)
- MySQL / PostgreSQL (for Database panel)

---

## Commands

| Command | Description |
|---------|-------------|
| `Nexus: Open Server Control` | Main admin panel |
| `Nexus: Open Server Universe 3D` | 3D infrastructure visualization |
| `Nexus: Open Site Builder` | Visual site constructor |
| `Nexus: Open Site Editor` | Live site editor |
| `Nexus: Open Atomic Clock` | Clock + calendar widget |

---

## Author

**islam-dev**

Built for developers who live in their editor and refuse to leave.
