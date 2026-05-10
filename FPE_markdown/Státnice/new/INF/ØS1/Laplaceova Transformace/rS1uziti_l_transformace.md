---
title: "rS1uziti_l_transformace.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Státnice/new/INF/ØS1/Laplaceova Transformace/rS1uziti_l_transformace.pdf"
date: 2009-02-22
type: PDF (text-based)
---

K. Kadlec: Měřicí a řídicí technika pro FPBT

Základy operátorového počtu
Laplaceova transformace
• matematický aparát, který patří do t.zv. operátorového
počtu, kde jsou určité matematické operace nahrazeny
symboly, pro které je definována samostatná algebra
• využívá se k řešení lineárních diferenciálních rovnic
s konstantními koeficienty (s využitím operátorového
počtu se převede řešení diferenciálních rovnic na řešení
rovnic algebraických)
• umožňuje jednoduše vyjadřovat dynamické vlastnosti
systémů
• využívá se v teorii automatického řízení
1

Užití Laplaceovy transformace
k řešení diferenciálních rovnic
integrace
diferenciální rovnice

řešení
diferenciální rovnice

Laplaceova
transformace

L-1 transformace

L

zpětná

algebraické
operace
algebraická rovnice

řešení
algebraické rovnice

2

Definice Laplaceovy transformace:
Původní funkce
Originál (předmět)
y(t)
y(t)

Transformovaná funkce
Obraz
transformace

zpětná transformace

Y(p)
Y(p)

y(t) - funkce reálného argumentu t
Y(p) - funkce komplexního argumentu p
p - operátor
∞

L{ y (t )} = ∫ y (t ).e − p.t dt = Y ( p )

Definiční vztah:

0

podmínky transformace:
– y (t) je po částech spojitá
– y (t) = 0 pro t < 0
– y (t) je funkcí exponenciálního řádu

3

Vybraná pravidla Laplaceovy transformace:
Linearita transformace (násobení konstantou):

k 1.f (t ) + k 2 .g (t ) → k 1.F ( p ) + k 2 .G( p )
Obraz derivace při nulových počátečních podmínkách:

y ′(t ) → p.Y ( p )
y ( n ) (t ) → p n .Y ( p )
Obraz integrace při nulových počátečních podmínkách:

1

∫ y ( t ) dt → p Y ( p )
4

2-FPBT06-OPER_MODEL_B.DOC -16.2.2006

1

Operátorový počet-Přenosová algebra-Modelování

K. Kadlec: Měřicí a řídicí technika pro FPBT

Laplaceovy obrazy vybraných funkcí
Operátorový slovník
Transformovaná
funkce

Původní funkce
Originál
Jednotkový
skok
Diracův skok

Obraz
1(t)

1
p

δ (t)

1

e ± at

1
pma

1 - e −at

a
p(p + a)

Operátorového slovníku se využívá při zpětné transformaci

5

Popis dynamického chování obrazovým přenosem
u(t)

diferenciální
rovnice soustavy

y(t)

any(n) + . . . + a2y’’ + a1y’ + a0y = bmu(m) + . . . + b2u’’ + b1u’ + b0u
• n > m a všechny počáteční podmínky jsou nulové
• provedeme Laplaceovu transformaci diferenciální rovnice a
získáme operátorovou rovnici:

[anpn +. .+ a2p2 + a1p + a0].Y(p) = [bmpm +. .+ b2p2 + b1p + b0].U(p)
Definice obrazového přenosu:

Obraz výstupu

Obrazový přenos soustavy =
Obraz vstupu

G(p) =

Y(p)
U(p)

G(p) =

bm p + .. + b2 p 2 + b1p + b0
an p n + .. + a2 p 2 + a1p + a0
m

6

Popis dynamického chování obrazovým přenosem
U(p)

U(p)
obraz
vstupu

obrazový přenos
soustavy

G(p)

Y(p)
obraz
výstupu

Y(p)

přenos:
Y(p)
G(p) =
U(p)

• přenos vyjadřuje dynamické vlastnosti systému
bez ohledu na obraz a průběh vstupní veličiny
• obrazovým přenosem můžeme velmi jednoduše popsat
dynamické chování jednotlivých členů obvodu
• z obrazových přenosů jednotlivých bloků můžeme
vypočítat přenos celého obvodu a popsat jeho chováni
7

