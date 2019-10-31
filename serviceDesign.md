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

-   Kodi-Betriebssystem [Raspbian Buster](https://www.raspberrypi.org/downloads/raspbian/)
-   Android-Fernbedienung Kodi-Addon [Yatse](https://yatse.tv/wiki/yatse-kodi-addon
-   Spotify Kodi-Addon [Spotify](https://www.makeuseof.com/tag/how-to-listen-to-spotify-on-kodi/)
-   Arch Web-Interface Kodi-Addon [Arch](https://kodi.tv/addon/web-interface/arch)

## Installationsanleitung

### Raspberry Pi aufsetzen
Den Raspberry Pi mithilfe von [NOOBS](https://www.raspberrypi.org/downloads/noobs/) aufgesetzt. Zudem wurden Grundeinstellungen wie Keyboard Layout und Zeitzone angepasst.

Damit man Remote Zugriff auf den Raspberry Pi bekommt, SSH und VNC aktivieren:
![Raspberry Pi Konfiguration](/media/rasp_config.png)

Eine statische IP-Adresse geben:

```
sudo nano /etc/dhcpcd.conf
```
```
interface eth0
static ip_address=172.16.17.101/24
static routers=172.16.17.1
static domain_name_servers=172.16.17.1
```
```
sudo reboot
```

### Kodi aufsetzen
```
sudo apt-get update
sudo apt-get install kodi
```
#### USB Stick mounten
Mit dem command `lsblk` nach dem USB-Stick/externe Festplatte suchen und den Pfad merken. (In unserem Fall sda1)

Ein Verzeichnis für den zu mountenden USB-Stick erstellen: `mkdir ~/usbstick`

Den USB-Stick mounten: `sudo mount /dev/sda1 ~/usbstick/`

#### Kodi konfigurieren

##### Remote Control
Kodi starten und unter dem "Settings" Menü in die "Service Settings" - "Control" Einstellungen navigieren. In diesem Menü folgende Optionen aktivieren:
* Allow remote control via HTTP
* Allow remote control from applications on this system
* Allow remote control from applications on other systems.

![Kodi Remote Control](/media/remotecontrol_remote.jpg)

Zu dem Menü "UPnP / DLNA" navigieren und folgende Optionen aktivieren:
* Share my libraries
* Allow remote control via UPnP 

![Kodi Remote UPnP](/media/remotecontrol_upnp.jpg)

##### Medien Bibliothek einbinden


### Yatse Add-On installieren

### Spotify Add-On installieren

## Testing

| Test Nr. | SOLL                                                                                                                | Vorgehensweise für Testing                                                                     |
|----------|---------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|
| 1        | Kodi Version 17.6 ist unter Raspbian installiert                                                                    | grep Kodi .kodi/temp/kodi.log | head -3 um Version der Installation zu sehen                   |
| 2        | Das externe Medien-Verzeichnis (z.B. /dev/sda1/media) ist gemounted und in Kodi eingebunden.                        | Medien werden von Kodi indexiert und zur Verfügung gestellt                                    |
| 3        | Auf einem Android-Gerät kann mithilfe von Yatse das Kodi-Interface bedient werden                                   | Nach Konfiguration von Yatse kann damit das Kodi-Interface bedient werden                      |
| 4        | Das Spotify-Interface ist in Kodi sichtbar, kann aufgerufen werden und Musik kann abgespielt werden                 | Spotify Plugin öffnen, Account-Daten eingeben und dann Musik abspielen                         |
| 5        | Kodi-Webinterface ist von einem anderen Gerät aus im selben Netzwerk erreichbar und Medien können abgespielt werden | http://<raspberry-ip:8080> im Webbrowser aufrufen und dort Medien wiedergeben                       |
| 6        | Medien auf dem File-Share können auf dem Raspberry Pi über Kodi abgespielt werden                                   | Medien auf dem Fileserver speichern. Diese sollten dann in Kodi erscheinen und abspielbar sein |

### Protokoll

| Test Nr. | Status |
|----------|--------|
| 1        | Ok     |
| 2        | Ok     |
| 3        | Ok     |
| 4        | tbd     |
| 5        | Ok     |
| 6        | Ok     |

## Übergabe an den Betrieb

-   In separatem Word-Dokument auffindbar.

## Quellen

-   https://pimylifeup.com/raspberry-pi-kodi/
-   https://yatse.tv/wiki/yatse-kodi-addon
-   https://www.makeuseof.com/tag/how-to-listen-to-spotify-on-kodi/
-   https://kodi.wiki/view/Web_interface
-   https://kodi.tv/addon/web-interface/arch
