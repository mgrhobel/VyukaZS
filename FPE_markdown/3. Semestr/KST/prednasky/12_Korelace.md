---
title: "12_Korelace.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/12_Korelace.pdf"
date: 2009-12-27
type: PDF (text-based)
---

5. Korelace
5.1 Teoretické základy korelace
5.2 Způsoby měření závislostí pro různé typy dat
Při práci se statistickými údaji se velmi často setkáváme s daty , která jsou tvořena
dvojicemi, trojicemi hodnot. Složky takovýchto dat je možno vyšetřovat samostatně
metodami předchozích kapitol, ztrácíme však vazbu mezi nimi. Právě metodami zobrazování
dat, jejich účelnému seskupování do tabulek či jiných pomocných nástrojů se bude zabývat
tato kapitola. Navíc si vymezíme i metody pro analýzu vazeb mezi složkami vybraných dat.

5.3 Dvourozměrná rozdělení četností
Předpokládejme, že v provedeném výběru je obsaženo n jednotek, u nichž sledujeme
dva kvantitativní znaky x a y. Jejich konkrétním naplněním jsou tedy dvojice hodnot (xi , yj ),
kde i=1,…,p a j=1,…,r. Obecně není možné předpokládat, že čísla p a r jsou totožná, neboť
každý ze znaků x a y může mít různý počet variant. Dohromady však tvoří n členný výběr.
Označme absolutní četnosti jednotlivých kombinací variant xi a yj symbolem nij.
Seřaďme uspořádané dvojice (xi , yj ) uvedené ve výběru podle nějakého pravidla
( např. podle velikosti xi a poté podle velikosti yj). Potom v případě dvou znaků x a y budeme
rozumět pod pojmem dvourozměrného rozdělení absolutních četností zobrazení, které
přiřazuje jednotlivým uspořádaným dvojicím (xi , yj ) , pro i=1,…,p a j=1,…,r , hodnoty
absolutních četností nij . Podobně bychom mohli provést takovéto přiřazení u hodnot
relativních četností, kdy jednotlivé hodnoty nij budeme dělit součtem všech absolutních
četností n.
Velmi podobně můžeme uvést i pojem dvourozměrných intervalových rozdělení
četností . Nejdříve data vhodně uspořádáme ( půjde o vhodné uspořádání kartézského součinu
intervalů ) a potom provedeme stejný postup jako v předchozím odstavci s tím , že místo
uspořádaných dvojic budeme pracovat s uspořádanými dvojicemi intervalů.
Podobně můžeme zobecnit předchozí definice na případ, kdy u náhodného výběru
sledujeme k kvantitativních znaků z1,…,zk . Potom hovoříme o k rozměrném rozdělení
četností ( absolutních nebo relativních ) resp. o k rozměrném rozdělení intervalových četností.
Dvourozměrné rozdělení četností dvou kvantitativních znaků x a y lze velmi přehledně
uvést v tabulce , která se obecně nazývá korelační tabulka. Popišme si dále tuto tabulku:
V prvním řádku, v němž je uveden postupně obsah jednotlivých sloupců se uvedou seřazené
vzestupně všechny varianty jednoho ze znaků nalezené ve výběru; v prvním sloupci se
postupně uvedou seřazené vzestupně všechny varianty druhého znaku nalezené ve výběru.
Na průsečících takto popsaných sloupců a řádků se uvedou postupně absolutní ( relativní )
četnosti daných dvojic hodnot. Poslední sloupec ( resp. poslední řádek ) korelační tabulky
obsahuje tzv. podmíněné rozdělení absolutních ( relativní ) četností druhého znaku (
v případě posledního řádku prvního znaku ).
Jestliže se vyšetřuje závislost dvou znaků, které nabývají velké množství hodnot , nebo
předpokládáme, že jsou spojité, potom jednotlivé varianty znaků účelně seskupujeme do
intervalů. Výsledná korelační tabulka je potom tabulkou dvourozměrného intervalového
rozdělení absolutních ( relativních ) četností.

