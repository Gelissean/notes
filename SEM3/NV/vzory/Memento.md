Memento
token, pamätník

bez porušenia zapúzdrenia zachytáva vnútorný stav objektu, čo umožnuje jeho obnovenie neskôr

- možnosť navrhnúť undo redo bez porušenia zapúzdrenia (skryté atribúty)

vhodné použiť ak:
- aktuálny obraz stavu musí byť uložený a neskôr obnovený
- rozhranie na získanie vnútorného stavu by odhalilo implementačné detaily
![[memento_implementacia.png]]

- zachováva zapúzdrenie ukrytím komplexných implementačných detailov pôvodcu, ktoré sú mimo neho
- neudržiava vnútorné stavy pôvodcu, zjednodušuje a sprehľadňuje kód
- môže byť náročné na systém ak sú stavy veľmi veľké alebo náročné na obnovenie
- nemusí existovať konštrukt, ktorý umožní obmedziť prístup k stavu iba na pôvodcu
Príbuzné stavy
- [[Command]] - príkaz môže využiť pamätníka na správu operácií
- [[Iterator]] - pamätník môže ukladať pozície do iterátore pri prechode komplexnými štruktúrami
