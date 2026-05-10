---
title: "SVS_prednasky_623.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/moje materialy/Parametricke testy na normalitu/priklady/SVS_prednasky_623.pdf"
date: 2010-01-20
type: PDF (text-based)
---

SVS

přednášky

1. Přednáška
Základní etapy statistické analýzy

SAS INSIGHT – základní char.
SAS LAB – quided data analysis - široká nabídka opravných prostředků.

-1-

SVS

přednášky

-2-

1.1. Prostředky průzkumové analýzy
Jde o kombinace různých grafických a číselných postupů, které mají podat základní informace
o vlastnostech souboru. Základním prostředkem jsou grafy s různou orientací. Zobrazení
datového souboru – pomocí grafu –

1.1.1. Sloupcový diagram. (Bar Chart).
četnosti
(relativní
četnost)

analyzované veličiny
hodnoty (integrály)

procedury v SAS:
proc jmeno_procedury data = jméno datového souboru
var (proměnná)…..;
run;
zobrazení datového souboru v grafu.
proc chart data = jméno souboru
vbar vyska;
run;
výsledkem je sloupcový diagram v proceduře Chart.
hbar (horizontální orientace)
vbar (vertikální orientace)

SVS
•

přednášky

-3-

Procedury gchart – mají lepší grafické výstupy

proc gchart data=A;
hbar vyska;
run;

procedura automaticky data setřídí do intervalů podle Sturgesova pravidla – automaticky
vypočítá počet těch intervalů (tříd K).
pozn.: Při velkém rozsahu n náhodného výběru rozdělujeme hodnoty do tzv. tříd (třídních
intervalů). Celý obor hodnot je pak rozdělen na třídní intervaly, přičemž daná pozorovaná
hodnota spadá vždy do jedné třídy. Počet tříd k lze volit podle potřeby. Obvykle se k pohybuje
mezi 5 a 20, nebo se volí
je
.

, popř. použijeme tzv. Sturgesovo pravidlo, podle kterého

1.1.2. Histogram –
Zdokonalení sloupcového diagramu.
- zobrazení četností ve formě sloupců četnosti
- histogram nám určuje homogenitu souboru, určí
zda je homogenní nebo zda se rozpadá do
dílčích menších podsouborů.
(homogení soubor má jen jednu
nejčetnější hodnotu)
X – intervaly
Y – četnosti or relativní četnosti.
Z grafu lze odhadnout, jestli údaje datového souboru jsou soustředěny symetricky nebo
nesymetricky.

SVS

přednášky

-4-

1.1.3. Grafický výstup v proceduře univariate
pokud chci v proceduře jen grafický výstup (histogram), musím potlačit numerické výstupy.
proc univariable data = jméno souboru
histogram_jméno proměnné pro kterou kreslím
run;
Je třeba posoudit, jestli data mají normální rozdělení – do histogramu proto dáme
křivku normal, případně exponencial.

proc univariable data = jméno souboru
histogram <jm>/ normal exponencial;
run;

1.1.4. box plot
grafické zobrazení tvz. pětičíselného souhrnu

SVS

přednášky

-5-

2. Přednáška
2.1. Stem and leaf display ~ STEMPLOT
Technika kombinující jednoduché grafické a numerické vyjádření - semigrafická technika:
soubor:
připomíná histogram, ale zde všechny jednotlivé hodnoty jsou zobrazeny a současně při
otočení o 90stupnů je vidět případná asymetrie sloupců.

př.: měření výšky tuku zaměstnanců.
2 proměnné
- výška tuku – FAT
- pohlaví – gender

BOX PLOT

v SAS insight:
analyze – box plot (Y) (závislá proměnný – fat)

SVS
•

přednášky

-6-

Zobrazení četností

proc freq data=dd;
tables fat;
run;

The SAS System

15:20 Tuesday, January 2, 2007

37

Procedura FREQ

•

fat

Četnost

8
12
13
16
18
19
20
21
22
23
24
26
28
30
31

1
3
1
2
1
1
2
2
3
2
1
1
1
1
1

Procenta

Kumulativní
četnost

4.35
13.04
4.35
8.70
4.35
4.35
8.70
8.70
13.04
8.70
4.35
4.35
4.35
4.35
4.35

Kumulativní
procenta

1
4
5
7
8
9
11
13
16
18
19
20
21
22
23

4.35
17.39
21.74
30.43
34.78
39.13
47.83
56.52
69.57
78.26
82.61
86.96
91.30
95.65
100.00

Základní charakteristiky souboru

proc univariate data=dd;
run;
Procedura UNIVARIATE
Proměnná: fat

a. Momenty
N
Průměr
Std odchylka
Šikmost
Nekorigovaný SS
Variační koeficient

b.

23
19.9565217
5.99604613
-0.1011105
9951
30.045547

23
459
35.9525692
-0.3896871
790.956522
1.25026205

Základní statistické míry

Poloha
Průměr
Medián
Modus

Součet vah
Součet pozorování.
Rozptyl
Špičatost
Korigovaný SS
Std chyba průměru

19.95652
21.00000
12.00000

Variabilita
Std odchylka
Rozptyl
Rozpětí
Mezikvartilové rozpětí

5.99605
35.95257
23.00000
7.00000

NOTE: Zobrazený režim je nejmenší z 2 režimů s počtem 3.

SVS

přednášky
c.

-7-

Testy polohy: Mu0=0

Test

-Statistika-

----p hodnota-----

Studentovo t
Znaménko
Znam. pořadí

t
M
S

Pr > |t|
Pr >= |M|
Pr >= |S|

15.96187
11.5
138

<.0001
<.0001
<.0001

Kvantily (Definice 5)
Kvantil
100% max.
99%
95%
90%
75% Q3
50% Medián
25% Q1
10%
5%
1%
0% Min.

d.

Odhad
31
31
30
28
23
21
16
12
12
8
8

Procedura UNIVARIATE
Proměnná:

fat

Extrémní pozorování
----Nejnižší----

----Nejvyšší----

Hodnota

Poz

Hodnota

Poz

8
12
12
12
13

4
17
12
10
1

24
26
28
30
31

13
15
21
22
8

SVS

přednášky

-8-

2.1.1. Sten and leaf display + box plot
přidáním příkazu plot do procedury univariate – vyvolá zobrazení dat.
var proměnná (upřesnění).
proc univariate data=dd plot;
var fat;
run;
Kmen List
#
3 01
2
2 68
2
2 0011222334
10
1 6689
4
1 2223
4
0 8
1
----+----+----+----+
násobit listy větve číslem 10**+1

Krb.graf
|
|
+--+--+
+-----+
|
|

Graf pravděpodobnosti norm. rozdělení
32.5+
* ++*++++++
|
+*+*++++
|
***+*+*+*+*
|
+**+**+++
|
+*++*+*+*
7.5+ +++++*++
+----+----+----+----+----+----+----+----+----+----+
-2
-1
0
+1
+2

• Třídění podle pohlaví
Funkcí class roztřídíme výstupy podle pohlaví.
proc univariate data=dd plot;
class gender;
var fat;
run;
Procedura UNIVARIATE
Proměnná: fat
gender = f
Momenty
N
Průměr
Std odchylka
Šikmost
Nekorigovaný SS
Variační koeficient

10
22.3
5.31350481
-0.6035944
5227
23.8273758

Součet vah
Součet pozorování.
Rozptyl
Špičatost
Korigovaný SS
Std chyba průměru

10
223
28.2333333
0.47746822
254.1
1.68027775

Základní statistické míry
Poloha
Průměr
Medián
Modus

22.30000
22.50000
22.00000

Variabilita
Std odchylka
Rozptyl
Rozpětí
Mezikvartilové rozpětí

5.31350
28.23333
18.00000
5.00000

NOTE: Zobrazený režim je nejmenší z 2 režimů s počtem 2.

SVS

přednášky

-9-

Testy polohy: Mu0=0
Test

-Statistika-

----p hodnota-----

Studentovo t
Znaménko
Znam. pořadí

t
M
S

Pr > |t|
Pr >= |M|
Pr >= |S|

13.27162
5
27.5

<.0001
0.0020
0.0020

Kvantily (Definice 5)
Kvantil

Odhad

100% max.
99%
95%
90%
75% Q3
50% Medián
25% Q1
10%
5%
1%
0% Min.

30.0
30.0
30.0
29.0
26.0
22.5
21.0
14.0
12.0
12.0
12.0

The SAS System

15:20 Tuesday, January 2, 2007

49

Procedura UNIVARIATE
Proměnná: fat
gender = f
Extrémní pozorování
----Nejnižší----

----Nejvyšší----

Hodnota

Poz

Hodnota

Poz

12
16
21
22
22

17
16
20
18
14

23
23
26
28
30

19
23
15
21
22

Kmen List
30 0
28 0
26 0
24
22 0000
20 0
18
16 0
14
12 0
----+----+----+----+

31+
|
|
25+
|
|
19+
|
|
13+

#
1
1
1

1

Krb.graf
|
|
+-----+
|
|
*--+--*
+-----+
|
|

1

0

4
1

Graf pravděpodobnosti norm. rozdělení
*+++
*++++
*+++
+++
* *+*++
* ++++
++++
+*+
++++
++++*
+----+----+----+----+----+----+----+----+----+----+
-2
-1
0
+1
+2

SVS

přednášky

- 10 -

zvolení stonků:
STEM
0
1
2
3

3

8

1

3

2

ženy stem Muži
6
0
8
6
2
1
3
0
2
0
3
1

9
2

8
0

2
1

6
4

2

- u mužů je vyšší variabilita, hodnoty jsou více rozptýleny okolo středu, ale muži mají delší
stone. Technika je výhodná u malých souborů.

SVS

přednášky

- 11 -

2.2. Kvalitativní znaky - procedura gchart
Zde budeme provádět vizualizace údajů o kvalitativních znacích v proceduře gchart – lze
použít sloupcový diagram (bart chart)

