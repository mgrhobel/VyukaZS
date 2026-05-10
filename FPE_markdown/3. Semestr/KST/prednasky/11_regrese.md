---
title: "11_regrese.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/11_regrese.pdf"
date: 2009-12-27
type: PDF (text-based)
---

4. Regrese
Jedním z hlavních úkolů matematické statistiky je hledání a studium závislostí mezi
dvěma či více proměnnými. Závisle proměnná se zpravidla označuje Y a nezávisle proměnné
X1 , … , Xi ,i ≥ 1. Závislosti mezi Y a skupinou proměnných X mohou být funkční nebo
statistické.
V případě přímé funkční závislosti je náhodná část ve vyjádření této závislosti nulová,
proto se jí nebudeme samozřejmě zabývat. V běžných situacích však nastává situace , kdy Y
má povahu náhodné veličiny . Nezávisle proměnné X1 , … , Xi mohou být nenáhodnými
( pevnými ) veličinami nebo náhodnými veličinami.
Statistickou závislostí mezi náhodnou veličinou Y a veličinami X1 , … , Xi rozumíme
předpis, který každé uspořádané i – tici x1 , … , xi přiřazuje právě jedno podmíněné rozdělení
náhodné veličiny Y . Náhodná veličina Y je tedy statisticky závislá na veličinách X1 , … , Xi ,
jestliže změny v hodnotách x1 , … , xi mají za následek změnu podmíněného rozdělení
náhodné veličiny Y.

4.1 Teoretické základy
V praxi není většinou zákon rozdělení ( typ náhodné veličiny Y ) znám. Máme
většinou k dispozici pouze data ve formě uspořádaných i+1 – tic , kde prvních i složek
odpovídá hodnotám x a poslední složka odpovídá hodnotě y. Na základě experimentálních
údajů se provede výběr funkce , která má co nejlépe vystihovat rozložení skutečných údajů ,
tuto funkci nazýváme teoretickou regresní funkcí a je uváděna ve tvaru
y = f ( x1 ,K , xi ; γ 0 ,K , γ p )
(4.1),

γ 0 ,K , γ p

jsou nazývány teoretickými regresními parametry
( koeficienty ) . Tyto parametry mají povahu konstant, které nejsou známy . V modelovaných
vztazích je budeme nahrazovat jejich bodovými odhady a0 , … , ap tak , aby funkce
Y = f ( x1 ,K , xi ; a0 ,K , a p )
(4.2)
co nejlépe aproximovala naměřené hodnoty Y .Funkce (4.2) se nazývá empirickou
regresní funkcí a veličiny a0 , … , ap empirickými regresními parametry. Empirické regresní
parametry jsou náhodné veličiny. Jednou z metod jak je určit je použít metodu nejmenších
čtverců.
V dalším textu bude dále závisle proměnná Y ( vysvětlovaná proměnná ) náhodnou
veličinou , naopak nezávisle proměnné ( vysvětlující proměnné ) X1 , … , Xi jsou
nenáhodnými veličinami.
Regresní závislostí bude pro naše potřeby jednostranná závislost dané náhodné
veličiny ( např. Y ) na jiné veličině – ne nutně náhodné veličině ( např. X1 , … , Xi ). Pro další
účely třídění a studování regresních závislostí se rozlišují následující situace:
a. Náhodná veličina závisí na jedné další veličině – párová regrese. Například :
kde

hodnoty

y = γ 0 .x +

γ1
x +γ3

b. Náhodná veličina –závisí na dvou a více veličinách – mnohonásobná regrese
γ .x
.Například : y = γ 1.x1 + 2 2 + γ 0
γ 3 + x3
Z pohledu tvaru funkce (4.1) můžeme dále dělit jednotlivé případy regresních
závislostí na:
1. Lineární regresi – uvažovaná funkce f je lineární vzhledem k parametrům
γ 0 ,K , γ p . Například : y = γ 1.x1 + γ 2 .x2 + γ 0