Příklady vyjádření dynamického chování
diferenciální rovnicí a obrazovým přenosem
Poznámka:
Ve všech případech jsou všechny počáteční podmínky nulové

• K diferenciální rovnici napište přenos:
3y’’ + 8y’ + 5y = 9u’ + 4u

9p + 4
G(p) = ? 2
3p + 8p + 5

6y’’’ + y’ + 2y = 3u

3
G(p) = ? 3
6p + p + 2

• K přenosu napište diferenciální rovnici:
G(p) =

1
3p + 6

3?y ′ + 6 y = u
8

2-FPBT06-OPER_MODEL_B.DOC -16.2.2006

2

Operátorový počet-Přenosová algebra-Modelování

K. Kadlec: Měřicí a řídicí technika pro FPBT

Algebra přenosů
• jednosměrné šíření signálu
• jednotlivé členy se vzájemně neovlivňují
• vzájemné ovlivňování se vyjádří zpětnou vazbou

Sériové spojení bloků
U(p)

Y1(p)

G1(p)

Y(p)

G2(p)

Výsledný přenos spojených bloků:

G(p) =

Y(p)
= G1(p). G2 (p)
U(p)

9

Paralelní spojení bloků
Y1(p)

G1(p)

U(p)

Y(p)
Y2(p)

G2(p)

Výsledný přenos spojených bloků:

G(p) =

Y(p)
= G1(p) + G2 (p)
U(p)
10

Obvod se zápornou zpětnou vazbou
U(p)

U1(p)

Y(p)

G1(p)

–

G2(p)

Y2(p)

Y(p)

Výsledný přenos spojených bloků:

G(p) =

Y(p)
G1(p)
=
U(p) 1 + G1(p).G2 (p)
11

Obecný vztah pro výpočet přenosu obvodu:
Y(p)
přenos přímé cesty
G(p) =
=
U(p) 1 m ∑ přenosů všech smyček
− pro kladnou zpětnou vazbu
+ pro zápornou zpětnou vazbu

Příklad:

U(p)
G1(p)

G2(p)

–
G4(p)

G(p) =

G3(p)
G5(p)

Y(p)

G6(p)

G1(p).G2(p).G3(p)
1 − G3(p).G6(p) + G2(p).G3(p)G6(p).G5(p).G4(p)

2-FPBT06-OPER_MODEL_B.DOC -16.2.2006

12

3

Operátorový počet-Přenosová algebra-Modelování

K. Kadlec: Měřicí a řídicí technika pro FPBT

Shrnutí důležitých pojmů
Statické vlastnosti
• statická charakteristika

Dynamické vlastnosti
• diferenciální rovnice
• přechodová charakteristika
• obrazový přenos
• algebra přenosu

13

Modelování regulovaných soustav
Matematický model
• matematické vztahy popisující chování procesu (systému)
• dynamické chování popisujeme nejčastěji diferenciálními
rovnicemi
• pro účely řízení se často používá popisu ve tvaru
obrazového přenosu

Matematické modelování
• vytvoření matematického modelu procesu
• matematické modely jako náhrada experimentu
• technologické a ekonomické důvody vytváření
matematických modelů reálných zařízení
• možnost simulace chování systému na počítači
14

Postup modelování a simulace:
zásah
(vzruch)

reálný
objekt

odezva

MODELOVÁNÍ
vstupní
funkce

u(t)

matematický
model

výstupní
funkce

y(t)

SIMULACE
vstupní
signál

simulační
program

výstupní
signál

Přenos výsledků
do reality

• analýza procesu (systému)
• teoretický model
• matematický popis

• vytvoření simulačního
programu
• určení hodnot parametrů
• ověření shodnosti modelu

• výpočty chování systému
za různých podmínek
• predikce chování systému

15

Matematické modely:
• stochastické
– systém je studován jako černá skříňka
– matematický popis je formální

• deterministické

– vychází z obecně platných zákonitostí popisujících
proces
– matematický popis vyjadřuje podstatu procesu

Postup vytváření stochastického modelu:
• na vstup systému se přivádí proměnlivý signál a zapisuje
se odezva (získání dostatečného množství hodnot)
• speciálními matematickými postupy se zpracují výsledky
pro matematický popis
16

2-FPBT06-OPER_MODEL_B.DOC -16.2.2006

4

Operátorový počet-Přenosová algebra-Modelování

