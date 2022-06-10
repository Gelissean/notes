Technológia umožnujúca vykonávania simulácie na viacerých počítačových systémoch

Simulačný model sa dá predstaviť ako množina sekvenčných simulačných modelov (Logický proces **LP**)

Každý LP si udržiava vlastnú hodnotu lokálneho simulačného času (lokálny virtuálny čas)

Každý DP vykonáva simuláciu v kauzálnom poradí

**Synchronizačný mechanizmus** - zaručuje, že výsledky distribuovaného modelu budú totožné s výsledkami sekvenčného simulačného modelu

Metódy synchronizácie:
- konzervatívne - striktne dodržujú podmienku lokálnej kauzality
	- možné uviaznutie
		- riešenie napr. pomocou nulových správ na posúvanie času
	- bariérová synchronizácia - možnosť krokovať iba po určitú dobu (bariéru)
- optimistické - LP pracujú bez obmedzení, pri porušení sa napravujú
	- pri porušení kauzality návrat v čase (rollback)
	- antisprávy - ak sa niečo vykonalo skôr než sa malo
	- TimeWarp algoritmus
- kombinované