Tabulka 5.1 Korelační tabulka absolutních četností
yj
xi
y1
y2
…
x1
n11
n12
n1r
x2
n21
n22
n2r
…
xp
np1
np2
npr
n.j
n.1
n.2
n.r
V této tabulce tedy vždy platí:
r

ni. = ∑ nij

ni
yr

.

n1.
n2.
np.
n
(5.1)

j =1

p

n. j = ∑ nij

(5.2)

i =1
p

r

p

i =1

j =1

i =1 j =1

r

n = ∑ ni. = ∑ n. j = ∑∑ nij

(5.3)

Hodnoty nij se někdy nazývají také nepodmíněné četnosti a hodnoty ni. a n.j se nazývají
nepodmíněné marginální četnosti.
Graficky můžeme zobrazovat takováto dvourozměrná data například sloupcovým
grafem , v případě, že budeme dodržovat pravidla pro tvorbu histogramů, můžeme vytvořit
také histogram pro dva znaky ( někdy se nazývá stereogram ). Existují i jiné způsoby
zobrazení dvourozměrných dat, ale ty naráží především na komplikace s jejich konstrukcí,
proto je uvádět nebudeme.
Jestliže chceme zobrazit dvourozměrné ( nebo i vícerozměrné ) rozdělení četností
v případě kvalitativních znaků , můžeme využít pro zaznamenání údajů tabulku, která se
shoduje s korelační tabulkou . Sledujeme – li vztahy mezi dvěma alternativními znaky
nazýváme korelační tabulku v tomto případě asociační tabulkou. Jestliže alespoň jeden
kvalitativní znak nabývá více než dvou variant nazýváme korelační tabulku kontingenční.
Uveďme dále několik příkladů korelačních tabulek.
Příklad 5.1
Výsledky písemných prací z matematiky a fyziky studentů jedné třídy jsou uvedeny
dále v tabulce:
žák 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27
M 3 1 3 2 4 3 1 4 2 1 2 3 2 3 1 3 4 3 2 5 4 2 3 4 3 4 4
F 2 2 4 2 5 1 1 4 5 2 1 4 3 2 2 3 3 2 4 4 3 1 1 3 5 3 4
Uveďte odpovídající korelační tabulku!
Řešení:

FYZIK
A

1
1
3
0
0
0
4

1
2
3
4
5
n.j

MATEMATIKA
3
4
2
0
3
0
1
4
2
2
1
1
9
7

2
2
1
1
1
1
6

5
0
0
0
1
0
1

ni.
5
7
6
6
3
27

MATEMATIKA
3
4
0,0
0

5
0

ni.
0,1

0,1

0

0

0,0

0,1

0

0,0

0,0

Uveďme pro úplnost stejnou tabulku pro relativní četnosti:
1
0,0

1
38
2

74
0,1

11

FYZIKA

2
0,0
74
0,0
38

3

0

4

0

5

0

0,2

11
0,0

38

60

38
0,0

38

74

22

74
0,0

38

0,2

49
0,0

0,0
38

86

38
0,0

38

0,2
22

0

0,1
11

n.j

0,1
0,2
0,3
0,2
0,0
49
22
33
60
38
Nepřesnosti v dané tabulce jsou zaviněny zaokrouhlováním jednotlivých hodnot.

1

Příklad 5.2
U náhodně vybraných součástek se proměřovala jejich délka a výška. Pro každý
z těchto rozměrů se určilo, zda je vyhovující ( v normě ) či ne . 239 součástek mělo oba
rozměry správné, 14 mělo správně výšku a nesprávně délku, 60 mělo správně délku a
nesprávně výšku a 7 mělo oba rozměry nesprávně. Převeďte tyto hodnoty do korelační
tabulky.
Řešení:
Délka

výška
správná
nesprávná
celkem

správná
239
14
253

nesprávná
60
7
67

celkem
299
21
320

Jde o případ asociační tabulky.
Příklad5.3
Sledovala se souvislost mezi rodinným stavem ženichů a nevěst v souboru
československých snoubeneckých párů v roce 1966. Upravte tuto tabulku na tabulku
s relativními četnostmi.