2. Nelineární regresi – uvažovaná funkce f je nelineární funkcí vzhledem
γ .x + γ .x
k parametrům γ 0 ,K , γ p . Například : y = 1 1 2 2 .
γ 3 .x3 + γ 4 .x4
Regresní analýzou nazveme tedy tu část matematické statistiky , která se zabývá
studiem a konstrukcí regrese. Nejdříve určíme podmínky regresního modelu.
Definice 4.1
Určujeme regresi Y na i nenáhodných veličinách x1 , … , xi . Nechť je dále dáno n
( n > p+1 ) uspořádaných i+1 – tic ( x1k ,K xik , yk ) , kde k = 1 , … , n . Tyto údaje byly

postupně získány empiricky. Na základě těchto údajů byla zvolena teoretická regresní funkce
s neznámými parametry γ 0 ,K , γ p . Dále předpokládejme , že pro náhodné veličiny Yk ,
k=1,…,n platí:

1. Yk = f ( x1 ,K , xi ; γ 0 ,K , γ p ) + ek

(4.2)

Veličiny ek představují náhodné chyby měření a jsou zřejmě také náhodnými
veličinami. Tyto náhodné veličiny musí splňovat následující podmínky:
2. E( ek ) = 0
(4.3)
2
3. Var( ek ) = σ
(4.4)
(4.5)
4. cov( ek , el ) = 0
Dále platí
5. E(Yk) = f ( x1k ,K , xik ; γ 0 ,K , γ p )
6. VAR(Yk) = σ2 .
K řešení výše popsaného modelu používáme nejčastěji metodu nejmenších čtverců.
Součástí řešení je nalezení odhadů parametrů γ 0 ,K , γ p . Tyto odhady budeme dále označovat
symboly c1 , … , cp . Metoda spočívá v nalezení minima čtverců hodnot ek Obecněji budeme
studovat tuto metodu aplikovanou na případ lineární regrese.
Hledáme tedy minimum funkce
n

n

k =1

k =1

(

)

S r (γ 0 ,K , γ p ) = ∑ ek2 = ∑ Yk − f ( x1 ,K , xi ; γ 0 ,K , γ p ) ,
2

(4.6)

požadujeme tedy , aby součet čtverců odchylek naměřených hodnot Yk od
teoretických hodnot f ( x1 ,K , xi ; γ 0 ,K , γ p ) byl minimální. Najdeme tedy nejdříve podezřelé
body ( stacionární body S ) :
∂S (γ 0 ,K , γ p )
∂γ k

= 0,

k = 0,K , p

(4.7)

Poté ověříme pomocí klasických metod, zda v nalezených bodech se nachází
minimum. Soustava rovnic (4.6) se nazývá soustavou normálních rovnic . Řešení této
soustavy je jednoznačné , jestliže alespoň p + 1 z uspořádaných k – tic [ x1k ,..., xik ] , k=1,…,n
je navzájem různých. Řešením soustavy (4.6) budou potom hodnoty a1 , … , ap , které budou
bodovým odhadem parametrů γ 0 ,K , γ p . Odtud tedy získáme bodové odhady teoretické
regresní funkce (4.1) ve tvaru

Yˆk = f ( x1k ,...xik ; a0 ,...a p ) ,

k = 1,..., n

Rozdíly
eˆk = Yk − Yˆk

(4.8)

se nazývají rezidui a veličina
n

n

k =1

k =1

S r = ∑ eˆk2 = ∑ (Yk − Yˆk ) 2

(4.9)

se nazývá reziduálním součtem čtverců.
Studiem řešení soustavy normálních rovnic a reziduálního součtu čtverců se budeme
zabývat dále v následujících částech této kapitoly a v kapitole následující.

4.2 Model lineární regrese
V této části se budeme zabývat nejjednodušším případem lineární regrese – případem ,
kdy odhadujeme jen dva parametry α a β. Takovýto speciální vztah označujeme jako regresní
přímku a je vyjádřen
Y = α + β.x +e

(4.10)

