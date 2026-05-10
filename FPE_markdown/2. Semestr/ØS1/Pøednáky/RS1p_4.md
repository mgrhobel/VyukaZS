---
title: "RS1p_4.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/ØS1/Pøednáky/RS1p_4.pdf"
date: 2008-08-24
type: PDF (text-based)
---

Příklad:
Lineární dynamický systém je popsán přenosem:
F ( p) =

bo
a n p + a n −1 p n −1 + a1 p + a o
n

Odvoďte a) diferenciální rovnici
b) vnitřní popis
Řešení:
a)
Y ( p)
F ( p) =
U ( p)

(

)

Y ( p ) ⋅ a n p n + a n −1 p n −1 + a1 p + a o = boU ( p )
an y

(n )

(t ) + a n −1 y

( n −1)

(t ) + ... + a1 y ′(t ) + ao y(t ) = bo u (t )

b) Volme
•

y′ = x1 = x2
•

y′′ = x 2 = x3
.
.
.
y(

n −1)

•

= x n −1 = xn
•

y( n) = xn = −

ao
a
b
a
y − 1 y′ − ... − n −1 y ( n −1) + o u
an
an
an
an

Dosazením stavových proměnných za jednotlivé derivace výstupu má poslední rovnice tvar:
•

xn = −

ao
a
a
b
x1 − 1 x2 − ... − n −1 x n + o u
an
an
an
an

1

Vyjádříme maticově:
 •  0
 x1  
 •  0
 x2  
M  = L

 0
 x•  
 n −1   − ao
 •   an
 xn 

1
0
L
0
a
− 1
an

L
L
L
L

0

0 
  x1   
0
  x  0 
  2  M 
L
 ⋅ M  +   u
1
  x  0 
n −1 
b 
an−1  
L L −
  xn   o 
an 
 an 
0
1
L
L

 x1 


 x2 
y = (1 0 0 L 0 ) ⋅ M  + ( 0 ) u


 xn −1 
x 
 n 
Volbou stavových proměnných je určena struktura vnitřního popisu systému. Výše uvedená
struktura není jediná možná.
Vztah mezi přenosem a dynamickými rovnicemi systému.
•

x = Ax + Bu
y = Cx + Du
Aplikací L-transformace
pX ( p) − x(0) = AX ( p) + BU ( p)
Y ( p ) = CX ( p ) + DU ( p )

x(0) = 0

( pI − A) X ( p) = BU ( p)
X ( p ) = ( pI − A) −1 BU ( p)
Dosazením do výstupní rovnice
Y ( p ) = C ( pI − A)−1 B + D  U ( p )
F ( p) =

Y ( p)
= C ( pI − A) −1 B + D
U ( p)

Matice Φ( p ) = ( pI − A) −1 =

adj ( pI − A)
se nazývá matice přechodových funkcí
det( pI − A)

Adj(pI-A) je adjungovaná matice sestavená z algebraických doplňků příslušné transponované
matice.
Řešení dynamických rovnic systému
•

V některých kybernetických disciplínách potřebujeme odvodit vztah pro chování
výstupu systému v čase.
2

Dále uvedeme řešení dynamických rovnic lineárních t-invariantních dynamických systémů.
a) Autonomních systémů

u=0

•

x = Ax
y = Cx
Řešení stavové rovnice pomocí L-transformace:
pX ( p) − x(o) = AX ( p )
( pI − A) ⋅ X ( p) = x(o)
X ( p) = ( pI − A) −1 ⋅ x(o)

x(t ) = L−1 {( pI − A) −1} ⋅ x(o)
x(t ) = Φ(t ) ⋅ x(o) = e At ⋅ x(o) ⇒ y (t ) = Cx(t )
Jak vypočítat F(t) – L-1 {(pI-A)-1}
– eAt
Výpočet e At = I + At +

A2 2 A3 3
t + t + ...
2!
3!

b) Neautonomních systémů

u≠0

•

x = Ax + Bu
y = Cx + Du
Řešení stavové rovnice je dáno součtem řešení homogenní rovnice x′ = Ax ,
které má tvar x(t ) = Φ(t ) ⋅ x(o)
a řešení nehomogenní rovnice x′ = Ax + Bu , které představuje partikulární integrál
t

x p (t ) = ∫ Φ (t − τ ) ⋅ Bu (τ ) ⋅ dτ
0

Výsledné řešení stavové rovnice má tvar:
t

x(t ) = Φ(t ) ⋅ x(o) + ∫ Φ(t − τ ) ⋅ Bu (τ ) ⋅ dτ
0

3

