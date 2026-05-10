---
title: "zaverecna_prace.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomka/zdroje/cs zdroje/zaverecna_prace.pdf"
date: 2010-01-31
type: PDF (text-based)
---

Mendelova zemědělská a lesnická univerzita v Brně
Provozně ekonomická fakulta

Internacionalizace a lokalizace
softwaru
Bakalářská práce

Vedoucí práce:

Petr Pinkas

Ing. Roman Malo, Ph.D.

Brno, 2009

Děkuji Ing. Romanu Malovi, Ph.D., za vedení této bakalářské práce, za cenné
rady a připomínky, dále děkuji Ing. Tomáši Hoferovi za informace z praxe a z řízení
lokalizací pro některé části práce, Václavu Mikešovi a celému oddělení lokalizací společnosti AVG Technologies za jejich poznatky z praxe. Také děkuji Doc. Ing. Jiřímu
Rybičkovi, Dr., za jeho předpřipravený styl k psaní závěrečných prací a Ing. Janu
Přichystalovi, Ph.D., za aplikaci TEXonWeb, ve které tato práce vznikla.

Prohlašuji, že jsem tuto práci vyřešil samostatně s využitím literatury a zdrojů
uvedených v seznamu.

V Brně dne 25. května 2009

....................................................

4

Abstract
Pinkas, P. Software Internacionalization and Localization. Bachelor thesis. Brno
2009.
This thesis describes and evaluates the software localization process implemented by Zoner Software, a. s. Described herein are the tools used for professional
translations, as well as the project management and financial assessment components of localization projects. Part of this thesis is also the creation of an automated
software tool for translators, which simplifies the translation and the creation of
DTD for importing source files into the translation tool.
Keywords
internacionalization, localization, translation memory, alignment, terminology, Trados, XML, DTD

Abstrakt
Pinkas, P. Internacionalizace a lokalizace softwaru. Bakalářská práce. Brno 2009.
Práce popisuje a hodnotí zavedení lokalizací softwaru ve firmě Zoner Software, a. s. Popisuje podpůrné nástroje pro tvorbu profesionálních překladů, vymezuje
řízení a ekonomické zhodnocení lokalizací. Součástí práce je také vytvoření automatizovaného softwarového nástroje pro usnadnění procesu překladatelům a vytvoření
DTD pro import zdrojových souborů do nástroje pro překlad.
Klíčová slova
internacionalizace, lokalizace, překladová paměť, srovnání, terminologie, Trados,
XML, DTD

OBSAH

5

Obsah
1 Úvod a cíl práce
1.1 Úvod práce . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
1.2 Cíl práce . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

7
7
7

2 Analýza současného stavu v oblasti lokalizace a internacionalizace
software
9
2.1 Globalizace, internacionalizace, lokalizace . . . . . . . . . . . . . . . . 9
2.1.1 Globalizace . . . . . . . . . . . . . . . . . . . . . . . . . . . . 9
2.1.2 Internacionalizace . . . . . . . . . . . . . . . . . . . . . . . . . 10
2.1.3 Lokalizace . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 10
2.2 Nástroje pro lokalizace . . . . . . . . . . . . . . . . . . . . . . . . . . 13
2.2.1 Translation Memory – Překladová paměť . . . . . . . . . . . . 13
2.2.2 Text Memory – Textová paměť . . . . . . . . . . . . . . . . . 14
2.2.3 Machine Translation – Strojový překlad . . . . . . . . . . . . 15
2.2.4 Alignment – Srovnání . . . . . . . . . . . . . . . . . . . . . . . 16
2.2.5 Současné softwarové nástroje pro lokalizace . . . . . . . . . . . 16
2.2.6 Trados . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
2.2.7 Alchemy Catalyst . . . . . . . . . . . . . . . . . . . . . . . . . 17
2.2.8 Systran . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
2.3 Řízení lokalizací . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
2.3.1 Rozhodování . . . . . . . . . . . . . . . . . . . . . . . . . . . 19
2.3.2 Lokalizace řízené interním překladatelem . . . . . . . . . . . . 20
2.3.3 Lokalizace řízené vlastním distributorem . . . . . . . . . . . . 20
2.3.4 Lokalizace řízené externí agenturou . . . . . . . . . . . . . . . 20
2.4 Manažer lokalizací a jeho postavení ve firmě . . . . . . . . . . . . . . 20
2.4.1 Vlastnosti manažera lokalizací . . . . . . . . . . . . . . . . . . 21
2.4.2 Příklad samostatného oddělení lokalizací . . . . . . . . . . . . 21
3 Metodika a postupy
3.1 Softwarový nástroj . . . . . . . . . . . . . . . . . . . . . . . . . . . .
3.1.1 Použité programové vybavení . . . . . . . . . . . . . . . . . .
3.2 Ekonomické zhodnocení . . . . . . . . . . . . . . . . . . . . . . . . .
3.2.1 Případová firma . . . . . . . . . . . . . . . . . . . . . . . . . .

23
23
23
23
23

OBSAH

6

4 Vlastní práce
4.1 Ekonomické zhodnocení lokalizací . . . . . . . . . . . . . . . . . . . .
4.1.1 Nákladová stránka lokalizací . . . . . . . . . . . . . . . . . . .
4.1.2 Vysvětlení některých nákladových položek . . . . . . . . . . .
4.1.3 Výnosová stránka a přínosy lokalizací . . . . . . . . . . . . . .
4.1.4 Doba návratnosti investice . . . . . . . . . . . . . . . . . . . .
4.2 Softwarový nástroj pro podporu lokalizací . . . . . . . . . . . . . . .
4.2.1 Rozhraní pro práci se soubory . . . . . . . . . . . . . . . . . .
4.2.2 Glosář . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
4.2.3 Algoritmus označování nalezených výskytů . . . . . . . . . . .
4.2.4 DTD . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

25
25
25
27
28
29
30
31
31
31
33

5 Závěr

36

6 Literatura

37

Přílohy

38

A DTD pro import z XML zdrojových souborů webových stránek

39

1

ÚVOD A CÍL PRÁCE

1

Úvod a cíl práce

1.1

Úvod práce

7

V dnešním moderním a prakticky neomezeném trhu softwaru na světě se snaží firmy
rozrůstat na více než jen domácí trhy. Snaží se působit celosvětově a své produkty,
webové prezentace, služby a ostatní dokumenty mít přístupné a srozumitelné pro
co nejvíce lidí. Mnoho společností si však stále myslí, že mít připraven produkt
pro celosvětové působení znamená být připraven pro anglicky mluvící trh. Často
si ale neuvědomují, že mnoho jejich cílových zákazníků umí anglicky velmi málo
nebo vůbec a nejsou schopni produkt používat, což často vede k tomu, že se poohlédnou po jiném, který je dostupný v jejich rodném jazyce. Problém nemusí mít
pouze s jazykem, ale i s použitým uživatelským rozhraním, symbolikou, ergonomií,
barvami a dalšími aspekty, které ovlivňují vnímání a chápání lidí v odlišných zemích
a kulturách. Proces lokalizace a internacionalizace bývá i v dnešní době ještě jedním
z podceňovaných a společnosti tak přicházejí o nemalé počty svých potenciálních
uživatelů a tím pádem i o případné zisky.
Je tudíž nasnadě se tímto procesem více zabývat, zahrnovat jej do projektových
plánů, nákladů, rozpočtů firmy a počítat s ním také jako s přínosem a konkurenční
výhodou před ostatními. Navíc tento proces může a většinou také vede k rozvoji
prodejních kanálů a k mnohem větším úspěchům na ostatních celosvětových trzích,
což samozřejmě vede ke zvyšování jednak povědomí o značce či produktu, jednak
k většímu počtu uživatelů a z toho plynoucích větších příjmů. S těmito rostou samozřejmě i nároky na podporu a koordinaci.

1.2

Cíl práce

Cílem této práce je vytvoření podpůrného softwarového nástroje pro podporu lokalizačního procesu, který by měl usnadnit a zefektivnit práci překladatele. Daný
nástroj by měl překladateli zpříjemnit práci tím, že nebude nucen při překládání neustále sledovat dané terminologie, které se nepřekládají, a bude se moci soustředit
pouze na překlad samotný. Takto koncipovaný nástroj byl vymyšlen po diskuzích
s managery lokalizací a samotnými překladateli, kterým tento nástroj v současných
překladatelských softwarových programech chybí. Kromě tohoto budou navrženy
a vytvořeny dokumenty DTD pro popis struktury XML zdrojových souborů, které
se mají vložit a překládat v nástroji pro překladatele, přičemž tyto soubory budou
již upraveny právě daným softwarovým nástrojem.

1.2

Cíl práce

8

Kromě vytvoření takového nástroje je cílem také definice a vymezení základních možností a obecných východisek lokalizace. Dále je potřeba popsat a zohlednit
několik okolností, přičemž z praktického hlediska jde zejména o popsání samotného
procesu řízení lokalizací a projektového řízení, kdo a jak jej řídí, jaké má kompetence
a jakou má pozici ve firmě a jaké má odpovědnosti. Z ekonomického hlediska půjde
o vyčíslení nákladů, které jsou spojeny s lokalizacemi, a o změření doby návratnosti
investice celého procesu pro obhájení důležitosti a významnosti procesu. Budou také
vysvětleny jednotlivé terminologie běžně používané v této oblasti spolu se současným programovým vybavením a porovnáním možností, připadajících na jednotlivé
použití tohoto vybavení.

