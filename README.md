# Fuckingfast Downloader -  Deutsch

# Deutscher Fork von https://github.com/Riteshp2001/Fucking-Fast-Downloader  

Ein spezialisierter PyQt5-Desktop-Downloader für öffentliche FuckingFast-Freigabelinks. Links einfügen, eine Warteschlange erstellen und die fertigen Dateien herunterladen. Unterstützt FitGirl-Seitenextraktion, das Kopieren neuer direkter URLs, fortsetzbare Downloads sowie Pausen-/Abbruchfunktionen.

## Architektur

```text
ff_downloader/
|- core/
| |- resolver.py # Quellseiten- und Freigabelink-Resolver
| `- downloader.py # Fortsetzbare Streaming-Download-Engine
|- ui/
| `- main_window.py # PyQt-Desktop-Benutzeroberfläche
|- config.py # Laufzeiteinstellungen
|- workers.py # QThread-Adapter
`- __main__.py # Anwendungseinstiegspunkt
main.py # Kompatibilitätsstarter
```

## Installation

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# Linux/macOS: source .venv/bin/activate
pip install -r requirements.txt
camoufox fetch # Einmaliger Browser-Download (ca. 660 MB), erforderlich für die Auflösung von Freigabelinks
python main.py
```

## Funktionsweise

1. Fügen Sie die ursprünglichen Freigabe-URLs von `fuckingfast.co`, eine unterstützte Quellseite oder die aktuellen direkten URLs von `dl.fuckingfast.co` ein.

2. Wählen Sie **Vorbereiten**. Die vorbereitete Warteschlange wird im Fenster gespeichert, sodass der Download immer die von Ihnen überprüften Links verwendet – nicht einen versteckten Cache.

3. Falls der Host eine Verifizierung anfordert, führen Sie diese im sich öffnenden Browserfenster durch. Dies nutzt Ihre normale Browsersitzung; die App versucht nicht, die Herausforderung im Hintergrund zu lösen.

4. Wählen Sie **Bereit zum Herunterladen von Dateien** oder verwenden Sie die Schaltfläche „Kopieren“, um neue direkte URLs an einen anderen Download-Manager zu senden.

Direkte URLs von `dl.fuckingfast.co` sind 24 Stunden gültig. Eine veraltete direkte URL kann nicht automatisch erneuert werden; fügen Sie die ursprüngliche Freigabe-URL ein, um eine neue zu erstellen. Wenn ein Stapel veraltete Freigabe-URLs enthält, bleiben nutzbare Dateien in der Warteschlange, und nur die betroffenen Einträge werden zur Überprüfung markiert.

## Externe Manager

Verwenden Sie **Vorbereiten** und anschließend die Schaltfläche „Kopieren“, um für Tools wie JDownloader pro Zeile eine neue direkte URL zu kopieren.

Laden Sie nur Inhalte herunter, für die Sie berechtigt sind.