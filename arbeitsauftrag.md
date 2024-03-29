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

### Projektauftrag

Der Kunde, Tibor Rui, wünscht sich ein Media-Center System, welches mit seinem Fernseher verbunden ist und via sein Smartphone gesteuert werden kann. Die Medien (z.B. Filme) sollen auf einem per USB mit dem Media-Center verbundenen Datenträger (USB-Stick oder Festplatte) liegen. Zusätzlich wünscht er sich ein Web-Interface als Übersich für sein Media-Center system und eine Spotify-Integration, sodass er sich seine Lieblingsmusik auch direkt über den Fernseher anhören kann.

### Vorgehensweise
-   Raspberry Pi Betriebssystem installieren
-   Grundkonfiguration Betriebssystem vornehmen
-   Kodi installieren und konfigurieren
-   Yatse und Spotify Kodi-Addons installieren
-   *Fortgeschritten:* Web-Interface für Kodi einrichten
-   *Fortgeschritten:* Medien über einen SMB-Fileshare an Raspberry Pi anbinden

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
-   
### Grundauftrag

Für dieses Projekt soll Kodi als Media-Center-Software verwendet werden. Dieses soll direkt über das Betriebssystem [Raspbian Buster](https://www.raspberrypi.org/downloads/raspbian/) auf dem Raspberry Pi installiert werden.

-   Den Raspberry Pi mit [Raspbian Buster](https://www.raspberrypi.org/downloads/raspbian/) als Betriebssystem aufsetzen
-   Kodi installieren und konfigurieren
-   [Yatse](https://yatse.tv/wiki/) Kodi addon installieren
-   [Spotify](https://www.makeuseof.com/tag/how-to-listen-to-spotify-on-kodi/) Kodi addon installieren

### Advanced

Wenn Ihnen die obenstehenden Arbeitsschritte zu langweilig sind, können Sie noch folgende Zusatzaufgaben absolvieren.

-   [Web Interface](https://kodi.wiki/view/Web_interface) für Kodi einrichten
-   SMB File-Server auf zweiten Raspberry Pi einrichten (zusammen mit einem anderen Lernenden), um die Medien für Kodi dort abzuspeichern

## Qualitätskontrolle

#### Kodi Funktionalität

```shell
grep Kodi .kodi/temp/kodi.log | head -3
```

SOLL: Version 17.6
#### Yatse Plugin

SOLL: mit dem Android-Gerät kann das Kodi-Interface bedient werden

#### Spotify Plugin

SOLL: das Spotify Interface ist über Kodi erreichbar und Musik kann abgespielt werden

### Advanced

#### Web Interface

http://<raspberry-ip:8080> im Webbrowser aufrufen
SOLL: das Kodi-Webinterface wird angezeigt

#### File-Server

SOLL: Medien auf dem File-Share können auf dem Raspberry Pi über Kodi abgespielt werden

## Error-Handling

Diese [Kodi-Webseite](https://kodi.wiki/view/Troubleshooting) gibt einem einen guten Überblick über die Troubleshooting-Möglichkeiten von Kodi. In unserer Erfahrung ist der Kodi-Log unter `/var/log/kodi/error.log` der beste Anlaufpunkt für die meisten Probleme. 
