Navrhnite knižnicu, ktorá bude predstavovať všeobecný **logovací systém**, ktorý bude spĺňať nasledujúce požiadavky.

1.  Umožní jednoduché logovanie **správ**, ktoré budú obsahovať:
    -   typ správy (chyba, systémové hlásenie, varovanie, .. - konfigurovateľná kategória)
    -   autora,
    -   text správy,
    -   prioritu (veľká, malá, žiadna, .. - konfigurovateľná kategória) a
    -   kategóriu (napr. dátová chyba, chyba spojenia, .. - konfigurovateľná kategória).
2.  Knižnica poskytne rôzne druhy logovacích **miest** (napr. súbor, panel, okno, ..). Navrhnite knižnicu tak, aby bolo možné využiť existujúce a prípadne pridávať ďalšie logovacie miesta a aby tieto mohli v aplikácií koexistovať (v aplikácií môže byť aj viac miest toho istého druhu - napr. viac logovacích panelov). Navyše, logovacie miesta môžu byť konfigurovateľné, aby prijímali len správy od daného autora (autorov), typu, priority alebo kategórie. 
3.  Logovanie správ bude pre klienta **transparentné a jednoduché na použitie**. Logovanie správy spôsobí jej pridanie do každého miesta, jej vymazanie spôsobí vymazanie aj v ostatných miestach.

Implementujte a overte váš návrh.




mediator do stredu, zaloguje odloguje
- metody kto loguje co

logovacie miesto - sa prihlasuje

B:
![[cv5_B.png]]
C:
![[cv5_C.png]]

E:
![[cv5_E.png]]