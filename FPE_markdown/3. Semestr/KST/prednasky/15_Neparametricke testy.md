---
title: "15_Neparametricke testy.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/15_Neparametricke testy.pdf"
date: 2009-12-27
type: PDF (text-based)
---

8. Neparametrické hypotézy
V této části se budeme zabývat speciální částí teorie statistických hypotéz tzv.
neparametrickými hypotézami nebo jinak řečeno neparametrickými statistickými testy.
Neparametrické se nazývají proto , že při konstrukci těchto testů nejsou využity znalosti
parametrů rozdělení náhodných veličin , ale jiné způsoby práce s daty.

8.1 Znaménkový test
Jde o jeden z nejjednodušších testů. Nechť X 1 ,L , X n je výběr ze spojitého rozdělení
s mediánem x% Testujeme hypotézu H0 : x% = x0 , kde x0 je dané číslo. Test má jak
oboustrannou alternativu , tak i jednostrannou.
H1 : x% ≠ x0 . Jde tedy o oboustrannou alternativu. Nejdříve vytvoříme rozdíly
X 1 − x0 ,L , X n − x0 . Pokud je některý z těchto rozdílů nulový vynecháme ho . Tím získáme
množinu čísel. Z této množiny nás bude zajímat jen počet rozdílů s kladným znaménkem,
tento počet označme B . Pokud by platila hypotéza H0 , pak by náhodná veličina B byla typu
Bi( n ; 0,5 ) ( předpokládáme , hodnoty jsou vesměs různé od x0 ). Hypotézu H0 zamítneme ,
jestliže bude hodnota B velmi malá nebo naopak bude téměř rovna n. Kritické hodnoty tohoto
testu jsou tabelovány v tabulkách , ale můžete si je zjistit sami pomocí distribuční funkce
binomického rozdělení Bi(n;0,5).
Platí tedy

P ( B ≤ k1 ) ≤

α
2

, P ( B ≥ k2 ) ≤

α
2

.

(8.1)

Pro hodnoty n malé ( n < 20 ) se v tabulkách naleznou čísla k1 a k2 . Hypotézu
zamítneme , jestliže B ≤ k1 nebo B ≥ k2 .
V případě velkých hodnot ( n>19 )se provádí normalizace náhodné veličiny B .
Náhodná veličina
U=

2.B − n
n

(8.2)

se podle centrální limitní věty asymptoticky blíží k N(0,1) ( náhodná veličina U má
n
n
střední hodnotu rovnou
a rozptyl roven
, tato náhodná veličina vznikla „znormováním „
2
4
α 
B ) .Hypotézu H0 tedy zamítneme v tomto případě , když U ≥ u   .
2
Příklad 8.1
Nechť jsou naměřeny hodnoty 15.6 ; 14,8; 18,2; 14,7; 16,3; 20,7; 19,4; 18,2; 17,4;
16,4; 14,9; 15,1; 16,5 . Pomocí znaménkového testu rozhodněte , zda 18 může být mediánem
dat.
Řešení:
Od hodnot xi odečteme očekávanou hodnotu mediánu a dostaneme:
15,6 14,8 18,2 14,7 16,3 20,7 19,4 18,2 17,4 16,4 14,9 15,1 16,5
-2,4 -3,2 0,2 -3,3 -1,7 2,7 1,4 0,2 -0,6 -1,6 -3,1 -2,9 -1,5

Počet čísel kladných je roven 4 . Pro hodnotu n = 13 jsou kritické hodnoty na hladině
významnosti 0,05 rovny 2 a 9 . Protože číslo 4 leží mezi těmito hodnotami , nemůžeme
vyloučit možnost , že 18 je mediánem našich dat.
2.4 − 13
Pokusíme se využít ještě vzorec (8.2) , potom hodnota U =
= −1,38675 .
13
Zvolíme opět hladinu významnosti 0,05 . 97,5% kvantil rozdělení N(0;1) je roven 1,96 . Dále
−1,38675 〈1,96 , hypotézu H0 nezamítáme ani pomocí této metody ( hodnota n ale není větší
než 19 ).
Příklad 8.2
Při měření hmotnosti výlovku ryb ( v tunách ) byly zjištěny následující hodnoty:
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
11
12
13
2,64 1,537 1,02 0,162 1,263 3,215 0,3 1,014 1,774 1,823 0,899 2,743 6,397
14
15
16
17
18
19
20
21
22
23
24
25
26
2,021 0,623 0,107 0,26 2,704 2,78 1,004 1,344 6,954 1,479 0,123 7,19 3,62

