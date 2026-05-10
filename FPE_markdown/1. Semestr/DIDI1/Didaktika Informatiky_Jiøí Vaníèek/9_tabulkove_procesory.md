---
title: "9_tabulkove_procesory.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/1. Semestr/DIDI1/Didaktika Informatiky_Jiøí Vaníèek/9_tabulkove_procesory.pdf"
date: 2008-09-30
type: PDF (text-based)
---

Přednášky z didaktiky informatiky a výpočetní techniky

Jiří Vaníček, 2004

Tabulkové procesory, databáze
Úvod
Hromadné zpracování dat je vlastně hlavní téma, o němž bude řeč na dnešní přednášce. Jestliže na
Internetu žák data a informace získává a pomocí www stránek, textů a hypertextů je prezentuje, potřebuje
porozumět též oblasti zpracování dat, při němž z údajů původních jsou získávána data nová, která nesou novou
informaci, nový poznatek.
Dalším podstatným důvodem pro zařazení tohoto tématu je, že kromě programování je toto téma jediné,
v němž se žáci setkávají s aplikací matematických metod práce ve výpočetní technice. Vzorce, grafy,
matematické výrazy v dotazech, to vše je součástí dalšího vysoce formálního prostředí, do kterého žáci nahlížejí,
snaží se v něm orientovat a ti nejlepší jej dokáží mistrně ovládat. Jestliže inteligence je schopností orientace
jedince v neznámém prostředí, pak snaha pochopit princip fungování tabulkového procesoru nebo databázového
systému je velmi dobrým tréninkem inteligence.
Základní nebo střední škola?
Právě pro svoji obtížnost a vysokou abstrakci danou používáním matematických výrazů, kvantifikátorů,
nutností rozumět grafům apod. je toto téma velice náročné, a to jak pro žáky, tak pro učitele. Omezení při jeho
zařazení do výuky jsou dána též matematickými znalostmi a schopnostmi žáků různého věku a typu školy.
Z těchto důvodů pro základní školu rozhodně nepřipadá v úvahu práce s databázemi. Práce
v tabulkovém procesoru pak představují jen základní vzorce, jednoduché grafy a řešení úloh těmito prostředky
(jen velmi pozvolna a nenáročně je lze seznámit s pojmy např. kopírování vzorců roztahováním, formát buňky,
absolutní a relativní adresa).
Středoškoláci ve věku 16 - 17 let zvládnou i díky rozvinutějšímu matematického aparátu prakticky
všechny podstatné nástroje tabulkových procesorů včetně práce s jednoduchou databází. Se samotnými
databázovými systémy dokáží studenti většinou pracovat pouze na uživatelské úrovni (tabulky, výběrové a
křížové dotazy, formuláře, sestavy, relace). Správa databázových systémů se vesměs neobejde bez programování
maker a vytváření složitých dotazů, které je ovšem svou povahou již nad úrovní středoškolského vzdělání nebo
vyžadují delší praxi a zkušenosti. Pro seznámení s databázemi lze úspěšně použít tabulkové procesory, protože
pojmová struktura tématu (řazení dat, filtrování, souhrny) v obou druzích aplikací zhruba odpovídá.
Cíle výuky
Cíle výuky v práci s tabulkami i databázemi bychom mohli najít ve velmi podobné struktuře:
•
ovládat tabulkový procesor (databázový program), orientovat se v jeho prostředí
•
porozumět novým pojmům - adresy, vzorce, funkce, formáty … (dotazy, sestavy, relace…)
•
řešit úlohy na zpracování dat (převedení problému „do počítače“, tedy matematizace problému, a
opět správné převedení výsledku „z počítače“, tedy interpretace výsledky)
•
pochopit princip činnosti tabulkového procesoru (databázového systému)
•
trénink životních dovedností (např. řešení problémů, používání zdravého rozumu, spolupráce …)

1.

