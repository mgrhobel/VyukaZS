---
title: "14_Parametricke testy.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/14_Parametricke testy.pdf"
date: 2009-12-27
type: PDF (text-based)
---

7. Statistické hypotézy – parametrické testy
V této části se budeme zabývat statistickými hypotézami, pomocí vyšetřujeme
jednotlivé parametry populace. K takovýmto šetřením většinou využíváme nám již dobře
známé statistické intervalové odhady.

7.1 Testy o parametrech normálního rozdělení
V této části se budeme zabývat studiem případů , kdy testujeme základní parametry
rozdělení N(µ,σ2). Konkrétně budeme konstruovat testy pro střední hodnotu a rozptyl
takovéto náhodné veličiny.

7.1.1 Střední hodnota µ
Na základě náhodného výběru
= ( x1 ,…,xn), které pochází z populace popsané
2
rozdělením N(µ,σ ) budeme testovat hypotézu H0 : µ = µ0 , µ0 je předem zadané reálné číslo.
Z kapitoly o intervalových odhadech víme, že základem všech konstrukcí odhadů
střední hodnoty bývá výběrový průměr X a jeho vlastnosti. Právě z vlastností výběrového
průměru jsme konstruovali intervalové odhady a z těchto vlastností nyní odvodíme příslušné
testové statistiky pro konkrétní alternativní statistické hypotézy H1. Protože jsme při tvorbě
intervalových odhadů rozlišovali případ zda je nám znám rozptyl rozdělení provedeme
takovéto rozdělení i nyní .

7.1.1.1 Parametr σ2 je znám
V tomto případě použijeme jako testovací statistiku rozdělení
U=

X − µ0

σ

. n,

(7.1)

o kterém je známo , že při platnosti hypotézy H0 je typu N(0,1).
Budeme – li tedy vyšetřovat nejdříve případ pravostranné alternativní hypotézy
tedy: H1: µ > µ0 na hladině významnosti p získáme kritický obor = { u; u ≥ u1-p }, kde uα je
α % kvantil rozdělení N(0,1) a u je vypočtená hodnota testové statistiky.
V případě levostranné alternativní hypotézy H1 : µ < µ0 s použitím stejné testovací
statistiky na hladině významnosti p získáme kritický obor = { u; u χ u1-p }.
V posledním případě oboustranné alternativní hypotézy H1 : µ ≠ µ0 , s použitím
stejné testovací statistiky získáme na hladině významnosti p kritický obor


> = u; u ≥ u p  , kde opět uα je α% kvantil rozdělení N(0,1) a u je opět vypočtená hodnota
12

testové statistiky.
Dále uvedeme několik modelových příkladů k presentaci postupů a ke stanovení
silofunkce těchto hypotéz.
Příklad 7.1
Byl proveden náhodný výběr o rozsahu n=5 prvků z populace N(µ,10). Testujme
hypotézu H0 : µ = 8 proti alternativní hypotéze H1: µ ≠ 8 na hladině významnosti 5%.

Pomocí náhodného výběru byl nalezen výběrový průměr X = 8,8 . Rozhodněte o platnosti
hypotézy H0!
Řešení:
Vzhledem k hladině významnosti , je stanoven kritický obor > = {u; u ≥ 1,96} .
X − µ0

8,88 − 8
. 5 = 0,984 .
2
σ
Protože hodnota testové statistiky není v kritickém oboru nemůžeme hypotézu H0 zamítnout.
Hodnota silofunkce je v tomto případě rovna :
 µ − µ0

µ −µ

1-ß(µ ) = Φ 
. n +up  + Φ 0
. n + u p  . Pro jednotlivé hodnoty µ0
 σ
 σ
2 
2 
vypočteme hodnotu β, v následující tabulce jsou tyto hodnoty uvedeny:

Stanovíme hodnotu testové statistiky pro náš případ u =

µ0
5
6
7
8
9
10
11
12
13
14
15

. n=