Př.:
Základní skript pro grafický výstup.
proc gchart data=jnémo souboru;
hbar jm.kvalitativní zobrazované proměnné /sumvar=hodnota podle které se třídí;
run;

•

hbar_jméno kvalitativního znaku strana / sumvar(sečte hodnoty proměnné podíl) a
rovná se podíl
orientace grafu vodovorně – příkaz hbar (vertikálně bbar)
subgroup – doplňkový příkaz pro barevné odlišení a dole se objeví barevné zastoupení
stran.
descending- pokud chceme sloupečky uspořádat sestupným způsobem, tak do syntaxe
procedury přidáme (ascending)
rozšířený skript pro zobrazený výstup:

proc gchart data=b;
hbar strana/sumvar=podil subgroup=strana descending;
run;

•

2 možnost je pomocí výsečového grafu – koláčový graf
(procedura stejná)

proc gchart data=svs;
pie strana/sumvar=podíl;
run;
pie_ jméno kvalitativní zobrazované proměnné

SVS

přednášky

• Koblihový graf - DONUT
zobrazí podíly a indentifikuje zkratkou jednotlivé kvalitativní proměnné.
proc gchart data=b;
donut strana/sumvar=podil;
run;

•

trojrozměrné výsečové grafy

proc gchart data=svs;
pie3D strana/sumvar=podíl;
run;

• další grafické metody
V sasu lze jednotlivé výseče vyříznout ze zobrazení –
proc gchart data=ms;
pie3D strana/sumvar=podil sice=arrow explode="A" "B";
run;

slice= arrow/inside/none/outside – ovlivňuje popis zvoleného segmentu.
explode =<seznam> -uvádí seznam oddělených segmentů.
“A“ “B“ – chci specielně odtrhnout úseky vztahující se ke stanám A a B.
*komentář – poznámka musí být ukončena středníkem;
arrow – šipky k výsekům

- 12 -

SVS

přednášky

- 13 -

Př.:
proc gchart data=ms;
pie3D strana/sumvar=podil slice=arrow
explode="A" "B";
run;

pozn: úseky které jsou zastoupené méně než 5% SAS sloučí do jednoho - OTHER.

Př.: podniky – počet akcií –
2 proměnné
i.
ii.

kvalitativní – akcie
kvantitativní – počet

absolutní zastoupení proměnné počtu, nikoli procentické.
sumvar=<variable> - počítá součet hodnot danné proměnné
noheading – potlačuje tisk hlavičky (nadpisu)
percent=arrow/…..
value=arrow/inside/none/outside - připisuje jednotlivým segmentům jejich absolutní
hodnoty.
percent – pokud chceme absolutní vyjádření přepočítat na % u jednotlivých akcií.
slice=arrow/inside/none/outside – ovlivňuje popis zvoleného segmentu zobrazované
proměnné.
explode – seznam oddělených segmentůproc gchart data=A;
pie3D akcie/sumvar=pocet noheading percent=arrow value=inside alice=arrow
explode="C";
run;

V soudobé statistické metodologii
se moc nepoužívají – zkreslující
dojem.

SVS

přednášky

- 14 -

Vyjádření pomocí STEM PLOTU
procedura univariate

3. přednáška
proc univariate data=sasuser.fitness mu=50
cibasic normal plot trimmed=2 winsorized=2;
var oxygen;
run;

3.1. průzkumová analýza rozdělení četností
klíčovou roli zde hraje procedura univariate. Doplňkové příkazy:
mu0=50 – tímto příkazem je požadováno provedení testu hypotézy, že průměr
základního souboru stat. znaku OXYGEN je roven 50.
CIBASIC – výpočet intervalů spolehlivosti pro základní statistické char.(požadují
normalitu rozdělení)
NORMAL – výpočet testu normality rozdělení, otestování zdali je rozdělení normální.
(důležité pro test MU=50 a pro výpočet intervalu spolehlivosti).
PLOT – konstrukce visuelních prostředků
TRIMMED – výpočet useknutého průměru spolu s výpočtem intervalu spolehlivosti.
WINSOR – výpočet winsorizovaného průměru spolu s příslušným intervalem
spolehlivosti pro průměr a jednovýběrovým testem hypotézy o hodnotě průměru
prostřednictvím hypotézy nás zajímal výpočet intervalů spolehlivosti.

SVS

přednášky

- 15 -

3.2. výstupy procedury univariate
•
•
•

3.2.1. testy polohy

:

test polohy MU0=50
studentovo t (jednovýběrový ttest) – parametrický test, který požaduje normální rozdělení.
znaménko M – známenkový test – neparametrický test – nepožaduje normalitu rozdělení
Znam pořadí S – jednovýběrový Wilcoksonův test – neparametrický test – nepožaduje
normalitu rozdělení ani symetrii

Pr (0,0102) < 0,05 => H0 se zamítá (MU0=50).

3.2.2. testy normality (záleží na výběru statistika který vybere a použije)
•

•
•
•

Shapiro-wilk – pro malé soubory (obvykle použijeme) n<2000, kvalitní neparametrický
test, ale požaduje symetrické rozdělení četností – symetrický histogram (v souboru nesmí
být odlehlé hodnoty)¨
soubory s n>2000:
Kolmagorov-Smirnov
Cramer von Mises
Anderson darling

Tyto testy testují hypotézu:
H0: soubor má normální rozdělení – P value > 0,05 => Soubor má normální rozdělení
HA: soubor nemá normální rozdělení – P value < 0,05 => Soubor nemá normální rozdělení
Pr (P value) je menší než 5% tak zamítáme H0. U malých souborů (n<30) uvedené testy
mají snahu přijímat HO, uvedené testy jsou slabé a odchylku od normálního rozdělení
mohou potvrdit až u velkých souborů a proto se testu doplňují vhodným grafickým
prostředkem – příkaz PLOT.
PLOT – semigrafická podoba. ~ zobrazí STEM PLOT :
kmen listopad
60 1
58 6
56 36
59 468
44 6896704968
42 5697859607894960
40 8
36 4
Problematické hodnoty jsou maximální 60,1 a 58,6.

SVS

přednášky

- 16 -

Dále se zobrazí graf. pravděpodobnostního rozdělení – graf normálního rozdělení – pokud
jsou hodnoty ideální tak body
splývají s přímkou, ta je znázorněna
křížky a naše data *.

závěr: U testů normality kombinujeme výstup z Shapirova testu s grafikou, zvláště u malých
souborů (do 30). Pokud nám nevyjde normalita rozdělení (ttest), tak užijeme neparametrické
testy.
Neparametrické testy nepožadují, aby analyzovaná data měla normální rozdělení.
Wilkoksonův test je považován za velice kvalitní, ale chce aby soubor měl symetrické
rozdělení četností – symetrický histogram. U nás je v BOX PLOTU problém s odlehlými
hodnotami a v tomto případě dáme přednost znaménkovému testu (nepožaduje ani notmalitu
ani symetrii). Pokud máme v souboru nějaké nesrovnalosti tak soubor modifikujeme.
Provedeme úpravu:
trimmet=2 ~ systém odsekne 2 maximální hodnoty v souboru,ale systém automaticky
odsekne i 2 minimální hodnoty. 31 – 4 = 27 hodnot. Operace „cenzorování“, která u
souborů s malým rozsahem není vždy žádoucí.
winsorized=2 - „winzorizace“ je alternativa k odseknutí - 2 maximální hodnoty byly
nahrazeny třetí maximální hodnotou který byla hned před nimi a na konci se mi objeví 3
stejné hodnoty, které již nejsou považovány zas odlehlé, totéž se provede i u nejmenších
hodnot. Došlo k potlačení extrémů.

•

výstup pro useknutý průměr

Upravené průměry (useknutý nebo cenzorovaný průměr) – vzniklo useknutím dvou hodnot.
meze interval spolehlivosti
45,2
49,03
t pro H0 Pr> t
•

0,0047 (opět H0 zamítáme)

výstup pro winzorizovaný průměr

Průměry se neliší a tudíž obě hodnoty tam nehrají roli a lze je ponechat v souboru.
pozn.: V SAS je zkratka ODS – dovoluje nám z výstupů v systému sas vybrat pouze důležité
výstupy (charakteristiky) a také v lepších formátech.

SVS

přednášky

- 17 -

3.3. procedura MEANS
Další procedura v průzkumové analýze
proc means data=sasuser.fitness;
var oxigen;
run;
-

oxigen je proměnná. Chceme nasadit proceduru na pouze jednu proměnnou
oxigen, jinak by to provedl u všech proměnných.

výstup:
N
31

průměr
47,36

Std odch (směrodatná odchylka)
5,32

min.
37

max
60

poskytuje pouze základná informace o souboru – variabilitu a typickou hodnbotu (průměr).
výstup lze rozšířit:
proc means data=sasuser.fitnes n mean median min max g1 q2 range grange std cv skewness
kurtosis maxdec=3;
var oxygen age weight runtime runpulse runpulse; (u kterých proměnných má počítat)
run;
doplňkové příkazy na vyžádání:
n – počet pozorování
mean – průměr
medián –
Q1 – dolní kvartil
Q3 - horní kvartil
cd – var. koeficient – relativnéí char. variability – směr odch/ průměr* 100 – při porovnání
variability u proměnných vyjádřených v různých jednotkách
std – posílá směrodatnou odchylku
range – variační rozpětí
grange – kvartilové rozpětí – robusní char. variability
skewness – koeficient šikmosti
kurtosis – koeficient špičatosti – signalizuje lehké a těžké konce.
šikmost a špičatost by měla být v případě normálního rozdělení přibližně rovny 0!
maxdec = 3 – počet desetinných míst.

SVS

přednášky

