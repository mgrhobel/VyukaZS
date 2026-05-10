---
title: "13_Testovani hypotez.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/13_Testovani hypotez.pdf"
date: 2009-12-27
type: PDF (text-based)
---

6. Testování statistických hypotéz
Úvod
Při práci s daty se mnohdy spokojujeme s intervalovým či bodovým odhadem
parametrů populace. V mnohých případech se však uchylujeme k jinému postupu, většinou
jde o případy , kdy řešíme problémy související s typem rozdělení populace, s nezávislostí
výběru atd. , někdy jsme prostě nuceni stanovovat určité výroky, které mají statistické pozadí
a studovat jejich pravdivost. Zavádíme proto pojem statistické hypotézy .
Definice 6.1
Statistickou hypotézou budeme rozumět výrok o náhodných veličinách. V případě, že
tento výrok pojednává o parametrech populace nazýváme takovouto hypotézu
parametrickou, jestliže vyšetřujeme jiné okolnosti ( např. typ rozdělení populace, nezávislost
výběru, způsob výběru atd.) nazýváme takovou hypotézu neparametrickou.
Hypotézami parametrickými se budeme zabývat v následující 17. kapitole a
neparametrickými v kapitole 18. a kapitole 19.
Obecně je možnou dělit statistické hypotézy ještě mnoho dalšími způsoby např. podle
počtu šetřených populací, podle toho zda jsou jednoduché nebo složené. Těmito okolnostmi
se budeme zabývat víceméně okrajově.
Výrok, jehož platnost ověřujeme, nazýváme většinou nulovou nebo jinak testovanou
hypotézou. Podle ustáleného označení takový výrok popisujeme symbolem H0 . Hypotéza H0
v tomto případě vyjadřuje dosavadní představy o těch skutečnostech, které vyšetřujeme
( odráží stav poznání, které máme v současné době o těchto skutečnostech ). Názor
pochybnosti o platnosti nulové hypotézy vyjadřuje v našem modelu alternativní nebo jinak
výzkumná hypotéza. Takovouto hypotézu většinou stavíme tak, aby její pravdivost
znamenala většinou pokrok či nějakou změnu v dosavadních šetřeních. Alternativní hypotézu
většinou značíme H1 resp. HA .
Testem statistické hypotézy rozumíme proces rozhodování, při kterém na základě
náhodných výběrů provedeme rozhodnutí ve prospěch právě jedné z předložených hypotéz.
Znamená to, že formulace hypotéz je prováděna tak, aby v daném okamžiku platila právě
jedna. Z formálního hlediska představují tedy hypotézy H0 a H1 úplnou množinu
neslučitelných jevů.
Abychom tedy provedli korektní vyhodnocovací proces o správnosti předložených
hypotéz ( výroků ), je nutné mít k dispozici nástroj, pomocí něhož rozhodujeme o správnosti
předložených výroků.
Tento nástroj se nazývá testovací statistika nebo testové kritérium. Množina
hodnot, kterých testová statistika nabývá se rozpadá na dvě disjunktní množiny , které
nazýváme obor přijetí ( testované hypotézy H0 )
a kritický obor ( obor zamítnutí
hypotézy H0 ) . .
Kritický obor obsahuje takové hodnoty, že pravděpodobnost jejich výskytu je velmi
malá. Jestliže přesto hodnota testové statistiky je prvkem množiny , zamítáme testovanou
hypotézu H0 ve prospěch alternativní hypotézy H1 . Padne – li však hodnota testové statistiky
do množiny říkáme, že uvedený test neprokázal nepravdivost testované hypotézy H0 .
Při takovémto postupu samozřejmě mohou nastat chyby v našich rozhodnutích.
Zásadou je takové chyby studovat a pomocí jejich výskytu potom oceňovat vhodnost či
nevhodnost použité hypotézy. Jestliže chybně zamítneme hypotézu H0 vytvoříme chybu I.

druhu , pravděpodobnosti jejího výskytu je označována jako α ( někdy jako 1 - α ) , tomuto
číslu se pak říká hladina významnosti. V praktických úlohách se vyskytují převážně hodnoty
α = 0,95 ( resp. 0,05 )– říkáme , že tato hladina je významná ; pro hladinu α = 0,99
prohlašujeme, že hladina je velmi významná a konečně pro hodnotu α = 0,99 je hladina
vysoce významná.
Kromě chyby prvního druhu se můžeme dopustit při práci s hypotézami i chyby, kdy
nezamítneme hypotézu H0 , i když tato hypotéza neplatí. Takovéto chybě se říká chyba II.
druhu , pravděpodobnost výskytu takové chyby označujeme β . Doplněk hodnoty β do jedné
je 1 - β je tedy pravděpodobnost, že hodnota testovací statistiky správně spadne do kritického
oboru . Platí tedy následující ( symbolem T označujeme testovací statistiku )