β(µ0)
0,676958
0,829925
0,920902
0,95
0,920902
0,829925
0,676958
0,483994
0,294582
0,149161
0,061776

Samozřejmě , že pro hodnotu µ0 = 8 je hodnota β rovna 95% , celkově je vidět, že
hodnoty chyby druhého druhu jsou pro stávající hodnoty velmi nepříznivé, s rostoucí
vzdáleností od testované hodnoty β klesá. Jednoznačným viníkem těchto výsledků je malý
počet členů výběru.
Příklad 7.2
Výrobce tvrdí, že výrobek má rozměry 56,2 jednotky se směrodatnou odchylkou 2,2
jednotky . Odběratel tvrdí , že rozměry jsou větší, proto nechal přeměřit 70 náhodně
vybraných výrobků a zjistil, že jejich průměrný rozměr byl 58,9 jednotek. Je tato hodnota
výběrového průměru , za předpokladu normálního rozdělení a směrodatné odchylky rozměrů
2,2 jednotky , statisticky významně větší než tvrdí výrobce? Řešení prove’dte na hladině
významnosti 1%.
Řešení:
Stanovme nejdříve základní hypotézy: H0 : µ χ 56,2 a H1 : µ > 56,2 . Testová
statistika je i v tomto případě stejná , zjistíme tedy její hodnoty –
58,9 − 56, 2
2, 7
. 70 =
.8,37 = 10, 27
u=
2, 2
2, 2

V tomto případě je kritický obor = { u; u ≥ 2,326 }, protože vypočítaná hodnota se
nachází v kritickém oboru na hladině významnosti zamítáme hypotézu H0, výrobky jsou tedy
statisticky významně větší než tvrdí výrobce.

7.1.1.2 Parametr σ2 je neznámý
Při praktických úlohách se ve většině případů setkáváme spíše s případem , kdy
hodnoty parametru σ nejsou známy a můžeme z naměřených údajů je odhadovat jeho
skutečnou hodnotu. V tomto případě ( již na základě našich znalostí z části bodového
odhadu ) se jako testová statistika volí náhodná veličina
t=

X − µ0
. n
s

(7.2)

o které již z dřívějších kapitol víme, že je typu studentova rozdělení s n-1 stupni volnosti.
Takováto veličina se v souladu s tradicí označuje písmenkem t. Výraz s je klasická hodnota
statistického rozptylu.
Vypišme nyní kritické obory pro jednotlivé případy jednostranných resp.
oboustranných hypotéz:
Pravostranná alternativní hypotéza µ > µ0
> = {t ; t ≥ °t1− p } , hodnota t1-p je rovna (1-p)% kvantilu studentova rozdělení s (n-1)
stupni volnosti.
Levostranná alternativní hypotéza µ < µ0
> = {t ; t ≤ °t p } , při stejném označení.
Oboustranná alternativní hypotéza µ ≠ µ0


> = t ; t ≥ t p  , značení jako v předchozím.
1−
2 


Poznamenejme, že stejně jako v první části je jedním z podstatných předpokladů to, že
daná data jsou získávána z populace normální a způsob výběru je náhodný!
Příklad 7.3
Na základě náhodného měření jsme zjistili následující hodnoty 6;9;10;
10;11;12;12;13;14;14;14;14;15;16;16;7. Zjistěte , zda můžeme na hladině významnosti 5%
rozhodnout o tom, že střední hodnota populace nerovná 15.
Řešení:
Stanovíme nejdříve hypotézy H0 : µ =15 a H1 : µ ≠ 15. Protože z daných dat vyplývají
následující údaje : n = 16; X = 12, 625; s = 2,849 . Můžeme dále zjistit kritický obor pomocí
náhodné veličiny studentova rozdělení s 15 stupni volnosti
> = {t ; t ≥ 2,95} , dosadíme tedy do testové statistiky (7.2) a získáme následující

