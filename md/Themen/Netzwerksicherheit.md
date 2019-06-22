# Netzwerksicherheit

## Verschlüsselung 

### Symmetrische Verschlüsselung

- Ver- und Entschlüsseln mit demselben "Geheimnis"
- Schlüssel bleibt gehim

### Asymmetrische Verschlüsselung

- Unterschiedliche Schlüssel zum Ver- und Entschlüsseln
- Ein Schlüssel kann veröffentlicht werden

### Certificate Authority - CA

- Dritter Ansprechpartner um zu prüfen, ob Schlüssel wirklich zur richtigen Gegenstelle gehört

### Anwendungsschicht

- PGP (Mail) 
      - Public key basierend
      - Vorteil
          - Geeignet für alle Anwendungsfälle
          - Infrastukturungebunden
          - Anwendungsspezifisch optimierbar
      - Nachteile
          - Kommunikationsprofile bleiben sichtbar
          - Anwedungsprogramme müssen Methoden implementieren

### Scoket Layer (4+)

- SSL/TLS
      - Symmetrische Verschlüsselung
      - Vorteil
          - end-to-end Sicherheitsmodell
          - Transparent im hinblick auf Anwendungsdaten
          - Einfach integrierbar
      - Nachteile
          - Kommunikationprofile bleiben sichtbar auf der Transportschicht (einschl. Anwendungsprotokoll)
          - Anwendungsprogramme müssen Bibliothek benutzen

### Leitungsverschlüsselung

- Bis-Scrambling, WEP
      - Vorteile
          - Vollständige Informationsverschlüsselung
          - Völlig transparent gegenüber höheren Schichten
      - Nachteile
          - Leitungsgebunden, nicht end-to-end
          - Erfordert Hardwareunterstützung

### Funkdaten WEP/WPA

- Private key based: AP & STA halten pre-shared secret (40 | 104 bits)
- Authentication: Challenge(AP) - Response (STA) Schema
- Encryption: RC4 Verschlüsselung (XOR mit pseudo-Zufallsstrom) basierend auf (ungenügend vielfältigen) InitialisierungsVektoren (IV).

### MAC Sicherung + Tunnel (L2)

- MAC Sicher: ACLs, 802.1x port authentication
- Tunnel: PPP/PPTP, L2TP (+encryption),...

Vorteile
- Verhindert ARP spoofing + network intrusion
- Transparent zur Netzwerkschicht (nur Tunnel sichtbar)
  
Nachteile
- Benötigt Server / Provide Unterstützung
- Begrenzte Skalierbarkeit / Performanz

#### Tunneling

- Encapsulation und Encryption von Datagrammen

### RADIUS (Remote Authentication dial-In User Service)

- Client-Server-Protokoll zur Authentifizierung, Autorisierung und Accounting am Netzwerk
- Drei Protokolloperationen
      - Access-Request (Bitte um Freigabe)
      - Access-Accept (Genehmigt)
      - Acces-Reject (Abgehlent)
- Nach erfolgreicher Authentifizierung übermittelt RADIUS eine konfigurierbare anzahl von Zugangsattributen

### Internet Layer (IP)

- Paketverschlüsselung, Adressauthentifikation

Vorteile
- Transporttransparent
- Effizient & weitverkehrs-routebar
  
Nachteile
- Kommunikationsprofile auf dem IP layer sichtbar

Ansatz
- IP-in-IP secure tunnelling: IPSec

### Firewalls - schichtenübergreifendes Paketfiltern

Konzept
- Ungewollter Datenverkehr wird an einem Kontrollpunkt blockiert
- 