2

ANALÝZA SOUČASNÉHO STAVU V OBLASTI LOKALIZACE A INTERNACIONALIZACE SOFT-

9

WARE

2

Analýza současného stavu v oblasti lokalizace a internacionalizace software

2.1

Globalizace, internacionalizace, lokalizace

V této práci je nutné rozlišovat pojmy lokalizace, internacionalizace a globalizace.
Tyto pojmy mají sice mnoho společného, ale nelze je zaměňovat nebo je považovat za
zcela identické. Každý pojem má své určité meze a odlišnosti od ostatních, a proto je
třeba je vysvětlit a popsat. Zdrojů, názorů a definic není mnoho, jelikož v této oblasti
ještě nebylo zpracováno dostatečné množství dokumentací, úvah, prací či knih. Proto
není cílem těchto popisů přesné vymezení a určení těchto pojmů, ale spíše nabytí
představy o jejich rozsahu.
Je také nutné podotknout, že následující pojmy se vztahují k lokalizacím softwaru, nikoliv ke globální ekonomice, politice, historii a celosvětové problematice.
V těchto souvislostech by tyto pojmy nabývaly poněkud odlišných významů.
2.1.1

Globalizace

Globalizaci1 zde nelze chápat ve smyslu politickém či geopolitickém, který se zabývá
globalizací obchodu a ekonomiky jako ekonomické evoluce. Dále ji také nelze chápat
ve smyslu globalizace podniku, jakožto samotné zakládání poboček po celém světě
a ani jako kulturní globalizaci. (Esselink, 2000, s. 4)
Globalizaci lze popsat dle organizace LISA (Localisation Industry Standards
Association), která ji definuje jako obchodní rozhodnutí a aktivity, které dělají organizaci skutečně mezinárodní v její celé sféře působnosti. Je to taková transformace
obchodu a procesů, aby bez rozdílu jazyka, země či kultury podpořila zákazníky po
celém světě. (Lommel, 2007, s. 1)
Dalo by se říct, že globalizace je celopodnikový proces, který ovlivňuje nejen
překládání a úpravu produktů a služeb do daných jazyků, ale sahá mnohem dál
a hlouběji do firmy a proplétá se v různých podobách napříč organizací. Dotýká se
i firemní kultury, přístupu zaměstnanců k jednotlivým úkolům, obchodních jednání,
nutí zaměstnance k sebevzdělávání (ať už jazykovému nebo studii cizích kultur pro
úspěšná vyjednávání), zástupci firem jsou vysílání na obchodní cesty do zahraničí,
navazují se styky s různými distributory a prodejci softwaru.
1

Někdy také označována jako g11n, kde číslo 11 je počet písmen mezi „gÿ a „nÿ v anglickém
ekvivalentu tohoto slova.

2.1

Globalizace, internacionalizace, lokalizace

2.1.2

10

Internacionalizace

Je-li potřeba vyvíjet vícejazyčné produkty a weby, je nutné postupovat nebo změnit
software takovým způsobem, který usnadní a umožní překlad do ostatních jazyků.
Internacionalizaci2 lze popsat jako proces, který slouží k odstranění jazykově
a kulturně závislých informací z produktu během jeho vývoje tak, aby mohl být následně efektivně a snadno lokalizován. Tento proces předchází procesu lokalizace a je
na technické úrovni.
Neméně důležitou a nedílnou částí je také oddělení textů od vlastního zdrojového kódu. Toto je nezbytné pro překladatele, kteří by mohli zdrojový kód změnit
nebo překládat zbytečné řetězce, což by se samozřejmě projevilo ve výsledné ceně
a délce celé lokalizace. Výsledkem jsou takzvané zdrojové soubory nebo texty, které
obsahují pouze přeložitelné části, nikoliv zdrojový kód. (Esselink, 2000, s. 2)
Je třeba mít na paměti, že je nutné pečlivě vybírat nejvhodnější formát zdrojových textů s ohledem na nákladnost řešení a také rozsah změn ve způsobu práce
s texty, který byl zaveden doposud tak, aby co nejméně narušil současný stav nebo
ten, který existoval před zavedením lokalizačního procesu. Nutné je také určit způsob kontroly kvality zdrojových textů, protože platí pravidlo, že přeložené texty jsou
tak kvalitní, jak kvalitní jsou texty zdrojové.
Komponenty aplikací, které se většinou separují do zdrojových textů pro následný překlad jsou zejména:
• menu,
• dialogy,
• různé aplikační zprávy,
• nápovědy a tutoriály,
• grafika,
• toolbary,
• konstanty,
• chybová hlášení.
2.1.3

Lokalizace

Lokalizace3 je nedílnou součástí globalizace a následuje za procesem internacionalizace. Součástí tohoto procesu je samozřejmě vlastní překlad textů. Dle organizace
2

Někdy také označována jako i18n, kde číslo 18 je počet písmen mezi „iÿ a „nÿ v anglickém
ekvivalentu tohoto slova. (W3C, 2006)
3
Někdy také označována jako l10n, kde číslo 10 je počet písmen mezi „lÿ a „nÿ v anglickém
ekvivalentu tohoto slova. (W3C, 2006)

2.1

Globalizace, internacionalizace, lokalizace

11

LISA lze lokalizaci popsat jako proces úpravy produktů nebo služeb, který vede ku
prospěchu a výhodám na rozdílných (mezinárodních) trzích. (Lommel, 2007, s. 11)
V tomto procesu se nejedná pouze o překlad produktu, ale také o následující:
• nastavení rozměrů dialogů pro případy, že je přeložený text delší,
• kulturní a místní odlišnosti, které vyžadují úpravu ikon, kurzorů, barev, navigací (logiky posloupnosti příkazů a ergonomie) nebo symbolů (například manuál
k instalaci tiskárny, kde jedním z prvních kroků je zapojení tiskárny do zásuvky
a právě zásuvky jsou v jednotlivých státech odlišné, stejně tak napětí v nich),
• odlišnosti jako formáty telefonních čísel, adresy, data, číslice, oddělovače, oslovení,
• politické a ekonomické záležitosti typu nemožnost platit kreditní kartou online
v některých zemích, pomalé nebo omezené připojení k internetu v rozvojových
zemích, zakázané symboly (např. postavení muže a ženy v arabských zemích),
• právní záležitosti,
• rozdílné rozložení kláves a použití klávesnic,
• jazyky psané z prava do leva (hebrejština, arabština) nebo speciální znaky některých jazyků (norština, švédština).
Úkolem lokalizace není jen překlad a úprava produktu, ale také způsob, jakým
je produkt prodáván, promován, pozicován, prezentován, jaký má design nebo retailový obal pro patřičný trh, jakou má technickou i obchodní podporu, jak jsou
o prodejích zhotovovány reporty atd. Jakékoliv nedostatky nedodržené důslednou
lokalizací mohou zákazníka odradit od koupě nebo užití daného produktu či služby.
Dále je také na místě podotknout, že většina softwaru (dle Esselinka až 80 %) je lokalizována do ostatních jazyků z angličtiny a pokud ne, tak je většina prvně přeložena
do angličtiny a tento jazyk je brán jako zdrojový pro ostatní překlady.
Z výše uvedených a popsaných pojmů vyplývá, že provede-li se s daným produktem, službou, či webovou prezentací internacionalizace, lze provádět lokalizaci.
Po těchto dvou procesech je produkt připraven sloužit širšímu okruhu zákazníků.
Jestliže jsou tyto procesy splněny a jsou aplikovány na kompletní portfolia produktů
firmy, jsou akceptovány zaměstnanci a vedením firmy při všech výše uvedených krocích, pak lze hovořit o globalizaci. Nejdůležitějším úkolem je tvořit takové produkty,
které jsou neutrální a nezávislé na kultuře.
Pro praktickou ukázku lokalizace produktu lze použít následující diagram, který
byl aplikován na tvorbu nápověd pro daný produkt:

2.1

Globalizace, internacionalizace, lokalizace

Obr. 1: Diagram tvorby nápověd

12

2.2

Nástroje pro lokalizace

2.2

13

Nástroje pro lokalizace

V této kapitole je důležité popsat, jaké nástroje se pro lokalizace používají a definovat základní termíny, které se v této oblasti používají a které jsou rozhodující
pro zvážení výběru adekvátního nástroje. Je zbytečné využívat nástroj, který má
nedostatečné nebo naopak nadbytečné možnosti, které by byly nevyužity.
Nejdříve je třeba si uvědomit, že ať je software pro podporu lokalizací sebelepší
a sebesofistikovanější, nikdy nemůže nahradit lidský překlad, který provede překladatel. Tyto nástroje pouze pomáhají zefektivnit proces překladů, následných kontrol
a korektur (reviews), udržování slovníků, terminologií, proces lokalizace velmi urychlují, a tím šetří kapacity, čas a náklady.
Od 90. let minulého tisíciletí se stávají počítačové překladatelské nástroje nedílnou a nezbytnou součástí lokalizačního procesu. Například nástroje využívající
Translation Memory se velmi osvědčily společnostem, které pracovaly na velkých
lokalizačních projektech nebo využívaly již někdy přeložené materiály. Následující
kapitoly a jejich názvy jsou uváděny v anglickém jazyce s určitým českým ekvivalentem, který se pomalu dostává do povědomí překladatelů a lokalizátorů. Tyto pojmy
se však v praxi většinou používají v původním, tedy anglickém jazyce, proto jsou
uvedeny oba dva tyto výrazy.
2.2.1

