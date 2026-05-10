---
title: "2_Parametry stat. znakù.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/2_Parametry stat. znakù.pdf"
date: 2009-12-27
type: PDF (text-based)
---

1.2 Popisná statistika
Popisná statistika (deskriptivní statistika) se zabývá popisem stavu nebo vývoje
hromadných jevů. Nejprve se vymezí soubor prvků, na nichž se bude uvažovaný jev zkoumat.
Následně se všechny prvky vyšetří z hlediska studovaného jevu. Výsledky šetření kvalitativní i kvantitativní, vyjádřeny především číselným popisem - tvoří obraz studovaného
hromadného jevu vzhledem k vyšetřovanému souboru.
V předchozí části jsme studovali pojem statistického výběru. V této části budeme
předpokládat, že jsme provedli výběr z populace a budeme se snažit z těchto dat získat údaje o
vlastnostech základního souboru ( populace ).
Grafické znázornění výběrových rozdělení je uvedeno v následující kapitole. V celé
této kapitole budeme využívat data z tabulky 1.3
Tabulka 1.3: Rozdělení měsíčních nákladů studentů na bydlení
Pořadí
1
2
3
4
5
6
7
8
9
10

Náklady Pořadí
850
11
910
12
920
13
920
14
920
15
1030
16
1030
17
1150
18
1190
19
1190
20

Náklady Pořadí
1560
21
1560
22
1650
23
1670
24
1780
25
1790
26
1850
27
2200
28
2600
29
2800
30

Náklady
2900
2900
3100
3150
3250
3250
3400
3600
3700
3850

Uveďme dále důležité pojmy, které budeme neustále využívat.
Četnost ( absolutní ) hodnoty xi je daná počtem prvků xi ve výběru.
Relativní četnost hodnoty xi – je daná podílem absolutní četnosti a celkového počtu
prvků ve výběru.
Kumulativní absolutní četnost hodnoty xi je daná součtem všech absolutních
četností prvků, které jsou menší nebo rovny prvku xi .
Kumulativní relativní četnost hodnoty xi je dána součtem všech relativních četností
prvků, které jsou menší nebo rovny prvku xi .

1.2.1 Míry polohy
Jde o číselné hodnoty pomocí , nichž určujeme polohu míst, kolem kterých jsou data
nejvíce umístěny , zároveň můžeme ale vyšetřovat také určité referenční předem dané polohy
prvků populace.

1.2.1.1 Průměr
Průměr x se používá v případě kvantitativních znaků. Je velmi citlivý na odlehlé
hodnoty. Průměr n hodnot x1 , x2 , … , xn vypočteme takto
n

xi
x1 + x2 + ... + xn ∑
i =1
x=
=
n
n

(1.1).

Pro naše data je x = 2422,33 .
Někdy jsou data uvedena v tabulce včetně svých absolutních četností ( počtu
opakování ) , potom počítáme průměr jako tzv. vážený průměr:
k

∑ n .x

x = i =1

i

i

(1.2)

n

V tomto případě jsou data rozdělena na k skupin o nk prvcích.
Pokud jsou data uvedena v tabulce roztříděných dat ( původní dat jsou nahrazena
příslušností do jednoho z vybraných intervalů ) vytvoříme nejprve střed intervalu ( bude
nahrazovat všechna data uvedená v daném intervalu ) a pak z těchto hodnot vytvoříme podle
vztahu (1.2) průměr.
Příklad 1.1
Zjistěte hodnotu třídního průměru dat uvedených v tabulce 1.4.
Tabulka 1.4 třídní rozdělení četností:
Rozpětí četnost
0 -500
0
500 - 1000
5
1000 - 1500
5
1500 - 2000
7
2000 - 2500
1
2500 - 3000
4
3000 - 3500
5
3500 - 4000
3
4000 - 4500
0

Hodnota středů intervalů je 250 , 750, …, 4250 . Spočítáme – li průměr podle
vzorce (1.2) je hodnota třídního průměru rovna 1733,7. Je vidět, že hodnota tohoto průměru
velmi závisí na správné volbě rozpětí třídy. Pro vytvoření stejně velkých tříd o počtu
k z celkem n prvků je možno použít tzv. Sturgesovo pravidlo
k ≈ 1 + 3,3 . log10 n