Máme ověřit hypotézu , že medián výlovku ryb je roven 2 t.
Řešení:
Opět zjistíme hodnotu počtu kladných rozdílů mezi xi a hodnotou 2 . Těchto čísel je 10 .
Hodnota B = 10 . Ověření provedeme pomocí vztahu (8.2) , tento vztah je aproximativně
2.10 − 26
rozdělení N(0,1) . Vypočtěme hodnotu U , U =
= −1,1767 = 1,1767 , porovnáme
26
– li tuto hodnotu s kritickou hodnotou u0,975 = 1,96 , zjišťujeme , že hodnota U neleží
v kritickém oboru. Nemůžeme tedy vyvrátit možnost , že číslo 2 je mediánem výlovku ryb.
Pokud bychom prováděli výpočet klasickou metodou , měli bychom pro n = 26 k dispozici
kritické hodnoty 7 a 18 , a ani pomocí této metody nemůžeme vyvrátit možnost , že 2 je
mediánem hmotnosti výlovku.

8.2 Jednovýběrový Wilcoxonův test
Tento test je opět založen na pořadových statistikách. Předpokládáme , že daná
jednorozměrná data byla vybrána z populace popsané spojitou náhodnou veličinou . Nulová
hypotéza H0 je postavená tak , že zjišťujeme , zda distribuční funkce F(x) je symetrická kolem
počátku ( resp. kolem obecného bodu a ) tedy zda platí :
∀
F ( x) = 1− F (−x) ,
x ∈ (−∞, ∞)
oproti ní stojí alternativní hypotéza , která je negací tohoto výroku. Z požadavků na rozdělení
vyplývá , že mediánem rozdělení je 0 ( resp. bod a ) , pokud existuje střední hodnota
rozdělení je také rovna 0 ( resp. a ) .

Nechť X1,…,Xn je náhodný výběr z výše uvedeného rozdělení. Položíme Yi = Xi - 0
( resp. Xi - a ). Náhodné veličiny uspořádáme vzestupně podle jejich absolutní hodnoty , tedy
Y (1) ≤ Y ( 2) ≤ L ≤ Y ( n ) .
Symbolem Ri+ označíme pořadí veličiny Yi . Zaveďme dále označení

R + = ∑ Ri+
Yi ≥ 0

, R − = ∑ Ri+ .

(8.3)

Yi < 0

n. ( n + 1)
. Hypotézu H0 na hladině α
2
zamítáme , jestliže číslo R = min ( R + , R − ) ≤ wn (α ) , kde wn (α ) je tabelovaná kritická
Podle zavedení těchto hodnot jistě platí R + + R − =

hodnota . Tuto hodnotu získáte v tabulce kritických hodnot jednovýběrového Wilcoxonova
testu.
Věta 8.3
Platí – li hypotéza H0 , potom
n.(n + 1)
n.(n + 1).(2.n + 1)
E ( R+ ) =
, VAR ( R + ) =
4
24
Důkaz:
Viz [1].

(8.4).

Dá se dokázat, že náhodná veličina R + má asymptoticky rozdělení normální. Můžeme
tedy test hypotézy H0 založit na náhodné veličině

U=

n.(n + 1)
4
n.(n + 1).(2.n + 1)
24
R+ −

(8.5)

α 
Hypotézu H0 potom zamítneme , jestliže U ≥ u   , na hladině , která se s rostoucím
2
n přibližuje hodnotě α .
Příklad 8.4
V průběhu deseti za sebou jdoucích dnů si pacient měřil 10x tep. Můžeme na základě
těchto měření prohlásit , že medián naměřených hodnot je roven 75 tepům ?
měř. č.1 měř. č.2 měř. č.3 měř. č.4 měř. č.5 měř. č.6 měř. č.7 měř. č.8 měř. č.9 měř. č.10
76 tepů 76 tepů 74 tepů 77 tepů 79 tepů 81 tepů 83 tepů 67 tepů 65 tepů 90 tepů

Řešení:
Pokud by medián hodnoty tepů byl 75 , pak dostaneme hodnoty Yi takovéto
Y1
1

Y2
1

Y3
-1

Y4
2

Y5
4

Y6
6

Y7
8

