- alebo heuristiky s učením
- v závislosti na informácií o úspešnosti ale neúspešnosti v minulosti upravujú parametre heuristiky pre nasledujúce kroky

Algoritmus s návratom pri neúspešnom kroku s učením![[vahy_algoritmus s ucenim.png]]
```
ANNKU(u, a, b, c)
w = 0
do{
	h = GetRandomH(p(w))
	v = u + ah
	w = GetAktW(w, b, c,v, u)
	if (f(v) < f(u))
		u = v
} while (nie je splnená podmienka zastavenia)
return u
```
