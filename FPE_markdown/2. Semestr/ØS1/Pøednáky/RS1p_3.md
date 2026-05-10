---
title: "RS1p_3.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/ØS1/Pøednáky/RS1p_3.pdf"
date: 2008-08-24
type: PDF (text-based)
---

2.3 Popis systému
Dynamické vlastnosti systému lze popsat:
a) vnější popis – vychází s relace vstup – výstup
b) vnitřní popis – vychází s relace vstup – stav – výstup
a) Vnější popis
Systém považujeme za „černou skříňku“, která má vstup a výstup. Obsah černé skříňky nás
nezajímá. Předpokládáme, že počáteční stav systému je nulový.
Vnější popis lineárního spojitého dynamického systému s jednou vstupní a jednou výstupní
veličinou může být představován např.
1) diferenciální rovnicí
2) přenosem
ad 1) Diferenciální rovnice
u (t)

y (t)
S

diferenciální rovnice:
a n y( n ) ( t ) + a n-1 y( n-1) ( t ) + K + a1 y′ ( t ) + a 0 y ( t ) = b 0 u ( t ) + b1u ′ ( t ) + K + b m-1u ( m-1) ( t ) + b m u ( m ) ( t )
Aby byl systém fyzikálně realizovatelný: m ≤ n, řád diferenciální rovnice n udává řád systému
Př. Odvoďte vnější popis ve tvaru diferenciální rovnice
Obvod RLC:

je-li vstupní veličinou napětí u(t) a výstupní veličinou i(t)
di ( t ) 1 t
d
Ri ( t ) + L
+ ∫ id (t ) = u ( t ) /
dt
c0
dt

1

L

d 2i ( t )
di ( t ) 1
du ( t )
+R
+ i (t ) =
2
dt
dt
c
dt

ad 2) Přenos

u (t)

y (t)
S

F ( p) =

L { y (t )} Y ( p )
=
L {u (t )} U ( p )

/ n. p . p .

L – transformací diferenciální rovnice dostaneme:

(a p + a p
n

n −1

n

F ( p) =

n −1

+ K + a1 p + a0 ) Y ( p ) = ( b0 + b1 p + K + bm −1 p m −1 + bm p m ) U ( p )

Y ( p ) bm pm + bm −1 p m −1 + K + b1 p + b0
=
U ( p ) an p n + an−1 p n −1 + K + a1 p + a0

Příklad:
Systém je popsán diferenciální rovnicí
6,9 y′′′ ( t ) + 8, 6 y′′ ( t ) + 1,5 yI ′ ( t ) + 0, 2 y ( t ) = 0, 4u ( t ) + 1, 6u ′ ( t )
při nulových počátečních podmínkách. Odvoďte přenos daného systému.
L – transformací rovnice:

( 6, 9 p3 + 8, 6 p 2 + 1,5 p + 0, 2 ) Y ( p ) = ( 0, 4 + 1, 6 p ) U ( p )
F ( p) =

Y ( p)
1, 6 p + 0, 4
=
3
U ( p ) 6,9 p + 8, 6 p 2 + 1,5 p + 0, 2

b) vnitřní popis
Pohyb systému lze obecně zobrazit v n-rozměrném metrickém prostoru → stavový prostor.
Souřadnicemi tohoto prostoru jsou stavové veličiny systému (vektor stavu).
Složky vektoru stavu určují polohu „zastupujícího bodu“ → trajektorie systému.
V případě lineárních dynamických systémů lze za stavový prostor považovat n-rozměrný
Eukleidovský prostor.
Vnitřní popis je charakterizován relací: vstup – stav – výstup

2

vektor vstupu: u ( t ) = u1 ( t ) , u2 ( t ) , K , ur ( t ) 
vektor stavu: x ( t ) =  x1 ( t ) , x2 ( t ) , K , xn ( t ) 

T

T

u1

y1

u2

y2

S

M
ur

M
yp

x1 , x2 , K, xn

vektor výstupu: y ( t ) =  y1 ( t ) , y2 ( t ) , K , y p ( t ) 

T

Stav je funkcí počátečního stavu x(t0 ) a průběhu vstupního vektoru
x ( t ) = f  x ( t0 ) , u ( t ) 

(A)

Podobně pro výstup platí
y ( t ) = g  x ( t0 ) , u ( t ) 

(B)

(A) stavová rovnice systému
(B) výstupní rovnice systému
(A) + (B) Dynamické rovnice systému
Dále se budeme zabývat systémy, jejichž dynamické chování lze popsat obyčejnou
diferenciální rovnicí n-tého řádu (nebo ekvivalentně n diferenciálními rovnicemi prvního
řádu).
Obecný zápis:
x = f ( x, n, t )
y = g ( x , n, t )
Pro lineární dynamické systémy:
•

x = A(t )x + B(t )u
y = C (t )x + D(t )u
Dále se omezíme na t-invariantní systémy (jejich vlastnosti se v čase nemění). A, B, C, D jsou
pak konstantní matice.

3

•

x = Ax + Bu
y = Cx + Du
Strukturní schéma:

A - matice (dynamiky) systému
B - vstupní matice
C - výstupní matice
D - matice přímého působení vstupu na výstup
Obvykle je :
D≡0
•

x = Ax + Bu
y = Cx
Poznámka:
výběr souřadnicového systému ve stavovém prostoru je zcela libovolný, na rozdíl od u a y,
které mají konkrétní fyzikální význam.

4