Y8
-8

Y9
-10

Y10
15

V této tabulce máme dokonce hodnoty Yi seřazené podle velikosti . Vypočteme dále
hodnoty R + = 1 + 2 + 4 + 5 + 6 + 7 + 10 = 35, R − = 3 + 8 + 9 = 20 .

Hodnota R = min(35; 20) = 20 , tuto hodnotu porovnáme s kritickou hodnotou
v tabulkách , w10 ( 0, 05 ) = 8 , protože hodnota R je větší než 8 , nemůžeme na dané hladině

hypotézu H0 zamítnout.
Pokud bychom řešili tuto úlohu pomocí normální aproximace , získali bychom
35 − 27,5
hodnotu U =
= 0, 764471 , tato hodnota je menší než 1,96 , tedy i touto metodou
96, 25
nemůžeme hypotézu H0 zamítnout.
V případě jednovýběrového Wilcoxonova testu je velice důležitým předpokladem i
symetrie hustoty f kolem mediánu . K zamítnutí hypotézy H0 může tedy dojít také tehdy ,
když je sice medián roven nule ( resp. a ) , ale hustota je výrazně nesymetrická.
Můžeme tedy tento test použít i na jednoduché testování , zda vybraná data mohou
pocházet z rozdělení normálního!

8.3 Dvouvýběrový Wilcoxonův test
Nechť je X 1 ,L , X m je náhodný výběr ze spojitého rozdělení s distribuční funkcí F1 ,
nechť dále je Y1 ,L , Yn náhodný výběr ze spojitého rozdělení s distribuční funkcí F2 , který je
na výběru X 1 ,L , X m nezávislý. Hypotézu H0 sestavujeme tak ,že F1 = F2 , alternativní
hypotéza je oboustranná tedy F1 ≠ F2 .
Při konstrukci testu nejdříve vytvoříme z výše uvedených výběrů sdružený výběr
X 1 ,L , X m , Y1 ,L , Yn . Hodnoty v tomto výběru uspořádáme vzestupně podle velikosti.
Označíme S1 součet všech pořadí hodnot X 1 ,L , X m a S2 pořadí hodnot Y1 ,L , Yn ve
sdruženém výběru. Zřejmě podobně jako v jednovýběrovém Wilcoxonově testu platí
( n + m ) . ( n + m + 1) . V případě náhodných veličin S a S jde o tzv. lineární
S1 + S2 =
1
2
2
pořadové statistiky. Jejich základní parametry jsou popsány v následující větě.
Věta 8.5
Platí – li hypotéza H0 , potom
E ( S1 ) =

m. ( m + n + 1)

,

2
n. ( m + n + 1)
E ( S2 ) =
,
2

VAR ( S1 ) =

m.n. ( m + n + 1)

12
m.n. ( m + n + 1)
VAR ( S2 ) =
12

,

(8.6)

Důkaz:
Uveden v [1].

Vzhledem k vazbě mezi náhodnými veličinami S1 a S2 , stačí vyšetřovat jen jednu
z nich , zpravidla je to S1 . Podobně jako v případě jednovýběrového Wilcoxonova testu je
možné pro dostatečně velké hodnoty m , n provést znormování jedné z veličin S1 nebo S2 a
převést problém na šetření normálního normovaného rozdělení.
Stále častěji se místo takovýchto náhodných veličin vyšetřuje

U1 = m.n +

m.(m + 1)
− S1 ,
2

Test založený na náhodné veličině U1 se nazývá Mann – Whitneyův test. Zavedeme
– li ještě označení
U 2 = m.n +

n.(n + 1)
− S2 ,
2

platí U1 + U2 = m .n . Náhodná veličina U1 udává počet případů , kdy Xi < Yj ,
náhodná veličina U2 udává počet případů , kdy Xi > Yj . Opět podobně jako v případě
jednovýběrového testu stanovíme S=min( S1 , S2 ). Pokud hodnota S je menší nebo rovna
kritické hodnotě uvedené v tabulce kritických hodnot dvouvýběrového Wilcoxonova testu ,
zamítá se na dané hladině α hypotéza H0 . Označení výběrů přitom volíme tak , aby m ≥ n .
Na základě výsledků věty 8.5 zřejmě platí
E (U1 ) =

m.n
,
2

VAR (U1 ) =

m.n.(m + n + 1)
12

(8.7)

