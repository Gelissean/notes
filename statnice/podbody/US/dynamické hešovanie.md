- pri raste a zmenšovaní súboru sa uloženie dát reorganizuje automaticky
- okamžitý prístup k dátam v súbore
- kombinácia hešovacieho súboru a indexu (v tvare [[znakový strom]])
- alternatíva [[B+ strom]]u
- princíp fungovanie zhodný s [[rozšíriteľné hešovanie]], index je tvorený stromovou štruktúrou

princíp:
- hešovacia funkcia mapuje kľúč do bitových reťazcov určitej dĺžky
- pri prístupe sa kľúč využíva: 0 - vetvenie doľava, 1 - vetvenie doprava
- každý blok má vlastnú dĺžku $d$, obsahuje $d$ záznamov
- hĺbka bloku určuje koľko krokov je treba vykonať na dosiahnutie bloku (maximálna hĺbka)

- rozdelenie vrcholov na prázdny (interný) a plný (obsahuje dáta, externý)
![[dynamické hešovanie.png]]