rodinný stav nevěst

rodinný stav
ženichů

svobodné

celkem

ovdovělé

rozvedené

svobodný

95 145

902

4 385

100 432

ovdovělý

919

1 092

1 050

3061

rozvedený

5 876

1 090

5 265

12 231

celkem

101 940

3 084

10 700

115 724

Řešení:
rodinný stav nevěst

rodinný stav
ženichů

svobodné
svobodný

82,217%

ovdovělé

rozvedené

celkem

0,779%

3,789%

86,786
%
2,645%

ovdovělý

0,794%

0,944%

0,907%

rozvedený

5,078%

0,942%

4,550%

10,569%

2,665%

9,246%

100,000%

celkem

88,089%

Jak jsme viděli v předchozích případech je možno zobrazovat pomocí různých variant
korelační tabulky i data , která nejsou kvantitativního charakteru. Je možno provádět
srovnávání dat ordinálních ( záleží nám na pořadí ) např. pořadí při vyhodnocení otázky ,
pořadí subjektivních pocitů atd. Dále je možno zobrazovat také nominálně měřené znaky
v kontingenčních tabulkách.
Slovo asociace znamená v našich pojmech sloučení, složení. Slovo kontingence
znamená vazba.
Kromě popisu dat jen prostou korelační tabulkou , je naši snahou většinou získat
doplňující informace o vazbách mezi jednotlivými znaky ( korelační analýza ) a o způsobu
vyjádření těchto vazeb ( regresní analýza ).Těmito pojmy se budeme nyní u dvou znaků dále
zabývat.
Z pohledu vztahu dvou znaků již známe z prostředí např. středoškolské matematiky
funkční závislost dvou veličin. Známe – li stranu čtverce, je možno určit jednoznačně jeho
obvod, známe – li vklad , počet období, úrokovou míru , je možno určit výši vkladu včetně
úroků. V prostředí statistiky se však setkáváme a vyšetřujeme jiné typy vztahů.
Definice 5.1
Řekneme, že znak y ( náhodná veličina Y ) je statisticky závislý na znaku x ( náhodné
veličině X ), jestliže změna hodnoty znaku x má za následek změnu podmíněného rozdělení
znaku y ( náhodné veličiny Y ).
V praxi není většinou podmíněné rozdělení znaku y známo, proto se snažíme získat o
něm představu pomocí nástrojů regresní analýzy.

Definice 5.2
Řekneme, že znak y ( náhodná veličina Y ) je korelačně závislý na znaku x ( náhodné
veličině X ), jestliže změna hodnoty znaku x má za následek změnu podmíněné střední
hodnoty rozdělení znaku y ( náhodné veličiny Y ).
Zůstávají – li podmíněné průměry závisle proměnné konstantní , i když se hodnoty
nezávisle proměnné mění jakkoli , považuje se závisle proměnná za korelačně nezávislou na
příslušných nezávisle proměnných.
Podle příslušných definic je zřejmé, že pojem korelační závislosti je slabší než pojem
statistické závislosti. Korelační závislost je vždy i statistickou závislostí, protože změna
podmíněného průměru znamená i změnu podmíněného rozdělení. Na druhou stranu korelační
nezávislost ještě nemusí znamenat statistickou nezávislost. To že se nemění podmíněný
průměr nemusí znamenat, že se nemění podmíněné rozdělení. Statistická závislost může být i
korelační nezávislostí, jestliže se změny podmíněného rozdělení projeví ve změnách jiných
popisných hodnot než v podmíněném průměru. Statistická nezávislost je v každém případě
také korelační nezávislostí, neboť neměnnost podmíněného rozdělení znamená současně
konstantnost podmíněného průměru.
Korelací náhodných veličin chápeme vzájemnou korelační závislost uvažovaných
náhodných veličin. Přitom rozlišujeme :
1. Jednoduchou korelaci – korelaci dvou náhodných veličin;
2. Mnohonásobnou regresi – korelaci jedné náhodné veličiny a skupiny dvou a více
náhodných veličin.
Důležité je pochopit jaký je vztah mezi korelační závislostí na jedné straně a kauzální
závislostí na straně druhé. Jestliže jsou dvě náhodné veličiny korelačně závislé, pak to
znamená, že mezi těmito náhodnými veličinami může existovat kauzální závislost. Nelze ale
rozlišit zda jde o kauzální závislost bezprostřední , kdy změny jedné veličiny podmiňují
změny druhé, nebo o kauzální závislost zprostředkovanou . Existence korelační závislosti
dvou náhodných veličin nemůže být důkazem toho, že mezi nimi existuje kauzální závislost.
Na dalších obrázcích jsou uvedeny různé modelové situace korelace dvou náhodných
veličin ( dvou znaků ).
Obr. 5.1 –Extrémně kladná korelace

