# Ethernet

## Übertragung

- Ethernet benötigt 14 Bytes für einen Ethernet Header und 4 Bytes als Ethernet Trailer ("Schwanz", überträgt fehlerprüfende Maßnahmen. checksumme etc.)
- Ethernet Header:
  - 6 Bytes MAC-Empfänger
  - 6 Bytes MAC-Absender
  - 2 Bytes "Ether-Type", dort ist das zu versendente Protokoll hinterlegt. 
- Die zu nutzenden Bytes bewegen sich in dem Bereich von 64 bis 1500 Bytes.