# Transportprotokolle

## Zentrale Portvergabe

- Zur Kommunikation miteinander müssen sich zwei Rechner auf Portnummern einigen. Hierfür gibt es eine
      - Zentrale Vergabe: Ports < 1024 sind priviligiert und fest zugeordnet
      - Dynamische Vergabe:
          - Wird von Anwendungsprogrammen implementiert
          - > 1024
          - Die Dienst - Port Zuweisung findet sich in /etc/services

## UDP

- ungesicherter, verbindungsloser Transportdienst
- verarbeitet Daten paket- oder message-weise

## TCP

- Verbindungsaufbau findet durch (mindestens) Drei-Wege-Handshake statt
- Verbindungsabbau findet über `fin` statt. 
      - Client(fin) -> Server
      - Server(ack) -> Client
      - Server(fin) -> Client
      - Client(ack) -> Server

### TCP Sicherung

- Datenverluste werden an der Sequenznummer erkannt
- TCP versendet keine Verluste!, sondern nur ACKs
- Bei einem Verlust beginnt TCP, vom verlorenen Segment an den Strom neu zu senden
- TCP versucht ACK mit Daten zu versenden

### Retransmission

- Feste Timeouts problematisch -> Round Trip Time (durchschn. Verzögerung zwischen Aussenden und Quittungsempfang)
- RTT wird für jede Verbindung ermittelt
- Adaptive Zeitsteuerung:
      - Timeout = estRTT (erwartete RTT) + 4 * Delay-Variation (Jitter)
      - Jitter: nicht ganz verstanden
- Datenverluste werden als Anzeichen einer Netzwerküberlastung interpretiert -> TCP wendet Strategie zur Stauvermeidung an
  
### Dynamische Flußkontrolle zum Empfänger | Sliding Window

- TCP teilt den Datenfluss zur Übertragung in Segmente ein
- Der Empfänger steuert den Datenfluss durch Mitteilen der verfügbaren (Empfangs-) Puffergrößen: receive window
- Ein Fenster der Größe 0 stoppt den Fluss
- Der Empfänger kann zusätzliche ACKs schicken, um den Fluss wieder in  Gang zu setzen.

### Stauvermeidung 

#### Slow Start
- TCP tastet sich im `Slow Start` von unten an die Grenze
- Startet bei Anfangswert von 1-4 Segmenten
- Per ack erhöht sich die Fenstergröße um 1 Segment
- Slow Start endet bei Schwellwert: ssthresh
- ssthresh wird adaptiv an Verlustrate angepasst
- Staugefahr bei: cwnd > ssthresh

#### Congestion Avoidance

- Das cwnd wird nun nur noch pro RTT um 1 Segment erhöht
- Bei Stauanzeichen (timeout) wird cwnd auf 1 zurück gesetzt und TCP fällt in den Slow Start zurück

#### Jacobson Fast Retransmit

- Wird innerhalb eines sliding Window ein Segment verloren, muss das ganze Fenster erneut gesendet werden (und slow start)
- Annahme: wenn mehrere gleiche ACKs eintreffen, ist wahrscheinlich nur ein Zwischensegment verloren worden.
- Fast Retransmit:
      - Wird das dritte duplicate ACK erhalten, schickt der Sender das erste nicht bestätigte Segment unverzüglich erneut
      - Der Sender wechselt nicht in die Slow Start Prozedur, sondern auf ssthreh

## SCTP - Streaming Control Transmission Protocol

- Verbinungsorientiertes Transportprotokoll
- Message-orientiert:     
      - Unterstützt beliebig Große Nachrichten (fragmentiert)
      - Kann kleine Messages in einem SCTP-Paket bündeln
- Ermöglicht mehrere `Streams` pro Verbindung (analog SS7)
- Stream-Eigenschaften separat konfigurierbar
- implementiert SACK

## Datagram Congestion Control Procotol

- Protokoll für ugnesicherten Unicast Transport mit Staukontrolle
- Entworfen für Echtzeitwandwendungen
- Verbindungsorientiert, entdeckt Packetverlust, ohne Pakete zu wiederholen
- Bietet den Rahmen für verschiedene Staukontrollmechanismen

## QUIC - Quickc UDP Internet Connections

- Schnelles Verbindungsmanagement
      - Schneller Aufbau
      - Volles Multiplexing von (HTTP-)Streams
- Multipath
- Verbesserte Verlust- und Staubehandlung
- Integrierte TLS-Verschlüsselung