12, 625 − 15
−2,375
. 16 =
.4 = −3,33 , protože tato hodnota -3,33 leží v kritickém
2,849
2,849
oboru přijímáme alternativní hypotézu H1.. Pokud bychom hledali tzv. p hodnotu ( p-value )
těchto dat ( jde o hodnotu hladiny významnosti při které bude poprvé přijata hypotéza H0 ) ,
získali bychom v tomto případě p=0,0045 , tato hodnota je více než poloviční než byla
uvedena úvodní testovaná hladina významnosti.
hodnoty t =

Příklad 7.4
Po stanovení měření hodnot vzdáleností mezi dvěma sazenicemi na záhoně jsme
získali následující hodnoty :
4 5 7 8 12 10 5 9 11 18 15 12 14 12 10 9 11 12

Ověřte na hladině významnosti 5% zda vzdálenosti mezi jednotlivými sazenicemi jsou
vzdálené nejvýše 12 jednotek.
Řešení:
Nejdříve stanovíme opět testovanou a alternativní hypotézu. Zřejmě tedy bude
H0: µ χ 12 a H1: µ>12. V našem případě máme tedy stanovenou pravostrannou alternativní
hypotézu, kritický obor je tedy stanoven jako > = {t ; t ≥ °t0,95 } = {t ; t ≥ ° − 1, 74} .
Z uvedených hodnot získáme opět základní hodnoty n = 18; X = 10, 222; s = 3, 623 . Pro
další postup je nutné vypočítat hodnotu testové statistiky pro tato čísla , její velikost je rovna
t=-2,082. Pro stanovení odpovědi na naší otázku nyní ověříme, zda hodnota vypočtené testové
statistiky patří či nepatří do kritického oboru. Vypočtená hodnota nepatří do kritického oboru,
nemůžeme tedy na hranici významnosti 5% zamítnout možnost, že mezi sazenicemi je
vzdálenost nejvýše 12 jednotek. Pokud bychom hledali p-hodnotu zjistili bychom , že je na
úrovni čísla 0,0264.

7.1.2 Směrodatná odchylka σ
Směrodatná odchylka má pro normální rozdělení stejný význam jako střední hodnota.
Oba tyto parametry sice ovlivňují hodnoty normálního rozdělení každý jinak, ale celkově je
toto rozdělení dvouparametrické , potřebujeme proto znát oba parametry stejně dobře.
7.1.2.1 Při známém parametru µ
V kapitole o bodovém odhadu směrodatné odchylky populace popsané pomocí
normálního rozdělení jsme rozlišovali zda známe střední hodnotu normálního rozdělení či zda
je neznáma.
Chceme tedy testovat na základě náhodného výběru o n prvcích z populace hypotézu
2
H0 : σ = σ02 Jestliže byla střední hodnota µ0 populace známa potom vybíráme jako testovací
statistiku náhodnou veličinu
n

∑(X − µ )

χ 0 2 = n. i =1

i

σ 02

2

0

,

(7.3)

která má při platnosti hypotézy H0 rozdělení χ2 ( chi kvadrát ) s n stupni volnosti.
Podobně jako v předchozích případech můžeme stanovovat kritické obory v závislosti
na hodnotách alternativní hypotézy.
Pravostranná alternativní hypotéza σ2 > σ02.
Je zřejmé, že kritický obor je pak dán > = { χ 0 2 ; χ 0 2 ≥ χ 2 ( p; n)} , kde χ2(p;n) je roven

p% kvantilu rozdělení chi kvadrát s n stupni volnosti.
Levostranná alternativní hypotéza σ2 < σ02.
Kritickým oborem v tomto případě je > = { χ 0 2 ; χ 0 2 ≤ χ 2 (1 − p; n)}

Oboustranná alternativní hypotéza σ2 ≠ σ02.
Kritický obor je v tomto případě složitější, jde o dva disjunktní intervaly

p  
 p   
> =  0; χ 2  ; n   ∪  χ 2 1 − ; n  ; ∞ 
 2    2  