P (T ∈ – H 0 ) = α

(6.1)

P ( T ∈ • H1 ) = β

(6.2)

P ( T ∈ – H1 ) = 1 − β

(6.3)

Pro posouzení kvality testovacího postupu je důležitá silofunkce ,. Vyjadřuje průběh
pravděpodobnosti hodnoty 1 - β při různých hodnotách α .Nepodaří – li se nám prokázat, že
hodnota testové statistiky je v kritickém oboru, musíme se spokojit s tvrzením , že daná data
nejsou v rozporu s tvrzením hypotézy H0 .
Popišme si tedy dále vlastní postup při práci s testováním statistických hypotéz:

I.

Na základě znalostí matematického problému stanovujeme hypotézu H0 . Tuto
hypotézu budeme považovat za pravdivou do okamžiku, kdy vybraná data neprokážou
opak.
II.
Stanovení alternativní hypotézy H1 . Jde o tvrzení, které je v rozporu s hypotézou H0 .
Alternativní hypotéza je považována za pravdivou po vyvrácení hypotézy H0 .
III.
Volba testovací statistiky T . Jde o náhodnou veličinu na základě níž rozhodneme o
pravdivosti jednotlivých hypotéz.
IV.
Stanovení hladiny významnosti testu , stanovíme pravděpodobnost chyby
I. druhu
V.
Stanovení kritického oboru testovací statistiky T .Konkrétní stanovení kritického
oboru závisí na hladině významnosti α
VI.
Ověření předpokladů testu . Některé testy vyžadují splnění určitých podmínek, které
musíme pro naše konkrétní data ověřit
VII. Vlastní provedení náhodného výběru z populace by mělo být provedeno korektně .
Podmínky takového výběru by měli být podrobně ověřeny. Data poté musíme přesně
interpretovat při výpočtu v testovací statistice.
VIII. Po tomto procesu je zapotřebí rozhodnout o dvou možných výrocích :
a. Hypotéza H0 se zamítá a alternativní hypotéza se přijímá. Takovýto výrok
připouštíme tehdy , když hodnota testovací statistiky leží v kritickém oboru .
V tomto případě je zapotřebí konstatovat, že je prokázána pravdivost alternativní
hypotézy H1 nebo , že rozdíl mezi předpokládanou a vypočítanou hodnotou se
ukázal na dané hladině významnosti jako statisticky významný.
a. Hypotézu H0 nezamítáme v případě , je –li hodnota testovací statistiky v oboru
přijetí
. Většinou konstatujeme, že na dané hladině významnosti nebyla
testovaná hypotéza H0 zamítnuta..

V další části využijeme a upravíme příklad 2.3, který je uvedený ve skriptech
Praktikum k výuce matematické statistiky II: Testování hypotéz, VŠE Praha, 2000.
Příklad 6.1
Předpokládejme, že výsledky experimentů souhlasily s náhodnou veličinou X
s normálním rozdělením se střední hodnotou µ a rozptylem 64 . Dosud uznávaná hodnota µ je
25. Při vyhodnocování hodnot experimentů došlo k určitým změnám a nyní se zdá, že
hodnota µ vzrostla a je větší než 25. Úkolem je na základě n nezávislých experimentů
rozhodnout, zda platí hypotéza H0 : µ χ 25 nebo alternativní hypotéza H1 : µ > 25.
K tomu , abychom mohli některou z uvedených hypotéz zamítnout, je třeba nalézt
vhodnou statistiku. Již z předchozích přednášek víme, že nejlepším bodovým odhadem µ je
n

aritmetický průměr X =

∑X
i =1

i

, jako testovou statistiku použijeme tedy realizaci tohoto
n
průměru. Provedeme nyní řešení našeho problému třemi různými způsoby.
Varianta 1.
Předpokládejme , že jsme provedli náhodný výběr například o rozsahu 40 prvků.
Stanovíme hypotézu H0 : µ χ 25 a alternativní hypotézu H1 : µ > 25. Kritickým oborem bude
stanovena množina
n