Př.: 13 pozorování a měříme vrstvu podkožního tuku.
proměnná FAT - hodnota tuku
proměnná GENDER –
prohlížení datového souboru – procedura PRINT
proc print data=svs;
var fat gender;
run;
zvlášť spočítat pro muže a ženy:
proc means data=svs;
class (třídení) = gender;
var (pro kterou proměnnou má procedura rpoběhnout) fat;
run;
statistickou významnost mezi ženou a mužem provedeme ttestem:
proc ttest data=svs;
class gender;
var fat; (testujeme z hlediska hodnoty tuku)´
title “porovnání skupin“;
run;
výstup:
T – testy
equal – pokud máme stejné rozptyly souborů, koukáme na tento řádek
unegual – pokud rovnost variancí určí různou variabilitu souborů
dvou výběrový ttest požaduje aby oba soubory měli stejnou variabilitu při porovnání.
doplňkový test pro Ttesty - rovnost variancí – test variability souboru můžu a žen – oba
soubory mají stejný rozptyl.

- 18 -

SVS

přednášky

- 19 -

4. Přednáška - Analýza 2 a více souborů
4.1. 2 výběrový ttest
2 nezávislé náhodné výběry a testujeme hypozézu:
Ho: w1 = w2 => průměry základních souborů w1,w2 (mí)
předpoklady použitelnosti:
1.) nezávislost pozorování
2.) oba výběry mají normální rozdělení
3.) shodná variabilita obou porovnávaných souborů

př.: Je třeba posoudit zda zavedení nové
výrobní technologie má statisticky významný vliv na zvýšení rychlosti
pracovní operace. Bylo provedeno měření doby trvání této operace při staré i
nové technologii a zjištěny tyto výsledky:

Chceme posoudit výsledky z hlediska doby trvání – stat.významnost.

test hypotézy:

Ho: průměry základních souborů se neliší. w1 = w2

1. otestujeme nejprve nezávislost – předpoklad je splněn
2. otestování normality rozdělení:
Každá analýza začíná průzkumovou etapou – průzkumovou analýzou – grafická technika:
analyze – BOX PLOT – staraT/novaT jako Y. Roletka zobrazí další charakteristiky.

SVS

přednášky

- 20 -

4.1.1. schématické box ploty
Př.:

skript:
proc boxplot data=ms;
plot doba*technologie/boxstyle=schematic;
run;

nejsou zde problematické údaje. 1 soubor má zvláštní rozdělení.
Horní kvartil splívá s max. hodnotou. Průměr , medián splynul buď s horním
nebo dolním kvartilem. Medián a průměr se zde odlišují = asymetrie
rozdělení a to stěžuje předpoklad normality rozdělení.

Pro starou technologii je náročné splnit normalitu rozdělení

SVS

přednášky

- 21 -

4.1.2. Zářezové boxploty
– do jaké míry se tyto soubory odlišují, poskytují důkazy na rozdíl od normálních.
proc boxplot data=b;
plot doba*technologie/notched;
run;

Zářezy představují grafické vyjádření intervalu spolehlivosti pro medián.
Začátek zářezů u druhého souboru a konec
pokud se v promítnutí na sebe zářezy nepřekrývají tak to znamená že soubory se statisticky
významně liší a zamítnutí hypotézy Ho. Při překrytí není statisticky významný rozdíl.

SVS

přednášky

4.1.3. Průzkumová analýza pomocí means
Další ověření normality rozdělení:
proc means data=b maxdec=2;
class technologie;
run;
pouze základní charakteristiky:

směrodatná odchylka nové technologie je menší (1,65) – hodnoty jsou
vyrovnanější.
maxdec= zaokrouhlení na libovolný počet desetinných míst
class = rozdělení přístupu do 2 souboru dle technologie.

c)Ověření normality v obou souborech

- užitím testů normality implementovaných v proceduře univariete
ods select TestsForNormality;
proc univariate data=ms normal;
class technologie;
var doba;
run;
nechceme všechny výstupy, ale jen testy normality a proto je omezíme
zkratkou ODS – output delivery systém:
ods select TestsForNormality;

- 22 -

SVS

přednášky

- 23 -

vybereme Shapiro wilka –
u nové technologie: P (0,35) > alfa (0,05) => H0 platí a soubor má normální rozdělení
u staré technologie P(0,0195) < 0,05 => Ha – zamítáme H0 a není splněna normalita.

d) Další ověřování normality
Přes výsledky testů normality bychom měli dále ověřit, protože síla zvoleného testu vynikne
až u velkých souborů a proto konfrontujeme s dalšími grafickými výstupy:
proc univariate data=b noprint;
class technologie;
histogram doba/normal (color=red) kernel (color=green);
probplot doba/normal (mu=est sigma=est);
run;

příkaz noprint – potlačuje nadbytečné numerické výstupy
chceme histogramem proložit gausovu křivku a proto je za doba/normal
kernel – přibalí jádrovou hustotu – představuje empirické vyrovnání hystogramu, chceme
zelenou barvu hustoty.
probplot – chceme doplnit analýzu pravděpodobnostními grafy
mu=est (estimate ~ odhad) – do pravděpodobnostních grafů zobrazí ideální přímku, jak by
měla data vypadat, bez toho se zobrazí pouze křížky a hvězdičky.
sigma (směrodatná odchylka) – odhadnutá z našich dat.

SVS

přednášky

- 24 -

soubor má normální rozdělení,
jádrová hustota a gausova křivka se
tolik neliší – jde o malý soubor.
u staré je diference mezi gausovkou a
jádrovou křivkou velká.

SVS

přednášky

e) Vlastní provedení 2 výběrovéího ttestu
není ale splněn předpoklad normality!
proc ttest data=b;
class technologie;
var doba; (jméno proměnné kterou chci analyzovat)
run;

Průměr je doplněn horní a dolní mezí intervalu spolehlivosti. Diff je rozdíl souborů

- 25 -

SVS

přednášky

- 26 -

rovnost variancí – kontroluje předpoklad stejné variability (stability nebo vyrovnanosti
výsledků) souborů.
pomocná hypotéza: H0 – oba soubory byli pořízeny ve stejné kvalitě a hodnoty jsou stejně
rozházené.
H0: sigma1.2 = sigma2.2
P (0,1165) > 0,05 => H0 platí a předpoklad je splněn a lze se podívat na ttesty:
rozptyl – podle výsledku testu shodnosti rozptylů si vyberu test.
equal – stejné rozptyly
P(0,0158) <0,05 => H0 zamítáme.
unequal – nestejné rozptyly
Ha – průměrné doby nejsou stejné a nová technologie vede k významnému zrychlení té
operace.

f) neparametrický dvouvýběrový ttest.
Řešení problému s nesplněním požadavku na normální rozdělení a ttest byl doplněn
neparametrickým dvouvýběrovým Wilcoxonovým (univerzálnějším) testem
-

neparametrické testy (npar1way)

proc npar1way data=b wilcoxon;
class technologie;
var doba;
run;

SVS

přednášky

- 27 -

Poskytuje základní informace - wilkoksonovo score – nahrazení hodnot pořadovými čísli,
čísla se sečtou zvlášť pro oba soubory. Pokud se soubory neliší, čísla se sobě dost podobají.
Zajímá nás pouze jeden výstup. Normální aproximace:
Jednostranná hodnota
Dvoustranná hodnota

- 0,02 => potvrzujeme Ha.

souvisí s zadáním – testovali jsme H0 : doba S = doba N (průměr) proti jednostrané
alternativě w1<w2. – vyberu jednostranou alternatiuvu.
pokud testuji Ha: w1 nerovná se w2 vyberu oboustranou.
A soubor, respektive nová technologie vede ke kratší době. Potvrdíme ttest parametrický.
Narušení normality nemá až zase zásadní roli, mnohem více ovlivňuje narušení variability. U
obou nesplnění předpokladů se dá použít wilkokson, ale je méně silný než ttest.

SVS

přednášky

- 28 -

5. Přednáška
Porovnání více než 2 souborů z hlediska jejich středních hodnot

5.1. Analýza rozptylu
předpoklady: rozšíření ttestu pro více souborů.
1. analyzované výběry pocházejí ze základních souborů s normálním rozdělením
2. - analyzované soubory mají stejnou variabilitu
někdy nazýván předpoklad homoskedasticity. Opakem (neplatí stejná variabilita) je
heterostedasticita.

Př.:
výrobce zkouší 4 různá barevná a grafická provedení obalů svých
výrobků. Následující údaje představují počty výrobků balených
v různých obalech které byly prodány během jednoho měsíce ve 4
různých hypermarketech. Posuďte zda počet prodaných výrobků
je statisticky významně ovlivňován druhem zvolených obalů.
H0: δ 12 = δ 22 ...δ K2 , K>2
HA: alespoň jeden obal vede k jiným výsledkům.
2 proměnné:
prodej – kvantitativní
obal - kvalitativní
výběry nemají stejné počty pozorování – nevyvážený model.
H0: m1=m2=m3=m4
SAS: 2 možnosti analýzy –
a) proc anova (analysis of Variance) - lze použít pouze pro vyvážený model.
b) pro nevyvážený i vyvážený lze použít – univerzální proc.
proc glm (general linear model)
Začneme opět průzkumovou analýzou a naše výběrové soubory si zobrazíme☺
pozn: u malých souborů není analýza rozptylu zkreslována – robusnost. A.R je odolná na
narušení normality!!!
1.) zářezové box ploty – pro posouzení odlehlostí atd. Porovnáváme soubory mezi sebou,
pokud soubory dáme přes sebe a vruby se nepřekrývají, tak se soubory pravděpodobně od
sebe odlišují, jde pouze o orientační pomůcku.
proc boxplot data=dm;
plot prodej*obal/boxstyle=schematic notches;
run;

SVS

přednášky

- 29 -

/boxstyle –
schematic –
notches – zářezy na krabičce

horní kvartyl
dolní kvartil

medián –
křížek – průměr
hranice souboru – interval spolehlivosti pro medián
netypická hodnota (extrémní)
Nejlépe se prodává z hlediska průměrného počtu – 2, nejméně atraktivní je obal č.4.
2.)
proc glm data=dm;
class obal;
model prodej=obal;
means obal/hovtest t tukey lines cldiff;
run;