(1.3)

Například pro náš případ je n = 30 a tedy hodnota k ≈ 5,8745 . Tedy volíme k = 6.
Uveďme dále některé důležité vlastnosti průměru:
a)
b)
c)

Jestliže ke každé hodnotě xi ve výběru přičteme konstantu k , zvětší se
o konstantu k také původní průměr ( k může být libovolné reálné číslo ).
Násobíme – li každou hodnotu ve výběru xi stejnou konstantou m ,
vypočteme nový průměr jako součin starého průměru a konstanty m
Součet odchylek všech hodnot xi ve výběru od jejich průměru x je roven
nule

∑ ( x − x) = 0
n

i =1

i

(1.4)

d)

Součet čtverců odchylek všech hodnot od jejich průměru je menší než součet
čtverců odchylek všech hodnot od libovolné jiné hodnoty

∀
a≠ x

n

(

∑ xi − x
i =1

)

2

≤

n

∑ ( xi − a )

2

(1.5)

i =1

Těchto vlastností průměru využíváme také k tomu , abychom upravili vstupní hodnoty
jejich zmenšením ( resp. zvětšením ) a posunutím.
Průměr se používá jako číselná charakteristika protože:
a) Je jednoznačný
b) Je lineární
c) Je spolehlivou číselnou hodnotou.
Průměr nepoužijeme , jestliže
a) Rozdělení je vícevrcholové
b) Rozdělení má na krajích otevřené třídy
c) Údaje nejsou škálované metricky, ale ordinálně
d) Výběr je extrémně malý
e) Rozdělení je asymetrické

1.2.1.2 Modus
Modus x̂ je hodnota , která se vyskytuje nejčastěji. Podle tabulky 1.1 ho můžeme
zjišťovat i u znaků, které jsou kvalitativní, dokonce i nominální. Není ovlivňován všemi
prvky ve výběru. Jestliže je četnost všech prvků ve výběru stejná, modus neurčujeme. Jestliže
dvě nebo více navzájem sousedících hodnot nabývají stejné největší četnosti, pak aritmetický
průměr z těchto hodnot nazveme modulem. Jestliže existují dvě navzájem nesousedící
hodnoty s největšími stejnými četnostmi, uvádíme obě jako modus. Rozdělení je pak dvou
vrcholové ( bimodální ). Již ze samé definice modusu je jasné, že tato charakteristika velmi
závisí na výběru a většinou velmi kolísá.
Příklad 1.2
Zjistěte modus šetření výběru barev respondentů – bílá, červená, modrá , červená,
zelená, bílá , červená , modrá, bílá, červená.
Odpověď :
Nejčetnější výskyt má a modus je červená.
Příklad 1.3
Zjistěte hodnotu modusu pro data z naší tabulky 1.3.
Odpověď:
Podle tabulky je xˆ = 920 .
Jestliže jsou kvantitativní znaky uspořádány do třídní tabulky , určíme nejdříve
modální interval xD ( s nejvyšší četností ) a modus stanovíme interpolací
n
(1.6)
xˆ = xD + h.
n+m

kde h je délka modálního intervalu, n je četnost , xD je dolní hranice tohoto intervalu, n je
četnost následujícího intervalu a m četnost předchozího intervalu. Aplikujme vzorec (1.6) na
data z tabulky 1.4
n
1
xˆ = x D + h.
= 1500 + 500. = 1583,33
n+m
6
.
Vidíme tedy , že modus zjištěný podle vzorce (1.6) může být výrazně odlišný
od modusu skutečného.

1.2.1.3 Kvantily a medián
Přirozenou mírou rozdělení hromadných dat jsou kvantily. Daný výběr se nejdříve
seřadí od nejmenší hodnoty po největší a poté určíme pro daný p% kvantil pořadové číslo
jednotky np , pro které platí
p
p
(1.7)
n.
< n p < n.
+ 1,
100
100
kde n je počet prvků výběru.