Příklad 7.5
Při kontrolním měření byly zjištěny následující hodnoty 0,62; 0,64; 0,57; 0,61; 0,59;
0,57; 0,62; 0,59 za platnosti , že střední hodnota je rovna 0,5. Rozhodněte , zda je platná :
a) H0 : σ2 =0,003 proti H1 : σ2 ≠ 0,003
b) H0 : σ2 =0,003 proti H1 : σ2 < 0,003.
Ověření proveďte na hladině významnosti 5%.
Řešení:
Nejdříve stanovíme základní hodnoty n = 8; X = 0, 60125; s = 0, 025319; s 2 = 0, 000641 .
Část a) je případem oboustranné hypotézy, stanovíme tedy kritický obor pro tento případ.

 

> =  0; χ 2 p  ∪  χ 2 p ; ∞  = ( 0; 2,18 ) ∪ (17,535; ∞ ) . Dále musíme ještě zjistit
2 

 1− 2 
hodnotu testovací statistiky (7.3) , po dosazení vychází χ02 = 3,6042. Protože se nenachází
v kritickém oboru nemůžeme hypotézu H0 zamítnout.
V případě části b) stanovíme opět kritický obor > = { χ 0 2 ; χ 0 2 ≤ χ 2 (1 − p; n)} =

(0;2.733). Protože hodnota testovací statistiky leží i v tomto případě mimo kritický obor
nemůžeme ani nyní hypotézu H0 zamítnout.

7.1.2.2 Při neznámém parametru µ
Při práci s neznámou populací většinou její střední hodnotu µ neznáme , proto je více
reálný případ, který budeme vyšetřovat v této části. Podle kapitoly 8. , v níž jsme probírali
bodové odhady je náhodná veličina
n

∑(X − X )

χ 2 = (n − 1). i =1

2

i

,

σ2

(7.4)

typu χ2 s (n-1) stupni volnosti. Podobně jako v předchozí podkapitole tohoto tvrzení
využijeme ke konstrukci vhodné testovací statistiky.
Chceme tedy testovat na základě náhodného výběru o n prvcích z populace hypotézu
2
H0 : σ = σ02 Jestliže byla střední hodnota µ0 populace známa potom vybíráme jako testovací
statistiku náhodnou veličinu
n

∑(X − X )

χ 2 = (n − 1). i =1

2

i

σ 02

,

(7.5)

která má při platnosti hypotézy H0 rozdělení χ2 ( chi kvadrát ) s (n-1) stupni volnosti. Proti
předchozí části tedy získáváme statistiku stejného typu, ale protože musíme z dat získávat
navíc informaci o odhadu parametru µ je počet stupňů volnosti o jeden menší.

Podobně jako v předchozích případech můžeme stanovovat kritické obory v závislosti
na hodnotách alternativní hypotézy.
Pravostranná alternativní hypotéza σ2 > σ02.
Je zřejmé, že kritický obor je pak dán > = { χ 2 ; χ 2 ≥ χ 2 ( p; n − 1)} , kde χ2(p;n-1) je

roven p% kvantilu rozdělení chi kvadrát s (n-1) stupni volnosti.
Levostranná alternativní hypotéza σ2 < σ02.
Kritickým oborem v tomto případě je > = { χ 2 ; χ 2 ≤ χ 2 (1 − p; n − 1)}
Oboustranná alternativní hypotéza σ2 ≠ σ02.
Kritický obor je v tomto případě složitější, jde o dva disjunktní intervaly

p
p
  
 
> =  0; χ 2  ; n − 1  ∪  χ 2 1 − ; n − 1 ; ∞ 
2
   2
 

Příklad 7.6
Měřením jistého výrobku jsme získali následující hodnoty:
15,15; 15,2; 15,04; 15,14; 15,22.
Předpokládejme, že výsledky těchto měření jsou náhodné veličiny N(µ,σ2 ). Testujme
následující případy :
a) H0 : σ2 = 0,03 a H1: σ2 < 0,03
b) H0 : σ2 = 0,03 a H1: σ2 ≠ 0,03
Řešení:
a) Alternativní hypotéza je levostranná, tedy jejím kritickým oborem je
> = { χ 2 ; χ 2 ≤ χ 2 (1 − p; n − 1)} = (0; 2,17) . Musíme nyní zjistit hodnotu testovací

