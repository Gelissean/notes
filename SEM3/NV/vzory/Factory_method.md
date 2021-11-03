Factory Method
definuje rozhranie pre vytváranie objektov
virtual constuctor

![[Factory_method_iterator.png]]
pomocou virtuálneho konštruktora vráti správny typ iterátora

Použit keď netuším akú konkrétnu metódu budem vytvárať, konkrétnu triedu vytvorí potomok. Zodpovednosti sú delegované na potomka

![[factory_method_implementacia.png]]
jeden interface, ktorý zastrešuje produkt, jeden interface pre factory
klient nerieši typ produktu, pracuje s ním iba pomocou rozhrania

Odstraňuje potrebu uvedenia konkrétnej triedy
Nepohodlné pri tvorbe špecifického produktu (nutnú vlastnú továreň)
Podporuje ale princíp programovania proti rozhraniu
Čistejšie ako priama tvorba objektov (pomocou new()):
	ak v kóde volám new Auto() a potom zmením auto na nákladné auto treba všade prepísať
	pri použití factory method sa mení iba prepis triedy, volania sú všade rovnaké
	
![[factory_method_priklad.png]]
každá trieda si vytvorí vlastný iterátor, s ktorým vie dobre a efektívne pracovať

Príbuzné vzory:
[[Abstract_factory]] - často využíva továrenské metódy na implementáciu
[[Template_method]] - využíva factory method
[[Prototype]] - rieši podobné problémy (pomocou clone)