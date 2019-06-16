# Selbsteinschätzungsfragen Foliensatz 3a

## Was müssen sich leitungsvermittelnde Komponenten im Unterschied zu paketvermittelnden `merken`?

- der Vermittlungsweg muss abgespeichert werden. Dies geschieht bei paketvermittelnden autonom.

## Warum müssen Ethernet Sender ihr Signal für eine Round-Trip Laufzeit mithören?

- Da die Kollisionserkennung im schlechtesten Fall eine komplette Round-Trip Zeit benötigt.

## Warum sendet nach Kollisionseintritt ein Host erst, nachdem er einen Sendeslot gewürfelt hat?

- Bei sofortigen Senden beider Teilnehmer kann es sofort wieder zu einer Kollision kommen. 

## Welche Art von Vermittlungskomponente muss sich zwischen Ihrem Telefon-Internetanschluss und jedem weiteren Internet Host befinden?

- Ein Modem. Dieses dient als netzabschlussgerät für den Breitbandzugang.
- (Ein Router. Dieser muss beide Netze miteinander verbinden.)

## Warum können `bloße` Ethernet Switches nicht redundant verschaltet werden? Was bewirkt Spanning Tree?

- Da sonst ein Zyklus entstehen kann. Dies ist allerdings nicht erlaubt
- Spanning Tree ist ein Baum, der alle kürzesten Wege von einem Startpunkt zu allen Netzwerkteilnehmern enthält.

## Welchen Vorteil bietet eine Segmentierung gem. 802.1Q in großen geswitchten Netzen? Auf welcher Ebene geschieht sie?

- Abschottung zwischen einem Netzabschnitt und dem anderen Netz. Auf Layer 2.