K odvození bodových odhadů skutečných parametrů α a β použijeme klasickou
metodu nejmenších čtverců. Bodové odhady označíme pro naše potřeby a a b .Tedy podle
(4.6) je
n

n

k =1

k =1

S ( a, b ) = ∑ ek2 = ∑ (Yk − a − b.xk )

2

(4.11)

Tento výraz budeme derivovat podle proměnných a , b . Výsledná soustava
normálních rovnic je potom následující
n
∂S ( a, b )
= −2.∑ (Yk − a − b.xk ) = 0
∂a
k =1

(4.12)

n
∂S ( a, b )
= −2.∑ xk . (Yk − a − b.xk ) = 0
∂b
k =1

(4.13)

Přepíšeme – li tuto soustavu klasickým způsobem máme:
n

n

n.a + b.∑ xk = ∑ Yk ,
k =1

k =1

n

n

n

k =1

k =1

k =1

a.∑ xk + b.∑ xk2 = ∑ xk Yk

,

(4.14)

Z této soustavy vyplývá , že řešení existuje , je – li determinant soustavy různý od
2

n
 n

nuly. Tedy n.∑ xk2 −  ∑ xk  ≠ 0 , ale tento vztah nastane, jestliže hodnoty xk budou
k =1
 k =1 
navzájem různé ( stačí dokonce , aby aspoň dva byly navzájem různé ). Soustava tedy bude
mít právě jedno řešení. Nejprve upravíme první rovnici v (4.14) tím , že ji vydělíme hodnotou
n , získáme tak

a + b.x = Y

(4.15)

Budeme – li znát jednu z hodnot a , b pomocí tohoto vztahu dopočteme druhou .
Určíme hodnotu b , dosazením (4.15) do druhého vztahu v (4.14).
n

n

(Y − b.x ) .n.x + b.∑ x = ∑ x Y ⇒
k =1

2
k

k =1

k k

 n
 n
b.  ∑ xk2 − n.x 2  = ∑ xk Yk − n.x .Y ⇒
 k =1
 k =1
n

∑ x Y − n.x .Y
k k

b = k =1n

2
2
 ∑ xk − n.x 
 k =1


(4.16)

Ze vztahů (4.15) a (4.16) určíme samozřejmě hodnoty a , b.
Příklad 4.2
V 15 za sebou následujících dnech byla zaznamenána hodnota relativní vlhkosti v % a
hodnota orosení v mm3. Naměřené údaje jsou uvedeny v tabulce dále
Relativní vlhkost
Hodnota orosení

46 53 29 61 36 39 47 49 52 38 55 32 57 54 44
12 15

7 17 10 11 11 12 14

9 16

8 18 14 12

Provedeme – li výpočet získáme následující hodnoty a = -2,51 a hodnota b = 0,32.
Výsledek můžeme také zobrazit graficky

18

16

14

Hodnota orosení

12

teoretická hodnota

10

8

6
25

30

35

40

45

50

55

60

65

Z výše uvedeného grafu je patrno , že žádná ze skutečných naměřených hodnot Y na přímce
neleží , přesto však je vyjádření vztahu mezi x a Y pomocí lineárního vztahu dobré.
Podle předpokladů lineárního modelu předpokládáme , že střední hodnota chyb ek je rovna
nule, jejich rozptyl je konstantní a roven σ2 . Dále předpokládáme, že hodnoty Yk ( tzv.
vysvětlované proměnné ) jsou typu normální rozdělení. Odtud tedy vyplývá , že
E (Yk ) = α + β .xk a dále VAR (Yk ) = σ 2 . Celkově tedy Yk N (α + β .xk , σ 2 ) . Budeme dále
vyšetřovat vlastnosti bodových odhadů parametrů α a β. Tedy
n
 n
 n
 ∑ xk Yk − n.x .Y  ∑ ( xk − x ) E (Yk ) ∑ ( xk − x ) . (α + β .xk )
 = k =1
= k =1 n
=
E (b) = E  k =1n
n






