---
title: "rS1uloha_3.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Státnice/new/INF/ØS1/Úkoly/rS1uloha_3.pdf"
date: 2008-08-24
type: PDF (text-based)
---

Dynamické vlastnosti dvouparametrového obvodu
Víceparametrovými obvody rozumíme takové, které mají více vstupních a více výstupních
veličin, přičemž obecně každá výstupní veličina je ovlivňována alespoň jednou vstupní
veličinou.
Příklad dvouparametrového obvodu:

a11
y1

Σ

x1

Σ

a12
a21

y2

Σ

x2

Σ

a22
Popis pomocí přenosových funkcí
Označme: F ( p) =

K
p(1 + Tp )

x1 = F ( y1 − a11 x1 ) − a21 Fx2
x2 = F ( y2 − a22 x2 ) − a12 Fx1
x1 = Fy1 − a11 Fx1 − a21 Fx2
x2 = Fy2 − a22 Fx2 − a12 Fx1
x1 + a11 Fx1 = Fy1 − a21 Fx2
x2 + a22 Fx2 = Fy2 − a12 Fx1

(A)
(B)

Fy1 − a21 Fx2
1 + a11 F
Fy − a Fx
x2 = 2 12 1
1 + a22 F
x1 =

(C)
(D)

Dosazením D do A a C do B:
Fy − a Fx
x1 + a11 Fx1 = Fy1 − a21 F + 2 12 1
1 + a22 F
Fy − a Fx
x2 + a22 Fx2 = Fy2 − a12 F + 1 21 2
1 + a11 F
x1 (1 + a11 F )(1 + a22 F ) = Fy1 (1 + a22 F ) − a21 F 2 y2 + a12 a21 F 2 x1
x2 (1 + a22 F )(1 + a11 F ) = Fy2 (1 + a11 F ) − a12 F 2 y1 + a12 a21 F 2 x2
x1 (1 + a11 F )(1 + a22 F ) − a12 a21 F 2 x1 = F (1 + a22 F ) y1 − a21 F 2 y2
x2 (1 + a22 F )(1 + a11 F ) − a12 a21 F 2 x2 = F (1 + a11 F ) y2 − a12 F 2 y1
x1 =

(1 + a22 F ) Fy1 − a21 F 2 y2
(1 + a11 F )(1 + a22 F ) − a12 a21 F 2

x2 =

(1 + a11 F ) Fy2 − a12 F 2 y1
(1 + a11 F )(1 + a22 F ) − a12 a21 F 2

Odvodíme čtyři přenosové funkce:
X ( p)
(1 + a22 F ) F
F11 ( p) = 1
=
Y1 ( p) (1 + a11 F )(1 + a22 F ) − a12 a21 F 2
X 1 ( p)
− a21F 2
=
Y2 ( p ) (1 + a11 F )(1 + a22 F ) − a12 a21 F 2
X ( p)
(1 + a11 F ) F
F22 ( p) = 2
=
Y2 ( p ) (1 + a11 F )(1 + a22 F ) − a12 a21F 2

F21 ( p ) =

F12 ( p ) =

X 2 ( p)
− a12 F 2
=
Y1 ( p) (1 + a11 F )(1 + a22 F ) − a12 a21 F 2

y2 = 0
y1 = 0
y1 = 0
y2 = 0

Zadání
Simulujte zpožďující člen dvouparametrový obvod. Volte K = 1; T0 = 0,2[s]; a11=0,87;
a12=-5; a21=0,5; a22=0,1
Změřte 3 přechodové charakteristiky
y2 = 0
1. y1 = 1(t )
2. y1 = 0
y2 = 1(t )
3. y1 = 1(t )
y2 = 1(t )

Referát musí obsahovat:
•

Zadání
2

•
•
•

Teorie (výpočet přenosových funkcí dvouparametrového obvodu).
Schéma pro SIPRO (Multisim).
Tři naměřené přechodové charakteristiky.

3