Obr. 5.2 – Silná kladná korelace
6

2,5

5

2

4

1,5

3
1

2

0,5

1

0

0
0

0,5

1

1,5

2

2,5

0

1

2

3

4

5

6

Obr 5.3. – Slabá kladná korelace

Obr 5.4 – Korelace blízká nule
3,5

8
7

3

6

2,5

5

2

4

1,5

3
1

2

0,5

1
0

0
0

1

2

3

4

5

0

6

Obr 5.5 – Extrémně záporná korelace

2

50

1

49

0

48

-1 0
-2

47
46

0

1

2

3

4

5

6

Obr 5.7 – Nelineární korelace
20
10
0

-50

5

6

2

4

6

0

1

2

3

4

-5

Obr 5.8. – Nelineární korelace

30

-40

4

-4

44

-30

3

-3

45

-20

2

Obr 5.6 – Silná záporná korelace

51

-10

1

5

6

9
8
7
6
5
4
3
2
1
0
0

2

4

6

Z jednotlivých obrázků je patrno, že některá vyjádření vztahu mezi náhodnými
veličinami X a Y ( resp. znaky x a y ) mohou mít i podobu skoro funkční , dokonce i tehdy
když dané hodnoty spolu příliš nekorelují ( např. Obr 5.7 ) , ale mohou mít podobu lineárního
vztahu ( Obr. 5.1 ), když spolu korelují velmi.

5.4 Míry korelace dvourozměrných statistických souborů
Jak jsme již uvedli v předchozí části je jednou z nejdůležitějších charakteristik
vícerozměrných statistických souborů charakteristika vazby mezi jednotlivými znaky
Podstatné pro naše další šetření bude to , zda jsou data kvantitativní povahy, nebo jsou
ordinální nebo nominální. V následující tabulce jsou uvedeny jednotlivé typy charakteristik
míry korelace pro různé druhy dat.

Tabulka 5.2 Míry korelace
kvantitativní
korelační koeficient
r

Proměnná X

kvantitativní

Proměnná Y
ordinální
koeficient pořadové
korelace rS

ordinální
biseriální koeficient
rbis
nominální

nominální

koeficient Φ
asociační koeficient Q
kontingenční
koeficient C

5.4.1 Korelační koeficient
V dalším textu se budeme snažit osvětlit pojmy uvedené v předchozí tabulce 5.2.
Jestliže jsou obě veličiny povahově kvantitativního charakteru používáme k měření korelační
Pearsonův koeficient r. Jde o bezrozměrnou veličinu, která může nabývat hodnot mezi -1 a 1.
Pomocí toho koeficientu měříme většinou sílu lineární vztahu mezi znaky x a y . Jestliže
nabývá krajních mezních hodnot -1 nebo 1 můžeme vztah mezi znaky vyjádřit pomocí
funkčního lineárního vztahu. Pro hodnotu r=-1 při rostoucích hodnotách x hodnoty y klesá a
při hodnotě r=1 při rostoucích hodnotách x hodnota y klesá. Pro hodnotu r=0 vylučujeme
lineární vztah mezi znaky x a y , ale to neznamená, že mezi nimi nemůže vztah být viz např.
Obr. 5.8 nebo Obr. 5.7. Při užívání tohoto koeficientu je zapotřebí mít na zřeteli klasické
předpoklady lineárního modelu , tedy především normalitu a to , že pro libovolnou hodnotu xi
má náhodná hodnota Y střední hodnotu, která je dána příslušnou hodnotou
na regresní přímce . Více o těchto předpokladech se dozvíme v kapitole o statistické regresy
Při výpočtu korelačního koeficientu r se používají hodnoty odhadu směrodatné
odchylky sx a sy ,

