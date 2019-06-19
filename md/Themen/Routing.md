# Routing

- Bezeichnet die Wegefindung der Pakete im Internet 

## Wichtigste Festlegungen

- Die Routing-Entscheidung basiert allein auf der Zieladresse
- Jede Komponente bestimmt nur den nächsten Punkt des Weges
- Es gibt zwei Arten des Routings:
      - Direktes Routing: Der Zielrechner ist im gleichen Netz, d.h. direkt erreichbar
      - Indirektes Routing: Der Zielrechner ist nur über ein Gateway/Router erreichbar, an welchen das Paket zur Weiterleitung geschickt wird. 

## Routing Tabellen

- Gateways und Hosts besitzen Routingtabellen
      - Host-Tabellen: meist nur das Defaultgateway
      - Gateway-Tabellen: Eintrag für jedes `erreichbare` Netz
- Automatisiertes Update von Routing-Tabellen zwischen Gateways ist im Internet notwendig -> Routing-Protokolle

## Routing vs Forwarding

- Routing bezeichnet die Wegefindung im Netz
      - Verteilter Prozess zwischen Routern im Netzwerk 
      - Basiert auf Topologie-Erkennung und Wegewahl
      - Router haben oft Hilfstabellen hierfür (RIBs)
- Forwarding bezeichnet das Weiterleiten von Paketen
      - Lokaler Prozess auf einer Maschine
      - Eingehende Pakete werden zum Ausgangsport geschickt
      - Grundlage sind Weiterleitungstabellen (FIBs)
      - FIBs sind die (lokalen) Ergebnisse des Routings

## Routing Algorithmen

### Fluten 

### Hot / Cold Potato

### Distanz-Vektor-Algorithmen

- Jeder Router verfügt über eine Liste kürzester Distanzen zu allen Netzen der Routing-Domain (Distanzvektor)
- Distanzen werden in einheitlicher, vorgegebener Metrik gemessen (z.B. hops)
- Router broadcasten ihre Routingtabellen
- Neu erlernte kürzeste Wege ersetzen bisherige Einträge
- siehe RIP

### Link-State-Algorithmen

- Jeder Router testet den Status seiner Links zu den Nachbarroutern
- Link-Informationen werden an alle Router des Netzwerks weitergegeben (Fluten)
- Jeder Router baut hiraus eine Netztopologie auf
- Alle Router des Netzwerks berechnen in gleicher Weise die günstigsten Wege und bilden Routing-Tabellen (Dijkstra, OSPF)

### Routing Problem

- Zerfällt Grundsätzlich in zwei Teile
        - Routing innerhalb von Netzwerken
        - Routing zwischen Netzwerken
- Deshalb gliedert sich das internet in AS, deren innere Struktur nach außen transparent ist
- Innerhalb von ASes wird ein frei wählbares Routing Protokoll gesprochen
- ASes besitzen global eine eindeutige AS-Nummer (Google: AS15169)

## Exterior / Interior Gateway Protokolle

- Exterior
        - EGP
        - BGP
- Interior 
        - RIP
        - RIP-V2
        - OSPF
        - IS-IS

## Hierarchien der Internet Topologie

- Tier 1: Global Internet Core
- Tier 2: National/Regional ISPs
- Tier 3: Stub Networks, Local Eyeballs
- (Tier 4): Customer IP Networks (without ASN)

- kosten von unten (4) nach oben (1)