statistiky z výrazu uvedeném v (7.5) . Po dosazení naměřených hodnot získáváme
n

∑(X − X )
i

2

0, 0196
= 4,5733 . Protože tato hodnota neleží
σ0
0, 03
v kritickém oboru hypotézu H0 nemůžeme zamítnout.
b) Alternativní hypotéza v tomto případě je oboustranná, kritický obor sestrojíme
podle výše uvedených pravidel. > = ( 0;1, 69 ) ∪ (16, 013; ∞ ) . Protože ani v tomto
případě neleží hodnota testovací statistiky v kritickém oboru hypotézu H0
nezamítáme.

χ 2 = (n − 1). i =1

2

= 7.

V další části se budeme zabývat srovnáváním dvou náhodných veličin typu N(µ,σ2).
Osvojíme si metody, které se obecně nazývají t-test a F-test. V rámci nich jsou velmi
významným faktorem rozdělení studentovo a Fischer – Snedecorovo.

7.1.3 Testy pro podíl rozptylů
Nechť ⋅1 a ⋅2 jsou náhodné výběry z rozdělení N(µ1;σ12) a N(µ2;σ22) s počtem členů
výběru n1 resp. n2. Chceme zjistit intervalový odhad pro podíl rozptylů náhodných veličin

tedy

σ 12
. Při stanovení tohoto intervalového odhadu budeme vycházet z kapitoly 3 ze vztahu
σ 22

(3.21) . Dále je nutno rozlišovat dva různé případy:
7.1.3.1 Střední hodnoty µ1 a µ2 jsou známé
n

∑(X − µ )
i =1

Potom je náhodná veličina F =

1i

2

1

n1.σ 12

n

∑(X − µ )
i =1

2i

je Fischer – Snedecorovo rozdělení
2

2

n2 .σ 2 2
s ( n1 ; n2 ) stupni volnosti. V tomto případě je proto oboustranný (100-p) % interval
spolehlivosti roven:
n

∑(X − µ )
i =1

1
.
F p n
1−

2

1i

i =1

n2

σ1
1
<
.
2
σ 2 Fp n
2

n1
2i

∑(X − µ )

1

∑(X − µ )
i =1

n

2

2

<
2

2

1i

2

1

n1

∑(X − µ )
i =1

2i

,

(7.6)

2

2

n2

kde hodnoty Fp jsou příslušné kvantily rozdělení F(n1 ; n2 ). Z těchto tvrzení vyjdeme
ve stanovení základních hypotéz.
Stanovujeme hypotézu H0: σ12 = σ22 . , alternativní hypotézu H1 stanovujeme jako
n

∑(X − µ )
i =1

σ12 ≠ σ22. Za předpokladu , že platí hypotéza H0 je zřejmě podíl

1i

2

1

n1
n

∑(X − µ )
i =1

2i

prvkem
2

2

n2


intervalu  F p ; F p  . Tedy kritickým oborem je v tomto případě sjednocení intervalů:
 2 1− 2 

 

W =  0; F p  U  F p ; ∞  .
2 

 1− 2 

7.1.3.2 Střední hodnoty µ1 a µ2 jsou neznámé
Při tvorbě takového intervalu spolehlivosti vycházíme opět z vlastností F- rozdělení.
n

∑(X − X )
1i

i =1

Náhodná veličina F =

2

1

(n1 − 1).s12

n

∑(X − X )
2i

i =1

je potom Fischer – Snedecorovo rozdělení s (n1-1;n2-1)
2

2

(n2 − 1).s2 2
stupni volnosti. Konstrukce oboustranného (100 – p )% intervalu spolehlivosti v tomto
případě je velmi podobná konstrukci uvedené v předchozí části :
n

∑(X − X )
i =1

1
.
F p n
1−

2