Translation Memory – Překladová paměť

V současné době se software, web (jeho obsahová i designová část), různé marketingové materiály a další často a rychle mění. V případě obsahu webu prakticky
denně nebo týdně (tiskové zprávy, novinky, aktuality) a v případě softwaru se u nových verzí přidává nebo mění jen několik slov, v případě přidávání funkcionalit
se může jednat o větší celky nových textů (s přidáním funkcionality souvisí také
rozšíření nápověd, často kladených otázek, tutoriálů, manuálů a podobně). Nemělo
by smysl kontrolovat opět všechny texty, zda je potřeba je přeložit nebo ne, provádět kontroly kvality a řídit proces lokalizací celý znovu. Vyvstává zde otázka,
jakým způsobem využít předchozích textů, přeložených pomocí lokalizačních produktů k usnadnění překladů a k úspoře překládání zbytečných vět či řetězců. Pokud
se totiž využije překladů z již přeložených verzí, lze tím mnoho získat. Na to také
mysleli tvůrci nástrojů pro lokalizace a vymysleli a zavedli Translation Memory (dále
jen TM). TM využívá předchozích překladů jak nejvíce je to možné. (Esselink, 2000)

2.2

Nástroje pro lokalizace

14

TM je databáze, která uchovává segmenty4 již v minulosti přeložené, vytváří
tak jakousi paměť překladů. Jedná se o slova, fráze, slovní spojení a ostatní větné
celky, které někdy byly přeloženy překladatelem, nikoliv strojem, ale živou osobou.
TM pracuje takovým způsobem, že porovnává segmenty v databázi se segmenty ve
zdrojovém souboru. Pokud je nalezena shoda, TM navrhne akci překladu a tak dává
překladateli možnost soustředit se z větší části pouze na nový text. (Lommel, 2007)
V praxi se běžně používá export stringů do XML5 , čehož využívá většina lokalizačního softwaru pro následné překlady. Pro TM se využívá xml:tm6 , což vede
k vysvětlení dalšího, ale již méně užívaného a specifičtějšího pojmu Text Memory.
2.2.2

Text Memory – Textová paměť

Jedná se o XML standard, který se skládá ze dvou komponent:
• Author Memory – je segmentovaný XML dokument, který obsahuje historii
všech segmentů a revize.
• Translation Memory – jakmile je xml:tm dokument jmenného prostoru7 připraven k překladu, jmenný prostor určí text, který má být přeložen. xml:tm
umožňuje lepší porovnávání překladů než standardní TM technologie například
pomocí:
– přesné shody (Exact Matching),
– fuzzy shody (Fuzzy Matching), tedy na základě podobné shody s dříve
přeloženým textem,
– nepřeložitelný text (Non-Translatable Text), což jsou například numerické,
alfanumerické znaky nebo měrné jednotky, které jsou během překládání
označeny za nepřeložitelné a snižují počet slov potřebných k překladu již
při kalkulacích.
Na závěr je nutné dodat, že xml:tm bylo schváleno jako oficiální standard pro
oblast globalizace v únoru roku 2007 a je navrženo tak, aby bylo kompatibilní s ji4
Určitý element textu, který se považuje za nejmenší přeložitelnou jednotku. Zpravidla to bývají
věty, nadpisy, výčty nebo položky. Většinou se segmentuje, když je nalezen znak odstavce, konec
věty (tečka, po které následuje mezera), konec buňky v tabulce, konec výčtu.
5
Extensible Markup Language – obecný značkovací jazyk, který není majetkem žádného samostatného komerčního subjektu. Byl vyvinut podle zkušeností s předchozími značkovacími jazyky
a standardizován konsorciem W3C. Umožňuje vytváření konkrétních značkovacích jazyků pro různé
účely a široké spektrum různých typů dat. (Bradley, 2000)
6
XML-based Text Memory.
7
Jmenný prostor (namespace) je jakási pomyslná množina jmen, které jsou si významově blízké.
Jmenný prostor je určen URI identifikátorem, který je globálně jedinečný. (Young, 2006)

2.2

Nástroje pro lokalizace

15

nými standardy, které se dříve používaly a používají ještě dnes v této oblasti. (LISA,
2007)
Některé nástroje jsou schopné podávat statistiky typu:
• počet segmentů,
• celkový počet slov,
• počet opakovaných výskytů slov,
• plná shoda (100% shoda),
• různé úrovně fuzzy shod (50–99% shody),
• žádná shoda (nové slovo nebo segment).
Co se týče celkového počtu slov, tak tato statistika je velmi důležitá pro kalkulace a celkovou cenu překladů. Dalším důležitých ukazatelem je statistika žádné
shody. Toto jsou úplně nové segmenty, které je potřeba přeložit bez pomoci TM
a platí, že čím více je nových segmentů, tím je překlad dražší. Naopak čím větší je
procento shody s předchozími překlady, tím se celková cena snižuje.
2.2.3

Machine Translation – Strojový překlad

Tento pojem znamená automatický překlad z jednoho jazyka do jazyka druhého bez
pomoci a zásahu člověka. Nejedná se zde však například o slovníky, kde se překládají
jednotlivá slova nebo maximálně jednoduchá spojení či fráze. U Machine Translation
(dále jen MT) se překládají celé věty či souvětí a navíc slovník nedá uživateli na
výběr, který překlad se hodí pro tu kterou situaci. MT je velmi vhodný pro nový
text, který nebyl nikdy dříve překládán.
Je samozřejmé, že MT nedokáže nahradit lidského překladatele a výsledky bývají většinou takového charakteru, že pouze usnadňují překladateli práci a umožňují
mu vybrat si z několika variant, které následně upraví a použije. Přestože MT systémy pracují na gramatické analýze (parsování) zdrojového textu a následně na základě tohoto na vygenerování překladu, nejsou schopny přesně přeložit dané zdroje
tak, jak by je přeložil překladatel. (Dillinger a Lommel, 2009)
Příkladem MT může být například překladač8 od společnosti Google, který překládá webové stránky nebo vybraný text, který uživatel potřebuje přeložit. V tomto
případě lze mluvit spíše o pochopení než o přeložení textu. Pokud uživatel vůbec nezná daný jazyk a chtěl by alespoň rámcově pochopit o co na dané stránce nebo v daném textu jde, může mu tento překladatel pomoci. Nelze však mluvit o doslovném
8

Překladač je možné najít na http://translate.google.com/

2.2

Nástroje pro lokalizace

16

a gramaticky korektním překladu, který by se dal využít pro překlady komerčních
aplikací.
2.2.4

Alignment – Srovnání

Lze říci, že alignment je možné použít, pokud není z nějakého důvodu k dispozici TM,
ale jsou k dispozici zdrojové soubory a k nim existující překlady. Slouží k porovnání
překladů, které vznikly v minulosti. Alignment se používá zejména tehdy, když jsou
některé překlady hotové, ale nejsou vytvořeny pomocí TM. To znamená, že nebyl
použit lokalizační software, ale je potřeba a vůle těchto překladů využít. Poté, co
je proveden alignment, převedeny a porovnány zdrojové a cílové texty, vzniká TM.
Může se jednat o časově náročný proces, který navíc vyžaduje vysokou pozornost
a účast překladatele. (Esselink, 2000)
Jako příklad lze uvést následující situaci, kdy existují anglické texty z webové
prezentace a k nim italský překlad. Plán do budoucna je využívat TM pro další
italské překlady. Nyní nastává situace, kdy je třeba aplikovat alignment, který zároveň připraví TM, který byl požadován. Na alignmentu je nutná účast překladatele
a technicky zdatné osoby, která umí pracovat s daným překladatelským softwarem.
Může se jednat o časově náročný proces, obzvlášť při velkých objemech překládaných
textů.
Je zřejmé, že většina lokalizačních softwarů, alespoň těch nejpoužívanějších
a nejrozšířenějších, by měla tuto službu podporovat a mít ji v sobě zabudovanou.
2.2.5

Současné softwarové nástroje pro lokalizace

Tato část by měla vymezit, uvést a stručně popsát jednotlivé v dnešní praxi běžné
a nejvíce používané nástroje, pomocí kterých se provádí lokalizace webů, produktů,
softwaru, knih, marketingových materiálů, dokumentů, manuálů, nápověd atp.
2.2.6

Trados

