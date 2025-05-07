# LibreBridge — Libérez vos données personnelles

LibreBridge est un outil libre, local et modulaire qui permet aux utilisateurs de récupérer leurs données personnelles en les exportant depuis des services propriétaires (Google, Apple, Meta, WhatsApp…) vers des alternatives ouvertes comme Nextcloud, DAVx⁵, Signal ou WebDAV.

Objectif : permettre une migration fluide et respectueuse de la vie privée grâce à des passerelles simples et auditables.

## Fonctionnalités principales

- Passerelles fiables pour calendriers, contacts, messages et fichiers
- Traitement 100 % local, aucune donnée envoyée à des serveurs externes
- Authentification sécurisée (OAuth2, tokens API), sandboxing
- Système de plugins extensible (format JSON ou JS)
- Migration en un clic depuis Google vers des formats libres
- Export périodique automatique (sauvegardes planifiées)
- Conversion d’exports WhatsApp en archives lisibles par Signal

## Stack technique

- Interface : React + Tauri (application locale multiplateforme)
- Back-end local : Node.js
- Authentification : OAuth2, tokens (Google, Meta, Apple)
- Formats de fichiers : `.ics`, `.vcf`, `.json`, `.eml`, `.zip`
- Distribution : Build Tauri, AppImage, Docker (WIP)

## Cas d’usage (MVP – v1)

| Données     | Export depuis             | Import vers                   |
|-------------|----------------------------|--------------------------------|
| Calendrier  | Google Calendar (.ics)     | Nextcloud / Thunderbird        |
| Contacts    | Gmail (.vcf)               | DAVx⁵ / Nextcloud              |
| Messages    | WhatsApp (.txt export)     | Archive compatible Signal      |
| Fichiers    | Google Drive               | Nextcloud / WebDAV             |

## Respect de la vie privée

LibreBridge fonctionne exclusivement sur l’ordinateur de l’utilisateur.  
Aucune donnée personnelle n’est transmise en ligne.  
Toutes les opérations sont isolées (sandboxées) et journalisées de manière transparente.

## Installation (prototype alpha)

LibreBridge est actuellement en développement. Voici les étapes pour exécuter un export de calendrier Google.

### 1. Prérequis

- Node.js ≥ 18
- Un projet Google Cloud avec l’API Calendar activée
- Vos identifiants OAuth2 (Client ID / Secret)

### 2. Cloner le dépôt

```bash
git clone https://github.com/MaxenceWyckhuys/LibreBridge.git
cd LibreBridge
