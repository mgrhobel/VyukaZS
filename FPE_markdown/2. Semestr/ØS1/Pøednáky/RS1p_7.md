---
title: "RS1p_7.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/ØS1/Pøednáky/RS1p_7.pdf"
date: 2008-08-24
type: PDF (text-based)
---

4.3 Dynamické vlastnosti lineárních dynamických systémů
Dynamické chování je charakterizováno odezvou systému na vnější podnět.
Z matematického hlediska jde o transformaci prostoru vstupních funkcí do prostoru
výstupních funkcí. Pro lineární dynamické systémy představuje tato transformace vnější popis
systému a může být představována:
a) diferenciální rovnicí,
b) obrazovým přenosem,
c) přechodovou funkcí nebo přechodovou charakteristikou,
d) frekvenčním přenosem nebo frekvenční charakteristikou,
e) rozložením nul a pólů přenosové funkce.
Statické chování systému je určeno závislostí výstupní veličiny na vstupní veličině
v ustáleném stavu. Grafickým vyjádřením je statická charakteristika. Podle tvaru statické
charakteristiky se systémy dělí na lineární a nelineární.
Způsob popisu dynamického systému diferenciální rovnicí a obrazovým přenosem jsme
probrali dříve.
Přechodová funkce: je odezva systému na Hevisideovu funkci (jednotkový skok) působící na
vstup systému. Grafem přechodové funkce je přechodová charakteristika.
Heavisideova funkce

l (t) =

L {l (t)} =

H (p) =

0

t<0

1

t≥0

1
;
p

1
F(p)
p

L obraz přechodové funkce

1

1

h(t) = L−1  F(p) 
p


přechodová funkce

Měření přechodové charakteristiky
Jednotkový skok na vstup – na výstupu zapisovač

Příklad:
Vypočítejte přechodovou funkci a nakreslete přechodovou charakteristiku pro systém popsaný
diferenciální rovnicí:
3 y ′ + y = 2u

y (0 ) = 0

Řešení:
a)
u(t) = l(t)
3y ′ + y = 2
charakteristická rovnice:
3λ + 1 = 0
λ= −

1
3
y ( t ) = C ⋅ e λt + y(0)

Vypočítáme (metodou variace konstant):
t
− 

3

y (t ) = h(t ) = 21 − e 



b) L - transformací
L ( p )( 3 p + 1) = 2U ( p )
U ( p) =

h (t ) = L

−1

1
p

t


− 

2
3

 = K = 2 1 − e 


 p ( 3 p + 1) 

2

Frekvenční přenos a frekvenční charakteristika.
Frekvenční přenos je definován jako poměr Fourierova obrazu výstupní veličiny k Fourierovu
obrazu vstupní veličiny při nulových počátečních podmínkách.
F ( jω ) =

Y ( jω )
U ( jω )

Definice Fourierovy transformace:
∞

{ f ( t )} = ∫ f ( t ) e

F ( jω ) = F

− jωt

dt

−∞

f (t ) = F

−1

∞

}

{F ( jω ) = 21π ∫ F ( jω ) ⋅ e jωt dω
−∞

Frekvenční charakteristika je geometrické místo koncových bodů vektoru frekvenčního
přenosu F ( jω ) mění-li se kruhová frekvence ω ∈ (− ∞; ∞ ) . (V technické praxi ω ∈ 0; ∞ ) ).
Příklad:
Sestrojte frekvenční charakteristiku systému s přenosem F ( p ) =
F ( jω ) =

K
; K = 2; T = 3s .
Tp + 1

2
2
1 − 3 jω 2(1 − 3 jω )
2
− 6ω
=
⋅
=
=
+ j
2
2
3 jω + 1 3 jω + 1 1 − 3 jω 1 + (3ω )
1 + 9ω
1 + 9ω 2
ω s −1

[ ]

0

0,2

5

Re{F ( jω )}

2

1,47

… 0,0088 …

Im {F ( jω )}

0

−0,88

−0,132

3

e) Rozložení pólů a nul přenosu
Mějme systém, který je popsán přenosovou funkcí ve tvaru:
F ( p) =

bm ( p − q1 )( p − q 2 )K ( p − q m )
a n ( p − p1 )( p − p 2 )K ( p − p n )
m≤n

Zavedené symboly mají tento význam:
bm
- zesílení
an
qi (i=1,2,…m) jsou nuly přenosové funkce
pi (i=1,2,…n) jsou póly přenosové funkce
K=

•
•
•
•
•
•

Jsou-li póly dále od Im osy, je přechodný děj kratší (více. tlumen).
Póly komplexně sdružené – přechodový děj obsahuje kmitavou složku.
Pól v počátku – integrační charakter systému.
Póly v pravé polorovině – systém je nestabilní.
Nuly blíže k imaginární ose než póly, bude převládat derivační složka.
Nuly v počátku – derivační charakter systému.

Př: Znázorněte rozložení nul a pólů v komplexní rovině pro systém s přenosem
p + 0,5
F ( p) =
p( p 2 + 2 p + 5)
nuly: q = −0,5
1

póly: p = 0
2

p

2,3

= −1 ± 2j

4.4 Typové soustavy
Podle ustálených hodnot přechodové funkce.dělíme soustavy na:
– Statické
• Proporcionální
• Derivační
4

–

Astatické
• Integrační

Platí (věta o konečné hodnotě)

lim F(t) = lim pF(p)
t→∞ p→0

1
H (∞) = lim pH(p) = lim p ⋅ F ( p ) = lim F ( p )
p
p→0
p→0
p→0
Pro F ( p) =

lim F( p ) =

p→ 0

Pozn.:

bm p m + ..... + b1 p + b0
a n p n + ... + a1 p + a0

m≤n

b0
a0
0

pro b0 ≠ 0 ∧ a0 ≠ 0 → proporcionální

∝

pro b0 ≠ 0 ∧ a0 = 0 → integrační

pro b0 = 0 ∧ a0 ≠ 0 → derivační

derivační – alespoň jedna nula v počátku
integrační – alespoň jeden pól v počátku

5

