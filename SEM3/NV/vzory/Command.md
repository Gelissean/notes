príkaz
Behaviorálny vzor

- používateľské rozhranie
pri ukladaní možno uložiť tlačítkom na GUI alebo v kontextovom menu, odkazujú sa na rovnakú akciu

Použiť keď:
- treba parametrizovať objekty akciami
- jednoduchá implementácia UNDO/REDO, makro

![[command_implementacia.png]]

Rozdeľuje závislosť objektov, ktoré vyvolávajú operáciu a tie, ktoré ju vykonávajú
Jednoduché pridávania nových príkazov

![[command_priklad_chodca.png]]

Príbuzné vzory:
[[Composite]] - možno vytvoriť macro príkazy
[[Memento]] - implementovanie príkazu Undo
[[Prototype]] - prototypy jednotlivých príkazov
[[xServant]] (mimo GoF) - "hej ty, sprav toto so mnou", servant sprostredkováva činnosť, príkaz vykonáva