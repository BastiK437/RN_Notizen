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