2
2
2
2
2
2
  ∑ xk − n.x  
 ∑ xk − n.x 
 ∑ xk − n.x 

 k =1

 k =1

  k =1

n

=

 n



 n 2
2
 ∑ xk − n.x 
 = β .  k =1
=β.
 n 2
2
 ∑ xk − n.x 
 k =1


α .∑ ( xk − x ) + β .  ∑ xk . ( xk − x ) 
k =1

 k =1
 n 2
2
 ∑ xk − n.x 
 k =1


Protože je E(b) = β , je podle definice 11.12 z kapitoly 11. tento odhad nevychýlený. Zjistíme
dále hodnotu rozptylu tohoto odhadu

n
 n
 n
2
2
2
 ∑ xk Yk − n.x .Y  ∑ ( xk − x ) .VAR (Yk ) σ .∑ ( xk − x )
k =1
 = k =1
VAR(b) = VAR  k =1n
=
=
2
2
n
n



2
2




2
2
2
2
  ∑ xk − n.x  
 ∑ xk − n.x 
 ∑ xk − n.x 

  k =1
 k =1

 k =1


=

σ2

(4.17)

 n 2
2
 ∑ xk − n.x 
 k =1


Při výpočtu jsme využili následující rovnost
n

n

∑ ( x − x ) = ∑ x − n.x
k =1

2

k

k =1

2
k

2

(4.18)

Podobně nyní zjistíme střední hodnotu a rozptyl pro odhad a.
 n

 ∑ Yk
 n α + β .x
k
− x .E (b) = α + β .x − x .β = α ,
E (a) = E  k =1 − b.x  = ∑
n
 n
 k =1





tedy i bodový odhad parametru α je nevychýlený. Rozptyl hodnoty a je roven
n

∑VAR(Yk )

VAR (a ) = k =1

n2

n

+ ( x 2 ) .VAR ( b ) =

σ2
n

+

σ 2 .x 2
 n 2
2
 ∑ xk − n.x 
 k =1


= σ 2.

∑x

2
k

k =1

 n

n.  ∑ xk2 − n.x 2 
 k =1


Závěrem můžeme tedy konstatovat , že náhodné veličiny a a b jsou typu normální rozdělení (
jsou lineární kombinací nezávislých náhodných veličin typu normálního rozdělení ) a můžeme
navíc určit jejich parametry tedy

a

n


σ 2 .∑ xk2


k =1

 a dále b
N α,

 n 2

2 
 n.  ∑ xk − n.x  
 k =1







2
σ

.
N β, n
 

2
2 
  ∑ xk − n.x  

  k =1

Tyto dva vztahy budou klíčové pro další určení intervalových odhadů skutečných parametrů α
a β.
Věta 4.3

Nechť Sr je reziduální součet čtverců definovaný vztahem (4.6) . Potom
Důkaz:

Sr

σ

2

χ n2−2 .

Proveden například v [1] .
Poznámka 4.4
Výše uvedený důkaz budeme motivovat následující úvahou: Náhodné veličiny Yk
nezávislé , jsou dále normálního typu. Pokud je znormujeme máme

Yk − E (Yk )
VAR (Yk )

=

Yk − α − β .xk

jsou

(4.19)

σ

Proto tedy

 Yk − α − β .xk 


∑
σ
k =1 

n

2

χ n2

Protože ale nahradíme skutečné hodnoty α a β jejich nevychýlenými odhady a a b , sníží se
počet stupňů volnosti o 2 – tedy o počet parametrů, které jsme odhadovali.
Pro další práci označme
n

n

k =1

k =1

S xY = ∑ ( xk − x ) . (Yk − Y ) = ∑ xk Yk − n.x .Y
n

(4.20)

n

S xx = ∑ ( xk − x ) = ∑ xk2 − n.x 2
2

k =1

(4.21)

k =1

n

n

SYY = ∑ (Yk − Y ) = ∑ Yk2 − n.Y 2
2

k =1

(4.22)

k =1

Jestliže použijeme tuto notaci můžeme koeficienty a a b zapsat také takto
b=

