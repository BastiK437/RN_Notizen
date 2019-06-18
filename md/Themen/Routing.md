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

- Fluten 
- Hot / Cold Potato
- Distanz-Vektor-Algorithmen
- Link-State-Algorithmen