∑ ( x − x )( y − y )
n

i

r = i =1

i

(5.4),
(n − 1).sx .s y
tento způsob výpočtu využívá hodnoty počítané přímo z korelační tabulky. Pro některé
výpočty je ale jednodušší používat následující vzorec
x. y − x. y
r=
(5.5),
σ X .σ Y
kde výše uvedené hodnoty jsou počítány podle těchto principů:
n

x. y =

∑XY

i i

i =1

(5.6),

n

n

x=

∑X
i =1

σX =

n

n

i

a

y=

1 n
.∑ ( X i − X ) 2
n i =1

∑Y
i =1

n

i

(5.7),
(5.8),

σY =

1 n
.∑ (Yi − Y ) 2
n i =1

(5.9).

Příklad 5.3
Byly zjišťovány reakční doby řidičů v určité situaci před stresem a po stresu. Zjištěné
údaje jsou uvedeny v tabulce níže. Zjistěte hodnotu korelačního koeficientu!
Tabulka 5.3

Po stresu
3
7
11
14
15

A
B
C
D
E

Čas
Před stresem
3
5
7
6
9

n

n

xi 2

yi 2

xi . yi

9
49
121
196
225

9
25
49
36
81

9
35
77
84
135

n

n

n

∑ xi = 50

∑ yi = 30

∑ xi2 = 600

∑ yi2 = 200

∑ x y = 340

x = 10

y=6

x 2 = 120

y 2 = 40

x. y = 68

i =1

i =1

i =1

i =1

i

i =1

i

Řešení:

Nejdříve určíme hodnotu r podle vztahu (5.4), potřebujeme ještě určit hodnoty sx a sy.

A
B
C
D
E

Tabulka 5.4
Čas
Po stresu
Před
stresem
3
3
7
5
11
7
14
6
15
9
n

n

∑ xi = 50

∑ yi = 30

x = 10

y=6

sx = 5 a sy =

5

i =1

i =1

xi − x

yi − y

-7
-3
1
4
5

-3
-1
1
0
3

n

n

∑ ( xi − x) = 0
i =1

21
3
1
0
15

(

)

∑ yi − y = 0
i =1

( xi − x).( yi − y )

n

∑ ( x − x).( y − y) = 40
i =1

i

i

40
2
2. 5
=
=
≅ 0,89
5
4.5. 5
5
Počítejme nyní podle vzorce (5.5) . Musíme nejdříve určit hodnoty σx a σy . Tyto
hodnoty jsou σx = 20 = 2. 5 a σy = 2 .
r=

r=

68 − 6.10
8
2. 5
=
=
≅ 0,89 .
5
2. 5.2
4. 5

Příklad 5.4
Vypočítejte hodnotu korelačního koeficientu z údajů uvedených v následující
korelační tabulce:
Tabulka 5.4
x

3

4
5
6
7
8
9
10

2
6
2

y

n.j

1

4

5

2
3
5
3
2

1
1
3
5
6
9

1

6

7
1
1
3
5
2

1
5
5
3
2

2

1

1

ni.

xi ni.

x i2n i.

2
4 12
3 12
1 17
17
12
13

5 20
60
72
119
136
108
130

80
300
432
833
1088
972
1300

10 88

645

5 005

8

0

5

5

6

2

yj n.j

30

60

125

96

84

80 475

yj2 n .j

90

240

625

576

588

640 2 759

Řešení:
Počítáme hodnotu korelačního koeficientu r podle (5.5). Potřebné hodnoty určíme
z předchozí tabulky. Tedy
645
475
x=
= 7,329; y =
= 5,398; σ X = 1, 776; σ Y = 1, 489 . Z těchto hodnot již
88
88
můžeme spočítat korelační koeficient r :
r = -0,144
Výsledná hodnota je velmi nízká, nemůžeme tedy hovořit o lineárním vztahu mezi X a
Y.
Pro vyšetřování statistických hypotéz o nulovosti korelačního koeficientu jsou dále důležité
následující věty, které umož.
Věta 5.1