,protože U2 = m.n - U1 . Je E (U1 ) = E (U 2 ) ,

VAR (U1 ) = VAR (U 2 ) . Dá se dokázat ,

že veličiny S1 , U1 asymptoticky normální rozdělení , tedy
U=

U1 − E (U1 )

(8.8)

VAR (U1 )

α 
Pokud U ≥ u   , zamítneme hypotézu H0 na hladině blížící se hodnotě α . Tento
2
test se dá použít v případě , že m > 10 a n > 10 .

Dvouvýběrový Wilcoxonův test je velmi citlivý zejména na případ posunutí , tedy na
případ , kdy F1(x) = F2(x - ∆) , kde ∆≠0.
Příklad 8.6
Dvěma způsoby jsme prováděli analýzu procentního obsahu zlata ve vzorcích rudy.
Výsledky analýz jsou uvedeny v následující tabulce:
hodnoty X
hodnoty Y

3,3
3,2

3,4
3,5

3,4
3,4

3,2
3,4

3,5
3,4

3,3
3,3

3,2
3,5

3,5

3,4

3,5

Řešení:
Seřadíme uvedené hodnoty do jedné tabulky, zjistíme pořadí hodnot X:
3,2

3,2

3,2

Odlišným

3,3

3,3

3,3

podkladem

3,4

3,4

3,4

3,4

3,4

3,4

3,5

3,5

3,5

jsou
označeny
hodnoty
X.
( 7 + 10 ) . ( 7 + 10 + 1) − 40 = 153 − 40 = 113 .
S1 = 1 + 2 + 4 + 5 + 7 + 8 + 13 = 40 a S 2 =
2

3,5

3,5

Hodnoty

Zjistíme

a

spočteme

U1 = 7.10 +

hodnoty

7.8
− 40 = 70 + 28 − 40 = 58 a
2

10.11
− 113 = 70 + 55 − 113 = 12 . V tabulkách dvouvýběrového Wilcoxonova testu
2
zjistíme pro hodnoty m = 10 a n = 7 ( první hodnota je podle úmluvy vždy větší nebo rovna
druhé hodnotě ) kritickou hodnotu 14. Tedy zamítáme na hladině významnosti 0,05 hypotézu
H0 o stejném způsobu měření.
Použijeme – li přechod na rozdělení N(0,1) získáme
58 − 35
U=
= 2, 24457 , protože je tato hodnota větší než 1,96 zamítáme i tímto
105
způsobem hypotézu H0 . Data tedy pocházejí z různých rozdělení!
U 2 = 7.10 +

Příklad 8.7
Ověřme , zda existuje významný rozdíl v hektarových výnosech brambor při použití
dvou metod hnojení. V následující tabulce jsou uvedeny hektarové výnosy :
hodnoty X
hodnoty Y

58
67

55
60

57
71

59
68

54
56

52
53

50
62

53

56

Řešení:
Nejdříve seřadíme hodnoty X a Y dohromady a setřídíme je podle velikosti:
50

52

53

53

54

55

56

56

57

58

59

60

62

67

68

71

Opět jsme odlišným způsobem označili hodnoty X . Podobně jako v předchozím
příkladu zjistíme hodnoty S1 = 54 a S2 = 82 , stejně tak zjistíme , že hodnoty U1 = 54 a U2 = 9
, protože kritická hodnota pro případ m = 9 a n = 7 je rovna 12 , zamítneme hypotézu H0 na
hladině významnosti 0,05.
Pokud bychom počítali aproximaci pomocí rozdělení N(0,1) získáme hodnotu:
54 − 31,5
U=
= 2,31455 . Tato hodnota je větší než 1,96 . Zamítáme tedy i touto metodou
42
hypotézu H0 o stejných výnosech pomocí obou metod hnojení.

8.4 Jednovýběrový Kolmogor –Smirnovův test
Nechť X 1 ,L , X n je náhodný výběr. Mějme dále určité spojité rozdělení s distribuční
funkcí F. Stanovme hypotézu H0 : Distribuční funkce rozdělení, z něhož pochází náhodný
výběr je F .
Nejdříve vytvoříme empirickou distribuční funkci Fn. vytvořenou z hodnot výběru
X 1 ,L , X n . Položíme
Dn = sup Fn ( x) − F ( x)

(8.9)

x