Zřejmě nejpoužívanější produkt pro lokalizace je software Trados (webová prezentace říká, že je to standard v oboru a praxe to potvrzuje), který je výtvorem společnosti SDL. Tato společnost za léta její působnosti koupila mnoho lokalizačních
firem a produktů, jako jsou třeba Passolo (nyní SDL Passolo), Idiom Technologies,
Lingua Franca, Alpnet a další. Jedná se o největší společnost světa, která se zabývá
touto problematikou. Mezi nejvýznamnější klienty SDL, kteří používají její produkty

2.2

Nástroje pro lokalizace

17

patří například Microsoft, Canon, Hewlett-Packard, NetApp, Oracle, Siemens, Sun
Microsystem, Philips, ale i české společnosti AVG Technologies a Zoner Sotware.
Je také důležité si uvědomit, že většina současných překladatelů a překladatelských agentur pracuje s moderním softwarovým vybavením, ve kterém nechybí
produkty společnosti SDL a pokud si firma vybírá, kterou agenturu osloví, zjistí,
že většina z nich pracuje právě s Tradosem a je pro ně jednak jednodušší přebírat
TM, vytvořené v Tradosu a jednak v těchto formátech a databázích posléze provádět korektury a opravy. Toto se většinou týká firem, které mají interní překladatele
nebo specialisty, kteří vytvářejí jednotlivé jazykové varianty (stačí jednu nebo dvě)
a chtějí rozšířit své portfolio jazyků.
Kromě TM (v Tradosu se vyskytuje pod pojmem Translator’s Workbench)
a Alignment utility, obsahuje Trados také integrované nástroje pro projektové řízení a nástroje pro správu terminologií. Terminologie je dalo by se říci databáze slov
a pojmů, kde jsou tyto pojmy přesně vysvětleny a většinou se nepřekládají, pokud to
význam a daný jazyk nevyžadují (zde je nutno odkázat na kapitolu Lokalizace, kde
se hovoří o kulturních odlišnostech jednotlivých zemí). Kromě pojmu Terminologie
se často použivá i pojem glosář. Produkty jsou nabízeny jak pro koncové stanice,
tak pro nasazení na server. Serverová řešení jsou podstatně dražší.
2.2.7

Alchemy Catalyst

Firma Alchemy Software Development působí na trhu lokalizací od roku 2000 a její
produkt Alchemy Catalyst 7.0 by se dal zařadit také do těch rozšířenějších. Jelikož je
však produkt Trados více používaný, má produkt Alchemy Catalyst komponentu9 ,
která synchronizuje tyto dva produkty. Je tomu tak především proto, že firma SDL
uvolnila SDK10 a umožňuje tak firmám implementovat do svých produktů určité
části a funkčnosti produktů Trados.
2.2.8

Systran

Tato společnost byla založena již roku 1968 a roku 2000 vstoupila na burzu. Jedná se
o jednu z nejstarších společností, která vyvíjí lokalizační produkty vůbec. Proslavila
se především prací s Ministerstvem obrany Spojených států amerických a Evropskou komisí. Systran má k dispozici hned několik produktů v mnoha verzích, od
webových překladačů, přes překladače dokumentů kancelářských aplikací až po kla9
10

Alchemy TRADOS Component (v2)
Software development kit.

2.3

Řízení lokalizací

18

sické lokalizační produkty, které pomáhají překládat software. Kromě desktopových
a serverových řešení jsou k dispozici i online aplikace a překladač, který je možné
spustit na mobilních telefonech v prostředí Windows Mobile.
Kromě výše uvedených produktů existuje ještě celá řada dalších, které už však
nejsou považovány za tak rozšířené a jejich použití může vycházet z konkrétních
požadavků firem, které například nemají dostatek finančních prostředků na použití
placených produktů nebo kvůli specifickým požadavkům. Lze jmenovat například
produkty Transit, Déjà Vu X, Visual Localize, Localizer, Wordfast Translation Studio, OmegaT a další.
Pro zmíněné firmy, které nemají dostatek prostředků na koupi takovýchto produktů jsou k dispozici i některé neplacené produkty, které však většinou nebývají
kompatibilní s produkty překladatelů a bývají pro větší množství dokumentů na
překlad nedostačující.
Vedle produktů existují samozřejmě také lokalizační služby, které celý proces
outsourcují. Mezi ně by se daly zařadit například služby společností IBM, EQHO,
Argos Translations, Lionbridge a další.

2.3

Řízení lokalizací

Proces lokalizace není jednoduchý a vždy jednoznačný a skládá se z více fází. Tyto
fáze lze rozdělit například do těchto dílčích procesů:
• obchodní rozhodování (obecně o možnostech, přínosech a důležitosti lokalizace),
• plánování a rozpočtování lokalizací (které jazyky budou zvoleny, kdy, co a za
kolik se bude lokalizovat),
• testování připravenosti na lokalizace (zda současný stav textů a produktů je
vhodný k překladu, pokud ne, je třeba tak učinit),
• výběr dodavatele překladů a jazykových revizí, jejich řízení či spoluřízení,
• výběr nástroje (nástrojů) pro zpracování obsahu nápovědy, dokumentace a tutoriálů s ohledem na dlouhodobou návratnost,
• příprava zdrojových souborů, exportování řetězců z webů, dokumentů atd.
• zaslání těchto lokalizačnímu partnerovi a následná kontrola jeho práce,
• management a dohled na dodavatele překladů a jazykových revizí – dohled na
včasnost a kvalitu dodávek, monitorování průběhu prací, plánovaní zdrojů pro
připravované projekty,

2.3

Řízení lokalizací

19

• testování funkčnosti a kvality lokalizovaných verzí – revize obsahu po stránce
jazykové kvality, kontrola GUI11 z pohledu uživatele – ořezy a přetékání textu,
kontrola zobrazování rozšířených znaků v daném jazyce a další kontroly,
• beta testování,
• vypuštění lokalizovaného produktu (běžně známo pod pojmem release),
• sběr ohlášených chyb (bugreporting – součástí je také zvolení vhodného systému12 na hlášení těchto chyb) a další testování (jako u běžného životního cyklu
programu).
2.3.1

Rozhodování

Zde je na místě upozornit, že každé takovéto rozhodování a proces probíhá pro
každý jazyk zvlášť, jelikož cena překladu každého jazyku je jiná, časová náročnost
provedení lokalizace je různě velká, ne každá překladatelská agentura dělá všechny
jazyky, do kterých je potřeba překládat. Také se od sebe liší technické požadavky
na jednotlivé jazyky. Je nutné každý jazyk pečlivě zvážit a stanovit si priority a postupy. Například, že nejvíce podpořit potřebují prodeje v Itálii, takže italština bude
mít nejvyšší prioritu a na tento překlad se bude vynakládat nejvíce prostředků jak
finančních, tak z oblasti lidských zdrojů a navíc bez této lokalizace by bylo složité,
ne-li nemožné, rozvíjet tamní aktivity.
Rozhodovat se lze také na základě doporučení místního zastoupení (distributoři,
partneři, reselleři, pobočky) nebo pouze na základě analýzy prodejních výsledků
podle kanálů s ohledem na předchozí výsledky lokalizací. Aby měla lokalizace ten
správný efekt a dopad, je nutné lokalizovanou verzi správně promovat, podporovat
prodej obchodními kanály, navazovat obchodní styky s místními prodejci (výstavy,
konference, workshopy), uzavírat kontrakty například na základě spojování různých
výrobků za účelem prodeje jednoho balíku (tzv. bundling).
Důležité je rozhodnout a určit, kdo bude provádět lokalizace. Většinou se vybírá
mezi následujícími třemi variantami:
• interní překladatel nebo tým překladatelů (zaměstnanci firmy),
• lokalizaci, kterou řídí některý z distributorů (většinou v dané zemi, pro kterou
se lokalizuje),
• externí agentura.
11
12

Grafické uživatelské rozhraní.
Například produkty Bugzilla, Unfuddle, Mantis, FogBugz a mnoho dalších.

2.4

Manažer lokalizací a jeho postavení ve firmě

2.3.2

20

Lokalizace řízené interním překladatelem

Výhoda interního překladatele je rychlá flexibilita na případné změny, větší rychlost
celého procesu a možnost okamžité interakce. Snižují se i náklady s tím spojené
(interní překladatelé bývají více obeznámeni s používanými terminologiemi a nejsou
tak nákladní jako profesionální překladatelské agentury).
2.3.3

Lokalizace řízené vlastním distributorem

Případ řízení lokalizací vlastním distributorem přináší výhodu v tom, že se prakticky
o celém procesu pouze vyhotovují reporty, které se sledují, řízení se deleguje na
distributora a také je možné zvolení strategie spolupodílení se na nákladech celého
procesu. Toto řešení je poměrně výhodné i z finančního úhlu pohledu.
2.3.4

Lokalizace řízené externí agenturou

V posledním případě kromě externího překladatele (nebo týmu překladatelů) je potřeba rozhodnout také o tom, zda bude ponechán i celý proces řízení na externí
agentuře nebo se v něm bude firma nějakým způsobem podílet a pokud ano, tak
na jaké bázi. Ideální je spolupodílení se na řízení z větší části a tím zajištění větší
kontroly nad dodržováním plánů, časových horizontů a možnosti vzniku neočekávaných prodlení nebo problémů. Tato varianta se volí také tehdy, není-li firma schopna
zajistit koordinaci vlastními silami. Externí agentura má většinou dobré kontakty
s lokalizačními agenturami, má zkušenosti s řízením, případnými riziky a odhady
průběhu a nákladů celého procesu. Tato varianta je sice nejdražší, ale vysoce kvalitní.

