KV - verejný kľúč
KT - tajný kľúč

Účastník A podpíše správu tak, že k nej pripojí výsledok dešifrovania správy kľúčom $KT_A$, teda
$Sig(M) = D_{KT_A}(M)$

Účastník B overí pravosť podpisu tak, že vypočíta
$M' = E_{KV_A}(Sig(M))$
a skontroluje  čí platí $M = M'$
Ak neplatí, správa bola zmenená alebo podpis nie je pravý
Ak sa zhoduje podpis je pravý a správa nezmenená
Iba účastník A mohol k správe vytvoriť Sig(M) pretože on jediný má kľúč $KT_A$

postup podpisovania správy M:
1. Vypočíta $h(M)$
2. odtlačok zašifruje tajným kľúčom
$Sig(M) = D_{KT_A}(h(M))$
3. odtlačok pripojí ako digitálny podpis

postup overenia podpisu:
1. vypočíta $H = h(M)$
2. vypočíta sa $H'=E_{KV_A}(h(M))$
3. skontroluje sa či $H'=H$

Pridanie časovej známky:
Ku správe sa priloží odtlačok správy a verejne známa informácia, ktorá vznikla v deň podpisu
Ako podpis pridáme časť Y = sig(MD(M),PUB), vytvorený podpis z podpisu správy a časovej známky
Zverejníme trojicu MD(M), PUB, sig(MD(M),PUB)