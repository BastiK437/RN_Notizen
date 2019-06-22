# Netzwerk Management

## Aufgaben

- Fehlermanagement
      - Erkennen, Isolieren und Beheben von Störungen
- Konfigurationsmanagement
      - Auslesen und Einstellen der Konfigurationsparameter
- Performancemanagement
      - Sammeln und Bewerten von Betriebsdaten
- Accountingmanagement
      - Nutzerbezogene Verbrauchsmessungen
- Sicherheitsmanagement
      - Dokumentation und Abwehr unerlaubter Zugriffe

## SNMP

- Einzige ernstzunehmende Standard für Managementaufgaben
- Benutzt einfachen Datagramm-Dienst zur Nachrichtenübermittlung
- Bestandteil eines überfreifenden NMM-Mmodells
      - Managed Nodes, ausgestattet mit SNMP Agenten
      - Leistungsfähige Network Management Station
      - Proxy Agents zur Einbindung von Nicht-SNMP-Systemen
      - Zielsystemunabhängige Strukturbeschreibung in ASN.1

### SMI

- Macht SNMP erst so richtig unabhängig
- Beschreibt die Daten die zwischen 2 Komponenten ausgetauscht werden. Sowas wie little-endian, datentyp etc.
- Es können komplexe Datentypen wie int etc. ausgetauscht werden, aber es sind auch `komplexe` Datentypen wie `ifPhysAddress` dabei.
- Alle Daten werden nach dem gleichen Prinzip verschickt: TLV (Type, Length, Value)

### OID

- Eine Information (Objekt) die von einem 

### MIB

- Hier werden die Objekte genauer beschrieben
- Ist wie ein Lexikon für die bekommene OID