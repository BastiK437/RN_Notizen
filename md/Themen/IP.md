# IP

- Universelles Paketformat mit einheitlichen Adressen
- Findet Wege und leitet Pakete zwischen Rechnern: Routing und Forwarding
- Regelt Paketverarbeitung und Fehlerbehandlung
- Legt das Format von Paketen fest
- Zerteilt Pakete bei Bedarf

## IPv4

- 32-bit Adresse
- hardwareunabhängig
- die Adresse gliedert sich in zwei Teile: |netid|hostid|
      - netid: Netzwerkadresse als Prefix
          - alle Hosts in einem Netzwerk haben dieselbe netid
          - diese ist weltweit eindeutig und wird vom LIR zugeteilt
      - hostid: Host-Adresse als Suffix
          - eindeutig in einem Netzwerk
          - wird vom lokalen Administrator eingestellt

### Ursprüngliches Klassenkonzept

![](../../img/IP_Klassen.png)

### Subnetze 

- Unterteilt den hostid-Anteil einer Adresse in
      - subnetid: nachgeordnete Netzwerkadresse
      - hostid: Rechneridentifikation

### Berechnung

- Bei einer Subnetzmaske sieht die Berechnung wie folgt aus:
      - Bsp.: Adress: 128.10.2.30       (10000000 00001010 00000010 00011110)
      - Netzmaske: 255.255.255.0        (11111111 11111111 11111111 00000000)
      - netid (logisches AND): 128.10.2 (10000000 00001010 00000010)
      - hostid (logisches XOR): 30      (                           00011110)

### Spezielle Adressen

- Alle bits = 0: "dieser Host, dieses Netzwerk"
      - Bsp.: 0.0.0.7 ist Host 7 in diesem Netzwerk
      - Bsp.: 134.15.0.0. bedeutet `dieses (Class B-) Netzwerk`
- Alle bits = 1 bedeutet `Broadcast an alle`
- Hostid bits = 1 bedeutet `selected Broadcast`
      - Bsp: 134.15.255.255 oder 134.15.7.255
- 127.0.0.1 ist reserviert für das Loopback-Interface

### Network Address Port Translation

- Um in internen Netzen private IP-Adressen zu benutzen, versorgt ein zentrales Gateway (mit einer offiziellen Adresse) die Netzteilnehmer mit IP-Adressen. Diese privaten IP-Adressen werden dann mithilfe eines NAT, PAT oder NAPT in die öffentliche Adresse umgewandelt. 

### Fragmentierung von Datagrammen

- Wenn ein IP-Datagramm größer als die zugelassen MTU ist, wird das Paket in n viele `Fragmente` aufgeteilt.
- erfolgt am Router, Defragmentierung im Zielsystem

#### Defragmentierung

- Beim Eintreffen des ersten Fragments im Ziel wird ein Timer gestartet
- Sind nach Ablauf des Timers nicht alle Fragmente vorhanden -> Nachricht wird verworfen

### ICMP

- Liefert Grundlagen für Informationsaustausch im Netzwerk
      - Echo Request - Echo Reply       - Überprüfen der Betriebsbereitschaft oder Performance (ping)
      - Destination unreachable
      - Source Quench                   - Empfänger hat keine Puffer mehr frei
      - Redirect                        - Gateway teilt die IP-Adresse eines besser geeigneten Gateways mit
      - Time Exceed                     - Benachrichtigung über vernichtetes Datagramm (TTL = 0)
      - Paramter Problem
      - Timestamp Request / Reply

### Routing

- Die Routing-Entscheidung basiert allein auf der Zieladresse
- Jede Komponente bestimmt nur den nächsten Punkt des Weges
- Zwei Arten:
      - Direktes Routing: Der Zielrechner ist im gleichen Netz, d.h. direkt erreichbar
      - Indirektes Routing: Der Zielrechner ist nur über ein Gateway/Router erreichbar, an welchen das Paket zur Weiterleitung geschickt wird (z.B. Defaultgateway)

### ARP Funktionsweise

- A benötigt MAC-Adresse von C zum Senden
- A sendet per (Layer 2-) Broadcast ARP-Request mit der IP-Adresse von C
- Alle Rechner empfang, aber nur C beantwortet den Broadcast mit seiner MAC-Adresse
- A sendet Daten direkt an C per Unicast

### DHCP

- Dieses Protokoll ermöglicht die Zuweisung der Netzwerkkonfiguration an Clients durch einen Server

## IPv6

- 128 Bit lange Adresse
- mehrere Adressen pro IP Interface üblich
- vereinfachte Administration
- fließende Netzmasken
- keine Header checksumme
- keine Fragmentierung möglich
- Kein DHCP zur Konfiguration nötig
- Durch Neighbor Discovery wird ARP abgelöst
- kann bei icmp - packet too big - entweder das nächste paket direkt auf eine größe von 1280 setzen (geht immer durch), oder bei jeder msg das paket ein bisshen kleiner machen

### Standardformat

- 8 * 16 Bit, Hexa-Dezimal: 1080:0:FF:0:8:800:200C:417A

### Verkürzte Form

- Folgen von 0en ersetzt: 80:0:0:0:0:0:0:1 -> 80::1

### IPv4 kompatible Addressen

- 0:0:0:0:0:FFFF:13.1.68.3 -> ::FFFF.13.1.68.3

### CIDR 

- 1080:645:FF::/48

