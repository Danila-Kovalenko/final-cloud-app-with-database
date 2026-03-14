# Online Course Plattform mit Prüfungsfunktion (Django)

Diese Anwendung ist eine webbasierte Lernplattform auf Basis von **Django**. Nutzer können sich registrieren, anmelden, Kurse durchsuchen, sich einschreiben und am Ende kursbezogene Prüfungen mit Multiple-Choice-Fragen absolvieren.

## Projektüberblick

Die App besteht aus einem Django-Projekt (`myproject`) und der Hauptanwendung `onlinecourse`.

Wichtige Funktionen:
- Benutzerregistrierung und Login/Logout
- Kursübersicht mit Einschreibestatus
- Kurseinschreibung mit Zählung der Teilnehmer
- Kursdetailseiten mit Lektionen und Prüfung
- Prüfungsabgabe und automatische Punkteberechnung
- Anzeige des Prüfungsergebnisses pro Abgabe

## Datenmodell (Kurzfassung)

Die zentrale Domäne ist `onlinecourse/models.py` und enthält u. a.:
- `Instructor` und `Learner` für Rollenprofile
- `Course` und `Lesson` für Kursinhalte
- `Enrollment` für Einschreibungen
- `Question`, `Choice` und `Submission` für die Prüfungslogik

## Technologie-Stack

- Python 3.8
- Django 3.1.3
- SQLite (standardmäßig lokal)
- Gunicorn (für Deployment)
- Bootstrap (über CDN in Templates)

## Lokale Ausführung

1. Abhängigkeiten installieren:
   ```bash
   pip install -r requirements.txt
   ```
2. Migrationen anwenden:
   ```bash
   python manage.py migrate
   ```
3. Entwicklungsserver starten:
   ```bash
   python manage.py runserver
   ```
4. Anwendung öffnen:
   - `http://127.0.0.1:8000/onlinecourse/`

## Nützliche Befehle

- Tests ausführen:
  ```bash
  python manage.py test
  ```
- Admin-Benutzer erstellen:
  ```bash
  python manage.py createsuperuser
  ```

## Deployment-Hinweise

Das Repository enthält bereits Dateien für Cloud-Deployment, u. a.:
- `Procfile`
- `manifest.yml`
- `runtime.txt`

Die Anwendung ist so strukturiert, dass sie mit einer relationalen Datenbank betrieben werden kann (lokal standardmäßig SQLite; alternativ z. B. PostgreSQL/MySQL via Django-Konfiguration).

## Lizenz

Siehe `LICENSE`.
