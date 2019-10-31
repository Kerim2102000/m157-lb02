# Service-Design für Werkstattauftrag

## Inhaltsverzeichnis

-   01 - Autoren, Versionierung
-   02 - Funktion des Services
-   03 - Benötigte Hard- und Software
-   04 - Installationsanleitung
-   05 - Testing
-   06 - Übergabe an den Betrieb
-   07 - Quellen

---

## Autoren, Versionierung

### Autoren

-   Noah Fleischmann
-   Yannis Bär

### Versionierung

Das komplette Projektverzeichnis mit allen Markdown-Dateien ist Teil des Git-Repositories, welches auf GitHub gehostet wird. Somit wird die Versionierung mit Git gehandhabt.

## Funktion des Services

Der Kunde, TIbor Rui, wünscht sich ein Media-Center System, welches mit seinem Fernseher verbunden ist und via sein Smartphone gesteuert werden kann. Die Medien (z.B. Filme) sollen auf einem per USB mit dem Media-Center verbundenen Datenträger (USB-Stick oder Festplatte) liegen. Zusätzlich wünscht er sich ein Web-Interface als Übersich für sein Media-Center system und eine Spotify-Integration, sodass er sich seine Lieblingsmusik auch direkt über den Fernseher anhören kann.

## Benötigte Hard- und Software

### Hardware

-   Raspberry Pi (Aufgabe optimiert für Pi 3 Model B)
-   Micro USB Netzteil (optimal mit >2.5A)
-   Micro SD Karte (mindestens 16GB)
-   Netzwerk- und Internetverbindung (entweder LAN oder WLAN)
-   USB Stick oder Festplatte für Medien-Dateien

### Software

-   Kodi-Betriebssystem [OSMC](https://osmc.tv/download/)
-   Android-Fernbedienung Kodi-Addon [Yatse](https://yatse.tv/wiki/yatse-kodi-addon
-   Spotify Kodi-Addon [Spotify](https://www.makeuseof.com/tag/how-to-listen-to-spotify-on-kodi/)

## Installationsanleitung

(Saubere und ausfuehrliche Dokumentation. Muss ohne Nachfragen oder Nachschlagen nachgebaut werden koennen)

## Testing

| Test Nr. | SOLL                                                                                                                | Vorgehensweise für Testing                                                                     |
|----------|---------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|
| 1        | Kodi Version 18.5 ist unter Raspbian installiert                                                                    | grep Kodi .kodi/temp/kodi.log | head -3 um Version der Installation zu sehen                   |
| 2        | Das externe Medien-Verzeichnis (z.B. /dev/sda1/media) ist gemounted und in Kodi eingebunden.                        | Medien werden von Kodi indexiert und zur Verfügung gestellt                                    |
| 3        | Auf einem Android-Gerät kann mithilfe von Yatse das Kodi-Interface bedient werden                                   | Nach Konfiguration von Yatse kann damit das Kodi-Interface bedient werden                      |
| 4        | Das Spotify-Interface ist in Kodi sichtbar, kann aufgerufen werden und Musik kann abgespielt werden                 | Spotify Plugin öffnen, Account-Daten eingeben und dann Musik abspielen                         |
| 5        | Kodi-Webinterface ist von einem anderen Gerät aus im selben Netzwerk erreichbar und Medien können abgespielt werden | http://<raspberry ip> im Webbrowser aufrufen und dort Medien wiedergeben                       |
| 6        | Medien auf dem File-Share können auf dem Raspberry Pi über Kodi abgespielt werden                                   | Medien auf dem Fileserver speichern. Diese sollten dann in Kodi erscheinen und abspielbar sein |

## Übergabe an den Betrieb

-   Qualitaetssicherungprozess (separates Schriftliches Dokument, Uebergabe-
    protokoll)

## Quellen

-   https://pimylifeup.com/raspberry-pi-kodi/
-   https://yatse.tv/wiki/yatse-kodi-addon
-   https://www.makeuseof.com/tag/how-to-listen-to-spotify-on-kodi/
-   https://kodi.wiki/view/Web_interface
