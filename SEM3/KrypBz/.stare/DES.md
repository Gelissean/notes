Data Encryption Standard
bloková šifra s 64b blokom
56b tajný kľúč na generovanie kľúčov
Feistelova sieť s 16 kolami
na začiatku inicializačná(vstupná) permutácia
na záver výstupná permutácia, ktorá je inverzná k vstupnej
![[DES.png]]

![[DES_permutacia.png]]
prvý bit výstupu bude 1. bit na vstupe. 50. bit na vystupe bude 2. na vstupe

![[DES_f.png]]

![[DES_expanzia.png]]

![[DES_S_box.png]]
![[DES_S_box_pravidla.png]]
pri poslednom jedno z nich má mať výstupný byt, nie vstupný
![[DES_generovanie_klucov.png]]
![[DES_permutacie_PC.png]]

počet kľúčov $2^{56}$ sa dnes javí ako málo

prelomenie napr. pomocou *diferenciálnou kryptoanalýzou*, zakryptovaním dvojice priamych textov s malými rozdielmi, snada odhadnúť jednotlivé bity kľúča, celkom neefektívne

lineárna kryptoanalýza - útok so známym priamim textom
![[DES_S-box_priklad.png]]