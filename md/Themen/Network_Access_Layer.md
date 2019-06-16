# Network Access Layer

## Subnetzwerktypen

- Leitungsvermittelt: 
      - Stellt jedem Nutzer einen `physikalischen` Pfad zur Verfügung (z.B. durch Multiplexing)
      - Stets verbindungsorientiert
      - Vermittlungsweg wird beim Verbindungsaufbau festgelegt
- Paketvermittelt:
      - Stellt einzelnen Paket einen `Beförderungsweg` zur Verfügung
      - Häufig verbindungslos
      - Pakete werden autonom vermittelt

## Medienzugriffsverfahren

- Single Access
      - Netzwerk zwischen wei Teilnehmern steht exklusiv über dedizierte "Leitungen" zur Verfügung
- Multiple Access
      - Gemeinsame Netzwerknutzung durch viele Teilnehmer über geteilte Leitungen
      - Synchronisationsproblem zur Kanalreservierung
      - Carrier Sense: Wenn das Medium eine bestimmte Zeit lang (IFS) frei ist, kann gesendet werden.
      - Tritt eine Kollision auf, bekommt der Sender eine Meldung. Nach erhalt dieser Meldung schickt dieser an alle ein `jam` Signal. Somit wird sichergestellt, dass jeder die Kollision mitbekommt.
      - Dann wird eine zufällige Zeit gewartet und die Nachricht wird noch einmal gesendet.
      - Problem: Kollision kann erst nach t = 2*ŧ (ŧ = Kabellaufzeit) garantiert werden
          - Deshalb: minimale Paketlänge = 2 * ŧ * v (v = NW-Speed)

## Ethernet Protokollaufbau
 
- MAC-Adressen
      - 6 Byte lang
      - weltweit eindeutig
      - `fest` auf die Netzkarte eingebrannt

### Maximale Framerate

- v = NW Datenrate = 10 Mbit/s
- S = min Framesize = 84 * 8 bit
- Maximale Framerate = v/S = 10 000 000 / (84*8) /s = 14 880 Frames pro Sekunde

### Maximaler Durchsatz (relevanter)

- Max. Framerate = v/S = 812.74 frames/s
- Max. Datendurchsatz = Max. Framerate * Payload = 812.74 * (1500 * 8) = 9 752 880 bit/s

## Logical Link Control

- Zusätzliche Schicht um eine Steuerung der Datenübertragung zu gewährleisten
- Das Protkoll unterscheidet zwischen:
      - Unzuverlässigen Datagram-Dienst
      - Datagram-Dienst mit Paketbestätigung (ACKs)
      - Zuverlässigen verbindungsorientierten Dienst
- Header beinhaltet:
      - Ziel-Access-point
      - Quell-Access-point
      - Kontrollfeld -> Seq- und Ack-nummern

## Token Ring

![](../../img/Token_Ring.png)

- Stationen sind in einem Ring verbunden
- Zuteilung des Senderechts durch zirkulierenden Token

## ATM

## PPP

- war der Standard-Link für Internet Dial-up
- Schicht-2 Rahmenformat mit Flusskontrolle
- eigenes Protokoll für Verbindungsaufbau, -abbau und -kontrolle (LCP)
- Mechanismus zum konfigurationsaustausch, z.B. IP-Adresse (NCP)
- eigene Fehlerkontrolle

## Switching/Bridging (Layer 2)

- Vermittlung auf dem layer 2: Pakete werden an Interfaces gemäß Hardware-Adresstabellen (MAC-Tables) weitergeleitet
- Merkt sich gelernte Adressen in Forwarding Database
- Ursprünglich: Bridges zur Segmentierung von Busnetzen
- Heute: Switches zur flexiblen Strukturierung & Protokollwechsel

### Switching Logik

- Switch hält FDB per Port (alle MAC Adressen hinter diesem Port)
- Broadcast für unbekannte Adressen

### Switch Architekturen

- Store-and-Forward
        - Langsamer, speicher und weiterleiten kostet Zeit
        - Erkennt Fehlerhafte Datenpakete
- Cut-Through
        - teuer, weil Verbindungen zwischen allen Teilnehmern vorhanden sein müssen. Dafür schneller.
        - der Schaltprozess wird bereits eingeleitet, bevor das vollständige Datenpaket eingetroffen ist (nur destination reicht)
        - keine Fehlerkorrektur! (da direkt weitergeleitet wird)

### Virtuelle LANs

- Gruppierung von Netzwerkteilnehmern innerhalb eines LANs
- Müssen seperat auf jedem Switch konfiguriert und Ports zugewiesen werden
- Automatische Verteilung der VLAN Informationen durch GARP

#### Port Based VLAN (802.1Q)

- Ein unicast oder broadcast Paket wird auf einem Port der ID = x empfangen und nur an Ports derselben ID geforwarded
        - Jede Hostgruppe erhält eine ID
        - Pakete werden nur innerhalb eines VLANs geforwarded
        - Jeder Switchport gehört zu mind. einer ID


#### MAC Address Based VLAN

- Die VLAN Mitgliedschaft eines Pakets wird an der Quell- oder Zieladresse identifiziert
- Switches halten eine Membership-Tabelle
- 
#### Protocol (L3) Based VLAN

- Die Mitgliedschaft eines Pakets in einem VLAN wird an dem Layer 3 Protokoll (IP, IPC, Netbios..) und der L3 Netzzugehörigkeit festgestellt

#### VLAN Prioritätstag (802.1p/Q)

- Wenn Tagging in Anwendung, dann wird das Prioritätsbit extrahiert und mit dem Schwellwert 3 vergliechen. (0-3 niedrieg, 4-7 hoch)

### Priorisierung (802.1p)

- Prioritätsklassen werden auf switching queues abgebildet
- Port-basierte Priorität



## Hub (Layer 1 (physikalisch))

- Leitet jedes Datenpaket an `alle` anderen Ports weiter! 
- Keine Kontrolle der Pakete, somit auch keine Fehlerüberprüfung
- Keine Verzögerung

