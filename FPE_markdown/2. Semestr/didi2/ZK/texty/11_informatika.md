---
title: "11_informatika.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/didi2/ZK/texty/11_informatika.pdf"
date: 2009-06-11
type: PDF (text-based)
---

Přednášky z didaktiky informatiky a výpočetní techniky

Jiří Vaníček, 2005

Informatika
Úvod
V názvech školních předmětů na základních a středních školách týkajících se práce s počítači není zcela
jasno. Názvy nevystihují přesně obsah předmětů, pod kterým bychom rádi tušili ovládání počítače. Máme pocit,
že název předmětu informatika jako nauka o informacích a jejich hromadném zpracování pomocí výpočetní
techniky nevystihuje povahu práce na základní škole, nicméně název výpočetní technika jako technická
disciplína ji nevystihuje taktéž.
Řada učitelů si slovo informatika přeložila jako počítače a tak se vlastní infomatice vyhnula. Jiná část
učitelů zařazuje informatické téma do učiva výpočetní techniky na střední škole jako téma teoretické, naukové.
V ní se žáci dozví, co že je informace, co je základní a co nejmenší jednotkou informace, kolik bajtů že je 1
kilobajt (buď 1000 nebo 1024, protože 2 10), kolik informace se vejde na CD-disk a kde se v počítači zjistí
velikost souboru. Tím je informatika jakoby vyčerpána.
Informatika a společnost
V dnešní informační společnosti, kde se informace staly zbožím a kde vlivem trhu nemůže jedna firma
získat výhodu nad jinými pouhým nákupem výpočetní techniky (protože to může učinit i konkurence, výpočetní
technika není drahá), ale především způsobem práce s informacemi (jejich zpracováním, ochranou, systémem
práce s nimi) a tedy výběrem a tréninkem svých zaměstnanců (tak, aby uměli s informacemi zacházet a používat
je). Řada firem je úspěšná právě díky tomu, že velmi rychle dodá zpracované informace až k zákazníkovi.
Cíle výuky informatiky
Chápejme informatické téma jako stejně plnohodnotné s počítačovou grafikou, programováním, výukou
komunikace či třeba práci s texty. Rozvíjí představu dítěte o tom, že při výuce tohoto předmětu kromě vlastních
počítačů jako fyzických předmětů zde existují další, tentokrát nehmotné objekty, které ovšem mohou taktéž
přinášet potěšení, zisk či někomu i smysl života.
Děti by měly (na různých příkladech) porozumět tomu, co znamená informační společnost a jak se liší
pojem informace od pojmu data.
Především by však toto téma mělo být využito k poznání, jak vlastně počítač pracuje. To je podstatnější
pro rozvoj žáka než poznání, z čeho se počítač skládá. Poznatky typu „jádrem či srdcem počítače je procesor“,
„paměť si pamatuje čísla“ a „v počítači je základní deska, takzvaný motherboard“ jdou poměrně po povrchu
poznání, nijak výrazně nezlepšují představu, co to vlastně počítač je. Jiné jsou otázky typu „jak vlastně počítač
s těmi jedničkami a nulami počítá“, „co se v počítači, stane, když zmáčknu klávesu A“, „jak počítač uchovává
obrázky a zvuky, když má k dispozici pouze ty jedničky a nuly“.
Stěžejním termínem je tedy pojem digitalizace. V závislosti na stupni matematických schopností pak
obsáhnout příklady konkrétní digitalizace různých druhů informací.
Obsah výuky, některé pojmy
Jak počítače uchovávají v paměti jedničky a nuly?
Předně je třeba dětem poctivě říci, že počítače s žádnými jedničkami a nulami nepracují. Dva stavy
v „drátcích“ počítače (je napětí či není napětí, prochází proud nebo neprochází proud apod.) si lidé pro svoji
vlastní potřebu představují jako jedničky či nuly. Elektrické obvody v počítači jsou zkonstruovány tak, že tyto
dva stavy uchovávají a zpracovávají tak, jako by sčítaly a násobily čísla ve dvojkové soustavě (tedy ty jedničky a
nuly).
Protože tento text je určen lidem, nikoliv počítačům, budeme pro názornost ty jedničky a nuly používat.
Jak je to s těmi bity a byty?
Informace má svoji hodnotu a velikost. Velikost informace je dána možnostmi, variabilitou informace.
Např. pro vyjádření, jaký je den v týdnu, potřebujeme vybrat ze 7 možností, informaci o datu narozenin pak
z 366 možností, o aktuálním čase s přesností na sekundu již vybíráme z 86400 možností.
Přitom hodnota informace a tedy její důležitost nijak nesouvisí s její velikostí. Odpověď na otázku
„Vezmeš si mne?“, „Bude válka?“ nebo zda „se mi narodí dcera“, znamená výběr pouze ze dvou možností
(ano/ne), přesto má dalekosáhlý dopad na lidské osudy.
Jeden „drátek“ může v daný časový okamžik nést 2 možnosti informace, jedna buňka paměti mlže
uchovat jednu ze dvou možností. Dva bity nesou informaci vybíranou ze čtyř možností (11, 10, 01, 00), na
zapamatování dne v týdnu stačí 3 bity, aktuální čas pak vyžaduje minimálně 17 dvojkových číslic.