S xY
S xx

;

a = Y − b.x .

Dále odvodíme následující výpočetní identitu :

S xx .SYY − S xY 2
Sr =
S xx
n

ST = ∑ (Yi − y )

2

i =1
n

S y = ∑ ( yi − y )
i =1

2

(4.23)

2



S
S
S r = ∑ (Yk − a − b.xk ) =∑  Yk − Y + xY .x − xY .xk  =
S xx
S xx 
k =1
k =1 
n

n

2

 S xx .(Yk − Y ) − S xY .( xk − x )  S xx 2 .SYY − 2.S xx .S xY .S xY + S xY 2 .S xx
= ∑
=
 =
2


S xx
S
k =1 
xx

S xx .SYY − S xY 2
=
S xx
2

n

Ze všech výše uvedených rovností vyplývají následující tvrzení:

1.

Sr

σ

χ n2−2

2

(4.24)

(b − β )
σ

2.

3.

S xx
Sr
2
σ .( n − 2 )

=

n.( n − 2 ) .S xx
n

∑ x .S
k =1

2
k

( n − 2 ).S xx . b − β
(
)
Sr

.( a − α ) tn − 2

tn − 2

(4.25)

(4.26)

r

Toto jsou základní vztahy , pomocí nichž je možno konstruovat jak intervalové odhady
neznámých parametrů α a β , ale i neznámé hodnoty σ. Dále jsou na nich založeny klasické
statistické hypotézy o těchto parametrech.
Často jsme postaveni před otázku nalezení odhadu ( prognózy ) hodnot v nějakém bodě x0 , na
základě znalosti vstupních dat {xk , Yk }. Podle způsobu naší konstrukce je zřejmé, že
přirozeným bodovým odhadem je v tomto případě hodnota a + b.x0 ( je opět nevychýleným
odhadem skutečné neznámé hodnoty – dokažte! ) . Podobně jako v předchozích krocích nás
bude především zajímat typ náhodné veličiny .
n

a + b.x0 =

∑ Yk
k =1

n

n

∑ Y .( x − x ) .( x − x )

− k =1

k

0

k

S xx

n
 1 ( x − x ) . ( x − x0 ) 
= ∑ Yk .  − k
 (4.27)
S xx
k =1
n


Z předchozího vztahu (4.25) vyplývá ( proč ? ), že náhodná veličina a + b.x0 je typu
normální rozdělení . Je tedy nutno zjisti jeho střední hodnotu a rozptyl.
A. E ( a + b.x0 ) = E (a) + x0 .E (b) = α + β .x0

B.
2
2
2
n 
 1 ( xk − x ) .( x − x0 ) 