zřejmě velké hodnoty Dn budou podporovat hypotézu H1 . Pro malé hodnoty n nacházíme
kritické hodnoty v tabulkách , pro velké hodnoty n se provádí aproximace

Dn

1
2
.ln  
2.n  α 

(8.10)

Hypotézu H0 zamítáme , když Dn ≥ Dn(α).
Tento test můžeme používat bez jakýchkoli úprav na testování , zda daná data pochází
z rozdělení , které známe včetně všech možných parametrů , které toto rozdělení definují.
Tedy bez úprav se nehodí přímo na testování , zda daná data pochází z normálního
rozdělení. V případě , že by dané parametry byly odhadnuty z výběru , změní se velmi
výrazně hodnoty kritických hodnot Dn . Pro takovéto případy jsou kritické hodnoty odhadnuty
pomocí simulačních metod viz Lillieforst , Iman .
Příklad 8.8
V následující tabulce je uvedeno 20náhodných čísel vygenerovaných generátorem
náhodných čísle v programu Excel . Protože tato čísla mají pocházet z rozdělení
rovnoměrného na intervalu (0,1) , budeme testovat hypotézu H0 : Dané údaje jsou popsány
pomocí rozdělení Ro(0,1) ( rovnoměrné rozdělení na intervalu (0;1)).
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
0,040391 0,061493 0,077673 0,086749 0,123528 0,136589 0,168583 0,327113 0,376007 0,376199
11
12
13
14
15
16
17
18
19
20
0,446321 0,528015 0,655216 0,786571 0,789621 0,842974 0,861987 0,890659 0,972825 0,974874

Řešení:

Nejdříve sestrojíme empirickou distribuční funkci . Protože vygenerované hodnoty
jsou jedinečné ( jsou od sebe různé ) bude konstrukce empirické distribuční funkce takováto :
Pro hodnoty x ≤ 0,040391 bude F20(x)=0 , v každé hodnotě xi bude mít empirická
1
= 0, 05 ( jestliže by se některá z hodnot xi
distribuční funkce skok stejný a rovný
20
p
v bodě xi ) .
vyskytovala např. p – krát , pak by měla funkce Fn skok
n
Dále je zobrazena empirická distribuční funkce F20 a distribuční funkce rovnoměrného
rozdělení na intervalu (0,1):

1
0,9
0,8
0,7
0,6
emp. D.f.

0,5

Ro(0,1)

0,4
0,3
0,2
0,1
0
0

0,1

0,2

0,3

0,4

0,5

0,6

0,7

0,8

0,9

1

Výpočtem zjistíme , že v našem případě je hodnota D20 = 0,18147 . V tabulkách
ověříme , že pro hladinu významnosti je kritická hodnota pro n = 20 rovna 0,29408 . Protože
D20 je menší než kritická hodnota , nelze zamítnout hypotézu o výběru z rozdělení Ro(0,1).

8.5

Dvouvýběrový Kolmogor – Smirnovův test

Nechť je X 1 ,L , X m je náhodný výběr ze spojitého rozdělení s distribuční funkcí F1 ,
nechť dále je Y1 ,L , Yn náhodný výběr ze spojitého rozdělení s distribuční funkcí F2 , který je
na výběru X 1 ,L , X m nezávislý. Hypotézu H0 sestavujeme tak ,že F1 = F2 , alternativní
hypotéza je oboustranná tedy F1 ≠ F2 .
Označíme – li F1m a F2n empirické distribuční funkce jednotlivých výběrů ( sestrojené
stejným způsobem jako v předchozím případě jednovýběrového testu ) , vyplývá z obecných
vět , že s rostoucími hodnotami m , n se tyto funkce blíží ke skutečným distribučním funkcím
F1 a F2 . Označme dále
Dm ,n = sup F1m ( x ) − F2 n ( x ) .
x

Celý test je založen na následující větě:
Věta 8.9

Označme M =

m.n
. Nechť dále je
m+n

∞

K ( λ ) = 1 − 2.∑ ( −1)
k =1

k +1

.exp ( −2.k 2 .λ 2 )

(8.11)

Potom pro každé λ platí
lim P

m , n →∞

( M .D < λ ) = K ( λ ) .
m,n

Důkaz : Proveden např. v Hájek a Šidák (1967).
2

Funkci K(λ) často aproximujeme pomocí jejích počátečních členů 1 − 2.e−2.λ . Tato
1 2
.ln   , aproximativní kritická hodnota pro Dm ,n je
2 α 

