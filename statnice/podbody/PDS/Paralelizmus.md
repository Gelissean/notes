ekvivalencia rozvrhov

permutovatelnosť operácií
- dve operácie Read sú permutovateľné
- operácie read a write nad tým istým objektom nie sú permutovateľné

dostatočná podmienka serializovateľnosti:
- aby mohol byť transformovaný pomocou permutovateľných operácií na sériový rozvrh

precedencia transakcií
- transakcia T1 predchádza transakciu T2 ak v ňom existujú dve nepermutovateľné operácie

graf precedencie transakcií
- orientovaný graf, ktorého množina vrcholov je množinou transakcií a množina hrán je množina orientovaných hrán v = \[Ti, Tj\] takých, že traksakcia Ti predchádza Tj

dostatočnou podmienkou serializovateľnosti rozvrhu, je ak v grafe precedencií neexistuje cyklus

problémy súvisiace s paralelizmom
- problém straty operácií - ak druhá transakcia prepíše moju premennú skôr ako ja
- problém nekomitovaných dát - ak druhá transakcia vráti svoj stav a ja prečítam nevrátené dáta
- prípad nekonzistentných dát - ak druhá transakcia prepíše moje zmeny 
- fantóm - ak druhá transakcia zmení hodnoty premenných a u mňa sú dve totožné čítania odlišné

dva druhy zámkov:
- zdieľaný zámok (S-lock) - umožnuje čítanie, zabezpečuje nemennosť záznamov.
- exkluzívny zímok (X-lock) - v danom momente vlastní iba jedna transakcia, druhá nemôže získať ani S ani X lock