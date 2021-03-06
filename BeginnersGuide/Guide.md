# Beginner's Guide
![NodeMCU](img/NodeMCU-v2.jpg)
Anstelle den ESP8266 oder NodeMCU mit dem Terminal zu programmieren, kann die Arduino IDE genutzt werden. In dieser Anleitung werden die Schritte gezeigt, um die Arduino IDE für den ESP8266 vorzubereiten.

## Identifizieren des NodeMCUs
NodeMCU umdrehen und schauen, ob CP2102 oder CH340G Treiber installiert müssen.
Nur für Windows und Mac, Linux braucht keine Treiber.

#### NodeMCU v2
CP210x USB TO UART Bridge Treiber
[Treiber für Mac / Win](https://www.silabs.com/products/mcu/Pages/USBtoUARTBridgeVCPDrivers.aspx)

#### NodeMCU v3
CH340G Bridge Treiber
[Treiber für Mac](http://www.wch.cn/download/CH341SER_MAC_ZIP.html)
[Treiber für Windows](http://www.arduined.eu/files/CH341SER.zip)

Nach der Installation der Treiber Rechner neustarten.

## Board Manager installieren
Die Arduino IDE 1.6.5 runterladen & installieren: 
https://www.arduino.cc/en/Main/OldSoftwareReleases#previous

In den Einstellungen in das **Additional Board Manager URLs** Feld diese URL einfügen: http://arduino.esp8266.com/stable/package_esp8266com_index.json 

![Einstellungen](img/Einstellungen.png)

In **Werkzeuge** → **Platine** → **Boardmanager** nach dem ESP8266 Paket suchen und installieren.

![Boardmanager](img/Boardmanager.png)

## ESP8266 / NodeMCU Einstellungen
Nach dem Neustart der Arduino IDE in **Werkzeuge** → **Platine** das entsprechende Board auswählen
b
- NodeMCU 0.9 (ESP-12 Module) **für NodeMCU v1**
- NodeMCU 1.0 (ESP-12E Module) **für NodeMCU v2 und v3**

![NodeMCU Einstellungen](img/NodeMCU.jpg)

## Port auswählen
Port auswählen **Werkzeuge** → **Port**.
Beim CP2102 wäre das auf dem Mac der **/dev/cu.SLAB_USBTOUART**, für den CH340G ist es der Port **/dev/cu.wchusbserialXXXXXXXX** auf dem Windows COM3. Wenn dies nicht der richtige ist, dann einfach den nächsten in der Liste auswählen.

## Code auf den NodeMCU überspielen
Den aktuellsten Code von GitHub in die Arduino IDE einfügen.
*Tipp: um den Code besser zu kopieren einfach auf den **RAW** Button klicken*
https://github.com/HackNorris/OpenDataStuttgart/blob/master/Dusty/Dusty.ino

#### Wifi einstellen
![Wifi Einstellungen](img/Wifi.jpg)

in der **WiFi declaration** die SSID (Name des WLANs) und das dazugehörige Passwort eintragen.

#### NodeMCU flashen
Auf den → oder im Menü *Sketch* → *Hochladen* klicken.

![Überspielen des Codes](img/Uberspielen.jpg)

## Überprüfen
**Werkzeuge** → **Serieller Montior** aktivieren, damit man über USB Schnittstelle die aktuellen Daten lokal anschauen kann.
Nun kann überprüfen, ob es an einer Stelle zu Fehlern führt, z.B. NodeMCU kann sich nicht ins Wlan einloggen, kann die Daten nicht hochladen,…

![Überprüfen](img/Uberspielen.jpg)