Přednášky z didaktiky informatiky a výpočetní techniky

Jiří Vaníček, 2005

Bajt (byte) je sice užívanější, ovšem méně zdůvodnitelnou jednotkou velikosti informace (chcete-li,
velikosti dat). Proč zrovna 8 bitů je 1 bajt? Důvod je patrně historický, vždyť dnes máme 32bitové počítače
(dokáží zpracovávat současně data 32 „drátků“) a třeba přenos textu po Internetu je sedmibitový (proto absence
češtiny a různé mime kódování) atd. Vztah mezi bitem a bajtem je podobný vztahu jednotek elektrického náboje
(elementární el. náboj a Coulomb) nebo (nepřesněji, ale méně fyzikálně odborně) vztahu mezi stupni Kelvina a
Celsia.
Dvojková soustava
Seznámení s dvojkovou soustavou (za podmínky, že žáci již mají vybudovaný matematický aparát)
může pěkně ukázat, jak vlastně počítač pracuje. Je dobré při výpočtech žákům zdůrazňovat, že počítač si
nepřevádí čísla do desítkové soustavy jako my, abychom jim rozuměli, ale počítá s nimi automaticky.
Můžeme žákům ukázat,
a) jak lze převádět čísla z desítkové do dvojkové soustavy a naopak (např. 10012 = 9)
b) jak počítač počítá s binárními čísly (např. 100102 * 10112 = 110001102)
(dvojku za binárním číslem píšeme kvůli rozlišení: napíšeme-li nyní pouze 1001, nepoznáme, zda jde o číslo 9
nebo „tisíc a jedna“ - podle toho, ve které ze soustav se právě nacházíme)
ad a) Pomocí kalkulačky v příslušenství snadno zobrazíme hodnotu binárního čísla v desítkové soustavě a
naopak.
Se studenty lze převádět binární číslo na dekadické podle vzoru: 10112 = 1.23+0.22+1.21+1.20 = 8+2+1 = 11. Lze
ukázat také zpětný převod na binární číslo pomocí hledání opakovaného hledání mocniny čísla 2.
Příklad: Převedeme 203 do dvojkové soustavy.
ad b) Sčítání binárních čísel se dá ukázat pomocí stejného algoritmu, jako běžné písemné sčítání. Je to ještě
jednodušší: jediné, co si musí žák pamatovat, že ve dvojkové soustavě neexistují jiné číslice než 0 a 1, takže 1+1
není 2, ale 10 (nečtěme „deset“, ale „jedna nula“), 1+1+1 = 11.
Příklad: Máme 2 čísla: 1101001011112, tedy číslo 3375, a 110010112, tedy 203.
převod
1111
Komentář: číslice v sloupci pod sebou
110100101111
sčítáme. Vyjde-li 10, nulu napíšeme a 1
11001011
připíšeme o 1 řád vlevo do řádku „převod“.
110111111110
Odčítání binárních čísel je podobné:

převod

10011
- 110
-1
1101

Třetí sloupec zprava: 1 a kolik je 10?
1 + 1 = 10. 1 zapíšeme, 1 dáme do řádku
„převod“.
4. sloupec: 1 a kolik je 10?

