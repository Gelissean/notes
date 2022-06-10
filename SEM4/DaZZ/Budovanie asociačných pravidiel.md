- jednoduché metódy
- 2 problémy:
	- výpočtová komplexnosť
	- pokrytie a presnosť výsledných pravidiel

- asociačné pravidlá sa tvoria kombináciou jedno až $n$ položkových množin, ktoré majú aspoň požadovanú presnosť a požadované pokrytie
![[asociačné pravidlá.png]]

apriory princípy:
- generácia nových pravidiel - ak kombinácia má dobré pokrytie tak aj predkovia kombinácií budú mať dobré pokrytie
- pruning - ak má kombinácia malé pokrytie, tak aj všetci potomkovia budú mať malé pokrytie
