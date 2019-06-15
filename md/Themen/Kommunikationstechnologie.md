# Kommunikationstechnologie

## Signalklassen
 
![Signalklassen](./img/Signalklassen.png)

## Übertragung

- Abtastung: Diskretisierung in der Zeit
- Quantisierung: Diskretisierung im Wertebereich
- Codierung: (ggf. komprimierte) Binärdarstellung der quantisierten Werte

## Kanaleinfluss

- Signalveränderungen durch
      - Kanaleinflüsse (Dämpfung, Reflektion, Nebensprechen)
      - Signalausbreitung (Laufzeitunterschiede, Dispersion)

## Abtasttheoreme

- Shannon und Raabe: t = 1/(2*B), wobei B die höchste Signalfrequenz ist und t der Zeitabstand der Messungen des Signals ist. -> Die Abtastfrequenz muss mindestens doppelt so hoch sein wie die höchste vorkommende Signalfrequenz.

## Übertragungstheoreme

- H. Nyquist: max DR (Datenrate) = 2 B ld n bit/s
      - B: Kanalbandbreite
      - n: diskrete  Kanalstufen
      - Bsp.: Kanal mit 3 kHz, binäres Signal -> 2 * 3000 * log2(2) = 6000 bit/s
- C. Shannon: max DR = B ld (1 + S/N) bit/s
      - B: Kanalbandbreite
      - S/N: Signal-Rauschverhalten
      - Bsp.: Kanal mit 3 kHz Signal-Rauschverh. von 30 dB:
          - 30 dB umrechnen:
          - 10*log10(S/N) = 30 dB 
          - S/N = 10³ = 1000
      - Somit: 3000 * log2(1+1000) = ~30 kbit/s

## Glasfaser

![](./img/Multimode_Stufenindex.png)
![](./img/Multimode_Gradientenindex.png)
![](./img/Monomode.png)

- Multimode für kurze, Monomode für lange Strecken

## Multiplexing

- Space Division Multiple Access (SDMA). Bsp. Funkzelle
        - Aufteilung des Mediums in räumlich getrennte Übertragungskanäle
- Time Division Multiplex Access (TDMA). Bsp. WLAN
        - Die Benutzer werden in Zeitblöcke eingeteilt in denen sie eine Frequenz nutzen dürfen.
- Frequency Multplex Access (FDMA)
        - Die Benutzer werden einer jeweiligen Frequenz zugewiesen
- Code Division Multiplex Access (CDMA)
        - alle Stationen operieren auf derselben Frequenz und nutzen so gleichzeitig die gesamte Bandbreite des Übertragungskanals
        - Signal wird auf der Senderseite mit einer für den Sender eindeutigen Pseudozufallszahl verknüpft (XOR) 
        - Empfänger kann mittels bekannter Sender-Pseudozufallsfolge und einer Korrelationsfunktion das Originalsignal restaurieren
- Wavelength Division Multiplexing
        - Lichtsignale verschiedener Quellen werden auf unterschiedliche Frequenzen gehoben und dann addiert

### Richtungs-Multiplexing

- Simplex: Daten gehen nur in eine Richtung
- Half Duplex: Daten gehen im Wechsel in beide Richtungen, nicht gleichzeitig
- Duplex: Daten gehen gleichzeitig in beide Richtungen