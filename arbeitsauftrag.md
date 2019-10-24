# Service-Design für Werkstattauftrag

## Inhaltsverzeichnis

-   01 - Autoren, Versionierung
-   02 - Einführung
-   03 - Materialliste
-   04 - Installationsanleitung
-   05 - Qualitätskontrolle
-   06 - Error-Handling

---

## Autoren, Versionierung

### Autoren

-   Noah Fleischmann
-   Yannis Bär

### Versionierung

Das komplette Projektverzeichnis mit allen Markdown-Dateien ist Teil des Git-Repositories, welches auf GitHub gehostet wird. Somit wird die Versionierung mit Git gehandhabt.

## Einführung

## Ausgangslage

### Projektauftrag

Der Kunde, TIbor Rui, wünscht sich ein Media-Center System, welches mit seinem Fernseher verbunden ist und via sein Smartphone gesteuert werden kann. Die Medien (z.B. Filme) sollen auf einem per USB mit dem Media-Center verbundenen Datenträger (USB-Stick oder Festplatte) liegen. Zusätzlich wünscht er sich ein Web-Interface als Übersich für sein Media-Center system und eine Spotify-Integration, sodass er sich seine Lieblingsmusik auch direkt über den Fernseher anhören kann.

### Vorgehensweise

#### Grundauftrag

Für dieses Projekt soll Kodi als Media-Center-Software verwendet werden. Dieses soll direkt über das Betriebssystem [OSMC](https://osmc.tv/download/) auf dem Raspberry Pi installiert werden.

-   Den Raspberry Pi mit [OSMC](https://osmc.tv/download/) als Betriebssystem installieren
-   OSMC einrichten und konfigurieren
-   [Yatse](https://yatse.tv/wiki/yatse-kodi-addon) Kodi addon installieren
-   [Spotify](https://www.makeuseof.com/tag/how-to-listen-to-spotify-on-kodi/) Kodi addon installieren

#### Advanced

Wenn Ihnen die obenstehenden Arbeitsschritte zu langweilig sind, können Sie noch folgende Zusatzaufgaben absolvieren.

-   [Web Interface](https://kodi.wiki/view/Web_interface) für Kodi einrichten
-   SMB File-Server auf zweiten Raspberry Pi einrichten (zusammen mit einem anderen Lernenden), um die Medien für Kodi dort abzuspeichern

### Zeitaufwand

-   Grundauftrag: 4 Lektionen
-   Advanced: 4 Lektionen

## Materialliste

-   Raspberry Pi (Aufgabe optimiert für Pi 3 Model B)
-   Micro USB Netzteil (optimal mit >2.5A)
-   Micro SD Karte (mindestens 16GB)
-   Netzwerk- und Internetverbindung (entweder LAN oder WLAN)
-   USB Stick oder Festplatte für Medien-Dateien

## Installationsanleitung

(Didaktisch reduzierte Anleitung aus Service-Design) So, dass Lernende eigene Lösungswege realisieren koennen)

-   Anweisungen verstaendlich und nachvollziehbar - Keine fertigen Loesungsschritte aufzeigen
-   Hilfestellung (Tipps, Quellen...)

## Qualitätskontrolle

### Grundauftrag

#### Kodi Funktionalität

```shell
grep Kodi .kodi/temp/kodi.log | head -3
```

SOLL: Version 18.5

#### Yatse Plugin

SOLL: mit dem Android-Gerät kann das Kodi-Interface bedient werden

#### Spotify Plugin

SOLL: das Spotify Interface ist über Kodi erreichbar und Musik kann abgespielt werden

### Advanced

#### Web Interface

http://<raspberry-ip> im Webbrowser aufrufen
SOLL: das Kodi-Webinterface wird angezeigt

#### File-Server

SOLL: Medien auf dem File-Share können auf dem Raspberry Pi über Kodi abgespielt werden

## Error-Handling

???