1i

n1 − 1
2i

n2 − 1

∑(X − X )

1

∑(X − X )
i =1

n

2

2

i =1

σ
1 s
1
=
.
< 12 <
.
F p s
Fp n
σ2
2
1−

2
1
2
2

2

2

2

1i

2

1

n1 − 1

∑(X − X )
i =1

2i

2

1 s12
=
.
F p s2 2
2

(7.7),

2

n2 − 1

kde hodnoty Fp jsou kvantily F – rozdělení s ( n1-1; n2-1 ) stupni volnosti.
Podobně jako v předchozí části stanovujeme hypotézu H0: σ12 = σ22 . , alternativní
hypotézu H1 stanovujeme jako σ12 ≠ σ22.
n

∑(X − X )
i =1

Za předpokladu , že platí hypotéza H0 je zřejmě podíl

1i

2

1

n1 − 1
n

∑(X − X )
i =1

2i

2

=
2

s12
prvkem
s2 2

n2 − 1


intervalu  F p ; F p  . Tedy kritickým oborem je i v tomto případě sjednocení intervalů:
 2 1− 2 

 

W =  0; F p  U  F p ; ∞  .

 1− 2 
2 
Oba případy se liší použitím náhodných veličin F- rozdělení o různých stupních
volnosti.
Práce s oběma předchozími hypotézami se obecně nazývá F – test. Rozhodujeme
v něm o tom, zda můžeme přijmout či vyvrátit rovnost σ12 = σ22 na dané hladině
významnosti. Tento test se užívá velmi často v regresní analýze, v t – testu a v analýze
rozptylu ( ANOVA ).
Velmi důležitými parametrickými testy jsou tzv. t – testy, pomocí nichž zjišťujeme ,
zda dvě náhodné veličiny mají stejné střední hodnoty.

7.1.4 Testy o shodě středních hodnot dvou normálních rozdělení
Jak už jsme uvedli dříve budeme v této části testovat základní hypotézu H0 :µ1 = µ2 .
Jako alternativní hypotézu můžeme volit buď jednostranné nebo oboustranné hypotézy.

Nechť tedy podobně jako v předchozí části jsou ⋅1 a ⋅2 náhodné výběry z rozdělení N(µ1;σ12) a
N(µ2;σ22) s počtem členů výběru n1 resp. n2. V celé této části budeme vyšetřovat hypotézy na
hladině významnosti p. V dalším musíme rozlišovat několik různých případů.
7.1.4.1 Rozptyly populací σ12 a σ22 jsou známé
Již z předchozích kapitol je známo, testové kritérium

U=

X1 − X 2

σ 12
n1

+

(7.8),

σ 22
n2

je typu N(0;1). Odtud můžeme odvodit kritické obory pro případy jednotlivých
alternativních hypotéz :
1. H1 : µ1 > µ2 . W =< u1− p ; ∞)

