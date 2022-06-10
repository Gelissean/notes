- prioritný front
- kľúč - **priorita**
- priorita ich kľúča je vyššia ako priorita ich potomkov
![[fibonacci-heap.png]]
- uzol má 4 referencie: ľavý/pravý sused, otec, jeden zo synov
- každý uzol drží označenie (či stratil syna od doby, keď bol nastavený ako syn iného uzla)
- prvok sa odznačí ak je označený a stratí syna
- pri vkladaní sa vloží ako ľavý sused uzlu s maximálnou prioritou (koreňa)
- pri operácií merge sa väčší koreň stane synom menšieho
- pri mazaní sa nesmú vytvoriť dva koreňe rovnakého stupňa, musí sa vykonať operácia merge