2.4

Manažer lokalizací a jeho postavení ve firmě

V případě, že se společnost rozhodne pro některou z předchozích variant, je zapotřebí někoho, kdo tento proces bude mít na starosti nerozhodno na míře řízení
lokalizací. Pozice takovéhoto manažera by měla vycházet jednak ze struktury dané
firmy a jednak z míry participace na daném řízení lokalizací. Pokud manažer pouze
kontroluje průběh celého procesu a případně reportuje příslušné události ostatním,
bude jeho zařazení a pozice jiná než v případě kompletního řízení včetně plánování,
alokace zdrojů, projektového řízení, kontrolingu a dalších nezbytných činností.

2.4

Manažer lokalizací a jeho postavení ve firmě

2.4.1

21

Vlastnosti manažera lokalizací

Lze jmenovat několik důležitých vlastností, které by měl každý takovýto manažer
mít, aby dobře plnil svoji funkci a roli:
• plánování – nezbytný podklad pro kalkulace a správné rozvržení zdrojů a časových kapacit a požadavků,
• organizace – nutnost organizačních schopností na vyšší než standardní úrovni
kvůli komunikaci s více odděleními, lokalizačními partnery, distributory, interními zaměstnanci, vedením a dalšími zapojenými členy,
• koordinace lidí – v případě, že jsou do projektu zapojení další zaměstnanci,
• komunikace – bez této vlastnosti není lokalizační manažer schopen se obejít,
protože musí jednat se všemi lidmi, do lokalizací zapojených a navíc s lidmi
z rozdílných kultur a zemí,
• technologická zdatnost v oblasti IS/IT,
• flexibilita – praxe ukazuje, že ač jsou projekty naplánovány a nastaveny tak,
aby do sebe vše zapadalo, vždy se stane nějaká neočekáváná skutečnost, která
může zpozdit celý proces a vytvořit jak časová manka, tak další finanční výdaje
a jiné újmy. (Rubric, 2004)
Jelikož by každý takovýto manažer měl správně spolupracovat úzce s několika
odděleními ve firmě (webové, produktové, projektové, vývojové, oddělení podpory,
dokumentací a další), není snadné jej přímo a jednoznačně zařadit do struktury
firmy. Obzvláště do silně strukturované a hierarchicky rozvětvené. Všeobecně je
možné říci, že lokalizační manažer by měl spadat do okolí produktových a projektových manažerů, jelikož tito jsou silně propojeni celou organizací v oblasti procesů
i komunikace. V praxi se takovýmto manažerem většinou stávají právě produktoví
nebo projektoví manažeři a bývá to jeden z jejich dalších úkolů. Zmíněníhodné je,
že ve větších firmách (korporace o více než 200 zaměstnancích) většinou vznikají
samostatná oddělení o několika členech, která řídí lokalizace.
2.4.2

Příklad samostatného oddělení lokalizací

Jako příklad lze použít společnost AVG Technologies, kde existuje právě takovéto
oddělení, které má v současné době tři pracovníky – vedoucí pracovník lokalizací
a dva specialisté lokalizací.
Pracovní náplně jednotlivých členů týmu:

2.4

Manažer lokalizací a jeho postavení ve firmě

22

Vedoucí pracovník
• zajištění chodu celého oddělení,
• odpovědnost za veškeré smlouvy s lokalizačními partnery, subdodavateli, dodavateli nástrojů, atd.
• plánování a alokace zdrojů,
• rozhodování o pracovních postupech a nástrojích, které se užívají a budou užívat,
• zajištění komunikace s vedením včetně reportingu a komunikace s ostatními
odděleními.
První specialista
• specialista na produkt IDIOM, včetně jeho serverového řešení,
• příprava projektů,
• zodpovídání požadavků překladatelů,
• distribuce přeložených částí v rámci firmy do příslušných oddělení.
Druhý specialista
• architekt aplikací, spojených s přípravou segmentů a zdrojových textů, definice
XML struktur,
• úzká spolupráce s vývojovým týmem,
• přispívání a spoluúčast na vytváření interního SVN systému, systému pro kontrolu verzování zdrojových kódů,
• programování skriptů pro převody zdrojových souborů do různých formátů pro
potřeby překladatelských nástrojů a naopak.
Tyto popisy nejsou zcela vyčerpávající a pod každým výčtem se skrývá ještě
několik dalších dílčích činností. Možná zde vyvstává otázka, zda je vůbec nutné takovéto oddělení a pracovníky vytvářet, ale když se vezme v potaz 10 jazykových
mutací webové prezentace a 15 jazykových variant celého produktu v různých verzích, je tato otázka prakticky zodpovězena. S neustálými aktualizacemi veškerých
materiálů a textů k překladu je to obrovský tok dat, které je nutné okamžitě a efektivně překládat a mít k dispozici pro zákazníky, partnery, distributory a ostatní
obchodní zástupce.

3

METODIKA A POSTUPY

3

Metodika a postupy

3.1

Softwarový nástroj

23

Nástroj byl vyvíjen jako webová aplikace z důvodů lehké přenositelnosti a také
z důvodů nasazení do webového redakčního systému firmy. Ten si však firma striktně
řídí sama a převzala si pouze zdrojové soubory aplikace, které si naimplementovala
do svého systému. Aby aplikace mohla pracovat s databází (seznam slov v glosáři),
byl zvolen skriptovací jazyk PHP. Pro ošetření nahrávání souborů na server bylo
využito již hotového řešení, které bylo následně upraveno jak po stránce designu,
aby zapadlo do daného stylu, tak po stránce výpisů a zobrazování souborů. Toto
řešení je chráněno BSD licencí, zdrojový kód je volně šiřitelný a autorem je Petr
Kahoun. Dané řešení je poměrně dost propracované a realizace vlastního nahrávání
by tak byla poněkud neúčelná.
3.1.1

Použité programové vybavení

Aplikace je odladěna pod nejrozšířenějšími prohlížeči Internet Explorer, Firefox,
Opera a Safari. Práce byla vytvořena pod operačním systémem Mac OS X verze
10.5.6. a pro vytvoření databáze bylo využito prostředí dbMan verze 0.37 na školním
serveru Akela, který provozuje Mendelova zemědělská a lesnická univerzita v Brně.
Pro nahrávání zdrojových souborů aplikace byl využit FTP klient Cyberduck a pro
editaci těchto souborů produkt TextMate. Při práci s databázi bylo využito klasického terminálu, který je součástí operačního systému. Pro testování zobrazení
a funkčnosti překladatelského softwaru bylo využito produktu SDL Trados 2007,
který má i firma, která proces lokalizací doporučovala a řídila. Tento produkt také
používají její interní překladatelé. Během několika měsíců vychází nová verze tohoto
produktu, která podporuje více možností a také více formátů zdrojových souborů, se
kterými může pracovat. Pro tvorbu diagramu byl využit produkt společnosti Microsoft – Microsoft Office Visio Professional 2007.

3.2

Ekonomické zhodnocení

3.2.1

Případová firma

Případovou firmou je společnost Zoner Software, a. s., pro kterou bylo v rámci poradenských činností společnosti Ander Lippin, s. r. o., doporučeno zavést překlady
do jiných jazyků. Veškeré poznatky této práce tak vycházejí právě z těchto čin-

3.2

Ekonomické zhodnocení

24

ností. V daném případě se jedná o produkt Zoner Photo Studio ve verzi 11, což je
nástroj pro zpracování digitální fotografie, který je v rámci České republiky velmi
populární, avšak v zahraničí prakticky neznámý. Lokalizace byly součástí zvýšení
povědomí o produktu a zvýšení tržeb v zahraničí.
Při popisu většiny skutečností z praxe byly využity jednak vlastní poznatky,
jednak poznatky lokalizačních expertů a lokalizační agentury. Podklady pro přehled
nákladové stránky lokalizací vychází především z obdržených faktur a ze smluv,
které byly sepsány a označeny za finální. Četné dodatky jednotlivých smluv totiž
většinou cenu a specifika jednotlivých detailů měnily. Proto se vychází vždy z posledního dodatku smlouvy. Veškeré ostatní poznatky vyplynuly z komunikace se všemi
zapojenými subjekty do celého procesu.

4

VLASTNÍ PRÁCE

4

Vlastní práce

4.1

Ekonomické zhodnocení lokalizací

25