Násobení čísel v dvojkové soustavě je výhodné pro ty, kteří neumějí násobilku. Stačí použít analogii
z desítkové soustavy. Násobíme-li v desítkové soustavě mocninou 10, tedy 100, 1000, 100000, stačí přidat nebo
ubrat nuly (posunout desetinnou čárku). Pokud ve dvojkové soustavě přidáme vpravo k čísli nulu, násobíme
nikoliv deseti, ale dvěma. Jestliže např. 10012 znamená 9, pak 100102 je 18, 1001002 je 36 atd.
Jak vypadá násobení čísly jinými než mocninami dvou? Druhého činitele „rozložíme“ na mocniny
dvou a převedeme tak násobení na sčítání.
Příklad: Vynásobíme 203 * 5, tedy 110010112 * 1012. Číslo 5 je vlastně (4+1), což jsou obě mocniny
dvou. Vynásobíme číslo 110010112 čtyřmi (přidáme 2 nuly) a přičtěme číslo 110010112. Viz ukázka:
*4
1100101100
*1
11001011
= 1+2+4+16+32+64+128+256+512 = 1015
1111110111
A konečně dělení v dvojkové soustavě používá stejný algoritmus jako v desítkové. Přitom dělení
dvěma, čtyřmi, osmi, šestnácti atd. opět pouze posouvá
„desetinnou“, nebo asi správněji „binární“ čárku.
Počítáme: 111 děleno 110 je 1krát, zbytek 1.
Dělíme 30 číslem 6: 11110↵ 2 : 1102 = 1012
Sepíšeme (červenou) jedničku, 11 děleno 110 je
11
nula, zbytek 11, sepíšeme (modrou) nulu atd.
110
0
Poznámka: Na první pohled to vypadá, že výpočty s delšími čísly jsou pomalejší. Jestliže ale používáte
jen 2 číslice, náročnost výpočtů se rapidně snižuje a rychlost roste.

Přednášky z didaktiky informatiky a výpočetní techniky

Jiří Vaníček, 2005

Digitalizace
Jak počítač získá jedničky a nuly, se kterými potom počítá a které je schopen si pamatovat?
Pomocí různých přístrojů a zařízení (mikrofon, fotoaparát, skener, kamera, různé fyzikální sondy teploměr, EKG, sonar, radar) sbírá signály a ty převádí do číslicové podoby. Toto převádění se nazývá
digitalizace (z latinského digitus = prst). Digitalizace tedy znamená převod signálu ze spojitého na „spočítatelný,
vyjádřitelný pomocí prstů, tedy číslem“).
Jak počítač uchovává text
Text je do počítače vkládán pomocí kláves. Každá klávesa má svůj vlastní kód, vyjádřený pomocí
jedniček a nul. Například písmeno „velké A“ si počítač pamatuje jako 1000000 (to není milión, to je jednička a
šest nul). Jsou vytvořeny tabulky, podle kterých jsou znakům kódy (třeba ASCII nebo UNICODE) přiřazovány.
Poznámka: V průběhu historie počítačů se tabulky kódů měnily, navíc každý stát či systém si mohl vytvářet své
kódové tabulky. Obecně řečeno tato roztříštěnost a množství znaků, kterými lidstvo líše, způsobují i dnes
nečitelnost textů některých e-mailů, špatné zobrazování znaků s diakritikou při použití určitých fontů písma atd.
Text je tedy převáděn na binární číslice nikoliv ze spojitých hodnot, ale překódováním hodnot
diskrétních.
obrázek vlevo:
text z úvodu této
přednášky
a
jeho
hexadecimální kód ve
Windows (CP 1250). Šipky
stejné barvy ukazují znak a
jeho kód (např. velké I má
kód
4916 =4.16 + 9 = 73).

obrázek dole:
zatímco znaky bez
diakritiky mají stejnou
interpretaci (velké I je stále
čteno jako velké I), znaky
ostatní mohou být v jiném
kódování zobrazeny jinak
(znak á se mění v kódování
DOS na ß)

Přednášky z didaktiky informatiky a výpočetní techniky

Jiří Vaníček, 2005

Jak se digitalizuje grafika
Obrázek se digitalizuje pomocí skeneru. Hotovo, tečka.
Z této velmi povrchní informace se žák nedozví nic o fungování počítače. Lepší metodou je „hra na
skener“ (na digitální fotoaparát). Žáci mohou kreslit na papíře, zručnější třeba v programu. V následujících
odstavcích je popsáno, co by se měli studenti střední školy při „hře na skener“ dozvědět.

Příklad: digitalizace písmene F (lze použít též srdíčko nebo jiný nejlépe nesouměrný znak)
1. Obrázek překryjeme rastrem (hustota rastru ovlivňuje náročnost práce i kvalitu výsledného
digitálního obrazu). Každý čtvereček rastru představuje 1 pixel.
2. U každého čtverečku se rozhodneme, zda vybarvení je větší než 50% plochy čtverečku. Takový
čtvereček vybarvíme celý, zbylé čtverečky necháme nevybarvené.
3. Vytvoříme číselnou kopii digitalizovaného obrázku: ve vytvořené matici čísel jednička znamená
vybarvený čtvereček, nula nevybarvený
4. Každý řádek matice představuje 1 binární kód jednoho řádku obrázku. Lze převést do desítkové či
šestnáctkové soustavy.