K. Kadlec: Měřicí a řídicí technika pro FPBT

Postup vytváření deterministického modelu:
• analýza procesu
– specifikace a podstata dějů probíhajících v systému
– vlivy působící na proces
– veličiny popisující proces (jejich významnost)
– možnosti zjednodušení popisu (zanedbání vlivu)
⇒ výsledkem je teoretický model procesu

• matematický popis procesu
– matematické vyjádření fyzikálních, fyzikálněchemických či chemických zákonitostí
– vytvoření modelových rovnic
– určení počátečních a okrajových podmínek řešení
– návrh metody řešení modelových rovnic
⇒ výsledkem je matematický model
17

Obecné zásady odvozování modelů
• základní rozvaha
– nakreslení blokového schéma
– vyznačení výstupní veličiny
– vymezení vlivů, vyznačení vstupních veličin
– zjednodušující předpoklady

• bilance

– bilancovaný systém (okolí systému, rozhraní)
– určení bilancované veličiny
– určení bilančního časového intervalu
– bilance v ustáleném stavu či v průběhu
přechodového děje
– bilanční rovnice pro bilanci hmoty nebo energie

• matematický model
– diferenciální rovnice
(počáteční podmínky, zápis v dohodnutém tvaru)
– obrazový přenos

18

Základní bilanční rovnice
vstup + zdroj = výstup + akumulace
• vstup
množství bilancované veličiny, které za bilanční interval
vstoupí z okolí přes rozhraní do bilancovaného systému

• výstup
množství bilancované veličiny, které za bilanční interval
vystoupí z bilancovaného systému přes rozhraní do okolí

• zdroj
množství bilancované veličiny, které za bilanční interval
uvnitř systému vznikne (znaménko +), nebo zanikne (-)

• akumulace
změna množství (zádrže) bilancované veličiny uvnitř
bilancovaného systému za bilanční interval

19

Příklady odvozování modelů regulovaných soustav

Koncentrační směšovač
roztok A
c 1, Q 1

M

roztok B
c 2, Q 2

Q1
Q2
c1
c2

objem roztoku
v nádrži
V
roztok C
c 3, Q 3
Bilancovaná veličina:
množství rozpuštěné látky

c3

Zjednodušení:
• ideální promíchávání
• Q3 = Q1 + Q2
• V = konst.
c - koncentrace [kg.m-3]
Q - průtok [m3.s-1]
V - objem [m3]

Bilance v ustáleném stavu:

Statická charakteristika:

Q1.c1+ Q2.c2 = (Q1 + Q2).c3

c3 =

Q1.c1 + Q2.c2
Q1 + Q2

2-FPBT06-OPER_MODEL_B.DOC -16.2.2006

20

5

Operátorový počet-Přenosová algebra-Modelování

K. Kadlec: Měřicí a řídicí technika pro FPBT

Bilance v průběhu přechodového děje:
bilanční interval: dt
množství látky vstupující
do systému za interval dt

zdroj = 0
množství látky vystupující
ze systému za interval dt

=

+
akumulace látky v systému
za bilanční interval dt

Q1.c1.dt + Q2.c2.dt = Q3.c3.dt + V.dc3
úprava rovnice:
dělit dt a převést:
na levou stranu rovnice výstupní veličinu, na pravou vstupní veličiny

Matematický model směšovače:

počáteční podmínky:

dc
V . 3 + Q3 .c3 = Q1.c1 + Q2 .c2
dt

pro t = 0, c1,2 = c1,2

0

c3 = c30

21

Převod na nulové počáteční podmínky:
Další zjednodušení:
• uvažujeme pouze změnu koncentrace c1
• ostatní vstupní veličiny se nemění

c1 = c10 + ∆c1
c3 = c30 + ∆c3

Zavedeme odchylkové tvary:

V.

d(c30 + ∆c3 )
+ Q3 .(c30 + ∆c3 ) = Q1.(c10 + ∆c1 ) + Q2 .c2
dt
Q3 .c30 = Q1.c10 + Q2.c2

pro ustálený stav platí:

Diferenciální rovnice s konstantními koeficienty a nulovými
počátečními podmínkami:

V .( ∆c3 )′ + Q3 .∆c3 = Q1.∆c1

pro t = 0, ∆c3 = 0
uvažujeme změnu ∆c1 skokem
22