W = ( x1 ,L , xn ) ; ∑ xi > 40.25 = 1000  .
i =1


Zjistíme hodnotu silofunkce K(β) = 1 - β(µ). Silofunkce udává pro různé hodnoty µ
pravděpodobnost, že výběrový průměr bude větší než 25. Při náhodném výběru z populace
64 8
= ).
popsané N(µ,64) víme, že výběrový průměr je typu normální rozdělení N(µ,
40 5
Můžeme tedy hodnotu K(µ) přímo spočítat :




 X − µ 25- µ 

25- µ 
 = PZ >
.
K ( µ ) = P ( X > 25) = P 
>
 8

8 
8 




5 
5 
 5


V dále uvedené tabulce jsou zaznamenány hodnoty K(µ) :
K(µ)
0,008853
0,056923
0,214598

µ
22
23
24

K(µ)
0,5
0,785402
0,943077
0,991147

µ
25
26
27
28

Všimněme si, že pro µ = 25 je hypotéza H0 pravdivá, ale pravděpodobnost jejího
zamítnutí je 50%. To je příliš vysoká pravděpodobnost zamítnutí pravdivé hypotézy !
Varianta 2.
Alternativní hypotézu H1 : µ > 25 přijmeme za podmínky, je – li výběrový průměr
větší než 27. V tomto případě bude hodnota silofunkce K(µ)rovna


 27 − µ 

K ( µ ) = P ( X > 27) = 1 − Φ 

8 


5 


(6.4)

Po dosazení stejných hodnot jako v minulé variantě získáváme následující tabulku:
K(µ)
3,86E-05
0,000783
0,008853
0,056923
0,214598
0,5
0,785402

µ
22
23
24
25
26
27
28

Pro hodnotu µ = 25 je nyní pravděpodobnost zamítnutí ( pravdivé ) hypotézy H0 malá
na úrovni 5,7% , ale pro hodnotu 26 ( nepravdivé ) je pravděpodobnost zamítnutí jen 21,5% a
to je trochu příliš.
Varianta 3.
V této části budeme postupovat obráceně a určíme přímo hodnoty silofunkce K(µ)
v některých důležitých bodech a z těchto skutečností budeme chtít určit kritický obor W a
n


rozsah výběru. Nechť tedy W = ( x1 ,L , xn ) ; ∑ xi > n.c  , kde hodnoty n a c jsou v dané chvíli
i =1


neznámé a budeme je dále počítat. Za těchto podmínek má silofunkce hodnotu


c−µ 

K ( µ ) = P ( X > c) = 1− Φ 
 64 


 n 

(6.5)

Chtějme nyní , aby pro hodnotu µ = 25 byla síla testu rovna 0,05 a zároveň aby pro
hodnotu µ = 26 byla síla testu 0,9. Získáme tedy po dosazení následující soustavu:



 c − 25 
 = 0, 05 ,
1− Φ 
 64 


 n 



 c − 26 
 = 0,90
1− Φ 
 64 


 n 

Nyní využijeme kvantily N(0,1) a soustava se převede na
c − 26
= −1, 28
64
n

c − 25
= 1, 64
64
n

Řešením této soustavy jsou hodnoty n = 545,7 a hodnota c = 25,56. Shrneme – li nyní
získané výsledky měl by mít náš výběr rozsah aspoň 546 prvků a kritický obor by měl být
omezen číslem 25,56.
Příklad 6.2
Předávací cena mezi výrobcem a prodávajícím byla odvozena mimo jiné z toho, že
podíl reklamovaných výrobků v záruční době byl 15%. Tato situace se jednou za čas ověřuje.
Náhodným výběrem určitého počtu výrobků :
a) Chtějí oba ověřit, že předpokládaný podíl je stále aktuální
b) Výrobce chce ukázat, že podíl je nadhodnocený a cenu chce zvýšit
c) Prodejce chce prokázat, že podíl je podhodnocený a cenu chce snížit.
Formulujte v těchto případech hypotézy .
Řešení:
Je zřejmé , že ve všech případech je hypotéza H0 stejná a rovna :
H0 : π = 0,15
Hodnota π je parametr alternativního rozdělení. Hypotéza H0 je jednoduchá( není
složená – neobsahuje tedy více výroků o náhodných veličinách). Provedeme nyní konstrukci
alternativních hypotéz pro jednotlivé případy.
a) H1 : π ≠ 0,15 . Jde o dvoustrannou hypotézu ( složenou – výroků je dokonce
nekonečně mnoho!).
b) H1 : π < 0,15 . Jde o jednostrannou hypotézu levostrannou ( složenou ).
c) H1 : π > 0,15 . Jde o jednostrannou hypotézu pravostrannou ( složenou ).
Příklad 6.3
Pokračujme v našem příkladě. Výrobce předpokládá, že podíl zboží v reklamaci je
15%. Prodejce tvrdí, že v předcházejícím roce byl tento podíl 21% a chce proto cenu snížit.
Nakonec se dohodnou , že vyberou 10 výrobků, jestliže budou ve výběru nejvýše 2
reklamované výrobky nebudou cenu měnit. V opačném případě se cena sníží. Jakých chyb a
s jakou pravděpodobností se mohou oba dopustit?
Řešení:
Provedeme konstrukci hypotéz .
H0 : π = 0,15
H1 : π = 0,21