~
Pro hodnotu p = 50% se daný kvantil označuje medián x . Jestliže je počet n sudé
číslo , vypočteme medián jako průměrnou hodnotu z hodnot stojících vlevo a vpravo od
teoretického mediánu určeného vzorcem (1.7). Medián popisuje hodnotu, která dělí daný
výběr na dvě stejně velké části. V našem příkladě je x% = 1780 + 1790 = 1785 .
2
Další významné kvantity jsou :
Dolní kvartil x0,25 je určen jako 25% kvantil.
Horní kvartil x0,75 je určen jako 75% kvantil.
V našem případě je x0,25 = 1080 a x0,75 = 3000.
Pro hodnoty kvartilů vytváříme ještě jednu míru ( jde o míru variability ) a to
kvartilové rozpětí Rq = x0,75 - x0,25
V našem případě je Rq = 3000 – 1080 = 1920.
Pro hodnoty p=10,20,…,90 nazýváme takto spočtené kvantily názvy decily.
Pro hodnoty p = 1,2,3,…,99 nazýváme podobně kvantily jako percentily.
Pomocí kvartilů je také možno velmi přehledně znázornit data v grafu s názvem Box
Plot( krabicový graf ). Pomocí něho můžeme rozdělit data z výběru na vnitřní, vnější a
odlehlá. Vytváříme ho následujícím způsobem:
Základním prvkem grafu je obdélník, jehož hrany tvoří hodnoty dolního a horního
kvartilu – uvnitř tohoto obdélníku je 50% hodnot výběru. Uvnitř je svislou čarou vyznačen
medián, popř. tečkou průměr ( křížkem modus) .
Z obdélníku vedou dvě úsečky kolmé k hranám, jejichž délka je dána vzdáleností
vnitřních hradeb od hrany obdélníku. Vnitřní hradby se vypočtou tímto předpisem
hD = x0,25 – 1,5 . ( x0,75 – x0,25 )

(1.8)

hH = x0,75 + 1,5 . ( x0,75 – x0,25 )

(1.9)

V našem případě jsou hD = 1080 – 1,5 . 1920 = -1800 a hH = 3000+1,5.1920 =5865.
Dále se počítají vnější hradby
HD = x0,25 – 2.(1,5 . ( x0,75 – x0,25 ))
HH = x0,75 + 2.(1,5 . ( x0,75 – x0,25 ))

(1.10)
(1.11)

V našem případě je HD = 1080-1.1920= - 4680 a HH = 3000+1.1920 = 8730.
Hradby slouží pro identifikaci dat ve výběru. Hodnoty uvnitř vnitřních hradeb jsou
hodnoty přilehlé; hodnoty mezi vnitřními a vnějšími hradbami jsou hodnoty vnější a
hodnoty vně vnějších hradeb jsou hodnoty vzdálené nebo jinak odlehlé. Do grafu se
zakresluje i minimum a maximum jako body.
850

-4650

-1800

3850

1080

1785

3000

5865

8730

Jestliže máme data uvedena v třídní tabulce musíme p% kvantil počítat pomocí
lineární interpolace
x p − xD
p − nD
,
(1.12)
=
xH − xD nH − nD
kde xD je dolní a xH je horní mez intervalu v němž leží daný kvantil; nD je kumulativní
relativní četnost odpovídající xD a nH je kumulativní relativní četnost odpovídající xH
.Zjistěme hodnotu kvantilu pro náš případ tabulky 1.4:
x% − 1500
0,5 − 0,33
=
⇒ x% = 1854,167 .
2000 − 1500 0,57 − 0,33
Použití mediánu je vhodné při rozděleních s otevřenými třídami, pro ordinální
hodnoty, pro velmi symetrická rozdělení.

1.2.1.4 Geometrický průměr
Provádí se jen pro hodnoty ve výběru, které jsou kladné . Jeho označení je G a spočítá
se jako n – tá odmocnina ze součinu hodnot xi. Používáme ho , jak je zřejmé z definice ,
na kvantifikovatelné znaky měřené na poměrové stupnici. Používá se k určení průměrné
změny velikosti, jestliže předpokládáme , že tato změna je konstantní ( multiplikativně ).
(1.13)
G = n x1.x2 .L.xn

Užíváme ho například v případech nalezení průměrné úrokové míry za určité období.

1.2.1.5 Harmonický průměr
Harmonický průměr H zjistíme jako podíl počtu hodnot n a součtu převrácených
hodnot výběru.