Vyjádření dynamického chování obrazovým přenosem
Diferenciální rovnice popisující soustavu:

V .( ∆c3 )′ + Q3 .∆c3 = Q1.∆c1

pro t = 0, ∆c3 = 0

• V, Q3, Q1 jsou konstanty
• nulové počáteční podmínky

Obrazový přenos:
∆C1(p)
obraz
vstupu

G(p)

∆C3(p)
obraz
výstupu

G(p) =

Q1
∆C3 ( p )
=
∆C1( p ) Vp + Q3
23

Tepelný výměník
• elektrický vyhřívaný průtočný výměník tepla
• se ztrátami tepla do okolí
P
teplota okolí
teplá voda
Q
θ3
θ2, Q
θ1

θ2

θ3

příkon
topení

P

objem
zásobníku
studená voda

θ1, Q

V

Zjednodušení:
• ideální promíchávání
• zanedbatelná tepelná
kapacita stěn nádrže
• nezávislost ρ, α, cp na θ
• účinnost topení 100 %

θ - teplota [°C]

A - povrch výměníku [m2]
Q - průtok [m3.s-1] ρ - hustota [kg.m-3]
V - objem [m3]
α - koeficient prostupu [W.m -2.K -1]
P - příkon [W]
cp- měrná tep.kapacita [J.kg-1.K -1]

2-FPBT06-OPER_MODEL_B.DOC -16.2.2006

24

6

Operátorový počet-Přenosová algebra-Modelování

K. Kadlec: Měřicí a řídicí technika pro FPBT

Sestavení matematického modelu
Bilancovaná veličina: entalpie

Bilance v ustáleném stavu:

bilanční interval: libovolný

Qρc pϑ1 + P = Qρc pϑ2 + αA(ϑ2 − ϑ3 )
Qρc pϑ1 + P + αAϑ3
Statická charakteristika:
ϑ2 =
Qρc p + αA
Bilance v průběhu přechodového děje: bilanční interval: dt
+

vstup

=

zdroj

výstup

+

akumulace

Qρc pϑ1dt + Pdt = Qρc pϑ2dt + αA(ϑ2 − ϑ3 )dt + Vρc p dϑ2
Matematický model tepelného výměníku:

dϑ2
+ (Qρc p + αA)ϑ2 = Qρc pϑ1 + P + αAϑ3
dt
• diferenciální rovnice s nenulovými
ϑ2 (0) = ϑ20
počátečními podmínkami
Vρc p

25

Převod na nulové počáteční podmínky:
Další zjednodušení:
• uvažujeme pouze změnu příkonu P
• ostatní vstupní veličiny se nemění

P = P 0 + ∆P
ϑ2 = ϑ20 + ∆ϑ2

Zavedeme odchylkové tvary:

′
Vρc p ∆ϑ2 + (Qρc p + αA).(ϑ20 + ∆ϑ2 ) = Qρc pϑ1 + P 0 + ∆P + αAϑ3
Pro ustálený stav platí: (Qρc p + αA ).ϑ2 = Qρc pϑ1 + P
Po úpravě dostaneme:
0

′
Vρc p ∆ϑ2 + (Qρc p + αA)∆ϑ2 = ∆P

0

+ αAϑ3

pro t = 0, ∆ϑ2 = 0

• diferenciální rovnice s konstantními koeficienty a nulovými
počátečními podmínkami a pro změnu ∆P skokem
Analogicky získáme vztahy i pro změny dalších vstupních veličin

26

Diferenciální rovnice se změnami i dalších vstupních veličin
Uvažujeme změny ∆P, ∆θ1, ∆θ3 :

′
Vρc p ∆ϑ2 + (Qρc p + αA)∆ϑ2 = Qρc p ∆ϑ1 + ∆P + αA∆ϑ3
• V, ρ, cp, Q, α, A jsou konstanty
• nulové počáteční podmínky

∆ϑ1( p )
∆P(p)
∆ϑ3 ( p )

G1(p)
G2(p)
G3(p)

∆ϑ2 ( p )

Obrazové přenosy:

G1(p) =

∆ϑ2 ( p )
∆ϑ1( p )

G2(p) =

∆ϑ2 ( p )
∆P ( p )

G3(p) =

∆ϑ2 ( p )
∆ϑ3 ( p )
27

Nádrž s výtokem kapaliny
• nádrž opatřená dvěma přítoky
• odtok výtokovým ventilem
přítok
Q2