Aby bylo vedení společnosti ochotné podstoupit proces lokalizací, se kterým samozřejmě souvisí určité finanční výdaje, případné organizační změny, či najímání
nových lidí nebo outsourcing, je nutné alespoň rámcově stanovit přibližné odhady
nákladů a potenciálních výnosů nebo výhod, plynoucích z lokalizací. Veškeré rozhodování o tom, zda se bude lokalizovat do příslušného jazyka by mělo vycházet ze
zjištění velikosti13 daného trhu, konkurence a následného průzkumu trhu, tedy zda
by byl o přeloženou verzi zájem. U některých zemí je na základě zkušeností zjištěno,
že chybějící lokalizovaná verze by z tohoto trhu nepřinesla téměř žádné nebo velmi
nízké výnosy. Jedná se například o Itálii, Francii, Španělsko a Portugalsko a naopak
existují země, kde prakticky není důležité a účelné dělat lokalizované verze, protože
tyto země jsou zvyklé na produkty v anglickém jazyce. Je to například Holandsko,
Dánsko, Finsko a Švédsko.
Právě na základě těchto analýz, snahy o proniknutí na zahraniční trhy, předběžných odhadů nákladů a současné finanční situace firmy, se vedení rozhodlo o lokalizaci produktu, webu a všech ostatních materiálů do tří jazyků – ruštiny, němčiny
a italštiny. Součástí byla také nezbytná revize anglického překladu, který se stal výchozí pro všechny ostatní jazyky, protože právě překlady z angličtiny do ostatních
jazyků jsou nejlevnější. Lokalizace produktu do dalších jazyků jsou plánovány až do
dalších let.
4.1.1

Nákladová stránka lokalizací

Jednotlivé náklady je nutné rozdělit do několika sekcí, protože lokalizační proces se
skládá z určitých částí, které na sebe navazují a mohou být prováděny odlišnými
subjekty a je možné se dostat k různým cenovým relacím.
V popisovaném případě lokalizačního procesu firmy došlo k následujícímu nákladových výdajům:

13

Velikost a strukturu trhu lze zjistit například z materiálů výzkumných společnosti Gartner, IDC
nebo z online zdroje The World Factbook, vytvořeného Ústřední zpravodajskou službou dostupnou
z https://www.cia.gov/

4.1

Ekonomické zhodnocení lokalizací

26

• pořízení dvou licencí Tradosu ve verzi SDL Trados 2007 celkam za 53 420 Kč,
• příprava překladů – zahrnuje vytvoření definice XML, konverzi TXT do XML
a zpět (kontrola a úprava kódování), údržbu a úpravu tohoto procesu po dobu
života projektu – pro všechny jazyky celkem za 4 800 Kč,
• vytvoření Trados Translation Memory s použitím českých a anglických XML
zdrojových souborů, alignment segmentů a následná kontrola, školení na překlady v Tradosu, podpora pro překladatele, zodpovídání dotazů – 5 400 Kč,
• překlad licence pro koncového uživatele (z důvodu nedostatečné odborné právní
znalosti interního překladatele) – 3 439 Kč,
• překlad Help souborů (nápověd) z českého do anglického jazyka činící 55 006
slov na překlad – 57 744 Kč,
• kompletní překlad všech materiálů, včetně zajištění jazykové revize další osobou, nezávislou na překladatelském týmu. V ceně je zahrnuta i kompilace či výroba finálních helpů, PDF manuálů a dalších potřebných materiálů. Následující
nákladové kalkulace14 jsou odlišné podle jednotlivých jazyků:
– ruština – 283 825 Kč,
– italština – 284 813 Kč,
– němčina – 445 108 Kč,
• koordinace překladů – je vyjádřeno paušální 8% sazbou (běžné bývá tato sazba
v rozmezí 8–12 %) z ceny překladů. Členěno dle jazyků:
– ruština – 22 706 Kč,
– italština – 22 785 Kč,
– němčina – 35 609 Kč,
• glosář, terminologie a jejich firemní užití – koordinace výroby glosářů pro
všechny jazyky, asistence při vytváření terminologie, nasazení nástrojů na jejich
udržování a způsob používání ve firmě, zejména u vývojářů a partnerů v jiných
zemích. Podpora udržování těchto po celou dobu životnosti překládaného produktu. Paušální sazba za všechny jazyky činila 6 572 Kč. Zahrnuje i angličtinu
a češtinu jako výchozí zdrojové jazyky. Zahrnuta je i konzultace s jazykovými
experty a náklady s tím spojené.
Počet slov jednotlivých komponent, které se pro daný projekt překládaly je
přehledně zobrazen v následující tabulce, členěných podle jazyků:
14

Počítáno kurzem 26, 71 Kč za 1 euro ze dne 1. 5. 2009 podle ČNB, avšak skutečná výše byla
podle smlouvy odlišná, jelikož byla nasmlouvaná platba 20 % celé částky lokalizací předem, 20 %
po dodání alespoň poloviny lokalizovaných textů a zbylých 40 % po dodání kompletních překladů
vždy v aktuálním kurzu, čili firmě mohou vznikat kurzové rozdíly.

4.1

27

Ekonomické zhodnocení lokalizací

Tab. 1: Počty překládaných slov podle jazyků

Jazyk
italština

Komponenta
Aplikace (produkt)
Nápověda
Celkem
němčina Aplikace (produkt)
Nápověda
Webová prezentace firmy
Celkem
ruština
Aplikace (produkt)
Nápověda
Celkem

Počet slov
18 509
55 030
73 539
16 807
55 006
32 340
104 153
18 258
55 026
73 284

Celková cena lokalizací pro jednotlivé jazyky, včetně příprav pro překlady
v Tradosu, jeho zakoupení, zavedení a vytvoření TM a glosáře činí 1 226 221 Kč.
V následující tabulce lze sledovat rozdíly v cenách15 překladů za slovo:
Tab. 2: Přehled cen překladů za slovo podle jednotlivých jazyků

4.1.2

Jazyk

Cena za slovo [Kč]

italština

3,87

němčina

4,27

ruština

3,87

Průměr

4,00

Vysvětlení některých nákladových položek

Zdrojové texty, které jsou v anglickém jazyce, jsou překládány interním překladatelem, který zároveň pracuje jako technická podpora pro anglicky hovořící zákazníky
a tak nevznikají při tomto překladu žádné další náklady, protože tato aktivita je
zároveň pracovní náplní tohoto pracovníka. Na toto se však nevztahuje odborný překlad licence pro koncového uživatele (běžně známo pod pojmem EULA16 ). Stejně
15

V ceně nejsou zarhnuty koordinace, protože ty se mohou případ od případu lišit a zbytečně by
zkreslovaly cenu čistého překladu.
16
End User License Agreement

4.1

Ekonomické zhodnocení lokalizací

28

tak tomu je v případě ruských překladů, avšak zde se jedná o jiného interního zaměstnance, který má na starosti obchodní a marketingové činnosti pro Rusko.
Ujednání EULA bylo přeloženo do angličtiny subdodavatelem, který zároveň
právně ověřil korektnost tohoto ujednání a u dalších jazyků je situace taková, že
z právnického hlediska se vychází vždy z anglického originálu. Čili již není potřeba
speciálních, právnicky ověřených překladů. Překlad tohoto ujednání do jiných než
anglických jazyků prozatím nebyl započítáván a bude realizován v budoucnu.
Koordinace lokalizací, včetně výroby TM, alignmentu a školení byla realizována
pomocí externí firmy, která také zajišťovala jednotlivé překlady. Revize překladů
byly částečně zajišťovány interně (angličtina, ruština) a částečně pomocí partnerů
(italština, němčina).
Je vhodné si ve smlouvách s dodavatelem překladů stanovit určitou cenu, která
bude do budoucna neměnná, nebo která bude rámcově na stejné úrovni, například
při ceně za přeložené slovo, protože prvotní a kompletní překlad je vzhledem k objemu levnější než dopřeklady (v nové verzi produktu se změní například jen 5 %
zdrojových textů). U partnerů lze sjednat platbu revizí nebo koordinací skrz slevy
z prodeje licencí a poskytnutím možnosti na větší marži. I takto lze tedy snížit
nákladovou stránku lokalizací.
Překlady webové prezentace do italštiny a ruštiny jsou plánované až na třetí
kvartál roku 2009, čili nyní nejsou zahrnuty do kalkulací. Italský web je realizován
partnerem v Itálii a ruský web zatím interními zdroji.
4.1.3

Výnosová stránka a přínosy lokalizací

Kvůli vysokým jednorázovým fixním nákladům, které jsou spojené s lokalizacemi je
nutné vysvětlit, jak se tyto náklady pokryjí výnosy a jak budou užitečné a účelné.
Díky lokalizacím je možné uzavírat partnerské, distributorské či resellerské
smlouvy se zahraničními subjekty, které by jinak o daný produkt neměli vůbec
zájem nebo by tyto smlouvy podepsaly za méně výhodných podmínek. Zásluhou
přeložené verze lze také sjednat zajištění vyšších prodejů, které zajistí a je schopen
realizovat zahraniční prodejce.
Dalšími přínosy lokalizací jsou:
• zvýšení hodnoty firmy,
• zvýšení povědomí o značce,
• získání referencí od recenzistů, společností, či uživatelů,
• získání větší návštěvnosti webových stránek a tím větších prodejů,

4.1

Ekonomické zhodnocení lokalizací

29

• možnost cíleného marketingu do více segmentů,
• dosažení maximálního podílu na trhu, kterého by jinak bez lokalizované verze
nemohlo být dosaženo.
4.1.4

Doba návratnosti investice