5.4.2 Koeficient determinace
V případě lineární regrese ( ale nejen v tomto případě ) můžeme vyjádřit těsnost
vztahu pomocí mezi náhodnou veličinou Y a veličinou x také pomocí poměru variability
podmíněné lineární regresí a variabilitou způsobenou náhodnými vlivy.
Podle vztahu (13.23) je S r =

S xx .SYY − S xY 2
.
S xx

Měříme – li odhad variability Y máme
n

n

i =1

i =1

n

SYY = ∑ (Yi − Y ) 2 = ∑ ((Yi − a − b.xi ) − ( − a − b.xi + Y )) 2 = S r + ∑ ( b. ( xi − x ) ) −
i =1

2

n
S 
−2.∑ (Y − a − b.xi ). ( − a − b.xi + Y ) = Sr + b 2 .S xx − 0 = Sr +  xY  .S xx . Tedy
i =1
 S xx 

2

2
2
S xY
S xY
S
⇒ R2 = 1 − r =
. Hodnota R2 se nazývá koeficient
S xx
SYY S xx .SYY
determinace , jeho hodnota se pohybuje mezi 0 a hodnotou 1. Koeficient determinace
vyjadřuje poměr mezi variabilitou skutečnou ( SYY ) a variabilitou vypočítávanou ( Sr ). Je
zřejmé , že v lineárním případě je koeficient determinace roven druhé mocnině korelačního
koeficientu.

S r = SYY −

5.4.3 Index determinace
V případě jiných než lineárních regresí nebo mnohonásobných regresí je zapotřebí
zabezpečit také míru těsnosti vazby mezi náhodnou veličinou Y a hodnotami x . Stejně jako
v předchozí části je celková variabilita náhodné veličiny Y rovna součtu variability vyjádřené
regresním vztahem a variability náhodného chování . Definujeme proto podobně jako
v předchozím článku
Sˆ
2
I xY
= Y ,
SYY
kde SYˆ znamená hodnotu rozptylu empirické regresní funkce a SYY hodnotu rozptylu
závisle proměnné Y.
Častěji se k vystižení závislosti používá odmocnina z indexu korelace , tato hodnota se
nazývá index determinace.
Z obou předchozích hodnot vyplývá , že nejsou symetrické , platí totiž
I xY ≠ IYx .

5.4.4 Spearmanův korelační koeficient
V případě dvourozměrného souboru kvalitativních údajů, které jsou po složkách
ordinálního typu , je možno zjistit stupeň závislosti těchto dvou znaků. K měření takovýchto
závislostí se používá Spearmanův korelační koeficient ( někdy nazývaný též koeficientem
pořadové korelace ), který je založený na pořadích jedinců uspořádaných podle velikosti
vzhledem k oběma vyšetřovaným znakům. Každému jedinci tedy přiřadíme dvojici pořadí –
Q ( pořadí podle prvního znaku X ) a R ( pořadí podle druhého znaku Y ).
Jestliže budou hodnoty pořadí Y vzrůstat stejně jako hodnoty X , budou pořadí R a Q
stejná. Jestliže bude hodnota pořadí znaku Y s rostoucím pořadím znaku X klesat, budou
pořadí obou znaků opačná, tedy
R = n – Q+1.

(5.10)

Jestliže však budou hodnoty pořadí R a Q obou znaků libovolná potom očekáváme ,
že oba znaky budou nezávislé.
Pro n pozorovaných dvojic ve výběru určíme Spearmanův korelační koeficient
pomocí diferencí pořadí di = Qi – Ri takto
n

rS = 1 −

6.∑ di 2
i =1
2

n. ( n − 1)

(5.11).

Při shodném pořadí jsou hodnoty všech di = 0 , tedy rS = 0. Je – li pořadí opačné,
použijeme výraz (5.10) a di = Q – n + Q -1= 2 . Q – n - 1, hodnota Q postupně nabývá všech