class – třídící proměnná
jak prodej závisý na obalu (analyzovaná = klasifikační)
means – chceme průměry pro obal• hovtest – ověření předpokladu stejné variability.
• t (lsd) – nejmenší významný rozdíl (pokud zamítneme H0, umožní interpretovat
odlišný soubor) – jak jeden soubor dopadne v porovnání s ostatními.
• tukey – srovnání všech diferencí každý s každým

SVS

přednášky
•
•

- 30 -

lines
cldiff

pozn.: metody mnohonásobného porovnávání – pro rozlišení souborů a idenfifikace odlišností
od ostatních souborů. V sasu asi 15, např.:
• t metoda
• tukey metoda (T)
Výstup lze mít ve dvojí formě – vyžádáme požadavkem lines nebo cldiff.
pozn.: Je třeba rozlišit mezi plánovaním porovnávání porov.souborů nebo následné
porovnávání.
plánované se týká situace, kdy před analýzou si vytipuji jeden (je zajímavý) a ten chci
porovnat s ostatními. V tomto případě metoda lst. Pokud chceme porovnat soubory všechny
mezi sebou ~ následné srovnávání (posthok) vyberu metodutukey.
The SAS System

10:46 Wednesday, January 31, 2007

1

The GLM Procedure
Class Level Information
Třída

Úrovně

Hodnoty

obal

4

1 2 3 4

Number of Observations Read
Number of Observations Used

The SAS System

20

10:46 Wednesday, January 31, 2007

2

The GLM Procedure
Závislá proměnná: prodej
Zdroj

DF

Součet
čtverců

Průměrný
kvadrát

F
hodnota

Pr > F

Model

3

105585.0000

35195.0000

6.58

0.0042

Chyba

16

85595.0000

5349.6875

Korigovaný součet

19

191180.0000

H0 se zamítá (0,0042< 0,005) Platí Ha – existuje statisticky významný
rozdíl

Odmocnina

SVS

přednášky

- 31 -

R-kvadrát

Koef prom

MSE

prodej Průměr

0.552281

10.77195

73.14156

679.0000

Zdroj

DF

Type I SS

Průměrný
kvadrát

F
hodnota

Pr > F

obal

3

105585.0000

35195.0000

6.58

0.0042

Zdroj

DF

Type III SS

Průměrný
kvadrát

F
hodnota

Pr > F

obal

3

105585.0000

35195.0000

6.58

0.0042

koeficient determinace – z kolika % je závisle proměnná (závisí) je
ovlivňována tou nezávislou proměnnou (obalem) ~ 55%.
- Obal z 55% ovlivňuje množství prodaných výrobků.

doplňková syntaxe za / :

hovtest:
testuje pomocnou hypotézu na shodu rozptylů.
The GLM Procedure
Levene's Test for Homogeneity of prodej Variance
ANOVA of Squared Deviations from Group Means
Zdroj

DF

Součet
čtverců

Průměrný
kvadrát

F
hodnota

Pr > F

obal
Chyba

3
16

7.1431E8
2.1606E9

2.381E8
1.3504E8

1.76

0.1946

Přijímáme H0 – neexistuje stat. významný rozdíl mezi variabilitou.

SVS

přednášky

- 32 -

nyní je třeba ujasnit, které obaly vyčnívají:

LSD:
The GLM Procedure
t Testy (LSD) pro prodej
NOTE: Tento test určuje četnost srovnávací chyby typu I , nikoli četnost experimentální
chyby.
Alfa
0.05
Error degrees of freedom
16
Střední kvadrát chyby
5349.688
Kritická hodnota t
2.11991
Least Significant Difference
99.08
Harmonic Mean of Cell Sizes 4.897959
NOTE: Cell sizes are not equal.
Průměry se stejným písmenem nejsou významně odlišné.
t Seskupování

Průměr

N

obal

A
A
A

766.00

5

3

720.00

5

2

C
C
C

650.00

6

1

562.50

4

4

B
B
B

Least Significant Difference - nejmenší významný rozdíl. Pokud průměr
překročí hodnotu, je statistycky významný. Průměry se stejným číslem se
neliší. B jsou označeny obaly 2 a 1 a od sebe se významně neodlišují. 1 a 4
obal se od sebe také neliší, mají stejné písmeno C. 3 a 4 obal se odlišily
statisticky významně.

tukey:
The SAS System

10:46 Wednesday, January 31, 2007

7

The GLM Procedure
Tukeyho test studentizovaného rozsahu (HSD) pro prodej
NOTE: Tento test určuje četnost experimentální chyby typu I , obecně však má vyšší četnost
chyby
typu II než REGWQ.
Alfa
0.05
Error degrees of freedom
16
Střední kvadrát chyby
5349.688
Kritická hodnota studentizovaného rozsahu 4.04609
Minimální rozdíl významnosti
133.72
opatrnější – významný průměr je vyšší.
Harmonic Mean of Cell Sizes
4.897959
NOTE: Cell sizes are not equal.
Průměry se stejným písmenem nejsou významně odlišné.

SVS

přednášky

Tukey Seskupování

Průměr

N

obal

A
A
A
A
A

B
B
B

- 33 -

766.00

5

3

720.00

5

2

650.00

6

1

562.50

4

4

Cldiff – ekvivalence k předchozím 2 výstupům:
The GLM Procedure
t Testy (LSD) pro prodej
NOTE: Tento test určuje četnost srovnávací chyby typu I , nikoli četnost experimentální
chyby.
Alfa
0.05
Error degrees of freedom
16
Střední kvadrát chyby
5349.688
Kritická hodnota t
2.11991

Srovnání významnosti při úrovni 0.05 jsou indikovány ***.

obal
Srovnání

Rozdíl
mezi
průměry

95% Confidence
Limits

3 - 2
3 - 1
3 - 4
2 - 3
2 - 1
2 - 4
1 - 3
1 - 2
1 - 4
4 - 3
4 - 2
4 - 1

46.00
116.00
203.50
-46.00
70.00
157.50
-116.00
-70.00
87.50
-203.50
-157.50
-87.50

-52.06
22.11
99.49
-144.06
-23.89
53.49
-209.89
-163.89
-12.59
-307.51
-261.51
-187.59

The SAS System

144.06
209.89
307.51
52.06
163.89
261.51
-22.11
23.89
187.59
-99.49
-53.49
12.59

10:46 Wednesday, January 31, 2007

***
***
***
***
***
***
5

The GLM Procedure
Tukeyho test studentizovaného rozsahu (HSD) pro prodej
NOTE: Tento test určuje četnost experimentální chyby typu I.
Alfa
0.05
Error degrees of freedom
16
Střední kvadrát chyby
5349.688
Kritická hodnota studentizovaného rozsahu 4.04609

SVS

přednášky

- 34 -

Srovnání významnosti při úrovni 0.05 jsou indikovány ***.

obal
Srovnání

Rozdíl
mezi
průměry

Souběžné 95%
Confidence Limits

3 - 2
3 - 1
3 - 4
2 - 3
2 - 1
2 - 4
1 - 3
1 - 2
1 - 4
4 - 3
4 - 2
4 - 1

46.00
116.00
203.50
-46.00
70.00
157.50
-116.00
-70.00
87.50
-203.50
-157.50
-87.50

-86.35
-10.71
63.12
-178.35
-56.71
17.12
-242.71
-196.71
-47.58
-343.88
-297.88
-222.58

178.35
242.71
343.88
86.35
196.71
297.88
10.71
56.71
222.58
-63.12
-17.12
47.58

***
***

***
***

Závěr: pokud test homogenity nevyjde stejně nebo máme pochybnosti,
proceduru nahradím neparametrickým testem kruskal walis.
Kruskal – Wallisův – nezávislý na 1 a 2 předpokladu a ale nemá takovou
sílu.

proc nparlway data=dm wilcoxon;
class obal;
var prodej;
run;
H0: se zamítá a platí Ha a výsledky z glm lze považovat za platné.

6p.
1. Analýza vícerozměrných statistických souborů
-

na souboru zkoumáme větší počet znaků

SVS

přednášky

- 35 -

1.1. Jednoduchá regresní a korelační analýza
Zkoumáme statistickou závislost a její sílu.
• Y – závisle proměnná (vysvětlovaná proměnná)
• X – nezávislá proměnná (vysvětlující proměnná ~ regresní)
Regrese – průběh (tvar) závislosti.
Korelace – určení těsnosti závislosti.
Předpoklady použitelnosti regresní a korelační analýzy:
1.) Normalita rozdělení analyzovaných veličin (alespoň přibližně splnit)
2.) požadavky na rezidua – nezávislé náhodné veličiny které mají normální rozdělení
s nulovou střední hodnotou a konstantní rozptyl.
proměnné Y;X - regres.f : Y´ = a + bX
korelační pole

5

korelační pole

R
_
C

0

O
-5

10
8

10

12

14

P_CO

16

18

- body na přímce porovnáme se skutečnými.
rozdíl: Yi - Y´i = rezidua.

SVS

přednášky

- 36 -

Ex= 0 - kladná a záporná rezidua se vyruší, protože korelační funkce je proložena nejlepším
možným způsobem, ani blíž ani dál od jedné strany.
Př.: CO = auta
proc reg –
proc corr –
proc univariate –
1.1.1.

A) průzkumová analýza

proc gplot data=ms;
plot co*cars;
symbol v=dot c=blue; /*specifikace grafu*/
run;
quit;

plot závisle proměnná (osa Y) * nezávisle proměnná.
symbol – doplňkový příkaz:
V = dot (tečky), star atd.
C = barva bodů
quit – výstup z jednotlivých procedůr.

Zvýšení auto -> zvýšení CO.
Odhad ukazuje přímou a střední závislost až silnou závislost, odlehlé pozorování – může
skreslit analýzu.

SVS

přednášky
1.1.2.

- 37 -

