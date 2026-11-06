# SerNotes

Aufgaben per Sprachbefehl – mit Fristen, Timern, Prioritäten und Papierkorb. Eine einzelne HTML-Datei, läuft im Browser (Chrome, Edge, Safari) und muss über **https://** geöffnet werden, damit das Mikrofon funktioniert.

## Dateien
| Datei | Zweck |
|---|---|
| `index.html` | Die App |
| `version.json` | Aktuelle Version und Changelog – die App fragt diese Datei ab, um Updates zu erkennen |
| `CHANGELOG.md` | Änderungen zum Lesen |
| `.github/workflows/deploy.yml` | Lädt die App bei jeder Änderung automatisch per FTP auf den Webspace |

## Neue Version veröffentlichen
1. In `index.html` die Zeile `const APP_VERSION = "…"` erhöhen.
2. In `version.json` dieselbe Nummer bei `version` eintragen und oben im `changelog` einen Eintrag ergänzen.
3. `CHANGELOG.md` ergänzen.
4. Auf `main` hochladen – der Upload auf den Webspace läuft automatisch.

## Automatischer Upload einrichten (einmalig)
Unter **Settings → Secrets and variables → Actions → New repository secret** vier Secrets anlegen:

| Name | Inhalt | Beispiel |
|---|---|---|
| `FTP_SERVER` | FTP-Server des Hosters | `ftp.example.de` |
| `FTP_USERNAME` | FTP-Benutzer | `web123` |
| `FTP_PASSWORD` | FTP-Passwort | |
| `FTP_DIR` | Zielordner auf dem Webspace, mit `/` am Ende | `/notizen/` |

Die Notizen selbst liegen nur im Browser des jeweiligen Geräts – ein Update löscht sie nicht.
