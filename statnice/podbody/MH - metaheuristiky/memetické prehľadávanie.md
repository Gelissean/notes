- evolučná metaheuristika
- zobecnením ostatným metaheuristík, umožnuje ich spojenie
- populácia - množina prvkov, genotyp. prístupné riešenie - fenotyp
- šablóna algoritmu:
	- inicializuj populáciu
	- repeat
		- pop_ = generuj novu populaciu(pop)
		- pop = aktualizuj populaciu(pop, pop_)
		- if pop má malú diverziu
			- pop = restartuj populaciu(pop)
	- pokým nenastane podmienka zastavenia
![[memetic_init.png]]
![[memetic_new.png]]
![[memetic_restart.png]]