H= n

n

(1.14)

1
∑
i =1 xi

Užívá se například v případech nahrazení prosté průměrné hodnoty číslem, které data
popisuje přesněji ( například úlohy o průměrné rychlosti ).

1.2.2 Míry variability
Pomocí jen měr polohy nelze přesně popsat výběr, protože mnoho dat má stejné nebo
přibližně stejné hodnoty jednotlivých parametrů měr polohy, přesto jsou na první pohled
odlišné . Na obrázku níže je uveden případ tří skupin dat, která mají stejný průměr, modus,
medián a přesto jsou odlišná. Odlišnost vidíme v soustředění hodnot kolem průměru. Toto
soustředění budeme studovat pomocí různých měr variability.
0,8
0,7
0,6
0,5
0,4
0,3
0,2
0,1
0
-4

-3

-2

-1

0

1

2

3

4

1.2.2.1 Variační rozpětí
Variační rozpětí R se vypočte jako rozdíl mezi největší a nejmenší hodnotou výběru.
R = xmax – xmin

(1.15)

Pokračujme dále v našem příkladě , hodnota R = 3 850 – 850 = 3 000
Výhodou této míry je jednoduchost určení a porozumění. Je však málo stabilní
vzhledem k počtu členů výběru. Používá se proto jen u malých výběrů ( n ≤ 12 ). Výrazně
závisí na velikosti výběru. Proto nemůžeme mezi sebou porovnávat jednotlivé hodnoty
variačního rozpětí z různě velkých výběrů. Nedává spolehlivé odhady rozptylu základního
souboru.

1.2.2.2 Průměrná odchylka
Průměrnou odchylku e výběru definujeme jako aritmetický průměr z absolutních
hodnot odchylek všech hodnot výběru od průměru
n

∑ x −x

e = i =1

i

(1.16)

n

Uvádíme ji jen pro úplnost. Je málo stabilní vzhledem k velikosti výběru a dává
nespolehlivé odhady pro rozptyl.

1.2.2.3 Rozptyl a směrodatná odchylka
Nejužívanější mírou variability je rozptyl ( resp. směrodatná odchylka ). Pomocí
něho měříme velikost čtverců odchylek jednotlivých hodnot výběru od průměru. Označujeme
ho většinou symbolem s2 a nazýváme ho výběrovým rozptylem
2

n
1
s =
.∑ ( x i − x ) ,
n − 1 i =1

(1.17)

2

Všimněme si , že při výpočtu nedělíme součet odchylek čtverců hodnotou n ( jako při
definici klasického rozptylu ) , ale hodnotou n – 1 ( nazývanou také počtem stupňů volnosti ).
Je to provedeno proto, že získáme lepší odhad skutečného rozptylu σ2 populace.
Výběrová směrodatná odchylka se označuje symbolem s a je rovna odmocnině
z výběrového rozptylu
2

1 n
s=
.∑ ( xi − x ) ,
n − 1 i =1

(1.18)

Pro vlastní výpočet se hodí i jiná forma vzorce (1.17)
2

 n 
x
∑
i
 ∑ xi 
2
2
2
i =1
−  i =1  , i = 1,2,L ,n
s =x −x =
n
 n 




n

2

(1.19)

Použijeme – li vzorce na určení rozptylu pro data z tabulky 1.3 získáme
s = 1019733,448 a hodnota s = 1009,82 .
Jsou – li hodnoty xi výběru uvedené včetně četností ni potom přejde vzorec (1.16) na
2

2

s2 =

1 k
1  k

.∑ ni . ( xi − x ) =
.  ∑ ni .xi 2 − n.x 2  ,
n − 1 i =1
n − 1  i =1


(1.20)

kde k je počet všech různých hodnot ve výběru a n je celkový počet prvků výběru.
Jestliže jsou data uvedena pomocí třídění do intervalů např. data z tabulky 1.4 , potom
většinou hodnoty xi znamenají středy třídních intervalů a ni počet dat v tomto intervalu. Pokud
jsou třídní intervaly ekvidistantní ( mají pevnou délku ) s rozměrem h bude výpočet podle
vzorce (1.20) zatížen chybou . Tuto chybu opravujeme pomocí tzv. Sheppardovy korekce