Digitální úpravy grafiky
Běžného uživatele často nadchne, jaká
kouzla lze provádět s fotografiemi pomocí různých
efektů (převracení a otáčení, inverze, deformace,
pixelizace, olejomalba …). Všechny tyto operace
jsou ovšem pouhým matematickým přepočítáním
čísel, která obrázek v paměti počítače reprezentují.
Ukažme si na příkladu:
Máme zaznamenán digitální obraz písmene F.
Pokud vyměníme všechny nuly za jeničky a
obrázeně, dostaneme inverzní obrázek.

Přednášky z didaktiky informatiky a výpočetní techniky

Jiří Vaníček, 2005

Sešikmený obrázek (kurzíva u písma) dostaneme posunem kódu příslušného řádku o několik míst doleva či
doprava. Víme, že při násobení binárních čísel mocninou čísla 2 se pouze posouvá „desetinná čárka“. Pokud tedy
u obrázku písmene F vydělíme horní řádek 16, posune se kód tohoto řádku o 4 místa vpravo. Prostřední řádky
vydělíme postupně 8, 4, 2 (posun o 3, 2, 1 místo), spodní řádek zůstane nezměněn.
Asi je evidentní, že záměnou prvního řádku s posledním, druhého s předposledním atd. překlopíme obrázek
svisle, obdobnou výměnou jedniček a nul v řádcích lze obrázek překlopit vodorovně či otočit o násobky 90°.
Barevná hloubka
Jestliže na našem příkladu s písmenem F uvažujeme pouze 2 barvy, reprezentuje jednička černou barvu
a nula bílou (nebo obráceně, záleží na dohodě). Pokud digitalizujeme vícebarevnou předlohu, musíme přiřadit
jednotlivým barvám kódy (podobně jako u kódovacích tabulek pro text). Při šestnácti použitých barvách
potřebuje každý pixel 4 bity paměti, při zobrazení 256 barev pak 1 pixel = 1 bajt.
V zobrazení True color je pro popis každého z 16, 7 miliónů barevných odstínů vyhrazeno 24 bitů.

Přednášky z didaktiky informatiky a výpočetní techniky

Jiří Vaníček, 2005

Digitalizace zvuku
Zvuk je spojité chvění, které lze zaznamenat jednoduchým fyzikálním pokusem (hrot rozeznělé ladičky
při pohybu po papíru zanechává stopu ve tvaru křivky). Takovýto graf závislosti výkmitu na čase lze zobrazit i
při záznamu zvuku mikrofonem.
Spojité hodnoty tohoto záznamu lze „manuálně“ digitalizovat opět překrytím křivky určitým rastrem,
daným parametrem „jak často chci zkoumat momentální úroveň hlasitosti“ (rastrovací frekvence) a jemností
rozlišení hodnot amplitudy křivky. Poté se z grafu odečítají funkční hodnoty a zaznamenávají do tabulky - získá
se opět číselný kód, každé číslo kódu představuje momentální úroveň „hlasitosti“ zvuku.
Věrnost digitalizovaného zvuku opět závisí na hustotě rastru (na spodním obrázku, pokud by odpovídal
reálné situaci, by byl výsledný digitalizovaný zvuk hodně nepodobný originálu).

Digitální úpravy zvuku
Následující věty berte prosím jako ilustraci, která není fyzikálně a technicky zcela správná, ale pomůže
dítěti udělat si přibližnou představu.
Zesílení zvuku: vynásobíme-li všechna čísla deseti, zvuk bude desetkrát silnější (hlasitost se zvýší o 10
decibelů). Podobně docílíme zeslabení zvuku (plynulého zeslabení docílíme postupným dělením čísel kódu
neustále se zvyšujícím dělitelem).
Změna výšky tónů: jestliže vypustíme z kódu zvuku každé druhé číslo, bude se záznam přehrávat
dvakrát rychleji (přehraje se za dvakrát kratší dobu), což v důsledku znamená zvýšení zvuku o 1 oktávu.
Mixáž vzniká kombinací dvou zvukových záznamů (např. čísla dvou zvuků, odpovídající stejnému
okamžiku přehrávání, se sečtou).
Dozvuk (slabá ozvěna nebo pocit hudby ve velkých prostorách): kód zvuku se zeslabí, posune o několik
setin sekundy (před kód se přidá několik nul) a namixuje s původním zvukem.