• výstupní veličina: výška hladiny

Q1

přítok
Q1

h

Q2
Q3

hladina
h

odtok
Q3

Q - průtok [m3.s-1]
h - výška hladiny [m]
A - průřez nádrže [m2]
z - zdvih ventilu [mm]
Pro průtok ventilem platí:

Q3 = k .z. ∆p
∆p = h.ρ .g
Q3 = K .z. h

2-FPBT06-OPER_MODEL_B.DOC -16.2.2006

28

7

Operátorový počet-Přenosová algebra-Modelování

K. Kadlec: Měřicí a řídicí technika pro FPBT

Sestavení matematického modelu
Bilancovaná veličina: objemové množství kapaliny

Bilance v ustáleném stavu:

Q1 + Q2 = Q3

bilanční interval: libovolný

Q1 + Q2 = K .z. h

Statická charakteristika:

h=

Q1 + Q2
K .z

(nelineární průběh)

Bilance v průběhu přechodového děje: bilanční interval: dt
=

vstup

výstup

+

akumulace

Q1dt + Q2dt = K .z. h.dt + A.dh
Linearizace vztahu: K .z. h
• uvažujeme malé změny ∆z a ∆h v okolí pracovního bodu z0, h0

K .z. h = K .z 0 . h0 + K . h0 ∆z +

K .z 0
∆h
2 h0

29

Linearizovaná diferenciální rovnice
Použijeme odchylkové tvary:
• pro vstupní veličiny:

z = z 0 + ∆z

Q1 = Q10 + ∆Q1
Q2 = Q20 + ∆Q2
0
h = h + ∆h
• pro výstupní veličinu:
Vyjdeme z rovnice sestavené bilancí za dt

A.dh + Kz h.dt = Q1dt + Q2dt
• dosadíme odchylkové veličiny a použijeme vztah pro linearizaci:

Kz 0
∆h ).dt =
2 h0
= (Q10 + ∆Q1).dt + (Q20 + ∆Q2 ).dt

Ad( h0 + ∆h ) + (Kz 0 h0 + K h0 ∆z +

• upravíme rovnici vydělením dt
30

Po úpravě dostaneme:

A

d( h0 + ∆h )
Kz 0
+ (Kz 0 h 0 + K h0 ∆z +
∆h ) =
dt
2 h0
0
= (Q1 + ∆Q1 ) + (Q20 + ∆Q2 )

Kz h = Q1 + Q2
Pro ustálený stav platí:
Po úpravách
• respektování ustáleného stavu
• převedení vstupních veličin na pravou stranu rovnice
dostaneme:
0

A.∆h′ +
pro t = 0,

0

0

0

Kz 0
∆h = ∆Q1 + ∆Q2 − K h0 ∆z
2 h0
∆h = 0

• linearizovaná diferenciální rovnice s konstantními
koeficienty a nulovými počátečními podmínkami

31

Porovnání matematických modelů různých systémů
Uvažujeme vždy jen jednu vstupní veličinu
Koncentrační směšovač:

V .( ∆c3 )′ + Q3 .∆c3 = Q1.∆c1

Tvorba matematického modelu soustavy
∆c3 (0) = 0

• blokové schéma
• vyznačení výstupní veličiny
• vyznačení vstupních veličin
• hmotnostní nebo energetická bilance
• úprava diferenciální rovnice do standardního tvaru
• obrazový přenos

Tepelný výměník:

′
Vρc p ∆ϑ2 + (Qρc p + αA)∆ϑ2 = ∆P

∆ϑ2 (0) = 0

Nádrž s ventilem:

A.∆h′ +

Kz 0
∆h = −K h0 ∆z
2 h0

∆h(0) = 0

Ukázky pouze jednoduchých modelů
• analogicky je možno řešit i komplikovanější
– systémy s přenosem tepla
– systémy s chemickou reakcí
– kinetika biotechnologických procesů

Fyzikálně odlišné systémy, které vykazují shodné dynamické
vlastnosti můžeme popsat jedinou diferenciální rovnicí:

s1.y ′ + s0 .y = b0 .u

y (0) = 0
32

2-FPBT06-OPER_MODEL_B.DOC -16.2.2006

Shrnutí dnešní přednášky

8

33

Operátorový počet-Přenosová algebra-Modelování