B) Posouzení normality

ods exclude Moments BasicMeasures TestsForLocation Quantiles ExtremeObs;
proc univariate data=ms normal plot;
run;
quit;
ods exlude – vyloučení nežádoucích výstupů.
V procedůře testujeme normalitu – NORMAL.
The SAS System

10:59 Sunday, January 7, 2007
Procedura UNIVARIATE

Proměnná:

1

co

Testy normality
Test

--Statistika--

----p hodnota-----

Shapiro-Wilk
Kolmogorov-Smirnov
Cramer-von Mises
Anderson-Darling

W
D
W-Kv
A-Kv

Pr < W
Pr > D
Pr > W-Kv
Pr > A-Kv

0.961221
0.126052
0.035129
0.213003

Kmen List
22 3
20 5
18 6
16 25
14 6
12 2
10 07
8 9
6 1
4 9
----+----+----+----+

23+
|
|
17+
|
|
11+
|
|
5+

#
1
1
1
2
1
1
2
1
1
1

0.8011
>0.1500
>0.2500
>0.2500

Krb.graf
|
|
+-----+
|
|
|
|
*--+--*
|
|
+-----+
|
|

Graf pravděpodobnosti norm. rozdělení
+*++
*+++
*+++
*+*++
*++
++*+
+*+*
++*+
++*
+*++
+----+----+----+----+----+----+----+----+----+----+
-2
-1
0
+1
+2

U malých souborů – předpoklad normality je splněn.
Medián – přibližně by se měl nacházet uprostřed krabice s vousy.
Graf pravděpodobnosti norm. rozdělení – opět ukazuje na rozdělení N.
U obou proměnných je předpoklad normality splněn.

SVS

přednášky

The SAS System

- 38 -

10:59 Sunday, January 7, 2007

2

Procedura UNIVARIATE

Proměnná:

cars

Testy normality
Test

--Statistika--

----p hodnota-----

Shapiro-Wilk
Kolmogorov-Smirnov
Cramer-von Mises
Anderson-Darling

W
D
W-Kv
A-Kv

Pr < W
Pr > D
Pr > W-Kv
Pr > A-Kv

0.953396
0.154158
0.03722
0.252849

Kmen List
3 1
2 5889
2 123
1 567
1 1
----+----+----+----+

3.25+
|
2.25+
|
1.25+

1.1.3.

#
1
4
3
3
1

0.6870
>0.1500
>0.2500
>0.2500

Krb.graf
|
+-----+
*--+--*
+-----+
|

Graf pravděpodobnosti norm. rozdělení
+++*++++
* *+++++*+
*+*+*+++
*++*++*+
+++*++++
+----+----+----+----+----+----+----+----+----+----+
-2
-1
0
+1
+2

C) corelační analýza

proc corr data=ms; /*výpočet korelace mezi analyzovanými proměnnými s proc
CORR*/
run;
quit;
Spočtou se korelace mezi všemi proměnnými, mezi dvojicemi. V souboru jsou jen 2
proměnné a zde je to tudíž žádoucí. U př. s více proměnnými je takový výstup
nežádoucí a je třeba upřesnit příkazem VAR.

The SAS System

10:59 Sunday, January 7, 2007

4

SVS

přednášky

- 39 -

Procedura CORR
2

Proměnná

N

Průměr

co
cars

12
12

13.79167
2.21667

Proměnné:

co

cars

Jednoduché statistiky
Std odch
Součet
5.62615
0.63509

165.50000
26.60000

Minimum

Maximum

4.90000
1.10000

22.30000
3.10000

Pearsonovy korelační koeficienty, N = 12
Prob > |r| pro H0: Rho=0
co

cars

co

1.00000

0.72923
0.0071

cars

0.72923
0.0071

1.00000

logická kontrola hodnot MIN/MAX
korelační matice - diagonála - maximální korelace mezi proměnnou CO a Cars.
síla závislosti mezi 2 proměnnými – korelace <-1; 1> ~ nepřímá závislost/přímá: 0.72923 -středně
silná
P hodnota – H0: Rho = 0 - 0,05 > 0,0071 -> HA. model je statisticky významný.
- určí statistickou významnost nejen pro náš výběr, ale pro celý základní soubor. Pokud není stat.
významný (platí H0), tak výsleek platí pouze pro našich 12 měření a výsledky nejsou zobecnitelné.
pozn.:
výbrová korelace – r
korelace v ZS - „RO“
Pokud není splněna normalita, tak použijeme Spearmanův koeficient koeralce – neparametrický koeficient.
proc corr data=ms spearman;
run;
quit;
Máme tedy významný model a středně silnou závislost.

1.1.4.

D) nalezení regresní přímky

proc reg data=ms;
model co=cars;
run;
quit;
model vysvětlovaný=vysvětlující.
The SAS System

10:59 Sunday, January 7, 2007
Procedura REG
Model: MODEL1
Závislá proměnná: co
Number of Observations Read
Number of Observations Used

12
12

6

SVS

přednášky

- 40 -

Analýza rozptylu
Zdroj

DF

Součet
čtverců

Průměr
Kvadrát

F
hodnota

Pr > F

Model
Chyba
Korigovaný součet

1
10
11

185.15953
163.02963
348.18917

185.15953
16.30296

11.36

0.0071

Odmocnina MSE
Závislý průměr
Koef prom

4.03769
13.79167
29.27632

R-kvadrát
Přizp R-kv

0.5318
0.4850

analýza rozptylu – Ověření zobecnění pro ZS. informuje o tom, zda regresní přímka je platná
i pro základní soubor a ne pouze pro náš výběr. Hodnotí model jako celek.
H0: pouze výběrový charakter – není zobecnitelné
HA: model je statisticky významný a model je zobecnitelný.
koef. determinace R2 = 53,1% Z kolika procent jsou změny závisle proměnné vysvětlitelné
nezávislou proměnnou. Emise jsou z 53% vyvolány frekvencí projíždějících aut.
Odhady parametrů

•
•

Proměnná

DF

Odhad
parametru

Standardní
chyba

t hodnota

Pr > |t|

Regresní
carstanta

1
1

-0.52840
6.46018

4.40615
1.91692

-0.12
3.37

0.9069
0.0071

intercept (regresní) – a absolutní člen
regresní koeficient – b (stejné znaménko jako korelační) – hodnota říká, o kolik se v průměru
změní závisle proměnná když se nezávisle proměnná změní o jednotku.

o 1000 vozů více -> CO naroste o 6,46

individuální p hodnoty – hodnotí jednotlivé složky
• absolutní člen
0.9069 – není stat. významný
• regresní člen
0.0071 – je statisticky významný.
• jako celek je to stat. významné.
U ideálního je všechno významné. Současný model je použitelný, ale ne 100%.
1.1.5. E) Zkooumání vlastností reziduí
proc reg data=ms;
model co=cars/r influence spec; /*r - studentizovaná rezidua a cookova
vzdálenost,*/
plot co*cars/cframe=pink; /*pozadí grafu - cframe*/
plot r.*p.; /*reziduální graf*/
plot cookd.*p./cframe=ligr;

SVS

přednášky

- 41 -

symbol v=dot c=green h=1;
output out=diag r=rezid; /*vytvoření nového souboru Diag */
run;
quit;

8.p
2. Vícenásobná regrese a
korelace
Př: studenti
do jaké míry je ovlivňována proměnná
body (Y) proměnnou hodiny a IQ.
Zajímá nás společné kombinované působení
obou veličin na absolutní člen.

pozn.: pouze 2 proměnné – Y….(X) ~ JEDNODUCHÁ REGRESE A KOR. r <-1, 0>
Y……(X1,X2…..Xk) ~ vícenásobná reg a korelace.
1.) změření těsnosti závislosti – korelace
• koef.mnohonásobné korelace R (v jed. r) <0, 1>
• koeficient mnoh. determinace R2 - z kolika % je y vysvětlováno veličinami X1
až Xk.
2.) průběh těsnosti – regrese – hledáme rovnici která popíše závislost Y a ostatních
proměnných. Regresní přímka:
Y´= b0+b1 X1+ …. bKXK
b0= absolutní člen
b1= parciální regresní koeficient, charakterizují část vlivů působící na příslušnou proměnnou X.

2.1. Předpoklady použitelnosti mnohonásobné regrese a korelace:
a. normalita rozdělení analyzovaných proměnných
b. nezávislost vysvětlujících proměnných – každá proměnná přispěje novou informací
k vysvětlení veličiny Y.

Y´= b0+b1 X1+ b2X2

SVS

přednášky

- 42 -

Ověření multikolinearity:
i. spočtu korelační matici vysvětlujících proměnných:
X1
X1
X2
.
Xk

X2
1 r x1x2

….

Xk
r x1 xk

1
1
1