hodnota je rovna 1 - α , jestliže λ =

1
2
.ln   = Dm* ,n (α ) . Jsou – li čísla m , n malá porovnává se hodnota Dm,n
2.M
α 
s tabelovanými hodnotami kritických hodnot na dané hladině významnosti.
Jestliže jsou hodnoty m , n větší ( m + n > 35 ) , vypočítáme nejdříve hodnotu
λ0 = M .Dm ,n , pomocí ní vypočítáme K ( λ0 ) .Jestliže je tato hodnota větší nebo rovna 1 - α ,

tedy rovna

zamítneme hypotézu H0 na hladině , která se s rostoucím rozsahem blíží k číslu α . Při
velkých hodnotách aproximujeme kritickou hodnotu číslem Dm* , n (α ) . Hypotézu H0 pak
zamítáme , jestliže je Dm ,n ≥ Dm* ,n (α ) .
Příklad 8.9
Budeme vyšetřovat hodnoty uvedené v příkladě 8.6. Máme tedy k dispozici data:
hodnoty X
hodnoty Y

3,3
3,2

3,4
3,5

3,4
3,4

3,2
3,4

3,5
3,4

3,3
3,3

3,2
3,5

3,5

3,4

Řešení:
Podobně jako v předchozí části si zobrazíme empirické distribuční funkce:
Empirické distribuční funkce
1

0,9

0,8
0,7

0,6
X

0,5

Y

0,4

0,3

0,2

0,1

0
3,1

3,15

3,2

3,25

3,3

3,35

3,4

3,45

3,5

3,55

3,6

3,5

Zřejmě je hodnota D10,7 = 0,371429 , kritická hodnota nalezená v tabulkách
dvouvýběrového Kolmogorova – Smirnova testu pro hladinu významnosti 0,05 je rovna
46
= 0,657142857 . Tedy na základě zjištěných údajů nemůžeme zamítnout hypotézu H0 , že
70
oba výběry pocházejí ze základních souborů se stejnými distribučními funkcemi. Pokud
*
bychom použili aproximovaných hodnot je v našem případě D7,10
( 0, 05) = 0,669279734 ,
tedy ani v tomto případě hypotézu H0 nemůžeme zamítnout.

8.6

Kruskalův – Wallisův test

Jde o test , který je zobecněním dvouvýběrového Wilcoxonova testu . Je používán na
data , která se velmi liší od dat typu normálního.
Nechť X i1 ,L , X ini je náhodný výběr ze spojitého rozdělení s distribuční funkcí Fi ,
i=1,…,N .Nechť jsou všechny na sobě navzájem nezávislé. Hypotézu H0 postavíme takto.
H0 : F1(x) = … = FN(x)
pro všechna x
Alternativní hypotéza H1 je stanovena v případě neplatnosti hypotézy H0 . Podobně
jako v předchozích případech vytvoříme sdružený náhodný výběr z hodnot Xij o rozsahu
n = n1 + L + nN ( předpokládáme , že ni >5,i=1,L ,N - tedy četnost každého výběru je větší
než 5 ). Hodnoty sdruženého výběru se uspořádají do neklesající posloupnosti a určí se pořadí
Rij v rámci každé veličiny Xij ze sdruženého náhodného výběru.
ni

V rámci každé skupiny zjistím hodnotu Ri = ∑ Rij , zřejmě je součet všech hodnot Ri
j =1

roven

n.(n + 1)
.
2
Testovou statistikou je
N
Ri2
12
.∑
Q=
− 3.(n + 1)
n.(n + 1) i =1 ni

(8.12)

Ukazuje se , že při platnosti hypotézy H0 je rozdělení Q asymptoticky χ2 rozdělení ,
jestliže hodnoty všech ni rostou nade všechny meze. Výpočtem se zjistí , že E ( Q ) = N − 1 ,
tedy půjde o rozdělení χ2
Q ≥ χ N2 −1 (α ) .

s N-1 stupni volnosti.

Hypotézu H0

zamítáme, jestliže

