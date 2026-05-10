---
title: "RS1p_5.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/ØS1/Pøednáky/RS1p_5.pdf"
date: 2008-08-24
type: PDF (text-based)
---

3 Simulace a modelování dynamických systémů
Syntéza metod výpočtů a experimentů, umožňující pracovat s tzv. počítačovým modelem
systému stejně jako s laboratorním vzorkem. Předmětem simulace jsou metody sestavení
(počítačových) modelů, ověřování jejich věrohodnosti – verifikace, analýzy chyb, apod.
Počítačový model:
analogový:
•

dynamické jevy se simulují v reálném čase. Obecně nižší přesnost než číslicový výpočet.

číslicový:
•

vyšší přesnost, simulace probíhá v počítačovém (diskrétním čase). Ve spojení s vhodným
programovým vybavením lze realizovat složité modely.

hybridní:
•

využívá předností obou dříve uvedených.

Simulace se provádí na modelech fyzikálních (např. model turbíny ...) nebo matematických
(počítačových). Při vytváření modelu se využívá principu analogie mezi jevy stejné nebo
různé fyzikální podstaty. Analogie spočívá v tom, že zkoumané děje lze popsat stejným
matematickým popisem.
Model a originál se mohou podobat buď jen v průběhu výstupních veličin (homomorfismus),
nebo i v průběhu vnitřních veličin, tj. i ve své struktuře (izomorfismus).
Fyzikální modely mají podobnost s originálem izomorfní. Počítačové modely mohou mít
podobnost homomorfní i izomorfní. To záleží na tom zda matematický popis sleduje strukturu
originálu nebo jen relaci vstup-výstup.

4 Teorie řízení
4.1 Základní pojmy
Úkolem teorie řízení je zjišťovat objektivní zákonitosti, jimiž se zabezpečuje cílevědomý
průběh nejrůznějších procesů v přírodě a společnosti.
Řízení lze charakterizovat jako cílevědomé (přinucovací) působení na objekt s cílem
zabezpečit žádanou funkční kvalitu objektu nebo jeho rozvoj při samovolně se měnících
okolních vlivech.

1

Řízení
•

je proces, ve kterém je získávána informace o řízeném objektu a jeho okolí a je
zpracovávána a využívána tak, aby docházelo k udržování výstupní veličiny řízeného
objektu v žádaných mezích, nebo ke změně výstupní veličiny podle zadaného kritéria.
Uskutečňuje-li se bez zásahu člověka jde o automatické řízení.
Při řízení je obvykle uplatněn jeden ze základních principů kybernetiky – zpětná vazba.

Ovládání
•

je způsob řízení bez využití informací o výsledku. K ovládání je využívána jen apriorní
informace o řízeném objektu.

Systém automatického řízení (SAŘ): řídící systém + řízená soustava

y (t )

řízená (regulovaná) veličina

w ( t ) řídící (požadovaná) veličina
e(t )

regulační odchylka

u (t )

řízení

z (t )

poruchová veličina (může působit kterékoliv části SAŘ)

Základní úlohy teorie řízení:
Analýza SAŘ
•

Úlohy analýzy jsou zaměřeny na zkoumání dynamického chování systému (řízené
soustavy) s cílem dospět k matematickému popisu (modelu) řízení soustavy.

Syntéza SAŘ
•

Úlohy syntézy jsou zaměřeny na výběr, návrh a realizaci řídícího systému k dané řízené
soustavě tak, aby bylo dosaženo požadavků kladených na SAŘ.

2

Dále se zaměříme na lineární t-invariantní spojité dynamické systémy s jedním vstupem a
jedním výstupem.

3

