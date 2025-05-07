🇫🇷 Lire ce document en français : [README.fr.md](README.fr.md)
# LibreBridge — Free your personal data

LibreBridge is a free, local-first, and modular migration tool that helps users reclaim their personal data by exporting it from proprietary services (Google, Apple, Meta, WhatsApp…) to open alternatives like Nextcloud, DAVx⁵, Signal, or WebDAV.

Goal: Enable painless, privacy-respecting migrations through user-friendly, auditable bridges.

## Key Features

- Simple, robust bridges for calendars, contacts, messages, and files
- 100% local operation — no data is ever sent to a server
- Secure authentication (OAuth2, API tokens), sandboxing
- Extensible plugin system (JSON or JS format)
- One-click migration from Google to open formats
- Scheduled backup mode (auto-export calendars, contacts, etc.)
- Convert WhatsApp exports into Signal-readable archives

## Technical Stack

- UI: React + Tauri (cross-platform local app)
- Local backend: Node.js
- Authentication: OAuth2, tokens (Google, Meta, Apple)
- File formats: `.ics`, `.vcf`, `.json`, `.eml`, `.zip`
- Distribution: Tauri build, AppImage, Docker (WIP)

## Use Cases (MVP – v1)

| Data Type   | Export From             | Import To                    |
|-------------|--------------------------|-------------------------------|
| Calendar    | Google Calendar (.ics)   | Nextcloud / Thunderbird       |
| Contacts    | Gmail (.vcf)             | DAVx⁵ / Nextcloud             |
| Messages    | WhatsApp (.txt export)   | Signal-like archive (readable)|
| Files       | Google Drive             | Nextcloud / WebDAV            |

## Privacy and Security

LibreBridge runs fully on the user’s device.  
No personal data is sent externally — all processing is sandboxed and local.  
A transparent logging system ensures traceability and auditability of operations.

## Installation (Alpha prototype)

LibreBridge is currently in early development. The following steps show how to run a basic Google Calendar export connector.

### 1. Prerequisites

- Node.js ≥ 18
- A Google Cloud project with Calendar API enabled
- OAuth2 credentials (Client ID / Secret)

### 2. Clone this repository

```bash
git clone https://github.com/MaxenceWyckhuys/LibreBridge.git
cd LibreBridge
