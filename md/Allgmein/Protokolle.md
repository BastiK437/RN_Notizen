# Protokolle

## Verbindungskontrolle

Protokolle können Daten mit unterschiedlicher Zielsetzung übertragen. 

### Verbindungsorientiert
- zustandsbehaftet, gesichert
- drei Phasen: 
  - Verbindungsaufbau
  - Datentransfer
  - Verbindungsabbau

### Verbindungslos
- zustandslos, ungesichert


## Zuverlässigkeit

### Zuverlässige Protokolle
- bieten Schutz vor Datenverlust/-zerstörung
- verifizieren Pakete nach Erhalt und quittieren
- haben Overhead, der verlangsamen kann

### Unzuverlässige Protokolle
- beachten Datenverluste nicht
- verifizieren und quittieren Pakete nicht
- Überprüfung und Korrektur kann in übergeordneten Schichten erfolgen 

### k-zuverlässige Protokolle
- stellen sicher, dass k (aus k+1) Paketen zuverlässig ankommen

## IP


## RIP

- Disctance-vector Protokoll
- Router tauschen ihr aktuellen Routing-Tabellen alle 30 Sekunden mit den direkten Nachbarn aus
- hop count metric
- max hop 15 (unenndlich := 16)
- nutzt UDP

## OSPF

- gehört zur Familie der Link-State Protokolle
- setzt direkt auf IP auf
- konvergiert schnell und unterstützt Load-Balancing
- Routen haben Versionsnummern
- unterteilt das Netz in Areas (IP Teilnetze, nach außen unsichtbar)
- utnerscheidet Punkt-zu-Punkt-, Multi-Access- und Stub-Netze
- verarbeitet neben Topologieinformationen auch Cost-Gewichte
- Problem: Routing-Entscheidungen können sehr komplex werden

## IS-IS

- Link-State Protokoll wie OSPF
- Initiiert Shortest Path Forwarding (Dijkstra)

### Unterschiede zu OSPF

- Area-Grenzen sind nicht Router, sondern Links

## BGP

- Gehört zur Familie der Path Vector Protokolle
- Regelt Routing zwischen 
- Operiert auf Path-Vektoren (List eder ASNs auf einem Weg)
- BGP Peers akzeptieren/verwerfen angebotene Pfade: Offen für Policies, z.B. shortest Path, bevorzugte Nachbarn, Hot oder Cold Potato
- BGP Router entscheid via Policy über eigene "Advertisements"

### Routing: Auswahlentscheidung

- Phase I: Präferenz-Zuweisung
      - Aufgrund lokaler Policies und Attribute erhalten alle RIB-Einträge eine Präferenz
- Phase II: Routen-Selektion
      - Für jedes Präfix werden alle routen höchste Präferenz ausgewählt, hiernach die kürzesten Pfade, dann die Multi-Exit-Discriminators und schließlich weitere Eindetigkeitsregeln angewandt
      - Ausgewählte Routen wandern in dei FIB
- Phase III: Routen Weiterleitung
      - FIB-Einträge werden vor der Weiterleitung erneut gem. Policies gefiltert

## Transportprotokolle

- UDP
- TCP