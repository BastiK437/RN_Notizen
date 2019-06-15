# DNS 

Domain Name System

## Aufbau

- hierarchischer, verteilter Namensraum 
- Von der Wurzel ausgehend Top-Level-Domains (NIC)
- Lokale zwischenspeicherung häufig erfragter Daten
- Der Namensauflösungs-Prozess geht bei Informationsmangel zum hierarchisch nächst höheren Server. "rechts nach links".  
  - Bsp: charlie.brown.peanuts.org
  - Ist die Adresse bereits bekannt? -> 
      - Ja: fertig
      - Nein: Referenz zum nächst höheren namens bereiche: .org
          - Anfrage: charlie.brown.peanuts.org
          - liefert Referenz auf: peanuts.org
              - wieder Anfrage: charlie.brown.peanuts.org
              - liefert Referenz auf: brown.peanuts.org
                  - wieder Anfrage: charlie.brown.peanuts.org
                  - liefert Referenz auf: charlie.brown.peanuts.org