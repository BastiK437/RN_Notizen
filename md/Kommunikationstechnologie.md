# Kommunikationstechnologie

## Signalklassen
 
![Signalklassen](img/Signalklassen.png)

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

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc4NTY1Mzc2NF19
-->