|r xj xk | < 0,75
|r xj xk | > 0,75 ~ multikolinearita - hodnota korelačního koef.
ii. v SASU – VIF – Variance Inflation Factor VIF > 10 ~ multikolinearita.
c. Rezidua, tvz rozdíly Yi – Yi` , i = 1,2,3…n by měla mít normální rozdělení s nulovou
stření hodnotou a konstantním rozptylem a konstantním rozptylem.
- konstantní rozptyl – čím je variabilita větší, tím jsou hodnoty kolísavější a méně přesná
- normální rozdělení říká, že odhadnutá regresní přímka leží zhruba ve středu hodnot
(naměřených).
2.2. testování:
začneme posouzením normality vstupních dat – univariate (test lze vynechat v případě malých
souborů, uvedené testy Shapiro-wilk atd jsou kvalitní až od n>30.)

v tomto případě zbytečné – málo dat! Lépe přes box
plot atd.
The SAS System

10:42 Sunday, January 14, 2007
Proměnná:

6

Procedura UNIVARIATE
R_hodiny (hodiny residuals)
Testy normality

Test

--Statistika--

----p hodnota-----

Shapiro-Wilk
Kolmogorov-Smirnov
Cramer-von Mises
Anderson-Darling

W
D
W-Kv
A-Kv

Pr < W
Pr > D
Pr > W-Kv
Pr > A-Kv

0.939701
0.200058
0.058844
0.340696

Kmen List
#
1 7
1
1 0
1
0 8
1
0 334
3
-0 2
1
-0 5
1
-1
-1 6
1
-2 3
1
----+----+----+----+
násobit listy větve číslem 10**-1

0.5497
>0.1500
>0.2500
>0.2500

Krb.graf
|
|
+-----+
*--+--*
|
|
+-----+
|
|
|

SVS

přednášky

0.175+
|
|
|
-0.025+
|
|
|
-0.225+

- 43 -

Graf pravděpodobnosti norm. rozdělení
++*+
++++
++*+ *
*+*++*
* *+++
++++
++++
++++ *
+++++ *
+----+----+----+----+----+----+----+----+----+----+
-2
-1
0
+1
+2

veličina IQ nemá normální rozdělení a proto není ideální použití pearsonova koef. a proto do
skriptu zahrneme ještě spearmana.
– spočte difoltně spearmena:
proc corr
var_ proměnné pro které chci provést výpočet.
run;
quit;
bez příkazu Var spočte všechny korelace proměnných.
– spočtění korelační matice:
proc corr data=ms pearson spearman;
run;
quit;

– rozšířený model mnohonásobné regrese
influence – zjistí, jestli v množině vysvětlujících proměnných není nějaká
odlehlá hodnota.
- Leverage( vliv) – hii –
- DFFITS – Welschova kulova vzdálenost – opět posouzení vlivnost
r – vlivnost a odlehlost
spec – spočte tvz Whiteův test – umožňuje posoudit konstantní rozptyl
reziruí.
plot r. *p. – konstrukce reziduálního grafu, orientační posouzení vlastností
plot cookd. *p. – graf hodnot cookovi vzdálenosti
symbol - provedení grafů : v=dot (tečky) c=green;
output - vytvoříme pomocný soubor: out=diag (název souboru) r=rezid; a
s jeho pomocí chceme kontrolovat vlastnosti reziduí, obsahuje jedinou
proměnnou nazvanou rezid – rezidua.

SVS

přednášky

Proc reg data=ms corr;
model body=hodiny iq/r influence vif spec;
plot r. *p.;
plot cookd. *p.;
symbol v=dot c=green;
output out=diag r=rezid;
run;
quit;

Proc reg data=ms corr;
model body=hodiny iq/r influence vif spec;
plot r. *p.;
plot cookd. *p.;
symbol v=dot c=green;
output out=diag r=rezid;
run;
quit;
cokova vzdálenost je obecnější – do jaké míry to pozorování ovlivňuje celý model
DFFITS - do jaké míry to nalezené pozorovaní ovlivňuje tu jednu konkrétní hodnotu
veličiny Y, kde byla vlivná hodnota nalezrna.

- 44 -

SVS

přednášky

10.P

Vícenásobná regrese
Y = a + bX

+ cX2

Y = b0 + b1 X1 + b2 X2
Př.:
proc gplot data=A;
plot spotreba*rychlost;
symbol v=dot c=blue;
run;

2 vysvětlující proměnné
X1 – původní rychlost vozu
X2 – rychlost2
1. průzkumová analýza

- 45 -

SVS

přednášky

mod insight: pro lineární model.

pozn.:
vyžádání souboru – procedura PRINT – zobrazí soubor na který se chci
podivat.
proc print data=svs;
var spotreba rychlost…
run;

synraxe:
proc svs1;
set svs;
rychlost2=rychlost*rychlost;
proc reg data=svs1;
LINEAR: model spotreba=rychlost;
plot spotreba*rychlost;
plot r.*p.;
symbol v=dot c=red h=1;
QUADRATIC: model spotreba=rychlost rychlost2/r influence spec;
plot r.*p.;
plot cookd.*p.; - nakreslí graf cook.vzdáklenosti. Osa X(predikované
hodnoty, osa Y (cook.vz) ~ pro kterou vyrovnanou hodnotu se objevil
problém.
plot cookd.*obs.; - pro které pozorování se problém objevil.
run;

- 46 -

SVS

přednášky

- 47 -

plot r.*p.; / konstrukce reziduálního grafu.
plot cookd – chark kooovy vzdalenosti

výstupy:

model: LINEAR

• statisticky významný.
• R2 = 0,6273
plot r.*p.; - reziduální graf modelu.

Podle reziduí se dá usuzovat, že model lineární není, ideální průběh
reziduí u lin.modelu zobrazuje obdélník.

model: Quadratic
• statisticky významný.
• R2 = 0,98 ~ 98% - variabilita proměné spotřeba je z 98% vysvětlená proměnnou spotřeba.
• odhady parametrů – individuální P-hodnoty jsou sta.významné.

Výstupové statistiky/ Výstupy regresní diagnostiky – posouzení kvality modelu
QUADRATIC: model spotreba=rychlost rychlost2/r influence spec;

SVS

přednášky

- 48 -

• studentizovaná rezidua – podává informaci, zda ve vysvětlované proměnné nebyla nějaká
hodnota, která by narušila model (extrém nebo odlehlost) - hodnoty ve sloupci porovnáme s
/SR/ >2, nebo z hvězdičkovým výstupem ****, v modelu nebyla nalezena Y hodnota která
by model zkreslila. Případný údaj je třeba ještě otestovat na vlivnost.
• cookovo D - cookova vzdálenost
určí že pozorování je nejen odlehlé, ale i vlivné. Hodnotí kombinace veličiny Y, X a X2
Jak vlivné pozorování ovlivňuje všechny hodnoty Y.
○ ukazuje vlivnost v globále, je ovlivněna počtem pozorování
○ D > 4
n

○ D > 0,5 = vlivné pozorování - pozorování č.8,
• DFFITS (lepší test než cookova vzdálenost) – Welschova-kuova vzdálenost
Říká jakým způsobem vlivné pozorování ovlivnilo pouze pozorování Y8.
○
p
| DFFITS

|> 2

n

= 0 , 80

p=3
n=8
○ |DFFITS| > = vlivné pozorování
p – počet parametrů regresního modelu. (b0, b2, b3)
opět identifikovala pozorování č.8 jako vlivné.

• Hat Diag H – klobouková matice
○

H ii > 2 ⋅

p
3
6
= 2⋅ =
= 0 , 75
n
8
8

n – počet měření
p – počet regresních parametrů (a, b = 2)

Ve sloupci žádný takový údaj není.
Provedeme kontrolu údajú a ….

test první a druhé specifikace momentu – výstup Whiteůva testu
kontroluje předpoklad použitelnosti modelu – zda rezidua (rozdíl závislé proměnné a
predikované) mají konstantní rozptyl.
• P-hodnota: 0,15 P.hot > 0,05 => H0.
H0: rezidua mají konstantní variabilitu.

SVS

přednášky

- 49 -

11.p
Kromě zkoumání kvantitativních proměnných je možné se zabývat zkoumáním kvatitativních
proměnných. Jejich obměny nejsou vyjádřeni číselně.

Kategoriální proměnné (Kvalitativní)
např.:
vzdělání – ZS, SS, VS
národnost
kvalifikace
barva očí
základní pojmy: (různé členění)
1) typy kvalitativních znaků:
a. alternativni znaky (pouze 2 obměny – pohlaví)
b. množné (vzdělání atd.)
2) nominální znaky – jednotlivé varianty znaku můžeme pouze pojmenovat, ale
nedají se utřídit např od nejmenší k největší. (národnost)
3) ordinální znaky – znaky lze pojmenovat a zároveň jdou setřídit na stupně.
(vzdělání, kvalifikace)
Analýza kvalitativních znaků:
znak A, B
A – A1, A2……….Ak
B- B1,B2,………..Bm zkoumání je založeno na sestavení kontingenční tabulky kx m
BN1

m

BN 2

n11 n12 KKK n1m
n21 n22 KKK n2 m
M
M

nij

M

k

M
M
M

nk 1 n k 2 KK K nkm

nij – empirické (experimentální četnosti) - kolikrát se společně vyskytla varianta A1, B1
společně.
2 základní úkoly:
I. posouzení závislosti kategoriálních znaků
II. určení síly závislosti (těsnosti)
III. ¨

SVS

přednášky

- 50 -

použití 2 testů:
chí kvadrát – vyžaduje spočítat očekávané četnosti, na základě velikosti těch
očekávaných četností se rozhodneme o užití testu. Tečkový způsob zápisu.

χ = ∑∑
2

k

( nij − oij )2
oij

m

počet stupňů volnosti
f = ( k − 1 )( m − 1 )
f = 1⋅1 = 1
○ tabulková hodnota
χ 02,05 ;1 = 3,841
○ porovnání vypočtené a tabulkové hodnoty
2
χ 2 < χ dif

⇒ H 0 nazamítáme

2
χ 2 > χ dif

⇒ H 0 zamítáme
existuje závislost a můžeme prokázat její těsnost

v SASU porovnáváme vypočtenou hladinu významnosti (P value). SAS se řídí heslem
všechno se může hodit a vyhodí vše co umí, je třeba si vybrat vhodnou charakteristiku.
p <α

⇒ H 0 zamítáme

H0: kvalitativní znaky A a B jsou nezávislé.
očekávané četnosti – počítají se z marginálních četností
n i • ⋅ n• j
o ij =
n

• chí kvadrát pro kontingenční tabulku k X m se nedá použít, jestli že více než 20%
očekávaných četností je < 5, případně když alespoň v jednom políčku kontingenční tabulky
je očekávaná četnost < 1. V těchto případech je nutno některé sousedící skupiny spojit
(řádky nebo sloupce).
Výstupy ~ 2 typy:
o chí kvadrátové míry těsnosti závislosti – odvozeny od tesu chí kvadrát

Cramerovo V
V =

χ2
n (k − 1; )
pokud H0 nezamítáme nemá smysl počítat těsnost závislosti

SVS

přednášky

- 51 -

K = menší hodnota z počtu řádků a sloupců.
•

0 ≤ |V| < 0,3 – velmi slabá závislost
0,3 ≤ |V| < 0,8 (0,75) – střední závislost
0,8 ≤ |V| < 1 – velmi silná závislost

U tabulky 2X2 je třeba rozhodovat vždy v absolutní hodnotě.
zásadní nevýhodou chí kvadrát testů závislosti je to, že nemají statistický obsah.
Příklad: V = 0,56 – střední závislost, ale samo o sobě to číslo
neznamená nic. Na rozdíl od r2 který vysvětluje variabilitu závislé proměnné.
Nerozlišuje jestli zkoumané znaky jsou nominální nebo ordinální, dále
nerozlišuje jestli znak je závisle nebo nezávisle proměnná.
o Predikční míry – míry typu PRE (proportionale reduction error) – mají překonat
zmiňované nevýhody. Testy pouze pro znaky nominální/ordinální.Charakteristiky rozlišují
mezi závislou a nezávislou (asimetrické) .
pozn.: vstupní tabulka 2x2 – Asociační tabulka
pohlaví / souhlas
M
Ž

ANO
B
C

NE
B
D

zvláštnosti – chí kvadrát test dává spolehlivé výsledky pouze pro dostatečně velké rozsahy
výběru.
Pro n<20 jsou výsledky obvykle velmi nepřesné a tento test by se neměl
používat.
pro 20<n<40 se test chí doporučuje používat pouze tehdy, jestliže žádná
očekávaná četnost není menší než 5.
n>40
pokud nepoužijeme test Chí kvadrát, použijeme Fisherův test.
Fisherův přesný test
Buňka (1,1) Četnost (F)
Levostranný Pr <= F
Pravostranný Pr <= F

10
0.9956
0.0521

Tabulková pravděpodobnost (P)
Dvoustranný Pr <= P

0.0477
0.0623

Velikost výběru = 20

SVS

přednášky

- 52 -

Př.:
Bylo sledováno zda pravidelná účast studentů na přednáškách má vliv na úspěch v prvním
termínu u ZK. Ověřte zda existuje závislost mezi znaky.
účast/ uspěch
Ano
ne

ANO
30
10

NE
15
25

Tři proměnné: proměnná počet je kvantitativní.Úspěch a účast jsou kvalitativní.

Příslušná procedura:
proc freq data=ms;
tables uspech*ucast/expected norow nocol nopercent chisq measures;
weight pocet;
run;

tables jméno_řádkové proměnné(úspěch)* sloupcová proměnná
weight– jméno kvantitativní proměnné. Bez ní by byli všechny četnosti nahrazeny 1.
/:
expected – vyžádání očekávaných četností, kůli zvolení testu.
norow,nocol ,nopercent – vyjadřují procentické zastoupení v řádcích, sloupcích a celkové.
Tímto je potlačujeme.
chisq – vytištění testového kritéria chí.kvadrát
measures – predikční míry
The SAS System

11:33 Sunday, January 28, 2007
Procedura FREQ
Tabulka pro uspech podle ucast
uspech

ucast

Četnost ‚
Očekávaná‚ano

‚ne

‚ Součet

ano

‚
‚

30 ‚
22.5 ‚

15 ‚
22.5 ‚

45

ne

‚
‚

10 ‚
17.5 ‚

25 ‚
17.5 ‚

35

40

40

80

Součet

Splňuje podmínky pro užití chí kvadrát testu, 80>20

1

SVS

přednášky

- 53 -

Statistiky pro tabulku uspech na ucast
Statistika

DF

Hodnota

Pr

Chí-kvadrát
Chí-kvadrát poměru věrohodností
Spojitě přizp. Chí-kvadrát
Mantel-Haenszelův Chí-kvadrát
Koeficient Fí
Kontingenční koeficient
Cramerovo V

1
1
1
1

11.4286
11.7384
9.9556
11.2857
0.3780
0.3536
0.3780

0.0007
0.0006
0.0016
0.0008

p (0,0007) < α

⇒ H 0 zamítáme

Prokázali jsme závislost mezi účastí na

přednáškách a ZK.
0,3 ≤ |V | < 0,8 (0,75) – střední závislost
Fisherův přesný test
Buňka (1,1) Četnost (F)
Levostranný Pr <= F
Pravostranný Pr <= F

30
0.9999
7.164E-04

Tabulková pravděpodobnost (P) 5.889E-04
Dvoustranný Pr <= P
0.001

The SAS System

11:33 Sunday, January 28, 2007

2

Procedura FREQ
Statistiky pro tabulku uspech na ucast
Statistika

Hodnota

ASE

Gama
Kendallovo Tau-b
Stuartovo Tau-c

0.6667
0.3780
0.3750

0.1361
0.1031
0.1027

Somersovo D C|R
Somersovo D R|C

0.3810
0.3750

0.1038
0.1027

Pearsonova korelace
Spearmanova korelace

0.3780
0.3780

0.1031
0.1031

Lambdaasymetrické C|R
Lambdaasymetrické R|C
Lambdasymetrické

0.3750
0.2857
0.3333

0.1169
0.1527
0.1257

Koeficient nejistoty C|R
Koeficient nejistoty R|C
Symetrický koeficient nejistoty

0.1058
0.1071
0.1064

0.0593
0.0600
0.0596

•
Pro znaky nomiální
•
Pro znaky ordinální
Zde se jedná o znaky nominální a zhodnotíme pomocí koef. lambda
•
•
•

Lambda asymetrické C|R (závisle proměnná – sloupcová/ řádková nezávislá)
Lambda asymetrická R/C (obráceně – úspěch/účast.
Lamba symetrické – nediferencuje.

Lambdaasymetrická R/C = 0,2857 – proměnná účast na přednáškách ovlivňuej úspěch z 29%.

SVS

přednášky

- 54 -

Typ studie

Hodnota

95% Meze interv. spolehlivosti

Případové řízení (Poměr šancí)
Skupina (Riziko slp1)
Skupina (Riziko slp2)

5.0000
2.3333
0.4667

1.9141
1.3287
0.2936

13.0609
4.0976
0.7417

Velikost výběru = 80

12.p
Př.:
Bylo zkoumáno, zda použití určitého očkovacího sera může snížit počet onemocnění
nakažlivou chorobou. Pokus byl proveden u 23 pokusných zvířat stejného stáří (12 jich bylo
očkováno) a 11 neočkováno. A byla vystevena stejné nákaze. Výsledky šetření jsou
uvedeny v tabulce:
počet
nakažených nenakažených celkem
očkovaných
1
11
neočkovaných
7
4
celkem
8
15

12
11
23

teoretická četnost:
(12*8) / 3 = 4,17 < 5 => nelze použít chíkvadrát test
pro ověření nulové hypotézy
H0: výskyt nákazy není závislý na očkování.
použijeme:

Fisherův test
celkem tři proměnné:
1. ockování – ano/ ne
2. nákaza – ano/ne – vysvětlovaná proměnná je ve sloupci
i. tyto proměnné nelze třídit podle nějaké stupnice a jde o znaky
nominální.
3. počet –
skript:
ods rtf;
proc freg data=ms;
tables ockovani*nakaza/norow nocol nopercent chisq measures;
weight pocet;
run;
ods rtf close;

SVS

přednášky

- 55 -

použitý:
proc freg data=mss;
tables ockovani*nakaza/norow nocol nopercent chisq measures;
weight pocet;
run;

P (0,0094) < 0,05 => HA.
Procedura FREQ
Tabulka pro ockovani podle nakaza
ockovani

nakaza

Četnost ‚ano

‚ne

‚ Součet

ano

‚

1 ‚

11 ‚

12

ne

‚

7 ‚

4 ‚

11

8

15

23

Součet

Statistiky pro tabulku ockovani na nakaza
Statistika

DF

Hodnota

Pr

Chí-kvadrát
Chí-kvadrát poměru věrohodností
Spojitě přizp. Chí-kvadrát
Mantel-Haenszelův Chí-kvadrát
Koeficient Fí
Kontingenční koeficient
Cramerovo V

1
1
1
1

7.7378
8.4155
5.4919
7.4014
-0.5800
0.5017
-0.5800

0.0054
0.0037
0.0191
0.0065

VAROVÁNÍ: 50% buněk má očekávané počty menší
než 5. Chí-kvadrát může být neplatný test.

Fisherův přesný test
Buňka (1,1) Četnost (F)
Levostranný Pr <= F
Pravostranný Pr <= F

1
0.0084
0.9997

Tabulková pravděpodobnost (P)
Dvoustranný Pr <= P

0.0081
0.0094

doplňkové charakteristiky – příkaz measure:
koef. mají statistický obsah
Procedura FREQ
Statistiky pro tabulku ockovani na nakaza
Statistika

Hodnota

ASE

Gama
Kendallovo Tau-b
Stuartovo Tau-c

-0.9012
-0.5800
-0.5520

0.1144
0.1610
0.1655

Somersovo D C|R
Somersovo D R|C

-0.5530
-0.6083

0.1655
0.1634

Pearsonova korelace
Spearmanova korelace

-0.5800
-0.5800

0.1610
0.1610

Lambdaasymetrické C|R
Lambdaasymetrické R|C
Lambdasymetrické

0.3750
0.5455
0.4737

0.3278
0.1734
0.2271

SVS

přednášky

- 56 -

Koeficient nejistoty C|R
Koeficient nejistoty R|C
Symetrický koeficient nejistoty

0.2832
0.2643
0.2734

0.1670
0.1598
0.1629

Vybíráme podle typu vstupních dat:
• pro ordinální znaky – koef. gamma or spearmen (pořadová korelace)
• pro nominální znaky – lambdy.
•
•
•

lambda asysmetrická C/R (závisle proměnná C – uvedená ve sloupci / R nezávislé proměnná –
řádková proměnná)
lambda asysmetrická R/C - obráceně
lambda symetrická – nerozlišujeme která proměnná má roli příčiny a která důsledku, pouze
vztah.

U příklady využijeme asymetrickou souvislost, zda je nakaza ovlivněna očkováním.
Souvislost zde je, to již zjistil fisher test. Vybereme C/R:
Lambdaasymetrické C|R - 0.3750 Nákaza je z 37,5% ovlivňováno tím, zda je jedinec
očkován.
„Budeme-li vědet, zda konkrétní jedinec byl očkován, tak tato informace nám o 37,5%
zredukuje chyby odhadu toto, co se z jedincem stane.“

Kontingenční tabulka
Př.: V určitém podniku byla prováděna analýza, zda příčina nespokojenosti pracovníků
v podniku souvisí se stupněm jejich dosaženého vzdělání.
cetnost
V
S
Z
suma

plat
15
28
38
81

prostredi vztahy
rizeni
jiné
7
6
16
29
27
17
32
28
12
68
61
45

suma
6
19
20
45

50
120
130
300

máme zde opět tři proměnné, 2 kvalitativní a jednu kvantitativní.
vzdělání – ordinální
nespokojenost – nominální
H0: není rozdíl ve spokojenosti a vzdělání.
tables rádková_proměnná*sloupcová proměnná
proc freg data=ms order=data;
tables vzdelani*nespokojenost/norow nocol nopercent chisq measures;
weight pocet;
run;

order=data – chceme aby byly zachovány řádky a sloupce v původním pořadí, tabulka
v původní struktuře.
pokud chci výstup ve formátu RTF – ods rtf;

SVS

přednášky

- 57 -

výstup:
automaticky u kontingenční tabulky není nabízen fisherův test. A pokud není splněna
podmínka pro chí test, fisherův test vyvoláme příkazem: exact
tables vzdelani*nespokojenost/exact

………………………………………………………………………………………………….
chí kvadrát
P (0,0211) < 0,05 => Ha
cramerovo V
0,17
…………………………………………………………………………………………………..
Ha: spokojenost souvisí s dosaženým vzděláním, závislost spokojenosti je slabá (0,17). Při
použití predikční míry: (pokud je alespoň jeden znak nominálního typu, využíváme pouze
koeficienty lambda)
nespokojenost je sloupcová proměnná – lambdaasymetrické C/R……………0,0091
Procentické ovlivnění nespokojenosti vzděláváním je 0,9%. Vzdělání hraje velmi slabou roly.

SVS

přednášky

- 58 -

Časové řady
závisle proměnná – sledovaný ukazatel
nezávisle proměnná – čas

Cílem je získat extrapolační předpoklady a navrhnout výstižné předpoklady.
TSFS – time series forecasting systém
Y1, Y2…………….Yn
1 2 …………n

vyrovnání časové řady funkcí a predikce

Základní termíny:
referenční období – (1995 až 2003)
V Sasu jsou k dispozici:
- klasické trendové modely (lineární, kvadratický, exponentiální atd)
- adaptivní modely – pokud řada vykazuje nějaké nesrovnalosti. Neustále se
přizpůsobují nejnovější informaci. Řadu modelují po částech a vyrovnávají
jednotlivé úseky. Zabezpečují diskontní váhy, které nejstarším hodnotám
přidávají menší váhu než těm novějším.
- kombinované modely které spojují obě – ARIMA a SARIMA modely –
univerzální systém pro modelování časových řad.

SVS

přednášky

- 59 -

12.přednáška
Tvorba předpovědí – největší váhu mají poslední údaje (stárnutí informace).
Stárnutí informace nám zabezpečují adaptivní modely:

a. Braunův model jednoduchého exponenciálního vyrovnávání
– váhy jednotlivých hodnot směrem do minulosti exponenciálně klesají. Váhy
přidělujeme jednou vyrovnávací konstantou.
Braunův model se nesnaží proložit model jednou „čarou“, ale hledá homogenní úseky a
ty pak prokládá.

Model je vhodný, pokud se časová řada dá rozložit na úseky, kdy má konstantní trend.Pro
jednoduché modely bez trendu.
vyrovnávací konstanta…………………………………α (0,1) – empirické nalezení
metodou: pokus/omyl
MSE = mean Squared Error - hledáme min. hodnotu charakteristiky.
MSE =

1
Σ(Yt − Y ´t ) 2
n

Yt , t = 1,….n – skutečné
Y´t – vyrovnané hodnoty (teoretické hodnoty časové řady)

b. Braunův model dvojitého exponenciálního vyrovnávání
-

vhodné pro situace, kdy se řada dá rozdělit na malé dílčí úseky, kdy každý úsek
se dá popsat lineárním trendem.

vyrovnávací konstanta…………………………………α (0,1) – pomocí konstanty se zde
modeluje průměrná hodnota časové řady a dále se zde modeluje trend čas. řady, jako u
bodu a.

c. Braunův model trojitého exponenciálního vyrovnávaní.
dílčí úseky lze popsat kvadratickým trendem

d. Hortův model exponenciálního vyrovnávání.
Podobné jako u dvojitého braunova, použijeme tehdy,kkdyž je zřetelná lineární složka,
resp. pokud je v modelu výrazný trend. Používá 2 vyrovnávací konstanty:
úrovňová vyrovnávací konstanta…………………………………α (0,1)
trendová vyrovnávací konstanta……………………………….…β (0,1)

SVS

přednášky

- 60 -

Časové řady v programu SAS
1. Založení datového souboru v knihovně work. Údaje psát do sloupců.
2. uložit datový soubor
3. čas. Řady lze dělat procedurálně (programovat), pokud přesně neznám typ trendu,
použiji modul.
Modul pro trend:
1. je třeba opustit tabulku.
2. Solutions – analysis –
Time series forecaasting systém - systém předpovědi čas.řad.
develop models
nabídka knihoven, vyberu náš datový soubor.
Vyplnit:
Data set: název souboru ms
Variable : proměnou sou peníze
Naším časovým intervalem sou roky a proměnou peníze a SAS to musí vědět.
Time Id:_____________
Interval: _____________

SELECT CREATE

Create from starting date and freguenci (tvořit podle vstupních údajů a
četností)
Create from existent variables – podle proměnných
…
Create from observation numbers – podle počtu měření (v našem příkladě 9)
Create from starting date and freguenci
Time ID creation …..
Starting date: 1995 počáteční údaj, první sledování
Interval : specifikovat- type ~ YEAR
Ok
OK

Po dvojím OK jsem zpátky v nabídce knihoven a mám vyplněny všechny údaje.
Data set: MS
Variable : PENÍZE
Time Id: DATE
Interval: YEAR
OK Potvrdím

SVS

přednášky

.

Nastavit MAPE
Mean A.P. error

Rozpětí : SET RANGES
DATA RANGE: celá řada
FIT RANGE: období modelu pro časové řady
EVALUATION RANGE: hodnotící období, které posuzuje modelu při extrapolaci.

- 61 -

SVS

přednášky

Zvolení modelu:
Ručně – TOOLS – Diagnostic serie

Automaticky vyhledá trend atd.
OK
Dále: OPTIONS – AUTOMATIC FIT
Zvolím si např. 6 best modelů.
To znamená, pokud existuje 6
Modelů, tak mi je to vyhledá a
seřadí podle nejlepšího.

- 62 -

SVS

přednášky

Pak pravím tlačítkem myši v ploše a
FIT MODELS AUTOMATICLI¸

Zobrazilo se několik nejlepších funkcí. Nejhorší je linear Trent ~ MAPE 3,16 %
Vyberu fci, linear trend –

Horní a dolní interval spolehlivosti. Naměřené hodnoty by
se měli s 95% spolehlivostí měli pohybovat v tomto rozmezí
--

rovnici trendové funkce
posouzení kvality modelu – tlačítko σ 2
forecast table. – předpovědní tabulka

- 63 -

SVS

b = 533,86
a = 28,78

přednášky

- 64 -

o Trendová linear. funkce Y´t = a + b . t

o

Y´t = 533,86 + 28,7833 t

posouzení kvality modelu σ 2

∑ (Yt − Yt )
R – Square –Index determinace I = 1 −
∑ (Yt − Y )
´

2

2

Mean Absolute chyba
MAPE – 3,16 %

= 0,89

SVS

přednášky

Předpovědní tabulka

Předpokládáme že v roce 2005 se zaplatí za kulturu 850 kč, v roce 2006 880 kč.

Volba jiného trendu
Braunůw double model je z těchto přednastavených nejlepší.
pravím / levým tlačítkem myši v ploše a
FIT ARIMA model

- 65 -

SVS

přednášky

- 66 -

ADD . – zobrazení nabídky funkce:

Linear trend
Trend curve - nabídka trendových funkcí.
Regressors
Interval
……
Zvolili jsme Quadratic trend – Přímka se dá velice slušně nahradit parabolou, která už je
hodně daleko a na krátkém úseku připomíná přímku.
Ok

Můj zvolený kvadratický trend je podle hodnoty MAPE mnohem lepší než původní
lineární a téměř stejně dobrý jako Brownův.

Do budoucna lehce klesá . Výdaje na kulturu by klesaly? Je třeba vyzkoušet ještě další trendy.
Nejlepší se jeví logaritmický s indexem MAPE 1,17. Je lepší než původní nabízené.

SVS

přednášky

- 67 -

Odhady:
Čekáme že se to bude každý rok zvyšovat , ale ne tak prudce, jak předpovídá lineární
trend ale logaritmicky.

.
Model se tedy jeví jako nejlepší a teď je třeba to ověřit.

Ověření kvality zvoleného modelu
Zvolím si kratší časový úsek, třeba 1995 – 2000 a udělám extrapolaci na rok 2001 do 2003.
Pokud se odhadované hodnoty budou shodovat s skutečnými naměřenými hodnotami, model
je velice kvalitní a vhodný pro předpověď do budoucna.