Kruskal – Wallisův test je velmi citlivý na případná posunutí v argumentech
jednotlivých distribučních funkcí. Jestliže dojde k zamítnutí H0 , snažíme se dále rozhodnout
, které dvojice se ve sdruženém výběru od sebe významně liší.
R
Pro tento případ označíme symbolem ri = i , kde i=1,…,N . Jestliže označíme
ni
symbolem kwN-1(α) kritickou hodnotu Kruskal – Wallisova testu ( v případě malých hodnot N
ji najdeme přímo v tabulkách tohoto testu, pro větší rozsahy ji aproximujeme výše uvedeným
rozdělením χ2 N-1(α) ) , potom prohlásíme , že se distribuční funkce i – tého a j – tého výběru
od sebe významně liší , jestliže platí

ri − rj >

1 1 1
.  +  .n.(n + 1).kwN −1 (α )
12  ni n j 

(8.13)

Tento postup opakujeme pro všechny možné dvojice.
Příklad 8.10
U přijímacích zkoušek se sledují počty bodů z testů z matematiky , chceme posoudit ,
zda se výsledky významně odlišují. Náhodně vybereme z jednotlivých sledovaných typů škol
8 studentů . Hladina významnosti je stanovena na 0,05. Dále následují data :
stud.

gymnasium gymnasium
státní
soukromé
1
78
84
2
95
42
3
47
54
4
78
76
5
85
68
6
96
61
7
75
71
8
83
66

SEŠ

prům. škola
32
72
65
41
67
52
53
70

93
74
58
85
60
72
67
59

Řešení:

Jednotlivé hodnoty přepíšeme do jediné tabulky a přidáme sloupec , v němž uvedeme
pořadí jednotlivého prvku ve sdruženém výběru , v poslední řádce čteme hodnoty Ri .
gymnasium
státní

stud.
1
2
3
4
5
6
7
8

78
95
47
78
85
96
75
83

pořadí
24,5
31
4
24,5
28,5
32
22
26
192,5

gymnasium
soukromé
84
42
54
76
68
61
71
66

pořadí
27
3
7
23
16
11
18
13
118

SEŠ

pořadí
32
72
65
41
67
52
53
70

1
19,5
12
2
14,5
5
6
17
77

prům.
škola
93
74
58
85
60
72
67
59

pořadí
30
21
8
28,5
10
19,5
14,5
9
140,5

Dosazením známých hodnot zjistíme velikost testovací statistiky
Q=

12  192,52 1182 77 2 140,52 
.
+
+
+
 − 3.33 = 9,877130682
32.33  8
8
8
8 

Kritická hodnota χ2 s 3 stupni volnosti na dané hladině významnosti je 7,81 . Protože
je hodnota testové statistiky větší než kritická hodnota χ2 , zamítáme hypotézu H0 o shodě
výsledků testů studentů z různých typů škol.

Dále budeme chtít posoudit na základě dat , které dvojice se vzájemně liší, použijeme
vztahu (8.13) . Vzhledem k tomu , že všechny skupiny mají stejný počet členů , bude také
pravá strana ve výrazu (8.13) konstantní a rovna 9,88 . Zjistíme tedy absolutní hodnoty
rozdílů stojících ve výrazu (8.13) na levé straně . Uvedeme tyto rozdíly v přehledné tabulce:
gymnasium
soukromé
gymnasium
státní
gymnasium
soukromé

9,3125

SEŠ

prům.
škola

14,4375

6,5

5,125

2,8125

SEŠ

7,9375

Z vypočtených hodnot je jasné , že významný rozdíl mezi výsledky studentů
jednotlivých typů škol je v případě státních gymnázií a SEŠ.

8.7

Friedmanův test

Nechť jako v minulém případě jsou Yij nezávislé náhodné veličiny spojitého typu
s distribučními funkcemi Fij. Friedmanovým testem testujeme hypotézu H0 , že Fij nezávisí
na j , na i záviset může. V podstatě jde o rozšíření Wilcoxonova testu pro dva závislé výběry ,
na více na N závislých výběrů.
Test se používá k ověření shody úrovně sledovaného znaku v souborech vytvořených
na základě N závislých výběrů se stejným rozsahem jednotek. Typickou úlohou je případ ,
kdy jednu skupinu jednotek sledujeme v určitých časových obdobích . Úlohou je potom
posoudit, zda sledovaný znak závisí na daných podmínkách.
Pro každou hodnotu Yij ( i=1,…,I a j=1,…,J) zjistíme pořadí Rij v dané skupině i. Tvar
testovací statistiky je potom roven
2

J
12
 I

Q=
.∑  ∑ Rij  − 3.I .( J + 1)
I .J .( J + 1) j =1  i =1 