hodnot od 1 do n. Zjistěme jaké hodnoty potom nabývá výraz (5.11) . Dosaďme přímo do
(5.11) a získáváme
n
 n3 n 
2
6.
6.∑ ( 2.i − n − 1)
 − 
3 3
= 1−  2
= 1 − 2 = −1 .
rS = 1 − i =1
2
n.(n − 1)
n. ( n − 1)
Při ostatních případech nabývá rS hodnoty ležící mezi těmito mezními hodnotami tedy
- 1 < rS < 1

(5.12)

Pro hodnoty rS blízké nule můžeme usuzovat, že pořadí R a Q jsou náhodně
zpřeházena a mezi znaky X a Y není závislost. Pro hodnoty n ≥ 31 je možné využít vztahu
mezi rozdělením N(0,1) a Spearmanovým koeficientem
Z = rS . n − 1

(5.13).

Tento vztah využijeme v části věnované statistickým hypotézám.
Příklad 5.5
Při přijímacím řízení se provádělo hodnocení komisí a hodnocení speciálním
programem. Na základě údajů o deseti studentech rozhodněte o tom, zda jsou obě hodnocení
závislá.
Tabulka 5.5
Student
A
Hodnocení 4
komisí
Hodnocení 1
programem
Diference
3
pořadí
Čtverec
9
diference

B
6

C
1

D
5

E
10

F
2

G
7

H
3

I
9

J
8

3

5

7

8

4

6

2

10

9

3

-4

-2

2

-2

1

1

-1

-1

9

16

4

4

4

1

1

1

1

Řešení:
10

Sečteme hodnoty čtverců diferencí

∑ d = 50 a dosadíme do vztahu (5.11).
i =1

2

i

Dostáváme
6.50
300 23
= 1−
=
U 0, 6970 .
10. (100 − 1)
990 33
Hodnota korelačního koeficientu rS ukazuje na určitou míru závislosti mezi
hodnocením komisí a hodnotitelským programem.
rS = 1 −

5.4.5 Míra asociace
V tomto článku budeme vyšetřovat závislosti dvou náhodných veličin X a Y , které
jsou nabývají alternativní ( dvouhodnotové). Předpokládáme, že ba znaky X a Y jsou
kvalitativní povahy.

Definice 5.3
Řekneme, že náhodné veličiny X a Y jsou asociačně závislé , jestliže v části výběru,
který se skládá z jednotek s určitou hodnotou jedné náhodné veličiny , je relativně více nebo
méně jednotek s určitou variantou druhé náhodné veličiny.

Z této definice je možno odvodit dva mezní případy:
a)
Případ, kdy všechny jednotky výběru , které mají určitou variantu jedné
náhodné veličiny , mají i určitou variantu druhé náhodné veličiny. Tomuto
říkáme úplná asociační závislost.
b)
Jestliže v části výběru, která se skládá z jednotek s určitou variantou jedné
náhodné veličiny , je relativně stejný počet jednotek s určitou druhé náhodné
veličiny jako v části výběru, který se skládá z jednotek nemajících
uvažovanou variantu první náhodné veličiny pak nazveme obě veličiny jako
asociačně nezávislé.
Asociací tedy rozumíme oboustrannou závislost mezi alternativními náhodnými
veličinami kvalitativní povahy. Z hlediska obecného se zkoumá asociace jen dvou znaků
( párová ) nebo asociace více znaků ( mnohonásobná ). V tomto textu se budeme zabývat jen
jednoduchou asociací. V následující tabulce si uvedeme obecný příklad tzv. asociační tabulky:
Tabulka 5.6

Hodnoty Y

Hodnoty X
+
Celkem

+
n11
n21
n.1

Celkem

n12
n22
n.2

n1.
n2.
n

Základní mírou závislosti jednoduché asociace je koeficient asociace
rA =

n.n11 − n1. .n.1
n1. .n2. .n.1.n.2

(5.14).