Poznámky k cílům výuky
Cílem výuky není zvládnutí určité aplikace (počítač je přeci nástroj, nikoliv cíl). Jistě, aby dítě nakreslilo graf,
musí se v aplikaci zorientovat. Ovšem „vyznat se“ neznamená „celou se ji naučit“. Výuka formou seznámení
s nabídkou pracovních nástrojů je vlastně ztrátou času - učitel by měl umět vybrat ty nástroje, které jsou účastny
výpočtů a aktivit veoucích k pochopení pojmů, k řešení standardních úloh.
Velmi konkrétní příklad: aby se žák naučil používat funkce v tabulkovém procesoru, nepotřebuje znát
všechny funkce, dokonce ani funkce všech typů. Také ovšem nestačí zvládnout funkci jednu nebo dvě. Potřebuje
zvládnout funkce různých druhů - např. pokud se neseznámí s některou z rozhodovacích funkcí (např. KDYŽ)
nebo s některou funkcí na úpravu textů, s funkcí z ryze matematických (náhodné číslo) nebo s funkcí vyžadující
více argumentů. Jinou otázkou je, co to znamená „zvládnout funkce“ – stačí, aby věděl, jak se použije průvodce
funkcí?
Jiné funkce žákovi ozřejmí některé pojmy, jako je formát buňky a čísla v buňce zapsaného Jde např.
o funkci ZAOKROUHLIT, pomocí níž lze velmi dobře vysvětlit rozdíl mezi formátem čísla v buňce (číslo
zobrazené na 2 desetinná čísla a číslo zaokrouhlené na 2 desetinná čísla nemusí být totéž číslo).
Dobře naučené používání funkcí v tabulkovém procesoru posiluje funkční myšlení žáků, posiluje
představu funkce i z matematického pohledu.

Přednášky z didaktiky informatiky a výpočetní techniky

2.

3.

Jiří Vaníček, 2004

Řada učitelů, vědoma si obtížnosti látky, často utíká k rámování a podbarvování tabulek. Také zapisování do
buněk tabulky by mělo být podřízeno výslednému cíli: chtít po žákovi vzorec, návod na řešení úlohy.
Úlohy typu „Napište si svůj rozvrh“ by neměly být prováděny v tabulkovém procesoru, a to z toho důvodu, že
v této úloze nejde o žádné zpracování dat, ale pouze o vyplnění tabulky a její zformátování (což lze s úspěchem
provádět v textovém editoru). Děti by mohly získat falešnou představu, že v tabulkovém procesoru se píší
tabulky, ale to je přeci omyl. To bychom mohli zadávat úlohy „napište básničku v grafickém editoru“, „pošlete si
mail sami sobě“, „napište počítačový program, který váš týdenní školní rozvrh vypíše“ - s argumentem „vždyť
to jde!“
Co znamená 3. bod cílů výuky, „pochopit princip činnosti“ daného druhu software? U databází jde např. o
pochopení, jak aplikace funguje, např. že něco jiného je vytvářet dotaz a něco jiného je dotaz použít.
U tabulkových procesorů je základním principem neustálé přepočítávání všech vzorců a grafů při změně obsahu
jakékoliv buňky.
Formy výuky
Styl práce při tématu hromadného zpracování dat poměrně dobře připomíná školní předmět matematiku.
Kromě některých úvodních hodin nebo práce na samostatných projektech jde vlastně o řešení (matematických)
úloh pomocí počítačového software. Učitel tedy zadává úlohy, které žáci sami nebo s učitelem řeší.
Výuka typu „návod, recept na dosažení výsledku“ nebo „prohlédněme si, co to dělá“ nesplňuje ani
druhý, ani třetí z vypsaných cílů. I když se učitel věnuje tomuto tématu delší dobu, žáci sice dokáží rychle
vyřešit jednoduchý úkol, který již dostali, ale jsou zcela bezradní při řešení trochu obměněné nebo úplně jiné
úlohy (efekt „učené opice“). Učit žáky podrobný pracovní postup jako např. v dílnách zde nevede k cíli.
Je velmi těžké vést typ výuky, vyžadující řešení (matematických) úloh pomocí počítačového prostředí,
zvláště pro učitele, který není matematik. Však není patrně jiné cesty. I na základní škole je potřeba zadávat
žákům úlohy k řešení, i když úlohy budou jednoduché. V případě, že studenti látce nerozumí (což lze z výsledků
zadaných úloh rozeznat), je třeba zvolnit, opakovat, dávat podobné úlohy a jejich variace. Jakmile studenti
pochopí pojmy, rychle zvládnou pracovní postupy.
Někdy učitel narazí na problém zapomenutých matematických znalostí nebo nezvládnutých
matematických pojmů. Typickým příkladem jsou procenta, kvadratické funkce a jakékoliv vzorce z geometrie.
Zde nezbývá než pokusit se pojmy (procenta) oživit nebo informace (vzorce) nechat vyhledat.
Vizualizace dat
Oba typy software mají dvě základní
schopnosti: zpracovávat data a vizualizovat je,
a to tvorbou grafů (mezi vizualizaci lze svým
způsobem počítat i tvorbu sestav).
Vizuální informace je jiného druhu
než informace čtená či slyšená. Čtení z grafu je
potřeba se též naučit.
Často vidíme na školách výuku tvorby
grafů pouze „podle čtyř oken průvodce tvorby
grafem“. Všichni studenti jsou schopni vytvořit
graf, řada z nich i nádherně měňavých barev,
ale málokdo vytvoří graf tak, aby poskytoval
dobrou informaci. Je třeba, aby se učitel
soustředil na tzv. vypovídací schopnost grafu
(viz obrázek - čeho že se týkají hodnoty,
znázorněné v grafu?).
Graf, který nemá popsané osy a u nějž
není zřejmé, co znamenají čísla na stupnicích a
co zobrazované řady, je naprosto nevyhovující,
i kdyby se otáčel či holograficky vystupoval
před obrazovku.
Typy grafů
Každý uživatel, který potřebuje vytvářet grafy, musí znát rozdíl v použití základních tří typů grafů:
- sloupcový
- spojnicový
- kruhový (koláčový)