(8.14)

Dá se opět dokázat, že při platnosti hypotézy H0 má náhodná veličina Q tvar χ2 s J – 1
stupni volnosti. Hypotézu H0 zamítáme , jestliže hodnota Q překročí kritickou hodnotu na
hladině významnosti α . Stejně jako v předchozích testech pro větší hodnoty za tuto hodnotu
budeme brát χ2 J-1(α) .
Zamítneme – li H0 zajímá nás většinou , které dvojice se od sebe významně
liší.Označme
I

R j = ∑ Rij

(8.15)

i =1

Podobně jako u Kruskal – Wallisova testu budeme zjišťovat zda Ru − Rt je větší nebo
rovno tabelované kritické hodnotě. Asymptoticky lze kritické hodnoty určit pomocí vztahu
qJ ,∞ (α ).

1
.I .J . ( J + 1)
12

(8.16)

Kritické hodnoty qJ ,∞ (α ) se opět hledají ve speciálních tabulkách .
Příklad 8.11
Máme k dispozici údaje z průzkumu cen u tří prodejen , u nichž byly sledovány ceny 7
druhů zboží. Chceme posoudit , zda ve sledované době byla významně odlišná úroveň cen
v těchto prodejnách.
a
b
c
d
e
f
g

4,5
12,5
5,7
1,4
27,8
72,4
8,4

5
11,7
5,5
1,5
32,6
89,4
6,7

8,2
14,1
5,6
1,8
28,1
72,5
7,8

Řešení:
Z dat je zřejmé , že je I = 7 a J = 3 . Nejdříve upravíme předchozí tabulku tak , aby se
v jednotlivých řádcích vyskytovali jen pořadí jednotlivých hodnot. Pro jednotlivé prodejny
tyto hodnoty sečteme , umocníme a dosadíme do vzorce (8.14).
zboží

1. Prodejna 2. Prodejna 3. Prodejna
1
2
3
a
2
1
3
b
3
1
2
c
1
2
3
d
1
3
2
e
1
3
2
f
3
1
2
g
12
13
17
Rj
144
169
289
Rj2

12
(144 + 169 + 289 ) − 3.7.4 = 86 − 84 = 2 . Z tabulek Friedmanova testu
7.3.4
vyplývá , že kritická hodnota pro α = 0,05 ; I = 7 a J = 3 je rovna 7,143 . Hodnota Q není větší
než kritická hodnota , proto nemůže na hladině významnosti 0,05 zamítnout předpoklad o
shodě cen jednotlivých prodejnách.
Tedy Q =

Příklad 8.12
Celkem 10 studentů řešilo stejně obtížné úlohy s přemísťováním předmětů ( každý
celkem 100 v jedné úloze) za různých teplotních podmínek . Pomocí Friedmanova testu
rozhodněte , zda se výkony v těchto podmínkách lišily. Dále jsou uvedeny data jednotlivých
studentů:
student
1
2
3
4
5
6
7
8

t=0°C
70
96
82
78
91
98
92
96

t=30°C
65
92
91
86
90
95
90
94

t=50°C
48
72
80
82
79
87
88
78

9
10

78
86

90
92

85
90

Řešení:
Podobně jako v předchozím případě zjistíme , že I = 10 a J = 3. Dále zjistíme pořadí :
student
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
Rj
Rj2

t=0°C
3
3
2
1
3
3
3
3
1
1
23
529

t=30°C
2
2
3
3
2
2
2
2
3
3
24
576

t=50°C
1
1
1
2
1
1
1
1
2
2
13
169

Z
těchto
hodnot
již
můžeme
spočítat
testovou
statistiku
.
12
Q=
. ( 529 + 576 + 169 ) − 3.10.4 = 7, 4 . Kritická hodnota pro dané hodnoty I a J je
10.3.4
rovna 6,2 . Tedy zamítáme nulovou hypotézu , výsledky studentů se na hladině významnosti
0,05 významně liší. Zjistíme dále hodnoty rozdílů částečných součtů pořadí:
R1-R2=
R2-R3=
R1-R3=

-1
11
10

Z tabulky Friedmanova testu pro mnohonásobná porovnávání je kritická hodnota
rovna 10,5. Tuto hranici překračuje R2 a R3 tedy na hladině významnosti 0,05 prokázán
významný rozdíl mezi výsledky při teplotě 30°C a 50°C.

