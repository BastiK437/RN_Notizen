# Wireless Networking

## Modulation und Demodulation

- Digitale Daten in Analoges Signal umwandeln
- Analoges Signal auf Träger Frequenz modulieren
- Demodulation genau umgekehrt

## Signalausbreitung

- geradlinig - wie Licht
- Empfangsleistung nimmt mit 1 / d² ab (d = Distanz Sender - Empfänger)
- Empfangleistung hat außerdem viele weitere Einflüsse (Reflexion, Refraktion, Streuung...)


### Bereiche

Es wird zwischen drei Bereichen unterschieden

- Übertragungsbereich
      - Kommunikation möglich
      - niedrige Fehlerrate
- Erkennungsbereich
      - signalerkennung
      - keine Kommunikation möglich
- Interferenzbereich
      - Signal kann nicht detektiert werden
      - Signal trägt zum Hintergrundrauschen bei

## SDMA

### Feste Kanalzuordnung

- Bestimmte Menge von Kanälen fest gewisser Zelle zugeordnet
- Problem: Wechsel in Belastung der Zellen

### Dynamische Kanalzuordnung

- Kanäle einer Zelle werden nach bereits zugeordneten Kanälen der benachbarten zellen gewählt
- mehr Kapazität in Gebieten mit höherer Nachfrage
- auch Zuordnung aufgrund von Interferenzmessungen möglich

## MA/CA - Kollisionsvermeidung

- RTS: Anfrage ob Paket gesendet werden kann
- CTS: Kann gesendet werden
- Signalisierungspakete beinhalten:
      - Senderadresse
      - Empfängeradresse
      - Paketgröße

## CSMA/CA

- Bei Ethernet gibt es eine Collission Detection, dies ist bei einer Funkübertragung allerdings nur bedingt möglich (https://www.elektronik-kompendium.de/sites/net/1712071.htm)
- Bevor ein Client sendet, schickt er ein LBT (Listen-Before-Talk). Ist die Funkschnittstelle belegt, wartet er eine zufällige Zeit (42 - 178 us) und schickt es nochmal. 
- Ist die Schnittstelle frei, kann gesendet werden
- Da nun keine CD durchgeführt werden kann, muss der Empfänger mit einem ACK antworten

## WIMAX

- langsamer als Wlan aber größere Reichweite
- Verbinungsorientierte Funktechnologie