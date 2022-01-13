- napodobňuje procesy v mozgu
- realizuje proces učenia a ukladanie poznatkov
- rozhodovacie procesy s využitím získaných poznatkov

konštrukcia neurónu:
vstupy - vstupné signály (dendrony), majú váhu
telo - obsahuje vyhodnocovaciu funkciu (g(z)=y)
výstup - axon

---
**dopredné neurónové siete**
- môžu mať len jednu výstupnú vrstvu alebo môžu byť tvorené jedným neurónom
- môžu mať viac vrstiev, kde neuróny z jednej vrstvy nie sú prepojené. Signál sa šíri od vstupnej vrstvy (prvá skrytá) do ďaľších a končí vo výstupnej
![[NS_dopredne.png]]
---
rozpoznávanie úlohy
![[NS_rozpoznanie.png]]
pri dvoch vstupoch môžeme modelovať jednobuňkové siete.
Funkcia AND a funkcia OR je na jednej bunke natrénovateľná ale funkcia XOR však nie, pretože je **lineárne neseparovateľná** (nie je možné oddeliť správne výsledky iba jednou lineárnou funkciou)