Je zřejmé, že testová statistika je rovna binomickému rozdělení Bi(10;π). Jestliže má
pravdu výrobce je rovna hodnota π = 0,15 , naopak má – li pravdu prodejce je hodnota π =
0,21. Podle zadání je jasné, že kritický obor je množina W ={3, 4, …,10} a obor přijetí
testované hypotézy je roven v={0,1,2}.
I. Za předpokladu , že má pravdu výrobce ( platí H0 ) a v náhodném výběru
budou 0,1,2 výrobky vede test k správnému přijetí testované hypotézy H0.
II. Za předpokladu, že pravdu má výrobce, ale ve výběru budou více než 2
reklamované výrobky , pak test vede k chybě I. druhu
III. Za předpokladu, že pravdu má prodejce a v náhodném výběru budou více
než dva reklamované výrobky , vede test ke správnému zamítnutí testované
hypotézy a k přijetí hypotézy alternativní.
IV. Za předpokladu, že pravdu má prodejce a v náhodném výběru budou
nejvýše dva výrobky reklamovány , pak test vede k chybě II. druhu.

Vidíme, že body I. a III. vedou ke správným závěrům. Spočítáme nyní dále s jakými
pravděpodobnostmi se dopouštíme chyb I. a II. druhu.
Pravděpodobnost chyby I. druhu označujeme α a nazýváme ji hladina významnosti.
 10 
10 − i
i
.0,15 . (1 − 0,15 ) = 0,1798
i =3  i 
10

α = ∑

Pravděpodobnost chyby druhého druhu označujeme β
 10 
10 −i
i
.0, 21. (1 − 0, 21) = 0, 6474 .
i =0  i 
2

β = ∑

Příklad 6.4
Provedli jsme výběr s rozsahem n = 400 prvků z populace normálně rozdělené.
Výběrový průměr X = 50 a výběrová směrodatná odchylka s = 16. Máme rozhodnout, zda
můžeme předpokládat, že střední hodnota populace je rovna 47,5.
Řešení:
Zformulujeme nejprve testovanou hypotézu.
H0 : µ = 47,5

Formulujeme alternativní hypotézu
H1 : µ ≠ 47,5

Testovací statistikou bude t =

X −µ

, která je za předpokladu normality populace
s2
n
studentovo rozdělení o n-1 stupních volnosti. Protože je hodnota n> 100 aproximujeme
studentovo rozdělení rozdělením normálním.
Stanovíme hladinu významnosti na 5% , musíme ještě najít příslušný kvantil N(0,1).
Jde o 97,5% kvantil, který má hodnotu 1,96. Tedy kritickým oborem jsou všechny hodnoty
větší nebo rovny hodnotě 1,96.
Stačí nyní dosadit do testovací statistiky za známé hodnoty a za hodnotu µ = 47,5.
50 − 47,5 2,5 50
=
=
= 2, 78 .
18
18 18
20
400
Tato hodnota leží v oboru zamítnutí testované hypotézy a v oboru přijetí hypotézy
alternativní. Kdybychom nyní zjišťovali při jaké hodnotě by za těchto předpokladů byla
poprvé přijata testovaná hypotéza, museli bychom zjistit příslušný kvantil normovaného
normálního rozdělení. Jde o 99,46% .
Museli bychom tedy volit 100% - 99,46% = 0,54% jako hladinu významnosti.
Takováto hodnota bývá nazývána v programech pro zpracování statistických testů jako p –
value.

