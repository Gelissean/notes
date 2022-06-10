Red-Black strom
- modifikácia [[2-4 strom]] na binárny tvar
***
- koreň je čierny
- červený uzol má výlučne čiernych synov
- v reťazcoch vpravo/vľavo nemôžu byť za sebou 2 červené uzly
- počet čiernych vrcholov na ceste od koreňa je rovnaký
***
- priemerná zložitosť operácií **O(log2 n)**
![[2-4 na R-B.png]]
- ak je novo vložený uzol koreň, je čierny
- ak je brat otcovského uzla čierny otoč uzly (vkladaný, otcovský, otcovský otcovského) tak, aby boli v poradí *inorder*
- ak je brat otcovského uzla červený, zafarbi otcovský a jeho brata na čierno, a ich otca na červeno. Toto sa cyklicky oprakuje ak sa nachádzajú dva červené
- pri mazaní sa na mieste čierneho uzla predstavuje **dvojito čierny**