s 2 kor = s 2 −

h2
12

(1.21)

Použijeme – li opět naše data z tabulky 1.4 získáme :
Nekorigované hodnoty s2 = 1002500 a s = 1001,249;
Korigované hodnoty s2kor = 981666,7 a skor = 990,7909.
Velmi často nastává případ , že celý výběr je z určitých důvodů rozdělen do k dílčích
částí . V i – té části je počet prvků roven ni , průměr je roven xi a výběrový rozptyl si2 .
Potom můžeme počítat celkový výběrový rozptyl s2 jako
s2 =

k
1  k
2
.  ∑ ( ni − 1) .si 2 + ∑ ni . ( xi − x ) 
n − 1  i =1
i =1


(1.22)

Z předchozího vzorce vyplývá, že celkový výběrový rozptyl s2můžeme rozložit na dvě
části – na vnitroskupinový a meziskupinový.
Vnitroskupinovým výběrovým rozptylem sledujeme variabilitu uvnitř jednotlivých
skupin a meziskupinovým výběrovým rozptylem variabilitu mezi těmito skupinami. Takovéto
metody rozdělení celkové variability na nezávislé části budeme dále využívat v části Analýza
rozptylu ( ANOVA ).
Výběrový rozptyl nezávisí na zvětšení či zmenšení všech hodnot výběru o konstantu.
Jestliže všechny hodnoty výběru zvětšíte m - krát , zvětší se výběrový rozptyl m2 – krát.
Těchto vlastností velmi často využíváme pro úpravu původní tabulky dat tím, že všechny
hodnoty posuneme - volba nového počátku a výrazně zmenšíme ( zvětšíme ) – volba nové
jednotky.

1.2.2.4 Variační koeficient
Nechť má výběr n členů s průměrem x a směrodatnou odchylkou s. Potom variační
koeficient výběru v je daný vztahem
s
(1.23)
v = .100%
x
Používáme ho , když chceme porovnat variabilitu různých znaků ve výběru nebo mezi
různými výběry.

1.2.3 Charakteristiky tvaru rozdělení

1.2.3.1 Výběrová míra šikmosti
Jde o číselný údaj, který vypovídá o o souměrnosti či nesouměrnosti tvaru rozdělení.
Označuje se symbolem a .
n

∑(x − x )

a = i =1

3

i

n.s 3

(1.24)

,

kde n je počet členů výběru, s je hodnota výběrové směrodatné odchylky, x je průměr
a xi je konkrétní hodnota výběru. Je – li rozdělení souměrné, je hodnota a = 0. Rozdělení je
tím nesousměrnější , čím se hodnota a více liší od nuly. Je – li jeho hodnota kladná, potom je
rozdělení zešikmeno kladně ( ve výběru je větší koncentrace menších hodnot ). Je – li jeho
hodnota záporná, potom je zešikmeno záporně (ve výběru je větší koncentrace větších
hodnot).
Pokračujme s naším příkladem , s daty z tabulky 1.1. Níže vidíme data v grafu.
Polygon četností
3,5
3
2,5
2
1,5
1
0,5
0
800

1300

1800

2300

2800

3300

3800

Hodnota míry šikmosti pro naše hodnoty a = 1. Je tedy kladná a data jsou zešikmena
kladně.

1.2.3.2 Výběrová míra špičatosti.
Tato míra popisuje stupeň koncentrace hodnot znaku kolem charakteristiky úrovně
( kolem průměru ). Stejné nahuštění prostředních i krajních hodnot vede k plochosti ( hodnota
míry je potom záporná ), větší nahuštění prostředních hodnot se projevuje špičatostí
rozdělení( hodnota míry je kladná. Tato míra porovnává dané rozdělení s normovaným
normálním rozdělením N(0,1) ( má hodnotu špičatosti rovnu nule ). Vypočte se podle vztahu

n

∑ (x − x )

b = i =1

i

n.s 4

4

− 3,

(1.25)

označuje se symbolem b.
Hodnota špičatosti pro naše data z tabulky 1.3 je rovna – 0,93 . Rozdělení je ploché,
což je vidět i z polygonu četností.