Pro případ změření návratnosti lokalizace lze kalkulovat s hodnotou, která by se počítala jako hodnota lokalizace produktu do daného jazyka, dělená cenou produktu.
Tímto výpočtem je výsledek, který představuje počet produktů, které je nutné prodat v dané verzi, aby se vložené náklady vrátily. Je nutné počítat s životním cyklem
produktu, který může být rozdílný.
V případě uvedeném v této práci jsou podklady pro výpočet doby návratnosti
investice do německé lokalizace následující:
• životní cyklus produktu 3 roky,
• cena překladů 445 108 Kč,
• cena produktu 2 000 Kč.
Na základě těchto údajů je doba návratnosti lokalizace do němčiny rovna prodejům 223 produktů během 3 let. Při současných prakticky nulových prodejích
do zahraničí (zhruba jeden produkt denně v celosvětovém měřítku) se toto může
zdát jako problém, ale jednak jsou na německém trhu očekávány nárůsty prodejů
v souvislosti s nutností lokalizované verze a jednak německý partner přislíbil rostoucí
prodeje, různé kampaně a ostatní prodejní aktivity, které nemohl bez lokalizované
verze realizovat. Rovněž jsou již nasmlouvané multilicence, které se v současné době
již předběžně uzavírají s různými institucemi v Německu, a které se budou realizovat
v okamžiku dodání lokalizované verze.
Zajímavý je také výpočet doby návratnosti u následujících verzí. Ze zkušeností
s překlady různých produktů několika firem v oboru bylo zjištěno, že s každou novou
verzí produktu se vygeneruje zhruba 20 % nových textů pro všechny komponenty
dohromady. V ohledu na toto lze spočítat dobu návratnosti lokalizace při vydání
další verze produktu. Při úměrném zachování cen překladů (maximálně 7% nárůst vzhledem k případným nárůstům cen překladů, inflaci, kurzovým výkyvům)
a při předpokládaném zvýšení ceny produktu o 10 % jsou podklady pro výpočet
následující:

4.2

Softwarový nástroj pro podporu lokalizací

30

• životní cyklus produktu 3 roky,
• cena překladů 95 253 Kč,
• cena produktu 2 200 Kč.
Doba návratnosti s další vydanou verzí činí 44 prodejů produktu během 3 let.
Při srovnání s prvotními náklady je rychlost návratu budoucích překladů více než
pětinásobná.
Ačkoliv se může zdát, že zavedení profesionálního řízení lokalizací za pomoci
profesionálních prostředků pro překlady je nejen organizačně, ale i finančně poměrně dost náročný proces, výsledky se dostaví (nebo by se měly dostavit, pokud
firma nezanedbává své ostatní povinnosti) především ve střednědobém horizontu.
Samozřejmě ne vždy se dá očekávat vzestup prodejů nebo vysoká efektivita tohoto
zavedení, protože někdy se do daného jazyka lokalizuje pouze z důvodů dosažení
zbylého místa na trhu (může se jednat i o jednotky procent) nebo z jiných důvodů,
které byly popsány v předešlých kapitolách.

4.2

Softwarový nástroj pro podporu lokalizací

Jelikož nejrozšířenější nástroje, kterými se lokalizace tvoří a obhospodařují jsou
velmi rozvinuté a sofistikované, bylo by neúčelné vytvářet takovýto další a navíc
omezený nástroj. Na takovýchto nástrojích spolupracují desítky a stovky odborníků
a programátorů již přes několik let. Pro tuto práci bylo tedy účelné zjistit od osoby,
která s Tradosem pracuje nejvíce – překladatele – co mu při překladu chybí, co by
mu práci zjednodušilo či urychlilo a zároveň, čeho není daný nástroj schopen.
Z praktického hlediska interního překladatele vznikl dotaz, zda by nebylo možné
nějak usnadnit práci ostatním externím překladatelům při práci s glosářem. Glosář
je seznam termínů, které jsou ustálené a nepřekládají se, nebo jsou tyto termíny
názvem produktu, který se taktéž nepřekládá, anebo se jedná o ustálenou zkratku.
Nástroj, který by tato slova označil ve zdrojovém textu by usnadnil práci všem,
kteří se dostanou do pozice překladatele. Přestože lokalizační nástroj Trados je velmi
sofistikovaný a dalo by se říci, že je standardem oboru, takovýto nástroj v sobě neobsahuje. Po konzultacích jak s překladatelem, tak s externisty s praxí v oboru bylo
navrženo takové řešení, které zdrojové soubory ve formátu XML otaguje takovým
způsobem, že výstupem bude zdrojový soubor obohacený o otagované výskyty daných termínů z příslušného glosáře. Tímto překladatel dostane k dispozici soubor,
ve kterém ihned uvidí, která slova a termíny se nemají překládat a nebude nucen

4.2

Softwarový nástroj pro podporu lokalizací

31

si pamatovat celý seznam ustálených termínů, které se navíc v průběhu lokalizací
mohou měnit.
4.2.1

Rozhraní pro práci se soubory

Daný softwarový nástroj pracuje v jednoduchém a přehledném webovém prostředí,
ve kterém nemělo smysl nijak inovátorsky přistupovat k designu. Cílem bylo vytvořit
prostředí, ve kterém bude potřeba se rychle zorientovat a využít daných funkcí.
Pomocí správy souborů, se nahrávají příslušné zdrojové soubory typu XML,
které obsahují slova nebo věty, které je nutno přeložit. Tyto soubory jsou jak exporty
ze samotné aplikace, tak exporty z webového obsahu a nápověd. U každého souboru,
který ještě není označen patřičnými tagy se zobrazuje odkaz, který toto provede.
Po provedení tohoto úkonu se soubor vypíše na obrazovku s tučnými výskyty slov
z glosáře. Poté se tento soubor přesune do složky „Otagovane souboryÿ a zároveň se
označí ikonou pro větší přehlednost. Takto upravený soubor je pak možné stáhnout
na disk a importovat jej do programu Trados, kde se s ním dá již normálně pracovat
a překládat jej s přehledným označením výrazů z glosáře, které se překládat nemají.
4.2.2

Glosář

Glosář je jednoduchá databáze, vytvořená v databázovém systému Oracle na školním
serveru Akela, který provozuje Mendelova zemědělská a lesnická univerzita v Brně.
Jedná se o jedinou tabulku, která obsahuje tři atributy a sice id, slovo glosáře a popis
tohoto slova. Pro budoucí možné využití je ošetřeno unikátní id každého slova pomocí sekvencí. Popis slova slouží jako jednoduchá specifikace a vysvětlivka daného
pojmu, protože se v produktu Zoner Photo Studio vyskytují pojmy, které mohou být
nejasné pro některé překladatele. Tuto databázi obhospodařuje hlavní překladatel,
který rozhoduje také o tom, která slova se do glosáře zahrnou a která nikoliv. V současné době databáze obsahuje přibližně 105 položek a počítá s nárůstem maximálně
o 15 položek s každou novou verzí.
4.2.3

Algoritmus označování nalezených výskytů

Daný algoritmus pracuje na principu vyextrahování veškerého textu, který se nachází
mezi jednotlivými elementy XML souboru do pole řetězců. Toto pole je pak následně
prohledáváno a případný výskyt, který se shoduje s daným slovem v databázi glosáře
je ohraničen jednak tagem, který danou položku zvýrazní, aby na prvotním výstupu

4.2

Softwarový nástroj pro podporu lokalizací

32

a kontrole byl výraz tučný (<B>) a ještě jej ohraničí tagem <NOT>, aby překladatel v Tradosu věděl, že s daným výrazem si nemusí dělat starosti a překládat
jej.
Každé jednotlivé slovo je vyhledáváno tak, že je sestaveno pole povolených
znaků, které se skládá z malých a velkých písmen. Znaky, které nejsou v tomto poli
pak představují konce a začátky slov, na základě kterých se hledá shoda s výrazy
v glosáři a případné tyto shody se tagují. Pole povolených znaků výrazně snižuje
případné nepříjemnosti spojené se speciálními znaky, jako jsou dvojtečky, středníky,
uvozovky, zpětná lomítka, pomlčky, otazníky, procenta a jiné. Výčet těchto znaků
by byl dlouhý a operovat s ním v podmínce by bylo neefektivní a nepřehledné.
Ukázka otagovaného souboru včetně zvýraznění pro přímé zobrazení na výstupu. Na výstupu ve webovém prohlížeči budou slova, která jsou označena jako
shodná s glosářem zobrazena tučně.
<text styleclass="Normal" translate="true">
A <NOT><B>histogram</B></NOT> shows how many pixels
in a <NOT><B>picture</B></NOT> are at each of its
possible brightness <NOT><B>levels</B></NOT>.
Its horizontal axis representsthe scale of possible
brightness values, usually either for the
<NOT><B>picture</B></NOT> overall or for a single
color channel.Its <NOT><B>vertical</B></NOT> axis
represents the pixel frequency in the
<NOT><B>picture</B></NOT> for each of these values.
</text>
Výsledný otagovaný soubor si poté překladatel stáhne a naimportuje do Tradosu. Díky rozšířeným funkcím Tradosu si může zvolit, kdy dané tagy odstraní.
Může tak učinit před konečným posíláním na revize nebo si je ponechat a odstranit
je až před předáním vývoji, webovému nebo marketingovému oddělení.
Ukázka otagovaného souboru v prostředí Trados, ve kterém pracuje překladatel:

4.2

Softwarový nástroj pro podporu lokalizací

33

Obr. 2: Otagovaný soubor v prostředí Trados
4.2.4

DTD

Zdrojové soubory, které mají být po dohodě s lokalizačním expertem v XML formátu, je potřeba pomocí Tradosu naimportovat tak, aby měl překladatel k dispozici
pouze segmenty, které jsou určené k překladu. Pro tyto soubory je potřeba stanovit
strukturu elementů těchto XML souborů, podle které budou importovány. Jedná se
o DTD – Definici typu dokumentu.
Zdrojové soubory aplikace vytvořila firma vlastními nástroji exportem textů
z vývojového prostředí Visual Studio podle požadavků lokalizační agentury. Stejně
tak tomu bylo u webové prezentace a nápovědy. V případě webové prezentace exportem z vlastního redakčního systému a v případě nápověd pomocí programu
Help & Manual, který podporuje XML.

4.2

Softwarový nástroj pro podporu lokalizací

34

Tyto zdrojové soubory je následně potřeba naimportovat do prostředí Tradosu.
Protože jsou zdrojové soubory v předem domluveném XML formátu, je potřeba
vložit a použít DTD soubor pro každou danou část (web, nápověda, aplikace). Výstupem Tradosu z tohoto importu je .ini definiční soubor. Vstupem místo DTD může
být právě i tento .ini soubor, který poskytuje program pro tvorbu nápověd a není
nutno definovat DTD pro zdrojové soubory u nápověd.
Z výše uvedeného plyne vytvoření dvou DTD, přičemž DTD pro webové zdrojové soubory je součástí přílohy práce. V případě tvorby DTD pro zdrojové soubory
aplikace lze uvést příklad zjednodušeného (jinak je struktura stejná, pouze mnohem
více položek) zdrojového souboru:
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE tm_database SYSTEM "zoner_tm.dtd">
<tm_database>
<content>
<node>
<language lang="English">Get More from Zoner Photo Studio</language>
</node>
<node>
<language lang="English">Learn More...</language>
</node>
</content>
</tm_database>

Dané DTD pro účely Tradosu tak, aby rozpoznal jednotlivé elementy a atributy
bude vypadat následovně:

<!ELEMENT tm_database

(content)>

<!ELEMENT content (node)+>
<!ELEMENT node (language+)>

4.2

Softwarový nástroj pro podporu lokalizací

35

<!ELEMENT language (#PCDATA)>
<!ATTLIST language
lang CDATA #REQUIRED
>
V daném DTD je nadefinováno, že pro překlad se budou zobrazovat texty,
které jsou mezi elementy „languageÿ s atributem „langÿ. Tyto hodnoty jsou povinné
a mohou nabývat hodnot libovolného řetězce.
Stejně tak tomu bude pro zdrojové XML soubory z webu. Toto DTD je přílohou práce. Trados je schopen po této definici definovat vizuální styly jednotlivým
elementům, případně je označovat za skryté nebo blokované.

5

5

ZÁVĚR

36

Závěr

Software pro automatizovanou podporu překladů je nasazen ve firemním webovém
redakčním systému a interní překladatel s ním pracuje a využívá jej. Následně bude
využit i ostatními překladateli, kteří poskytnou připomínky a komentáře k danému
řešení. Do budoucna by mohl být ještě více rozpracován design, který sice není prioritou, ale mohl by být další výhodou. Také by se mohl zajistit bezchybný průběh
označování jednotlivých slov glosáře, který v určitých momentech nemusí být optimální, protože je odzkoušen jen na daných výstupech případového produktu. Byl
by tak aplikovatelný na jakékoliv jiné zdrojové soubory, případně zdrojové soubory
v jiných formátech.
Definice typu dokumentu byly vytvořeny na základě předchozích zkušeností
s touto tvorbou, mohly by však být do budoucna přepracovány do XML schémat,
které budou podporovány novější verzí Tradosu. Výhodou této podpory je, že může
pomoci i firmám a překladatelům, kteří nemají zakoupené profesionální nástroje na
tvorbu překladů.
Práce shrnula možnosti přístupů a výchozí stanoviska pro zavedení lokalizačního
procesu do firmy, jaké existují nejrozšířenější nástroje pro překladatele a popsala
jednotlivé druhy a možnosti řízení lokalizací, včetně osoby nebo osob, zodpovědných
za toto řízení.
Dospělo se k zajímavému zjištění, že ačkoliv se zdá zavádění procesu lokalizace
poněkud nákladné, v dalších letech vývoje produktu tomu tak již není. Navíc daný
systém překladů, revizí, profesionálního řízení a zajištění kvality zaručuje vysokou
kvalitu jak překladů, tak funkčnosti přeložených verzí.
Ekonomické zhodnocení by mohlo počítat s více okolnostmi a pravděpodobnostmi, které mohou ovlivňovat lokalizace jako jsou kurzové rozdíly, odlišnosti od
budoucích smluv, rizika spojená s přechodem k jinému překladateli, firemní restrukturalizace, přidání dalšího produktu do firemního portfolia, slevy u multilicencí, atd.
Největším přínosem práce bylo získání zkušeností s celým procesem lokalizací
a jeho působením napříč firmou jak v ekonomickém ohledu, tak v technickém, včetně
získání představ nákladovosti celého procesu a způsobu jednání s jednotlivými subjekty. Při správném chodu všech oddělení ve firmě se jistě podaří prostředky investované do procesu lokalizace patřičně využít a získat tím všechny výhody, které jsou
s lokalizacemi spojeny.

6

LITERATURA

6

37

Literatura

Esselink, B. A Practical Guide to Localization 2. vyd, Amsterdam/Philadelphia:
John Benjamins Publishing Company, 2000. 488 s. ISBN 90-2721-956-7.
Lommel, A. The Globalization Industry Primer: An introduction to preparing your business and products for success in international markets. Rebecca Ray. [s.l.]: The Localization Industry Standards Association, 2007. 70 s. Dokument ve formátu PDF. Dostupný z WWW:
http://www.lisa.org/Globalization-Indust.468.0.html. ISBN 978-929228-025-3.
W3C Internationalization (I18n) Activity: Making the World Wide Web
world wide! [online]. c2005-2006 [cit. 2008-02-17]. Dostupný z WWW:
http://www.w3.org/International/questions/qa-i18n.
The

Localization Industry Standards Association [LISA] XML
Text Memory (xml:tm) [online]. c2007, [cit. 2009-02-25]. Dostupný
z WWW:http://www.lisa.org/XML-Text-Memory-xml.107.0.html.

Bradley, N. XML: Kompletní průvodce Jiří Bráza. 1. vyd. [s.l.]: Grada Publishing,
2000. 536 s. ISBN 80-7169-949-7.
Young, M. J. XML krok za krokem Aleš Thiemel 2. vyd. [s.l.]: Computer Press,
2006, 471 s. ISBN 80-251-1070-2 .
Dillinger, M., Lommel, A. LISA Best Practice Guides: Implementing Machine Translation Rebeca Ray. [s.l.]: The Localization Industry Standards
Association, 2004. 65 s. Dokument ve formátu PDF. Dostupný z WWW:
http://www.lisa.org/Best-Practice-Guides.467.0.html#c257.
Lommel,
A.
Guide
to
Localization
Management.
[online].
56 s.
Dokument
ve
formátu
PDF.
Dostupný
z
WWW:
http://www.issco.unige.ch/en/research/projects/ecolore/
localisation/Components/White%20Papers/Guide%20to%20Localisation
%20Management.pdf.

Přílohy

A

A

DTD PRO IMPORT Z XML ZDROJOVÝCH SOUBORŮ WEBOVÝCH STRÁNEK

39

DTD pro import z XML zdrojových souborů webových stránek

<!ELEMENT source (content)>
<!ELEMENT content (system_texts?,pages?, articles?)>
<!ELEMENT system_texts (text+)>
<!ELEMENT text (language)>
<!ATTLIST text System_text_mark CDATA #REQUIRED
>
<!ELEMENT pages (page_title, page_keywords, page_description,
page_name)+>
<!ELEMENT page_title (language)>
<!ATTLIST page_title
Page_category_id CDATA #REQUIRED
>
<!ELEMENT page_keywords (language)>
<!ATTLIST page_keywords
Page_category_id CDATA #REQUIRED
>
<!ELEMENT page_description (language)>
<!ATTLIST page_description
Page_category_id CDATA #REQUIRED
>
<!ELEMENT page_name (language)>
<!ATTLIST page_name
Page_category_id CDATA #REQUIRED
>
<!ELEMENT articles (article+)>
<!ELEMENT article (language)>
<!ATTLIST article
Page_category_id
CDATA #REQUIRED
Page_layout_id
CDATA #REQUIRED
Page_layout_div_id
CDATA #REQUIRED>
<!ELEMENT language (#PCDATA)>
<!ATTLIST language
lang CDATA #REQUIRED>

