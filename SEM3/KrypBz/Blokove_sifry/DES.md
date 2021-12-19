64b blok
56b kľúč
[[Feistel]]ova sieť s 16 kolami
inicializačná (vstupná) permutácia, výstupná permutácia, nemajú vplyv na bezpečnosť

![[DES.png]]

Na začiatku činnosti sa bity vstupného bloku poprehadzujú podľa vstupnej permutácie, na záver sa poskladajú naspäť
![[DES_permutacia.png]]


![[DES_f.png]]
Na spracovanie 32 bitov pravej pólky bloku sa vykoná expanzia štvoríc bitov podľa nasledovného algoritmu
![[DES_expanzia.png]]
Na spracovanie prepočítaných blokov sa použijú S-boxy, ktoré zredukujú počet bitov z 48 späť na 32
S-box je tabuľka so 4 riadkami a 16 stĺpcami
v každom boxe sa vnútorné bity spracujú na identifikáciu stĺpca, prvý a posledný na identifikáciu riadku

Keďže klúč je 56b, ale ukladá sa ako 64b s tým, že v každom bajte je 1 bit kontrolný, doplňujúci na nepárnu paritu.
Zvyšných 56b sa rozdelí na polovocie, na každú sa aplikuje ľavý rotačný posun buď o 1 miesto (i = 1, 2, 9, 16), alebo o dve.

**Útoky:**
- **hrubou silou** : $2^{56}$ kľúčov, v dnešnej dobe možno prelomiť distribuovaným výpočtom
- **diferenciálna kryptoanalýza** : šifrujú sa dva rôzne priame texty, diferenciou možno odsledovať niektoré vlastnosti kľúča
- **lineárna kryptoanalýza** : 
![[DES_linearna_kryptoanalyza.png]]
ak platí ^ s pravdepodobnosťou rôznou od 1/2, možno využiť pri kryptoanalýze
- **meet-in-the-middle**: ak poznám aj priamy aj zašifrovaný text (dvojicou kľúčov) možno nájsť dvojicu kľúčov zostrojením dvoch tabuľiek. Ak sa výsledok šifrovania zhoduje s výsledkom dešifrovania, našli sme kandidátov na kľuče
![[DES_meet-in-the-middle.png]]