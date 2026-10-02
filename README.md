# Obsidian Knowledge Base

Dieses Repository enthält eine vollständig dockerisierte Obsidian-Umgebung inklusive Konfiguration und Vaults. Das Projekt kann auf einem neuen Gerät aus GitHub geklont und anschließend direkt über Docker Compose gestartet werden.

## Projektstruktur

```text
obsidian/
├── config/              # Obsidian-Konfiguration und Anwendungsdaten
├── vaults/              # Obsidian-Vaults und Markdown-Dokumentation
├── docker-compose.yml   # Docker-Compose-Konfiguration
├── .gitignore           # Von Git ausgeschlossene Dateien
└── README.md            # Projektdokumentation
```

## Voraussetzungen

Auf dem Zielgerät werden folgende Komponenten benötigt:

- Git
- Docker
- Docker Compose
- WSL2, falls Docker unter Windows verwendet wird

Installation prüfen:

```bash
git --version
docker --version
docker compose version
```

## Repository klonen

Repository in das gewünschte Verzeichnis klonen:

```bash
cd ~/02_Ops
git clone <REPOSITORY-URL> obsidian
cd obsidian
```

Beispiel:

```bash
git clone git@github.com:<BENUTZERNAME>/<REPOSITORY>.git obsidian
```

## Obsidian starten

Container im Hintergrund starten:

```bash
docker compose up -d
```

Status prüfen:

```bash
docker compose ps
```

Container und Logs anzeigen:

```bash
docker compose logs -f
```

Anschließend Obsidian über die in der `docker-compose.yml` konfigurierte Adresse aufrufen.

Beispiel:

```text
http://localhost:<PORT>
```

## Obsidian stoppen

Container stoppen:

```bash
docker compose stop
```

Container stoppen und entfernen:

```bash
docker compose down
```

Die Inhalte in `config/` und `vaults/` bleiben erhalten, sofern diese Verzeichnisse als lokale Volumes eingebunden sind.

## Obsidian neu starten

```bash
docker compose restart
```

Falls Änderungen an der `docker-compose.yml` vorgenommen wurden:

```bash
docker compose down
docker compose up -d
```

## Container aktualisieren

Aktuelles Container-Image herunterladen:

```bash
docker compose pull
```

Container anschließend neu erstellen:

```bash
docker compose up -d
```

Nicht mehr verwendete Images können optional entfernt werden:

```bash
docker image prune
```

## Änderungen in GitHub sichern

Aktuellen Status anzeigen:

```bash
git status
```

Änderungen hinzufügen:

```bash
git add .
```

Commit erstellen:

```bash
git commit -m "Dokumentation aktualisiert"
```

Änderungen zu GitHub übertragen:

```bash
git push
```

Kurzvariante:

```bash
git add . &&
git commit -m "Obsidian aktualisiert" &&
git push
```

> Falls keine Änderungen vorhanden sind, wird kein neuer Commit erstellt.

## Änderungen von GitHub übernehmen

Vor der Arbeit sollten Änderungen vom Repository abgerufen werden:

```bash
git pull
```

Falls Obsidian auf mehreren Geräten verwendet wird, empfiehlt sich folgender Ablauf:

```bash
cd ~/02_Ops/obsidian
git pull
docker compose up -d
```

Nach der Bearbeitung:

```bash
git add .
git commit -m "Obsidian-Inhalte aktualisiert"
git push
```

## Neues Gerät einrichten

Auf einem neuen Gerät sind im Wesentlichen folgende Schritte erforderlich:

```bash
cd ~/02_Ops
git clone <REPOSITORY-URL> obsidian
cd obsidian
docker compose up -d
```

Der Container verwendet anschließend die mitgelieferte Konfiguration und die vorhandenen Vaults.

## Verzeichnisse

### `config/`

Enthält die Konfiguration der containerisierten Obsidian-Umgebung. Je nach verwendetem Docker-Image können hier unter anderem Einstellungen, Plugins, Themes und weitere Anwendungsdaten gespeichert werden.

Vor einem Commit sollte geprüft werden, ob sich darin Zugangsdaten, Tokens, Sitzungsinformationen oder andere vertrauliche Daten befinden.

### `vaults/`

Enthält die eigentlichen Obsidian-Vaults:

- Markdown-Dateien
- Bilder und Anhänge
- interne Verlinkungen
- Obsidian-Einstellungen
- installierte Community-Plugins
- Themes und Snippets

Die Inhalte dieses Verzeichnisses bilden die eigentliche Wissensdatenbank.

## Sicherheitshinweis

Das GitHub-Repository sollte als **privat** angelegt werden, wenn die Vaults interne oder persönliche Informationen enthalten.

Vor dem Hochladen prüfen:

```bash
git status
git diff --cached
```

Insbesondere folgende Inhalte dürfen nicht versehentlich eingecheckt werden:

- Passwörter
- API-Schlüssel
- Zugriffstokens
- Zertifikate und private Schlüssel
- vertrauliche Unternehmensinformationen
- personenbezogene Daten
- Sitzungs- und Browserdaten

Sensible Einstellungen sollten über eine `.env`-Datei verwaltet werden.

Beispiel:

```text
.env
```

Die `.env`-Datei muss in `.gitignore` eingetragen sein:

```gitignore
.env
.env.*
!.env.example
```

Als Vorlage kann eine `.env.example` ohne echte Zugangsdaten eingecheckt werden.

## Empfohlene `.gitignore`

```gitignore
# Geheimnisse und lokale Umgebungsvariablen
.env
.env.*
!.env.example

# Protokolle
*.log
logs/

# Temporäre Dateien
*.tmp
*.temp
*.swp
*.bak
*~

# Betriebssystemdateien
.DS_Store
Thumbs.db
desktop.ini

# Obsidian-Papierkorb
.trash/

# Obsidian-Cache und gerätespezifischer Workspace
**/.obsidian/cache/
**/.obsidian/workspace.json
**/.obsidian/workspace-mobile.json

# Anwendungsspezifische Cache-Verzeichnisse
config/logs/
config/cache/
config/Cache/
config/CachedData/
config/GPUCache/
config/Code Cache/
config/Crashpad/
config/SingletonCookie
config/SingletonLock
config/SingletonSocket
```

> Die Ordner `config/` und `vaults/` werden grundsätzlich eingecheckt. Nur temporäre, gerätespezifische oder sicherheitsrelevante Dateien werden ausgeschlossen.

## Backup-Hinweis

GitHub dient als Versionsverwaltung und zusätzliche Sicherung der eingecheckten Inhalte. Für große Anhänge oder eine vollständige Datensicherung des Systems sollte zusätzlich ein separates Backup eingerichtet werden.

## Nützliche Befehle

```bash
# Container starten
docker compose up -d

# Status anzeigen
docker compose ps

# Logs anzeigen
docker compose logs -f

# Container neu starten
docker compose restart

# Container stoppen
docker compose down

# Images aktualisieren
docker compose pull
docker compose up -d

# Git-Status anzeigen
git status

# Änderungen herunterladen
git pull

# Änderungen hochladen
git add .
git commit -m "Obsidian aktualisiert"
git push
```
