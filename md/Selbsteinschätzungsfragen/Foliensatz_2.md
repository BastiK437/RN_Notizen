# Selbsteinschätzungsfrage

## Ist das Internet Protokoll IP für Broadcast Netze geeignet?

- Ja

## Sie wollen eine Mail der Größe 1,2 KB über ein Ethernet Netzwerk versenden. Wie Groß ist der Protokoll Overhead?

- SMTP wird über TCP versendet. Bei TCP wird ein Header von 20 Bytes benötigt. Dort kommt noch ein IP-Header auch mit 20 Bytes und ein Ethernet Header mit 14 Bytes hinzu. Zusätzlich benötigt Ethernet einen Trailer mit 4 Byte. Somit: `20 + 20 + 14 + 4 = 58 Bytes Overhaed`

## Wie wird das eMail bcc in SMTP abgebildet? Wer übernimmt welche Aufgabe? 

- `Frage nicht ganz klar`
- Die bcc Einträge können im Header von SMTP abgebildert werden. Dies ist allerdings abhängig von der implementierung des jeweiligen E-Mail Programms und des beteiligten Mailservers. 

## Wie läuft der Namensauflösungsprozess im DNS ab?

- Zuerst wird geschaut, ob die Adresse bereits bekannt ist. 
- Falls sie nicht bekannt ist muss immer zum nächst höheren namens Bereich geschaut werden. 

## Inwieweit unterscheidet sich der Standardisierungsprozess im Internet von dem üblichen Vorgehen?

- Keine ahnung was das `übliche Vorgehen` ist.