xk − x ) .( x − x0 ) ( xk − x ) .( x − x0 ) 
(
1
2
+
VAR(a + b.x0 ) = ∑  −
=
 .VAR(Yk ) = σ .∑ 2 − 2.

Sxx
nS
. xx
Sxx2
k =1  n
k =1 n



n


 1 2. ( x − x ) n
0
= σ 2 . −
.∑
S xx
n
k =1



n



∑ (x − x) 

( xk − x ) + x − x 2 . k =1
(
0)
n

2

k

S xx 2

 1 ( x − x0 )2 
 = σ . +

n

S

xx




2

.
Z těchto rovností tedy vyplývá , že
a + b.x0


 1 ( x0 − x )2  
2
N  α + β .x0 , σ .  +


n
S

 
xx



(4.28)

Pro intervalový odhad skutečných hodnot využijeme vztahů (4.24) a (4.28) . Z těchto vztahů
vyplývá
a + b.x0 − α − β .x0
Sr
1 ( x0 − x )
+
.
n
S xx
( n − 2)
2

tn − 2

(4.29)

Pomocí tohoto vztahu je možno odhadovat chování α + β.x v daném bodě x0 ( odhadujeme
chování parametrů !).
Na druhou stranu je někdy důležité vyšetřit chování hodnoty Y v konkrétním bodě x0 .
V tomto případě stanovujeme budoucí hodnotu náhodné veličiny Y. Opět platí nám známé
vztahy v bodě x0
Y

N (α + β .x0 , σ 2 )

(4.30)

a vztah (4.29). Z nich můžeme stanovit rozdělení následujícího rozdílu
Y − a − b.x0


 1 ( x0 − x )2  
2

N 0, σ . 1 + +
  nebo ekvivalentně
 n


S
xx




Y − a − b.x0
n + 1 ( x0 − x )
σ .
+
n
S xx

2

N ( 0,1)

Využijeme – li dále vztahu (4.24) získáváme

(4.31)

Y − a − b.x0
n + 1 ( x0 − x )
Sr
+
.
n
S xx
( n − 2)
2

tn − 2

(4.32)

Tento vztah je rozhodující pro stanovení odhadu budoucí hodnoty Y v bodě x0 .
Velmi významným je také tzv. celkový F – test . V tomto testu ( v případě lineární
regrese je ekvivalentní t – testu parametru u proměnné x ) posuzujeme , zda náhodná veličina
Y statisticky závisí na hodnotě x. Jako vždy u testů je zvolena hladina významnosti α .
Stanovíme dále hypotézu H0 : β=0 , alternativní hypotéza H1 = non H0 a testová statistika
jako:
ST
F = 2 − 1 , při platnosti hypotézy H0 je tato testová statistika F rozdělení s 1 a k-2 stupni
Sr
n−2
volnosti. Hypotézu H0 zamítneme , jestliže bude hodnota testové statistiky v kritickém oboru
vymezeném příslušnými kvantily F rozdělení.

4.3 Mnohonásobná regrese
V této kapitole uvedeme základní myšlenky řešení případů, kdy vysvětlovaná
proměnná Y je vysvětlována pomocí více než jedné proměnné x .Podržíme dále předpoklady
obecných lineárních modelů a navíc regresní funkce bude lineární vzhledem k neznámým
parametrům .
Zavedeme tedy označení
Y = β 0 + β1.x1 + K + β k .xk + e ,

(4.33)

β0 , …, βk jsou neznámé parametry ( budeme je odhadovat z dat ), e je náhodná chyba se
střední hodnotou rovnou nule a rozptylem rovným σ2 . Parametry i hodnota σ2 jsou neznámé
hodnoty , podobně jako v předchozí kapitole je budeme odhadovat z dat ( budou tedy záviset
na náhodné veličině Y ). Podobně jako v předchozí části bude tedy platit
E (Yi ) = β 0 + β1.xi1 + L + β k .xik

(4.34)

Jestliže dále označíme B0 , …,Bk jako bodové odhady skutečných parametrů β0 , …
,βk, pak můžeme stejně jako v předchozí části použít metodu nejmenších čtverců a hledat tyto
odhady jako hodnoty , které minimalizují následující funkci
n

S ( β 0 ,L , β k ) = ∑ (Yi − β 0 − β1.xi1 − L − β k .xik ) 2

(4.35)

i =1

Označíme – li řešení (4.35) tak , jak jsme dříve uvedli B0 , …,Bk , dostaneme
derivováním vztahu (4.35) soustavu rovnic
n

∑ (Y − B − B .x − L − B .x ) = 0
i =1

0

i

1

i1

k

ik

n

∑ x .(Y − B − B .x − L − B .x ) = 0
i =1

i1

0

i

1

i1

k

ik

n

∑ x .(Y − B − B .x − L − B .x ) = 0 ,
i =1

i2

0

i

1

i1

k

(4.36)

ik

M
n

∑ x .(Y − B − B .x − L − B .x ) = 0
i =1

ik

0

i

1

i1

k

ik

která se nazývá stejně jako v jednorozměrném případě soustava normálních rovnic nebo
normální soustava. Tuto soustavu můžeme upravit například takto
n

n

n

∑ Yi = n.B0 − B1.∑ xi1 + L + Bk .∑ xik
i =1

i =1

i =1

n

n

n

n

i =1

i =1

i =1

i =1

n

n

n

∑ xi1.Yi =n.∑ xi1.B0 + B1.∑ xi12 + L + Bk .∑ xi1.xik
n

∑ x .Y =n.∑ x .B + B .∑ x .x + L + B .∑ x .x
i =1

i2

i =1

i2

0

1

i =1

i1

i2

k

i =1

i2

M
n

n

n

n

i =1

i =1

i =1

i =1

∑ xik .Yi =n.∑ xik .B0 + B1.∑ xi1.xik + L + Bk .∑ xik 2

ik

(4.37)

Dříve než budeme tuto soustavu řešit, zavedeme označení , které v dalším textu
budeme dodržovat.
 1 x11 x12 K x1k 
 Y1 


1 x21 x22 K x2 k 
 

= M  , =
 M M
M
M 
Y 


 n
 1 xn1 xn 2 K xnk  .
 β1 
 e1 
 B0 
 
 
 
e =  M , B =  M 
β= M  ,
β 
e 
B 
 k
 n
 k
Model mnohonásobné regrese je tedy možno zapsat pomocí předchozích symbolů
takto

 = .β
⋅ +e

(4.38)

Normální rovnice (4.37) se zapíší v maticové formě

 ⋅  ⋅  =  ⋅ 

(4.39)

Symbol  znamená transponovanou matici k matici  . Nalezení řešení (4.39)
znamená řešit tuto soustavu klasickými prostředky . Dá se ukázat , že matice  ⋅  je
pozitivně definitní a regulární viz [1] str. 62 .Existuje k ní inversní matice a je
 = (  ⋅  ) .
⋅  ⋅
--1

(4.40)

Příklad :
V tabulce jsou uvedeny hodnoty lokalit s počtem obyvatel , mírou rozvodovosti a
mírou sebevražd. Z daných údajů zjistíme hodnoty odhadů parametrů β0 , …, βk.
Řešení:
Tabulka 4.1
Počet obyvatel v Rozvodovost na Počet sebevražd na
tisících
100 000 obyvatel 100 000 obyvatel
679,00
30,40
11,60
1 420,00
34,10
16,10
1 349,00
17,20
9,30
296,00
26,80
9,10
6 975,00
29,10
8,40
323,00
18,70
7,70
4 200,00
32,60
11,30
633,00
32,50
8,40

Budeme zjišťovat hodnotu odhadů koeficientů β0 , …, β2 . Náhodnou veličinou Y
bude počet sebevražd , proměnnými hodnotami x1 a x2 budou postupně počet obyvatel a
rozvodovost v regionu. Řešením získáme hodnoty B0 = 3,50735 ; B1 = -0,00024771 a B2 =
0,260947 . Za předpokladů lineární regrese je vztah mezi výše uvedenými hodnotami

vyjádřen : Y = 3,5073 − 0, 0002.x1 + 0, 2609.x2 . Z tohoto vztahu je zřejmé , že proměnná x1
nehraje v určení hodnoty Y významnější roli. Tento příklad budeme ještě vyšetřovat dále.
V dalším textu uvedeme souhrnně výsledky , kterých lze dosáhnout analýzou výše
uvedených tvrzení.
Souhrnné výsledky:
1. Pro odhady B parametrů β platí :
1.1.

E (  ) = β , VAR (  ) = σ 2 . (  ⋅  ) .
−1

(4.41)

B je vícerozměrné normální rozdělení!
Obdoba tvrzení (4.7) !
2. Podobně

jako

v jednorozměrném

případě

n

nazveme

viz

např.

(4.6)

S r = (  − .
⋅ ) . (  − .
⋅ ) = ∑ (Yi − B0 − B1.xi1 − B2 .xi 2 − L − Bk .xik ) (4.42)
T

2

i =1

reziduálním součtem čtverců . Pro tuto hodnotu platí:
2.1.

S r =  ⋅ -− .
⋅  ⋅

(4.43)

2.2.

Sr

(4.44)

σ

2

χ n2−( k +1)

Sr
tzv. reziduální rozptyl . Tato
n − (k + 1)
náhodná veličina je jak je vidět z předchozího tvrzení nestranným odhadem parametru σ2

3. V dalším textu označujeme symbolem s 2 =

4. Nechť vij je (i,j) – tý prvek matice (  ⋅  ) . Pak pro každé i = 1, … , k má náhodná
−1

veličina

Ti =

Bi − β i

(4.45)

s 2 .vii

rozdělení tn-(k+1).

5. Podle obecných požadavků musí platit E (Y / x ) = β 0 + β1.x1 + L + β k .xk , bodovým
n

odhadem této hodnoty je ∑ Bi .xi , kde x0 = 1 . Jestliže chceme určit intervalový odhad
i =1

n

výše uvedené hodnoty , musíme určit rozdělení ∑ Bi .xi . Protože tento výraz můžeme
i =1

zapsat jako lineární kombinaci náhodných veličin Yi , které jsou typu normální rozdělení ,
bude i naše hledané rozdělení typu normálního. Spočtěme tedy střední hodnotu:

n
 n
 n
E  ∑ xi .Bi  = ∑ xi .E ( Bi ) = ∑ xi .β i
i =1
 i =1
 i =1
Spočtěme dále rozptyl:

(4.46)

n
n
−1 n

VAR  ∑ xi .Bi  = cov(∑ xi .Bi , ∑ x j .B j ) =  T . (  .
(4.47),
⋅ ) ⋅  ⋅σ 2
i =1
j =1
 i =1

 x0 
kde ==  M  je vektor vstupních hodnot. Výše uvedený výpočet je uveden v detailech
x 
 k

například v [1] . Jestliže tedy využijeme vztahy (4.46) a ( 4.47) získáme následující
n

n

∑ B .x − ∑ x .β
i =1

i

i

i =1

i

i

σ .  T . (  .
⋅ ) ⋅
−1-

N ( 0,1)

(4.48)

6. Využijeme – li vztahu (4.48) a (4.44) získáváme
n

n

i =1

i =1

∑ Bi .xi − ∑ xi .β i
−1Sr
.  T . (  .
⋅ ) ⋅
n − (k + 1)

tn − k −1

(4.49)

n

n

i =1

i =1

Odtud můžeme získat intervalové odhady pro odhady vzdáleností ∑ Bi .xi − ∑ xi .β i ,
neboli pro budoucí predikované hodnoty.
7. Podobně jako v případě jednorozměrném se zajímáme také o případ odhadu vzdáleností
n

Y(x) na ∑ Bi .xi . Pokud provedeme podobnou analýzu jako v předchozím , získáme
i =1

výsledky velmi podobné jednorozměrnému případu viz (4.32)
n

Y ( x ) − ∑ Bi .xi
i =1

−1Sr
. 1 + + T . (  .
⋅ ) ⋅
n − (k + 1)

tn − k −1

(4.50),

odtud můžeme odvodit intervalové odhady resp využít tento vztah pro konstrukci statistik
ve vhodných statistických hypotézách.
8. Podobně jako u případu jednorozměrné regrese , se provádí celkový F test, který rozhodne
o vhodnosti regresního modelu ( pokud provedeme n t – testů na jednotlivé koeficienty ,
jde o ekvivalentní postup ).
V tomto testu ( v případě lineární regrese je ekvivalentní t – testu parametru u
proměnné x ) posuzujeme , zda náhodná veličina Y statisticky závisí na hodnotách xi. Jako
vždy u testů je zvolena hladina významnosti α . Stanovíme dále hypotézu H0 :
β1=β2=…βn=0 , alternativní hypotéza H1 = non H0 a testová statistika jako:

ST
F = n−2
, při platnosti hypotézy H0 je tato testová statistika F rozdělení s n-2 a
Sr
k − n −1
k-n-1 stupni volnosti. Hypotézu H0 zamítneme , jestliže bude hodnota testové statistiky
v kritickém oboru vymezeném příslušnými kvantily F rozdělení.