2. H1 : µ1 < µ2 . W = (−∞; u p >
3. H1 : µ1 ≠ µ2 . W = (−∞; −u p > U < u p ; ∞)
1−

2

1−

2

Ovšem případy , kdy jsou známy rozptyly populací jsou velmi řídké, proto větší
uplatnění mají testy , kdy příslušné hodnoty rozptylů populací nejsou známy.
Příklad 7.7
Rozhodněme na hladině významnosti , zda výsledky testů v jedné škole jsou nižší než
výsledky testů ve škole druhé. Provedli jsme náhodný výběr 50 studentů v první škole a 40
studentů ve škole druhé. Průměrné výsledky testů studentů první školy byly 275 bodů a druhé
školy 280 bodů. Z dřívějších testů jsou známy rozptyly obou škol σ12 = 48 a.
Řešení:
Testovaná statistika H0 : µ1 = µ2 a zřejmě H1 : µ1 < µ2 . Dosadíme tedy do (7.8) a
275 − 280
u=
= −3,549 . Podle předchozího je pro tento případ alternativní hypotézy kritický
48 41
+
50 40
obor W = (−∞; −1, 645 > . Hodnota testové statistiky patří tedy do kritického oboru , takže
zamítáme testovanou hypotézu H0 a přijímáme hypotézu alternativní tj. výsledky druhé školy
mají větší bodové ohodnocení.
Příklad 7.8
Rozhodněte na hladině významnosti 1% , zda jsou shodné vzdálenosti dojezdu dvou
typů pneumatik. První typ jsme testovali v 25 kusech a průměrná vzdálenost dojezdu činila
21 500 km ; druhý typ jsme testovali 15 kusů s průměrným dojezdem 23 200 km. Rozptyl
dojezdu první pneumatik σ12 = 400 km2 a druhých pneumatik σ22 = 560 km2.

Řešení:
Testovaná statistika H0 : µ1 = µ2 a zřejmě H1 : µ1 ≠µ2. Opět dosadíme do vztahu (7.8)
21500 − 22200
u=
= −95,85 . Vzhledem k oboustrannému testu je hodnota 99,5% kvantilu
400 560
+
25 15
N(0,1) rovna 2,58. Tedy hodnota leží v kritickém oboru ( leží v kritickém oboru i pro případ
jednostranného testu, kdy µ1 < µ2 ). Proto hypotézu H0 zamítáme a přijímáme hypotézu H1.
7.1.4.2 Rozptyly populací jsou neznámé, ale jsou si rovny
V tomto případě použijeme opět metodu vedoucí na testovou statistiku:

t=

X1 − X 2

(7.9)

1 1
S 2 ( x).  + 
 n1 n2 

Následující hodnota S(x) se nazývá společný výběrový rozptyl a je váženým
průměrem výběrových rozptylů S12(x) a S22(x) s vahami n1 – 1 a n2 - 1 , tedy jeho hodnota je
rovna
S ( x) =

(n1 − 1).S1 2 ( x) + (n2 − 1).S 2 2 ( x)

(7.10).

n1 + n2 − 2

Náhodná veličina (7.9) je při platnosti H0 studentovo rozdělení s n1 + n2 – 2 stupni
volnosti. Nyní již tedy můžeme určit kritické obory pro různé formulace alternativních
hypotéz H1 .
1. H1 : µ1 > µ2 . W = < t n1 + n2 − 2;1− p ; ∞)
2. H1 : µ1 < µ2 . W = (−∞; tn1 + n2 − 2; p >
3. H1 : µ1 ≠ µ2 . W = (−∞; −t

n1 + n2 − 2;1−

p
2

>U<t

n1 + n2 − 2;1−

p
2

; ∞)

K tomu abychom mohli rozhodnout, že neznámé rozptyly σ1 a σ2 si jsou rovny
musíme použít v tomto případě F –test viz 7.1.3. Uvedeme opět několik příkladů pro tuto
situaci.
Příklad 7.9
Ve dvou prodejnách jsme zjišťovali ceny určitého typu produktu , získali jsme
následující výsledky:
n1 = 28, x1 = 104, 74, s12 = 505,14

n2 = 30, x2 = 117,97 , s22 = 789,83
Předpokládáme normalitu uvedených dat, ověřte shodu středních hodnot cen v obou
prodejnách.
Řešení:

Nejdříve použijeme F – test na ověření shody rozptylů cen v obou prodejnách .
Hodnota testovací statistiky pro F – test je v našem případě rovna
505,14
F=
= 0, 63956
789,83
Tato hodnota neleží v kritickém oboru F – testu . Na hladině 0,05 jsme tedy
neprokázali to , že by se rozptyly cen v obou prodejnách lišily.
Nyní tedy využijeme statistiku (7.9) ke stanovení rozdílu mezi středními hodnotami.
104, 74 − 117,97
t=
= −1,97096
1
1


652,55.  + 
28
30


Kritické hodnota pro oboustranný test je rovna 2,003697. Tedy test neprokázal na
hladině významnosti 0,05 mezi cenami žádný rozdíl.
Příklad 7.10
V podniku byly zkoumány dva odlišné technologické postupy . Máme na hladině
významnosti 0,05 zjistit , zda se od sebe liší! Dále následují celkem tuny výroby prvním a
druhým postupem vždy za jednu směnu:
1.
2.
technologický technologický
postup
postup
16,3
16,5
15,8
16,2
14,9
16,7
15,3
15,8
16
14,5
15,7
15,6
15,4
14,8
16,3
15
15,8
14,9
14,8
14,6
16,7
13,8
15,6
16,3

Řešení:
Prvním krokem bude porovnání rozptylů obou technologických postupů. Z daných
s22 = 0, 658222, n2 = 10 . Hodnota testové
hodnot zjistíme , že s12 = 0,571044, n1 = 14;
0,571044
statistiky je proto rovna F =
= 0,867555 . Tato hodnota neleží opět v kritickém
0, 658222
oboru F – testu , nemůžeme tedy zamítnou hypotézu H0 o rovnosti obou rozptylů.
Postupujeme jako v předchozím případě , zjistíme hodnotu testové statistiky
t = 0,500552 . Ověříme si kritické hodnoty studentova rozdělení s 22 stupni volnosti ( jde o
oboustranný test ) : 2,07388 . Z těchto hodnot vyplývá , že na hladině významnosti 0,05 nelze
zamítnout hypotézu o shodných výsledcích obou technologických postupů.

7.1.5 Rozptyly nejsou známé a nejsou si rovny
V tomto případě pro malé hodnoty n1 a n2 použijeme následující postup . Místo
předchozího dvouvýběrového t – testu používáme jedné z alternativ :
1. Cochran – Coxův test - vypočteme:
S=

s12
s22
.tn (α ) + .tn2 −1 (α )
n1 1−1
n2
s12 s22
X −Y − ∆
*
*
+
, dále T =
a konečně t =
. Hypotézu
2
s1 s22
S
n1 n2
+
n1 n2

H0 zamítneme , jestliže T * ≥ t * ( v tomto případě jde o oboustranný test ).
2. Welchův test: Nejdříve určíme aproximaci stupňů volnosti
2

 s12 s22 
 + 
n n2 
, toto číslo většinou zaokrouhlujeme dolu na nejbližší celé kladné
NW =  2 1
s1
s22
n1
n
+ 2
n1 − 1 n2 − 1
číslo. Vypočteme opět T * jako v předchozím způsobu a porovnáme s t NW (α ) .
3. Satterthwaiteův test . Opět určíme aproximaci stupňů volnosti
2

 s12 s22 
 + 
n n2 
− 2 . Výsledek opět zaokrouhlíme dolu na nejbližší celé kladné
NS =  2 1
s1
s22
n1
n
+ 2
n1 + 1 n2 + 1
číslo. Vypočteme opět T * jako v předchozím způsobu a porovnáme s t N S (α ) .
Hladina každého z těchto tří testů je přibližně rovna α .
Příklad 7.11
Pole stejných rozměrů byla upravena dvěma různými způsoby . Výsledné parametry
sklizní jsou následující n1 = 32, x1 = 23, s1 = 1, 78; n2 = 59, x2 = 28,3, s2 = 2,56 .
Zjistěte, zda obě úpravy pole vedou ke stejným výsledkům!
Řešení :
Nejdříve určíme hodnotu F – testu , číselně je rovna 0,48346 . Pro dané stupně
volnosti leží toto číslo v kritickém oboru F – testu . Tedy zamítáme hypotézu H0 o stejných
rozptylech. ( p – value = 0,0305 ).
Budeme tedy určovat hodnotu statistiky T* = -78,54152 . Hodnoty jednotlivých t*
jsou postupně pro metodu 1. 2,0195 ; pro metodu 2. 1,989 a konečně pro metodu 3. 1,988.
Pokud bychom tedy zvolili libovolnou z výše uvedených metod , dospěli bychom k zamítnutí
možnosti o stejných výsledcích.