Přednášky z didaktiky informatiky a výpočetní techniky

Jiří Vaníček, 2004

Graf sloupcový se používá v grafech, ve kterých porovnáváme hodnoty navzájem mezi sebou (např. či rozlohu
více zemí nebo jejich hrubý domácí produkt)
Graf spojnicový se používá při zobrazování trendů, tedy v situacích, kdy jedna hodnota z druhé vyplývá,
nejčastěji v časové posloupnosti (vývoj kurzu české koruny k euru, vývoj hrubého domácího produktu jedné či
více zemí)
Graf kruhový se používá tehdy, jestliže součet všech zobrazovaných hodnot dává 100% (výsledky voleb, věkové
složení obyvatelstva, rozložení hrubého domácího produktu)
Je tedy špatné použití grafu, jestliže pro zobrazení růstu inflace žák zvolí sloupcový graf, pro znázornění
srovnání míry nezaměstnanosti v zemích EU zvolí graf spojnicový a pro znázornění preferencí jedné politické
strany ve všech krajích ČR vybere graf kruhový.
Úlohy a projekty
Tabulkové procesory
•
elektronická žákovská knížka (počítání průměrů známek, odhadů, jakou známku dostat, aby „vyšla“ dvojka
na vysvědčení)
•
nakupujeme (nákupní košík, faktura, účtenka)
•
spoříme (úroky, porovnání služeb bank)
•
domácí úkol z matematiky, fyziky (vzorečky)
•
jubilant (kolik je mi dní, sekund)
•
zpracování údajů získaných z Internetu (zeměpisných, demografických, statistických)
•
porovnání tarifů služeb (elektřina, telefon, mobil)
•
zpracování sportovních ligových výsledků
•
výplatní páska zaměstnance, daňové přiznání
•
zpracování ankety, průzkumu
•
finanční rozvaha podnikatele, systém hodnocení zam.
•
základy teorie náhodných čísel - výzkum
Databáze
•
inventář
•
knihovna
•
videopůjčovna
•
internetový obchod
•
realitní kancelář
•
malá firma
obr. - projekt Jubilant