Podobně jako u ostatních koeficientů, kterými se snažíme měřit závislost náhodných
veličin nabývá hodnot z intervalu od <-1 ; 1>. Vyšetřeme si krajní případy.
a)
Jestliže jsou hodnoty n12 = n21 = 0 , potom rA =1. jde o případ úplné
asociační závislosti.
b)
Jestliže jsou hodnoty n11 = n22 = 0 , potom rA = -1. V tomto případě jde opět
o úplnou asociační závislost
c)
Jestliže výraz D = n11 . n22 – n12 . n21 = 0 , potom je hodnota rA = 0 a dané
náhodné veličiny jsou asociačně nezávislé.

Příklad 5.6
Byly vyšetřovány vztahy mezi vlastnictvím automobilu a ochotou jezdit hromadnou
dopravou do zaměstnání. Výsledné hodnoty šetření jsou uvedeny v následující tabulce 5.7.
Zjistěte míru asociace těchto veličin.
Tabulka 5.7
Ochota jezdit
hromadnou dopravou
ano
56
ne
312
Celkem
368

Vlastnictví automobilu
ano
ne
283
35
318

Celkem
339
347
686

Řešení:
Použijeme vzorec (5.14). Po dosazení příslušných hodnot získáme
rA=-0,73585. Uvedené vztahy ukazují na střední míru závislosti mezi vlastnictvím automobilu a
ochotou jezdit hromadnou dopravou.

5.4.6 Míra kontingence
Pokud vyšetřujeme dvě náhodné veličiny kvalitativního typu, které nejsou alternativní
( nenabývají jen dvou hodnot ), nemůžeme samozřejmě použít předchozí míru asociace. Pro
oboustrannou kvalitativní závislost náhodných veličin, které mají více než dvě varianty , se
užívá pojem kontingence.
Pro měření těsnosti kontingence dvou náhodných veličin se používá celá řada měr.
Předpokládejme, že náhodná veličina X nabývá s variant a náhodná veličina Y nabývá r
variant . K nejznámějším patří Pearsonův koeficient kontingence
c=

χ2
,
n + χ2

(5.15)

kde
n .n 

n.  nij − i. . j 
r
s
n 
χ2 = ∑ ∑ 
ni. .n. j
i =1
j =1

2

(5.16)

Výše uvedené symboly jsou definovány stejně jako v předchozí části. Při úplné
nezávislosti je hodnota Pearsonova koeficientu kontingence nulová, určitým nedostatkem je
to, že ani při úplné závislosti sledovaných náhodných veličin nenabývá hodnoty 1.
Užíváme proto někdy tzv. Čuprovův koeficient kontingence

K=

χ2
,
n. (r − 1).( s − 1)

v němž má χ2 stejný význam jako v (5.15).

(5.17)

Příklad 5.7
V jisté anketě odpovídali respondenti na dvě otázky , každá z nich měla celkem tři
možnosti odpovědí a,b,c. Zjistěte, zda mezi oběma otázkami existuje souvislost. Zjištěná data
jsou uvedena v tabulce 5.2.8.
Tabulka 5.8
Odpověď na
otázku č.1
a
15
b
18
c
14
Celkem
47

a

Odpověď na otázku č.2
b
53
20
59
32
10
7
122
59

Celkem

c
88
109
31
228

Řešení:
Podle vzorce (5.16) převedeme tabulku 5.8 na tvar, kdy v jednotlivých buňkách
tabulky budou hodnoty vypočtené ze vztahu (5.16).
0,543639
0,888974
9,061593

0,742339
0,007822
2,616276

0,337415
0,510292
0,130186

Takovéto hodnoty sečteme a získáme hodnotu výrazu χ2 = 14,8385. Tuto hodnotu
dosadíme nejdříve do vztahu (5.15) a získáváme c = 0,2472. Hodnota Pearsonova koeficientu
je velmi malá, můžeme proto předpokládat, že se dané odpovědi velmi odlišují.
Čuprovův koeficient kontingence dává hodnotu K = 0,0325. Podle něho můžeme
zamítnout vztah mezi jednotlivými odpověďmi.

