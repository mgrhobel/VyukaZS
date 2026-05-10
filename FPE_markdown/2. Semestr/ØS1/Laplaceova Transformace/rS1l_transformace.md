---
title: "rS1l_transformace.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/ØS1/Laplaceova Transformace/rS1l_transformace.pdf"
date: 2009-02-22
type: PDF (text-based)
---

Laplaceova transformace - studijní text pro cvičení v předmětu
„Matematika - 2.ÿ
Studijní materiál byl připraven pracovníky katedry E. Novákovou, M. Hyánkovou a L. Průchou za podpory grantu IG ČVUT č. 300012423 a v rámci rozvojového projektu MŠMT.

Obsah
1. Definice a základní vzorce
2. Zpětná Laplaceova transformace, předmět k racionální funkci
3. Laplaceova transformace impulsu
4. Zpětná transformace obrazu impulsu
5. Obraz periodické funkce
6. Řešení lineárních diferenciálních rovnic

Laplaceova transformace.
1. Definice a základní vzorce
Při řešení lineárních diferenciálních rovnic a jejich soustav s konstantními koeficienty můžeme
použít integrální transformace, které nahrazují operace derivování a integrování násobením či
dělením a vlastní řešení diferenciální rovnice je převedeno na řešení soustavy lineárních rovnic.
Jedna z nejčastěji používaných integrálních transformací je tzv. Laplaceova transformace.
Připomeneme nejprve definici a základní vlastnosti Laplaceovy trasformace, které při řešení
diferenciálních rovnic a jejich soustav používáme.
Definice Laplaceovy transformace. Je-li funkce f : h0, ∞) → R, pak její Laplaceovou
transformací rozumíme funkci F (p), která je definována vztahem
Z ∞
F (p) =
f (t)e−pt dt,
0

kde p je komplexní číslo. O funkci f (t) mluvíme jako o předmětu, funkci F (p) nazýváme
obrazem. Přiřazení f (t) → F (p) nazýváme přímou Laplaceovou transformací a budeme ji značit
symbolem L {f (t)} = F (p). Inverzní transformaci F (p) → f (t) nazýváme zpětnou Laplaceovou
trasformací a budeme ji označovat symbolem f (t) = L −1 {F (p)}. Vztah mezi předmětem a
obrazem budeme někdy stručněji zapisovat pomocí symbolu f (t) , F (p) či F (p) , f (t).
Poznamenejme, že proměnná p je sice komplexní, ale při výpočtu běžných obrazů počítáme
podle stejných pravidel jaká jsme používali při integrování a derivování reálných funkcí reálné
proměnné. Při počítání obrazů můžeme předpokládat, že p je reálná kladná proměnná.
Uvedeme základní vlastnosti přímé a zpětné Laplaceovy transformace, které využíváme při
řešení diferenciálních rovnic.

Přehled základních vzorců:
Linearita transformací.

L{

n
X
i=1

ai fi (t)} =

n
X

ai L {fi (t)},

i=1

L −1 {

n
X

ai Fi (p)} =

i=1

n
X

ai L −1 {Fi (p)}.

i=1

Základní vztahy transformace.
Označme L {f (t)} = F (p).
Předmět
f (t)
f (t)eat
f (at)
f 0 (t)
f 00 (t)
f (n) (t)
tf (t)
tn f (t)
1
f (t)
Rt t
0 f (z)dz

Obraz
F (p)
F (p −a)
p
1
aF a
pF (p) − f (0+)
p2 F (p) − pf (0+) − f 0 (0+)
pn F (p) − [pn−1 f (0+) + pn−2 f 0 (0+) + . . . + f (n−1) (0+)]
−F 0 (p)
n (n)
(−1)
R ∞ F (p)
p F (q)dq
1
p F (p)

Obraz konvoluce.
Konvolucí funkcí f (t) a g(t) nazýváme funkci
Z t
Z t
(f ∗ g)(t) = (g ∗ f )(t) =
f (t − u)g(u) du =
f (u)g(t − u) du
0

0

a označíme-li L {f (t)} = F (p) a L {g(t)} = G(p), pak
L {(f ∗ g)(t)} = L {(g ∗ f )(t)} = F (p)G(p).

Tabulka některých obrazů.
Předmět
1
t
t2
n
t , n∈N
eat
teat
t2 eat
tn eat , n ∈ N

Obraz
1
p
1
p2
2
p3
n!
pn+1
1
p−a
1
(p−a)2
2
(p−a)3
n!
(p−a)n+1

Předmět
sin ωt
cos (ωt)
sinh ωt
cosh ωt
t sin ωt
t cos ωt
eat sin (ωt)
eat cos (ωt)

Obraz
ω
p2 +ω 2
p
p2 +ω 2
ω
p2 −ω 2
p
p2 −ω 2
2pω
(p2 +ω 2 )2
p2 −ω 2
(p2 +ω 2 )2
ω
(p−a)2 +ω 2
ω
(p−a)2 +ω 2

Řešené úlohy na přímou Laplaceovu transformaci.
Pomocí základních vztahů transformace a s využitím uvedených obrazů některých funkcí
určete obraz F (p) k předmětu f (t).

1. f (t) = 2 + 3te−2t − 4t2 e−3t
3
4.2
F (p) = p2 + (p+2)
2 − (p+3)3

Použijeme linearitu, vztah eat f (t) , F (p − a), a = −2, a = −3 a vzorce 1 , p1 ,
t , p12 , t2 , p23 .
2. f (t) = 3 sin 2t − 5 cos 2t
5p
6−5p
F (p) = p3.2
2 +4 − p2 +4 = p2 +4

Použijeme linearitu a vzorce sin 2t , p22+4 , cos 2t , p2p+4 .
3. f (t) = 3t − sin 2t
F (p) = p32 − p22+4
Použijeme linearitu transformace a vzorce t , p12 , sin 2t , p22+4 .
4. f (t) = t2 − 1 + 3e−t + cos 2t
3
F (p) = p23 − p1 + p+1
+ p2p+4
n!
1
, e−2t , p+2
Použijeme linearitu a vzorce tn , pn+1
, cos 2t , p2p+4 .

5. f (t) = 4et + 2e−3t + sin 2t
4
2
F (p) = p−1
+ p+3
+ p22+4

Použijeme linearitu, vztah eat f (t) , F (p − a), a = 1, a = −3 a vzorce 1 , p1 ,
sin 2t , p22+4 .
6. f (t) = (2t + 5)e−2t + 3 cos t − 2 sin 3t
3p
2
5
6
F (p) = (p+2)
2 + p+2 + p2 +1 − p2 +9

Použijeme linearitu, vztah e−2t f (t) , F (p + 2) a vzorce 1 , p1 , t , p12 , cos t , p2p+1 ,
sin 3t , p23+9 .
7. f (t) = t(sin 2t + 4 cos 2t)

0
2
F (p) = − p22+4 + p24p+4 = 4p(p+4p−16
2 +4)2
Použijeme linearitu, vztah tf (t) , −F 0 (p) a vzorce sin 2t , p22+4 , cos 2t , p2p+4 .
8. f (t) = (t + 2) cos 3t

0
2 −9
2p
2p3 +p2 +18p−9
F (p) = − p2p+9 + p22p+9 = (pp2 +9)
2 + p2 +9 =
(p2 +9)2
Použijeme linearitu, vztah tf (t) , −F 0 (p) a vzorec cos 3t , p2p+9 .
9. f (t) = (3t2 + 2t − 1)e−t + (t + 1) sin 2t

0
4p
6
2
2
1
6
2
1
2
F (p) = (p+1)
+ p22+4 = (p+1)
3 + (p+1)2 − p+1 −
2
3 + (p+1)2 − p+1 + (p2 +4)2 + p2 +4
p +4
Použijeme linearitu, vztahy e−t f (t) , F (p + 1), tf (t) , −F 0 (p) a vzorce 1 , p1 ,
t , p12 , t2 , p23 , sin 2t , p22+4 .
10. f (t) = te−3t + (t − 5) cos 3t

0
p2 −9
5p
p
1
1
F (p) = (p+3)
−
− p25p+9 = (p+3)
2
2 + (p2 +9)2 − p2 +9
p2 +9

Použijeme linearitu, vztahy e−3t f (t) , F (p + 3), tf (t) , −F 0 (p) a vzorce t , p12 ,
cos 3t , p2p+9 .
11. f (t) = 3 sin 3t cos t
Je f (t) = 23 (sin 4t + sin 2t), tedy


4
6
+ p22+4 = p2 +16
+ p23+4
F (p) = 32 p2 +16
4
Použijeme linearitu a vzorce sin 4t , p2 +16
, sin 2t , p22+4 .

12. f (t) = 2e−3t cos 5t
2(p+3)
2p+6
F (p) = (p+3)
2 +25 = p2 +6p+34
p
Použijeme vztah e−3t f (t) , F (p + 3) a vzorec cos 5t , p2 +25
.

13. f (t) = e−2t (3 cos 3t − 4 sin 3t)
3(p+2)
3p−6
4.3
F (p) = (p+2)
2 +9 − (p+2)2 +9 = p2 +4p+13

Použijeme linearitu, vztah e−2t f (t) , F (p + 2) a vzorce cos 3t , p2p+9 , sin 3t , p23+9 .
14. f (t) = te−3t − 2e−2t sin 3t + 4
6
4
1
F (p) = (p+3)
2 − (p+2)2 +9 + p .

Použijeme linearitu, vzorce t , p12 , sin 3t , p23+9 , 1 , p1 a vztah f (t)e−at , F (p − a),
a = −2, a = −3.
15. f (t) = t sin 4t + (3te−2t )0
8p
3p
4
3
−2t ) =
F (p) = −( p2 +16
)0 + p (p+2)
+ (p+2)
2 − lim (3te
2
(p2 +16)2
t→0+

Použijeme linearitu, vztahy tf (t) , −F 0 (p), f 0 (t) , (pF (p) − f (0+)) a vzorce
4
1
sin 4t , p2 +16
, te−2t , (p+2)
2.
Rt
16. f (t) = e−3t (1 − 2 sin 3t) + 0 e3u cos 3udu
p−3
1
6
1
F (p) = p+3
− (p+3)
2 +9 + p (p−3)2 +9

Použijeme linearitu, vztahy f (t)eat , F (p − a), a = 3, a = −3 a
vzorce 1 , p1 , sin 3t , p23+9 , cos 3t , p2p+9 .

Rt

1
0 f (u)du , p F (p)

17. f (t) = tsinh 2t − 2 cos2 3t + 5
Je f (t) = tsinh 2t − 1 − cos 6t + 5, tedy F (p) = −



2
p2 −4

0

p
+ −1+5
− p2 +36
=
p

4p
p
+ p4 − p2 +36
.
(p2 −4)2

Použijeme linearitu, vztah tf (t) , −F 0 (p) a vzorce
sinh 2t , p22−4 , 1 , p1 a cos 3t , p2p+9 .
18. f (t) = 4t sin t cos t + (2e2t cosh 2 t − 4)0
Je 2 sin t cos t = sin 2t a 2cosh 2 t = 1 + cosh 2t, tudíž
f (t) = 2t sin 2t + (e2t + e2t cosh 2t − 4)0 .

0
2(p−2)
1
4
2t + e2t cosh 2t − 4) =
Odtud plyne F (p) = −2 p22+4 + p( p−2
+ (p−2)
2 −4 − p ) − lim (e
t→0+

a

8p
p
+ p−2
+ 2(p−2)
p−4 − 2.
(p2 +4)2

Použijeme linearitu, vztahy tf (t) , −F 0 (p), f 0 (t) , pF (p) − f (0+), e2t f (t) , F (p − 2)
a vzorce sin 2t , p22+4 , cosh 2t , p2p−4 , 1 , p1 .
19. f (t) = e−3t cos (2t + π2 ) + sin 3(t − π)
Je cos (2t + π2 ) = cos 2t cos π2 − sin 2t sin π2 = − sin 2t
a sin 3(t − π) = sin 3t cos 3π + cos 3t sin 3π = − sin 3t.
−2
3
Je f (t) = −e−3t sin 2t − sin 3t tedy F (p) = (p+3)
2 +4 − p2 +9 .

Použijeme linearitu, vztah e−3t f (t) , F (p + 3) a vzorce
ω
sin ωt , p2 +ω
2 , ω = 3, ω = 2.

20. f (t) = 5.2−t − 4t3t
5
4
Je f (t) = 5e−t ln 2 − 4tet ln 3 , tudíž F (p) = p+ln
2 − (p−ln 3)2 .

Použijeme linearitu, vztah eat f (t) , F (p−a), a = − ln 2, a = ln 3 a vzorce 1 , p1 , t , p12 .
21. f (t) =
Je

Rt

u
t
0
0 (2 + 4e sinh 3u)du − (3 − tsinh 5t)

F (p) = p1



2
4.3
p + (p−1)2 −9




−p

1
p−ln 3 +



5
p2 −25

0 

− lim (3t − tsinh 5t) =
t→0+

p
10p2
2
12
+ p(p2 −2p−8)
− p−ln
3 − (p2 −25)2 − 1.
p2

Rt
Použijeme linearitu, vztahy 0 f (u)du , p1 F (p), eat f (t) , F (p − a), a = 1, a = ln 3,
ω
f 0 (t) , pF (p) − f (0+), tf (t) , −F 0 (p) a vzorce 1 , p1 , sinh ωt , p2 −ω
2 , ω = 3, ω = 5.
22. f (t) = 6 sin t sinh 3t − 4t3 − 2 cos t cosh t
Je f (t) = 3 sin t(e3t − e−3t ) − 4t3 − cos t(et + e−t ), tedy
p−1
p+1
3
3
3!
F (p) = (p−3)
2 +1 + (p+3)2 +1 − 4 p4 − (p−1)2 +1 − (p+1)2 +1 =
p−1
p+1
3
3
+ p2 +6p+10
− 24
− p2 −2p+2
− p2 +2p+2
.
p2 −6p+10
p4

Použijeme linearitu, vztah eat f (t) , F (p − a), a = 3, a = −3, a − 1, a = −1 a vzorce
t3 , p3!4 , sin t , p21+1 , cos t , p2p+1 .
Rt
23. f (t) = (et sinh t + t3 e2t − 6)0 + 3 0 (u4 − u cos 2u) du

h
i

0 
p
1
3 4!
3!
6
t
3
2t
Je F (p) = p (p−1)2 −1 + (p−2)4 − p − lim (e sinh t + t e − 6) + p p5 + p2 +4
=
t→0+
3(4−p2 )
p
6p
6p
72
3 p2 +4−2p2
1
72
+ (p−2)4 − 6 + 6 + p6 + p p2 +4 = p−2
+ (p−2)
4 + p6 + p(p2 +4) .
p2 −2p

Rt
Použijeme linearitu, vztahy f 0 (t) , (pF (p)−f (0+)), 0 f (u)du , p1 F (p), tf (t) , −F 0 (p),
eat f (t) , F (p − a), a = 1, a = 2 a vzorce t3 , p64 , t4 , p4!5 , sinh t , p21−1 , cos 2t , p2p+4 .
Rt
24. f (t) = 3 − 4 0 sinh (t − u) cos udu


4p
F (p) = p3 − 4 p21−1 p2p+1 = p3 − (p2 −1)(p
2 +1)
Použijeme linearitu, větu o obrazu konvoluce (f ∗ g)(t) , F (p)G(p) a vzorce
1 , p1 , sinh t , p21−1 , cos t , p2p+1 .

25. f (t) =

Rt

0 e

u−t (t − u) sin 3u du

Rt

−(t−u) (t − u) sin 3u du = te−t ∗ sin 3t a tedy
0 e
1
3
F (p) = (p+1)
2 p2 +9 ,

Je f (t) =

když použijeme vztah pro obraz konvoluce na funkce te−t a sin 3t a vzorce
1
3
te−t , (p+1)
2 , sin 3t , p2 +9 .
Neřešené úlohy na přímou Laplaceovu transformaci.
K dané funkci f (t) nalezněte obraz F (p).

1.
2.
3.
4.
5.
6.
7.
8.

f (t)
f (t) = 3t2 − 5t + 1
f (t) = 2et − 3e−2t + 5e−t
f (t) = te−2t + t2 e−3t
f (t) = 6te−2t + 2e−t + t3 e−4t
f (t) = 2 sin t − 3 cos t
f (t) = 3 sin 2t + 4 cos 2t
f (t) = 8t2 e−2t + 3 sin t
f (t) = t sin 2t

F (p)
[F (p) = p63 − p52 + p1 ]
3
5
[F (p) = p−2 1 − p+2
+ p+1
]
1
2
[F (p) = (p+2)2 + (p+3)3 ]
6
2
6
[F (p) = (p+2)
2 + (p+1) + (p+4)4 ]
[F (p) = 2−3p
]
p2 +1
[F (p) = 6+4p
]
p2 +4
16
[F (p) = (p+2)3 + p23+1 ]
[F (p) = (p24p
]
+4)2

9.
10.
11.
12.

f (t) = t cos 5t
f (t) = e−3t sin 2t
f (t) = e−2t cos 2t
f (t) = (3t − 1)e−2t

−25
[F (p) = (pp2 +25)
2]
2
[F (p) = p2 +6p+13 ]
p+2
]
[F (p) = p2 +4p+8
1−p
[F (p) = (p+2)2 ]

13.

f (t) = (3 + 2t) cos t

+3p−2
[F (p) = 3p +2p
]
(p2 +1)2

14.

f (t) = (1 − t) sin 5t

[F (p) = 5p(p−10p+125
]
2 +25)2

15.

f (t) = te3t sin 2t

[F (p) = (p2 4(p−3)
]
−6p+13)2

16.

f (t) = (2t − 3)e−2t cos 4t

−76p−144
]
[F (p) = −3p (p−16p
2 +4p+20)2

17.

f (t) = (1 − 2t)e3t sin t

[F (p) = (pp2 −10p+22
]
−6p+10)2

18.

f (t) = t2 sin 2t

−16
[F (p) = 12p
]
(p2 +4)3

19.

f (t) = t2 cos 3t

−54p
[F (p) = 2p
]
(p2 +9)3

20.

25.

−6p+5
[F (p) = p(p272+36) + (pp2 −6p+13)
2]


5−p
5+p
f (t) = sin 3t cosh 2t − cos 3t sinh 2t
[F (p) = 21 p2 −4p+13
+ p2 +4p+13
]


p+3
p+3
f (t) = 2 + e−3t cos t cos 3t
[F (p) = p2 + 12 p2 +6p+25
+ p2 +6p+13
]


2p
1
24
f (t) = (e−t sinh t + t4 e2t − 2cosh 3t)0
[F (p) = p p2 +2p
+ (p−2)
+ 2]
5 − p2 −9


1
1
1
4
f (t) = (3t − 2 sin t sinh 2t + 4)0
[F (p) = p p−ln
−
+
+
− 7]
2
2
3
p
p −4p+5
p +4p+5


Rt
2)
3(36−p
f (t) = 0 (4 − 6u cos2 3u + 8 sin 2u cos 2u)du [F (p) = p1 p4 − p32 + (p2 +36)2 + p216
]
+16

26.
27.

f (t) = 4e−t + 3e−3t + 5 sin 2t
f (t) = (1 + 3t)e−2t + 4 cos 2t − 2 sin 2t

28.

f (t) = sin 2t sin 3t

29.

f (t) = tat , a > 0

30.

f (t) = 3 cos2 2t

21.
22.
23.
24.

f (t) = 4 sin2 3t + te3t cos 2t

2

3

2

2

3

2

2

2

3

2

2
4
[F (p) = p+1
+ p+3
+ p210+4 ]
3
[F (p) = (p+2)
+ 1 + 4p − 4 ]
 2 p+2 p2 +4 p2 +4
p
[F (p) = 21 p2p+1 − p2 +25
]
1
[F (p) = (p−ln
, at = et ln a ]
 a)2

p
[F (p) = 23 p1 + p2 +16
]

2

31.

+13)
f (t) = 4 cos 2t cos 3t [F (p) = (p24p(p
]
+1)(p2 +25)

32.
33.
34.

f (t) = 6 sin 3t cos t
f (t) = 5 sin 4t sin t
f (t) = 4e−2t sin2 3t

+8)
[F (p) = (p218(p
]
+16)(p2 +4)
40p
[F (p) = (p2 +9)(p2 +25) ]
[F (p) = (p+2)(p72
2 +4p+40) ]

35.

f (t) = 3e−t cos2 2t

3(2p +3p+17)
[F (p) = 2(p+1)(p
2 +2p+17) ]

2

2

2. Zpětná Laplaceova transformace, předmět k racionální funkci.
Hledáme funkci f (t), pro kterou je F (p) , f (t), (tedy L {f (t)} = F (p)) a F (p) je
racionální funkce. Poznamenejme, že z vlastností Laplaceovy transformace vyplývá, že ve funkci
F (p) je stupeň čitatele alespoň o jednu menší než stupeň jmenovatale.
Popis algoritmu.
Funkci F (p) rozložíme na součet parciálních zlomků a k jednotlivým sčítancům najdeme
předměty pomocí vztahů a vzorců, které jsme uvedli v prvním odstavci. Zde se omezíme na
nejjednodušší případy. Budeme uvažovat, že jmenovatel funkce F (p) má komplexní kořeny
násobnosti nejvýše 2. Pro reálné kořeny není třeba nějaké omezení uvažovat.
V rozkladu racionální funkce dostaneme jako jeho členy zlomky těchto tvarů:
A
pro reálný jednoduchý kořen p = a.
p−a
A
pro dvojnásobný reálný kořen p = a.
(p−a)2
A
pro reálný kořen p = a násobnosti n, n ≥ 1.
(p−a)n
Ap+B
pro ryze imaginarní dvojici jednoduchých kořenů p = ±jω.
p2 +ω 2
Ap+B
pro dvojici jednoduchých komplexních kořenů p = a ± jω, a 6= 0.
(p−a)2 +ω 2
Ap+B
pro ryze imaginarní dvojici dvojnásobných kořenů p = ±jω.
[p2 +ω 2 ]2
Ap+B
pro dvojici dvojnásobných komplexních kořenů p = a ± jω, a 6= 0.
[(p−a)2 +ω 2 ]2

Uvedeme základní vzorce, které budeme při výpočtu předmětu používat.
Přehled vzorců
Je a ∈ R, b > 0 a ω > 0.
F (p)
1.
2.
3.
4.
5.
6.
7.
8.
9.
10.
11.
12.
13.
14.

1
p−a
1
(p−a)2
1
(p−a)3
1
(p−a)n , n ∈ N
1
p2 +ω 2
p
p2 +ω 2
1
(p−a)2 +ω 2
p
(p−a)2 +ω 2
1
(p2 +ω 2 )2
p
(p2 +ω 2 )2
1
[(p−a)2 +ω 2 ]2
p
[(p−a)2 +ω 2 ]2
1
p2 −b2
p
p2 −b2

f (t)
eat
teat
1 2 at
2t e
1
n−1 eat
(n−1)! t
1
ω sin ωt
cos ωt
1 at
ω e sin ωt
eat (cos ωt + ωa sin ωt)
1
(sin ωt − ωt cos ωt)
2ω 3
1
2ω t sin ωt
1 at
e (sin ωt − ωt cos ωt)
2ω 3
1 at 2
e (ω t sin ωt + a sin ωt − aωt cos ωt)
2ω 3
1
b sinh bt
cosh bt

Řešené úlohy na zpětnou Laplaceovu transformaci.
Určete předmět f (t) k funkci F (p).
1. F (p) = p22p+3
+4p+3
Rovnice p2 + 4p + 3 = 0 má dva reálné kořeny p1 = −3 a p2 = −1. Je tedy
A
B
= p+3
+ p+1
.
F (p) = p22p+3
+4p+3

Rovnici vynásobíme jmenovatelem a pro neurčité koeficienty A a B dostaneme rovnici
2p + 3 = A(p + 1) + B(p + 3).
Dosadíme hodnoty kořenů p1 = −3 a p2 = −1 a dostaneme:
p = −3 :

−3 = −2A ⇒ A = 32 ;

p = −1 :

1 = 2B ⇒ B = 12 .

1
1
Je tedy F (p) = 23 p+3
+ 12 p+1
, a tudíž

f (t) = 32 e−3t + 21 e−t , t ≥ 0.
Použijeme linearitu zpětné transformace a vztah

1
at
p−a , e

pro a = −1 a a = −3.

2

+2p−4
2. F (p) = p3p
3 +7p2 +10p

Rovnice p3 + 7p2 + 10p = 0 má kořeny p1 = 0, p2 = −2 a p3 = −5 a tudíž je
2

3p +2p−4
B
C
F (p) = p(p+2)(p+5)
= Ap + p+2
+ p+5

Rovnici vynásobíme jmenovatelem a pro neurčité koeficienty dostaneme rovnici:
3p2 + 2p − 4 = A(p + 2)(p + 5) + Bp(p + 5) + Cp(p + 2).
Do rovnice postupně dosadíme hodnoty kořenů jmenovatele a dostaneme:
−4 = 7A ⇒ A = − 47 ;

p=0:
p = −2 :

4 = −6B ⇒ B = − 23 ;

p = −5 :

61 = 15C ⇒ C = 61
15 .

Je tedy
1
1
F (p) = − 47 p1 − 23 p+2
+ 61
15 p+5 a tudíž je
−5t , t ≥ 0.
f (t) = − 47 − 23 e−2t + 61
15 e
1
Použijeme linearitu zpětné transformace a vztah p−a
, eat pro a = 0, a = −2 a a = −5.
2

3p +5
3. F (p) = (p+1)(p+3)
2

Jmenovatel má jednoduchý kořen p = −1 a dvojnásobný kořen p = −3. Pro funkci F (p)
dostaneme rozklad ve tvaru
3p2 +5
B
A
C
= p+1
+ (p+3)
2 + p+3
(p+1)(p+3)2

Po vynásobení jmenovatelem dostaneme pro neurčité koeficienty rovnici
(♣)

3p2 + 5 = A(p + 3)2 + B(p + 1) + C(p + 1)(p + 3).

Dosadíme hodnoty kořenů jmenovatele a dostaneme:
p = −1 :

8 = 4A ⇒ A = 2;

p = −3 :

32 = −2B ⇒ B = −16.

Hodnotu C určíme dosazením některé jiné hodnoty do rovnice (♣) a nebo porovnáním
koeficientů u některé mocniny proměnné p. Připomeňme, že volíme nejvyšší nebo nejnižší mocniny. Ty obvykle mají jednodušší vyjádření. Zvolíme mocninu p2 a dostaneme
podmínku:

p2 :

3 = A + C ⇒ C = 3 − A = 3 − 2 = 1.

2
16
1
Je tedy F (p) = p+1
− (p+3)
2 + p+3 a tudíž

f (t) = 2e−t + e−3t (1 − 16t), t ≥ 0.
1
at
p−a , e

Použijeme linearitu zpětné transformace a vztahy
1
, te−3t .
(p+3)2

pro a = −1, a = −3 a

4. F (p) = p4p+7
2 +16
Je
4p+7
p
4
= 4 p2 +16
+ 74 p2 +16
p2 +16

a tudíž
f (t) = 4 cos 4t + 74 sin 4t, t ≥ 0.
Použijeme linearitu zpětné transformace a vztahy

4
, sin 4t
p2 +16

p
, cos 4t.
p2 +16

2p−7
5. F (p) = (p+6)(p
2 +4)

Pro funkci F (p) dostaneme rozklad na zlomky ve tvaru
2p−7
A
= p+6
+ Bp+C
.
(p+6)(p2 +4)
p2 +4

Po vynásobnení jmenovatelem získáme pro neurčité koeficienty rovnici
(♠)

2p − 7 = A(p2 + 4) + (Bp + C)(p + 6).

Po dosazení hodnoty p = −6 do rovnice (♠) dostaneme
p = −6 :

−19 = 40A ⇒ A = − 19
40 .

Zbývající koeficienty určíme opět porovnáním vhodné mocniny proměnné p v rovnici (♠).
Postupně získáme:
p2 :

19
0 = A + B ⇒ B = −A = 40
;

p0 :


51
−7 = 4A + 6C ⇒ C = 16 −7 + 19
10 = − 60 .

Je tedy
19 1
19 p
2
51
F (p) = − 40
p+6 + 40 p2 +4 − 120 p2 +4

a tudíž
−6t + 19 cos 2t − 51 sin 2t, t ≥ 0.
f (t) = − 19
40 e
40
120

Použijeme linearitu zpětné transformace a vztahy

1
−6t a
p+6 , e

2
, sin 2t,
p2 +4

p
, cos 2t.
p2 +4
4p+5
6. F (p) = p2 +4p+13

Rovnice p2 + 4p + 13 = 0 má komplexní kořeny. Lze tedy jmenovatele upravit na tvar
p2 + 4p + 13 = p2 + 4p + 4 + 9 = (p + 2)2 + 9
a tedy
4(p+2)
4p+5
5−8
= (p+2)
2 +9 + (p+2)2 +9 .
p2 +4p+13

Odtud plyne, že f (t) = e−2t (4 cos 3t − sin 3t), t ≥ 0.
Použijeme linearitu zpětné transformace a vztahy F (p + 2) , f (t)e−2t a
p
, cos 3t.
p2 +9

3
, sin 3t
p2 +9

p+2
7. F (p) = (p+1)
4

Je
p+2
1
1
= (p+1)+1
= (p+1)
3 + (p+1)4 ,
(p+1)4
(p+1)4

tedy
1
2!
3!
F (p) = 12 (p+1)
3 + 6 (p+1)4 .

Odtud plyne, že
f (t) = 13 t2 e−t + 16 t3 e−t , t ≥ 0.
Použijeme linearitu zpětné transformace, vztah F (p + 1) , f (t)e−t a vzorce

2
, t2
p3

a

6
, t3 .
p4
3

p
8. F (p) = (p+2)2 (p+1)(p+3)

Nejprve rozložíme funkci F (p) na součet parciálních zlomků. Příslušný rozklad má tvar
p3
A
B
C
D
= (p+2)
2 + p+2 + p+1 + p+3 .
(p+2)2 (p+1)(p+3)

Po vynásobení rovnosti jmenovatelem dostaneme pro neurčité koeficienty rovnici
(♣) p3 = A(p + 1)(p + 3) + B(p + 2)(p + 1)(p + 3) + C(p + 2)2 (p + 3) + D(p + 2)2 (p + 1).
Dosadíme do této rovnice hodnoty kořenů jmenovatele a dostaneme:
p = −2 :

−8 = −A ⇒ A = 8;

p = −1 :

−1 = 2C ⇒ C = − 21 ;

p = −3 :

−27 = −2D ⇒ D = 27
2 .

Jestliže dosadíme do rovnice (♣) hodnotu p = 0, získáme podmínku pro poslední z
koeficientů. Je
0 = 3A + 6B + 12C + 4D ⇒ B = − 16 (24 − 6 + 54) = −12.
Je
8
12
1 1
27 1
F (p) = (p+2)
3 − p+2 − 2 p+1 + 2 p+3 ,

tudíž
−3t , t ≥ 0.
f (t) = 8te−2t − 12e−2t − 21 e−t + 27
2 e

Použijeme linearitu zpětné transformace, vztah F (p − a) , f (t)eat , a = −2,
a = −1, a = −3 a vzorce p12 , t a p1 , 1.
1
9. F (p) = p(p+2)
2

Danou funkci rozložíme na parciální zlomky. Rozklad má tvar
B
1
C
= Ap + (p+2)
2 + p+2
p(p+2)2

a po vynásobení jmenovatelem dpstaneme pro neurčité koeficienty rovnici
(♠)

1 = A(p + 2)2 + Bp + Cp(p + 2).

Do této rovnice dosadíme hodnoty kořenů jmenovatele a postupně dostaneme:
p = 0;
p = −2;

1 = 4A ⇒ A = 14 ;
1 = −2B ⇒ B = − 12 .

Dosadíme-li do rovnice (♠) některou jinou hodnotu, např. p = 1, dostaneme vztah
1 = 9A + B + 3C ⇒ C = 31 (1 − 9A − B) = 13 (1 − 94 + 12 ) = − 14 .
1
1 1
Je tedy F (p) = 14 p1 − 12 (p+2)
2 − 4 p+2 ,

tudíž
f (t) = 14 − 12 te−2t − 14 e−2t , t ≥ 0.
Použijeme linearitu zpětné transformace, vztah F (p + 2) , e−2t f (t) a vzorce
1
, t.
p2
Rt
Úlohu můžeme řešit také jinak, jestliže použijeme vztah p1 F (p) , 0 f (u)du.

1
p , 1,

1
−2t a tedy
Je (p+2)
2 , te

t
R t −2u
1
1
du = − 12 ue−2u − 14 e−2u 0 = − 12 te−2t − 14 e−2t + 41 , t ≥ 0.
p (p+2)2 , 0 ue
2

p
10. F (p) = (p−2)
3

Danou funkci nejprve vyjádříme jako součet parciálních zlomků. Zde můžeme rozklad
získat jednoduchou úpravou. Je
2
2 +4(p−2)+4
p2
1
4
4
= (p −4p+4)+4p−4
= (p−2)(p−2)
= p−2
+ (p−2)
3
2 + (p−2)3 ,
(p−2)3
(p−2)3

tudíž
f (t) = e2t (1 + 4t + 2t2 ), t ≥ 0.
Použijeme linearitu zpětné transformace, vztah F (p − 2) , e2t f (t) a vzorce
1
, t, p23 , t2 .
p2

1
p , 1,

p−5
11. F (p) = p2 +2p+10

Polynom ve jmenovateli nemá reálné kořeny a proto danou funkci upravíme takto:
(p+1)−6
p−5
p−5
p+1
3
= (p2 +2p+1)+9
= (p+1)
2 +9 = (p+1)2 +9 − 2 (p+1)2 +9 .
p2 +2p+10

Je pak
f (t) = e−t (cos 3t − 2 sin 3t), t ≥ 0,
jestliže použijeme vztah F (p + 1) , e−t f (t) a vzorce

p
, cos 3t, p23+9 , sin 3t.
p2 +9

1
12. F (p) = p(pp+3
2 +1) + (p−2)3

První ze dvou zlomků rozdělíme na součet a získáme:
p+3
1
= p21+1 + p1 p23+1 + (p−2)
3.
p(p2 +1)

Odtud plyne, že
Rt
f (t) = sin t + 3 0 sin udu + 12 t2 e2t = sin t + 3 − 3 cos t + 12 t2 e2t , t ≥ 0.
Použijeme linearitu transformace a vzorce

1
1
1 2 2t
, sin t, (p−2)
3 , 2t e .
p2 +1

Neřešené úlohy na zpětnou Laplaceovu transformaci.
Určete předmět f (t) k racionální funkci F (p).
1.
2.
3.
4.
5.
6.
7.

2

p +1
F (p) = p3 +3p
2 +2p
1
F (p) = p(p+3)
2
F (p) = (p−1)12 (p+2)
F (p) = p2 (p12 +1)
1
F (p) = (p+1)
3
1
F (p) = p2 +4p+5
F (p) = p24p−3
−2p+5

[f (t) = 21 + 52 e−2t − 2e−t , t ≥ 0]
[f (t) = 19 − 13 te−3t − 19 e−3t , t ≥ 0]
[f (t) = 13 tet − 19 et + 19 e−2t , t ≥ 0]
[f (t) = t − sin t, t ≥ 0]
[f (t) = 12 t2 e−t , t ≥ 0]
[f (t) = e−2t sin t, t ≥ 0]
[f (t) = et (4 cos 2t + 12 sin 2t), t ≥ 0]

8.
9.
10.
11.
12.
13.

F (p) = 2p+3
p2 +4
3p+4
F (p) = p2 +2p+10
F (p) = p23p−5
+2p+5
6p+3
F (p) = p3 +5p
2 +9p+5
4p−3
F (p) = p2 (p+1)2 (p+2)
F (p) = (p2p+3
2 +4)2
2

[f (t) = 2 cos 2t + 32 sin 2t, t ≥ 0]
[f (t) = e−t (3 cos 3t + 13 sin 3t), t ≥ 0]
[f (t) = e−t (3 cos 2t − 4 sin 2t), t ≥ 0]
[f (t) = − 32 e−t + 32 e−2t (cos t + 5 sin t), t ≥ 0]
−t − 3e−t − 11 e−2t , t ≥ 0]
[f (t) = − 32 t + 23
4 − 7te
4
3
[f (t) = − 38 t cos 2t + 12 t sin 2t + 16
sin 2t, t ≥ 0]

−4p+5
14. F (p) = p32p
+7p2 +9p+8
4p+5
15. F (p) = p2 +6p+13

−t − 21 e−2t + 43 e−4t , t ≥ 0]
[f (t) = 11
3 e
2
6
[f (t) = e−3t (4 cos 2t − 72 sin 2t, t ≥ 0]

3p −6p+2
16. F (p) = (p+1)
3 (p+3)

2 −t − 35 te−t + 47 e−t − 47 e−3t , t ≥ 0]
[f (t) = 11
2 t e
4
8
8

2

17.
18.
19.
20.
21.

2

2p −3p+5
F (p) = p(p+1)(p+3)
4p+6
F (p) = p3 +7p
2 +10p
5p−2
F (p) = p2 +4p+5
2p+3
F (p) = (p+1)
3
p+3
F (p) = p2 (p2 +1)

−3t , t ≥ 0]
[f (t) = 53 − 5e−t + 16
3 e
−5t , t ≥ 0]
[f (t) = 35 + 13 e−2t − 14
15 e
[f (t) = e−2t (5 cos t − 12 sin t), t ≥ 0]
[f (t) = ( 12 t2 + 2t)e−t , t ≥ 0]
[f (t) = 3t + 1 − cos t − 3 sin t, t ≥ 0]

2

+10
22. F (p) = p(p5p2 −2p+5)

[f (t) = 2 + et (3 cos 2t + 27 sin 2t), t ≥ 0]

2

+p−4
23. F (p) = p(p+4)
2
1
24. F (p) = p2 +4p+3

[f (t) = 12 t sin 2t + t cos 2t, t ≥ 0]
[f (t) = 12 e−t − 12 e−3t , t ≥ 0]

3. Laplaceova transformace impulsu.
Při hledání obrazu funkce f (t), která je definována na omezeném intervalu nebo je dána
několika vzorci na různých intervalech ze svého definičního oboru používáme při výpočtu přímo
vzorec pro obraz a nebo používáme tvrzení o obrazu posunuté funkce. Toto tvrzení se nazývá
věta o translaci.
Označíme symbolem 1(t) funkci jednotkový skok, která je definována předpisem

0, pro t < 0,
1(t) =
1, pro t ≥ 0
a jejíž průběh je znázorněn na obrázku 1.

f (t)
1

f (t)

1(t)

1

t

Obr.1. Jednotkový skok

a

1(t−a)−1(t−b)

b

t

Obr. 2. Impuls

Věta o translaci. Je-li f (t) , F (p), pak f (t − a)1(t − a) , e−ap F (p) pro a > 0.
Ukážeme na příkladech výpočet obrazu funkcí popsaného typu. Připomeňme, že stále předpokládáme, že uvažované předměty jsou definovány pouze pro nezápornou hodnotu argumentu.

Řešené příklady na obraz impulsu.

1, 0 ≤ t ≤ 2,
1. f (t) =
0, t > 2.
Podle definice je
L {f (t)} = F (p) =

R∞
0

f (t)e−pt dt =

i2
h
−pt dt = − 1 e−pt
= p1 (1 − e−2p ).
1.e
p
0

R2

0

Pomocí věty o translaci a známých vzorců můžeme tento obraz nalézt pomocí následujícího
postupu.
Je f (t) = 2.[1(t) − 1(t − 2)] , p2 (1 − e−2p ),
když použijeme vzorec 1 , p1 a vztah f (t − 2)1(t − 2) , F (p)e−2p .

t, 0 ≤ t ≤ 3,
2. f (t) =
0, t > 3.
Podle definice je
L {f (t)} = F (p) =

R∞
0

f (t)e−pt dt =

h
i3
−pt dt = −t e−pt − e−pt
te
=
p
0
p2

R3

1
− p3 e−3p − p12 e−3p ,
p2

0

když použijeme integraci per-partes.
Pomocí věty o translaci a vzorce pro obraz t , p12 můžeme počítat takto.
Je
f (t) = t[1(t) − 1(t − 3)] = t1(t) − [(t − 3) + 3]1(t − 3) = t1(t) − (t − 3)1(t − 3) − 31(t − 3).
Odtud plyne, že
F (p) = p12 − p12 e−3p − p3 e−3p ,
když použijeme vzorce 1 , p1 , t , p12 a vztah f (t − 3)1(t − 3) , F (p)e−3p .
V dalších úlohách budeme hledat obraz impulsu pomocí věty o translaci. Přímý výpočet z
definice využívá integračních metod, které byly probírany v předchozím kursu matematiky.
* 0,
e−t ,
3. f (t) =
0,

0 ≤ t ≤ 1,
1 < t ≤ 2,
t > 2.

Je
f (t) = e−t [1(t − 1) − 1(t − 2)] = e−(t−1)−1 1(t − 1) − e−(t−2)−2 1(t − 2) =
e−1 e−(t−1) 1(t − 1) − e−2 e−(t−2) 1(t − 2).
Podle věty o translaci je
1
F (p) = (e−1 e−p − e−2 e−2p ) p+1
,
1
když použijeme vzorec e−t , p+1
.

cos t, 0 ≤ t ≤ π2 ,
4. f (t) =
1,
t > π2 .

Je
f (t) = cos t[1(t) − 1(t − π2 )] + 1(t − π2 ).
Nejprve upravíme výraz
cos t1(t − π2 ) = cos [(t − π2 ) + π2 ]1(t − π2 ) =


1(t − π2 ) cos (t − π2 ) cos ( π2 ) − sin (t − π2 ) sin ( π2 ) = − sin (t − π2 )1(t − π2 ).
Pro funkci f (t) máme celkové vyjádření
f (t) = cos t1(t) + sin (t − π2 )1(t − π2 ) + 1(t − π2 ).
Použijeme větu o translaci a dostaneme obraz
π

π

F (p) = p2p+1 + p21+1 e−p 2 + p1 e−p 2 .
Při výpočtu jsme použili vzorce cos t , p2p+1 , sin t , p21+1 , 1 , p1 .
*
5. f (t) =

0,
− sin t,
0,

0 ≤ t ≤ π,
π < t ≤ 2π,
t > 2π.

Je
f (t) = − sin t[1(t − π) − 1(t − 2π)] = − sin [(t − π) + π]1(t − π)+
sin [(t − 2π) + 2π]1(t − 2π)] = sin (t − π)1(t − π) + sin (t − 2π)1(t − 2π).
Odtud plyne, že
F (p) = p21+1 (e−pπ + e−2pπ ),
když použijeme větu o translaci a vzorec sin t , p21+1 .
*
6. f (t) =

1,
sin 2t,
0,

0 ≤ t ≤ π4 ,
π
π
4 < t ≤ 2,
π
t > 2.

Je
f (t) = 1(t) − 1(t − π4 ) + sin 2t[1(t − π4 ) − 1(t − π2 )] =
1(t) − 1(t − π4 ) + sin 2[(t − π4 ) + π4 ]1(t − π4 ) − sin 2[(t − π2 ) + π2 ]1(t − π2 ) =
1(t) − 1(t − π4 ) + cos 2(t − π4 )1(t − π4 ) + sin 2(t − π2 )1(t − π2 ).
Odtud plyne, že obraz
π

π

π

F (p) = p1 (1 − e 4 ) + p2p+4 e 4 + p22+4 e 2 .
Použijeme větu o translaci a vzorce 1 , p1 , cos 2t , p2p+4 , sin 2t , p22+4 .
*
7. f (t) =

t,
0 ≤ t ≤ 1,
2 − t, 1 < t ≤ 2,
0,
t > 2.

Je f (t) = t[1(t) − 1(t − 1)] + (2 − t)[1(t − 1) − 1(t − 2)] =
t1(t) − [(t − 1) + 1]1(t − 1) − [(t − 1) − 1]1(t − 1) + (t − 2)1(t − 2) =
t1(t) − 2(t − 1)1(t − 1) + (t − 2)1(t − 2).
Odtud plyne, že obraz
F (p) = p12 (1 − 2e−p + e−2p ),
jestliže použijeme větu o translaci a vzorec t , p12 .

8. f (t) =

sin t,
0,

0 ≤ t ≤ π,
t > π.

Je f (t) = sin t[1(t) − 1(t − π)] = sin t1(t) − sin [(t − π) + π]1(t − π) =
sin t1(t) + sin (t − π)1(t − π).

Odtud plyne, že
F (p) = p21+1 (1 + e−pπ ),
jestliže použijeme větu o translaci a vzorec sin t , p21+1 .

9. f (t) =

1 − cos t,
0,

0 ≤ t ≤ π,
t > π.

Je f (t) = (1 − cos t)[1(t) − 1(t − π)] =
1(t) − 1(t − π) − cos t1(t) + cos [(t − π) + π]1(t − π) =
1(t) − 1(t − π) − cos t1(t) − cos (t − π)1(t − π).
Odtud plyne, že
F (p) = p1 (1 − e−pπ ) − p2p+1 (1 + e−pπ ),
jestliže použijeme větu o translaci a vzorec cos t , p2p+1 .
Neřešené úlohy na obraz impulsu.
Určete obraz F (p) k danému impulsu f (t).

1. f (t) =

2,
0,

* 0,
2. f (t) =

1,
0,

0 ≤ t ≤ 1, [F (p) = p2 (1 − e−p )]
2 < t.
0 ≤ t ≤ 1,
1 < t ≤ 3,
t > 3.

[F (p) = p1 (e−p − e−3p )]



e−t ,
0,



2t,
2,

0 ≤ t ≤ 1, [F (p) = p22 (1 − e−p )]
t > 1.



t,
0,

0 ≤ t ≤ 1, [F (p) = p12 (1 − e−p ) − p1 e−p ]
t > 1.

3. f (t) =

4. f (t) =

5. f (t) =

1
0 ≤ t ≤ 2, [F (p) = p+1
(1 − e−2(p+1) )]
t > 2.

* 1,
0 ≤ t ≤ 1 [F (p) = p1 (1 − 2e−p + e−2p )]
6. f (t) =
−1, 1 < t ≤ 2,
0,
t > 2.
*
7. f (t) =

*
8. f (t) =

*
9. f (t) =

2t,
3 − t,
0,

0 ≤ t ≤ 1, [F (p) = p12 (2 − 3e−p + e−3p )]
1 < t ≤ 3,
t > 3.

t,
0 ≤ t ≤ 1, [F (p) = p12 (1 − e−p − e−2p + e−3p )]
1,
1 < t ≤ 2,
3 − t, 2 < t ≤ 3,
0,
t > 3.
sin t,
0,

π

0 ≤ t ≤ π2 , [F (p) = p21+1 (1 − pe−p 2 )]
t > π2 .

*
10. f (t) =

0 ≤ t ≤ 1, [F (p) = p12 (1 − 2e−p + 2e−3p − e−4p )]
1 < t ≤ 3,
3 < t ≤ 4,
t > 4.

t,
2 − t,
t − 4,
0,

4. Zpětná transformace obrazů impulsů.
Při hledání předmětu k funkcím, které obsahují výraz e−ap , a > 0, používáme větu o
translaci, kterou interpretujeme takto. Rozdělíme danou funkci na součet členů tvaru F (p)e−ap ,
kde k funkci F (p) známe předmět. Je-li f (t) , F (p), pak hledaný předmět k funkci F (p)e−ap
je funkce f (t − a)1(t − a), t ≥ 0. Výraz e−ap je pouze návěští, které nás upozorňuje na to, že
v získaném předmětu provedeme posunutí. Ukážeme způsob výpočtu na příkladech.
Řešené úlohy na zpětnou transformaci funkcí s faktorem e−ap .
Nalezněte předmět f (t) k dané funkci F (p).
1. F (p) = p12 e−2p + p1 e−3p
Je

1
,t
p2

a p1 , 1, tudíž pro předmět k funkci F (p) dostaneme vyjádření

f (t) = (t − 2)1(t − 2) + 1(t − 3), t ≥ 0.
Funkci f (t) lze také zapsat
* 0,
0 ≤ t ≤ 2,
f (t) =

t − 2,
t − 1,

2 < t ≤ 3,
t > 3.

2
2. F (p) = p(p−1)
e−p

Nejprve funkci

1
p(p−1)

rozložíme na součet částečných zlomků. Dostaneme (viz odst. 2)

2
−2
2
p(p−1) = p + p−1

a tedy
f (t) = −21(t − 1) + 2et−1 1(t − 1), t ≥ 0,
1
jestliže použijeme vzorce 1 , p1 , et , p−1
a větu o translaci (a = 1).

0,
0 ≤ t ≤ 1,
Funkci f (t) lze také zapsat f (t) =
2(et−1 − 1),
t > 1.
−πp

3. F (p) = p2p−e
2 +2p+2
Obdobně jako v odstavci 2 dostaneme:
2(p+1)
2p
2
−t (cos t − sin t);
= (p+1)
2 +1 − (p+1)2 +1 , 2e
p2 +2p+2
1
1
−t sin t.
= (p+1)
2 +1 , e
p2 +2p+2

Je tedy
f (t) = 2e−t (cos t − sin t)1(t) − e−(t−π) sin (t − π)1(t − π).
Funkci f (t) lze také zapsat

2e−t (cos t − sin t),
f (t) =
−t
e (2 cos t − (2 − eπ ) sin t) + sin t,

0 ≤ t ≤ π,
t > π.

4. F (p) = 3p+2−6e
p2 +4

−πp

.

Jestliže použijeme vzorců

p
, cos 2t, p22+4 , sin 2t
p2 +4

dostaneme, že

f (t) = [3 cos 2t + sin 2t]1(t) − 3 sin 2(t − π)1(t − π).
Funkci f (t) lze také zapsat

3 cos 2t + sin 2t,
0 ≤ t ≤ π,
f (t) =
3 cos 2t − 2 sin 2t, t > π.
−p

−2p

+2pe
5. F (p) = p−3ep2 +3p+2

.

Obdobně jako v odstavci 2 provedeme rozklad na parciální zlomky a dostaneme:
p
p
2
−1
= (p+2)(p+1)
= p+2
+ p+1
, 2e−2t − e−t
p2 +3p+2

a
1
1
−1
1
= (p+2)(p+1)
= p+2
+ p+1
, −e−2t + e−t .
p2 +3p+2

Odtud vyplývá, že
f (t) = (2e−2t − e−t )1(t) + 3(e−2(t−1) − e−(t−1) )1(t − 1) + (4e−2(t−2) − 2e−(t−2) )1(t − 2).
Funkci f (t) lze také zapsat vzorcem
* 2e−2t − e−t ,
f (t) =

(2 + 3e2 )e−2t − (1 + 3e)e−t ,
(2 + 3e2 + 4e4 )e−2t − (1 + 3e + 2e2 )e−t ,

0 ≤ t ≤ 1,
1 < t ≤ 2,
t > 2.

Neřešené úlohy na zpětnou transformaci funkcí s faktorem e−ap .
Nalezněte předmět f (t) k obrazu F (p).
1. F (p) = p22 e−p

[f (t) = 2(t − 1)1(t − 1), t ≥ 0]



0,
0 ≤ t ≤ 1,
f (t) =
2t − 2,
t > 1.

2. F (p) = p22 (1 − e−p − pe−3p )

[f (t) = 2t1(t) − 2(t − 1)1(t − 1) − 21(t − 3), t ≥ 0]

* 2t, 0 ≤ t ≤ 1, 
f (t) =

1
3. F (p) = p+1
(e−p−1 − e−2p−2 )

π

2,
0,

1 < t ≤ 3, 
t > 3.

[f (t) = e−1 e−(t−1) 1(t − 1) − e−2 e−(t−2) 1(t − 2), t ≥ 0]


* 0,
0 ≤ t ≤ 1,
f (t) =
e−t , 1 < t ≤ 2, 
0,
t > 2.
π

4. F (p) = p21+9 (3 − 3e− 2 p − (3 + p)e− 6 p )

[f (t) = sin 3t1(t) − sin 3(t − π6 ) + cos 3(t − π6 ) 1(t − π6 ) − sin 3(t − π2 )1(t − π2 ), t ≥ 0]

* sin 3t, 0 ≤ t ≤ π , 
6
f (t) =
cos 3t, π6 < t ≤ π2 , 
0,
t > π2 .

1
−πp )
5. F (p) = (p2 +p)(p
2 +4) (1 + e

1
1
[f (t) = ( 14 − 15 e−t − 20
cos 2t − 10
sin 2t)1(t)+

1
1
cos 2(t − π) − 10
sin 2(t − π))1(t − π), t ≥ 0]
( 14 − 15 e−t+π − 20



1
1 −t
1
1
− 5 e − 20 cos 2t − 10
sin 2t,
0 ≤ t ≤ π,
4
f (t) =
1
1 −t
1
1
π
t > π.
2 − 5 e (1 + e ) − 10 cos 2t − 5 sin 2t,

5. Obraz periodické funkce.
Pomocí věty o translaci snadno odvodíme obraz periodické funkce. K jeho určení potřebujeme
vypočítat obraz impulsu, který danou periodickou funkci vytváří.
Je-li fT : R → R funkce, která je nenulová pouze v intervalu h0, T ), pak je její periodické
prodloužení definováno vztahem
f (t + kT ) = fT (t), 0 ≤ t < T,
k je celé číslo.
Vztah lze přepsat ve tvaru
f (t) = fT (t − kT ), kT ≤ t < (k + 1)T,
k je celé číslo.
Periodické pokračování funkce f (t) můžeme zapsat jako součet posunutých impulsů fT ,
kdy provádíme posun vždy o jednu periodu. Je tedy
f (t)1(t) =

∞
X

fT (t − kT )1(t − kT ), t ≥ 0.

k=0

Odtud dostaneme pomocí věty o translaci vyjádření obrazu
F (p) = L {f (t)1(t)} =

∞
X

FT (p)e−pkT =

k=0

FT (p)
,
1 − e−pT

kde FT (p) = L {fT (t)} je obraz impulsu fT (t). Použili jsme skutečnosti e−pkT = (e−pT )k a
toho, že součet geometrické řady s kvocientem e−pT je roven 1−e1−pT ,
Obraz impulsu FT (t) počítáme buď podle definice ze vztahu
FT (p) = L {fT (t)} =

Z T

f (t)e−pt dt,

0

nebo z vyjádření
fT (t) = f (t)[1(t) − 1(t − T )], t ≥ 0,
kde použijeme větu o translaci.
Řešené úlohy na obraz periodické funkce.
Určete obraz F (p) periodické funkce f (t), která je vytvořena impulsem fT (t),
0 ≤ t < T a má periodu T.

1,
0 ≤ t ≤ 1,
1. fT (t) =
−1, 1 < t < 2.
Je fT (t) = 1(t) − 21(t − 1) + 1(t − 2), t ≥ 0. Odtud a z věty o translaci plyne
1
FT (p) = (1 − 2e−p + e−2p ),
p

tudíž
F (p) =

1 − 2e−p + e−2p
(1 − e−p )2
1 − e−p
=
=
.
p(1 − e−2p )
p(1 + e−p )(1 − e−p )
p(1 + e−p )

Použili jsme vzorce pro obraz periodické funkce, vztahu
dané funkce je T = 2.

sin t,
0 ≤ t ≤ π,
2. fT (t) =
0,
π < t < 2π.

1
p ,1

a skutečnosti, že perioda

Je f (t) = sin t[1(t) − 1(t − π)] = sin t1(t) + sin (t − π)1(t − π), tedy
FT (p) =

1
p2 + 1

+

1
p2 + 1

e−πp .

Vzhledem k tomu, že perioda funkce f (t) je rovna T = 2π, je
F (p) =

1 + e−πp
1
= 2
.
2
−2πp
(p + 1)(1 − e
)
(p + 1)(1 − e−πp )

Použili jsme vzorec pro obraz periodické funkce a vztahy sin t , p21+1 .
*
3. fT (t) =

t,
2 − t,
0,

0 ≤ t ≤ 1,
1 < t ≤ 2,
2 < t < 3.

Je fT (t) = t[1(t) − 1(t − 1)] + (2 − t)[1(t − 1) − 1(t − 2)] =
t1(t) − [(t − 1) + 1]1(t − 1) + [1 + (1 − t)]1(t − 1) + (t − 2)1(t − 2) =
t1(t) − 2(t − 1) + 11(t − 1) + (t − 2)1(t − 2).
Odtud dostaneme obraz FT (p) = p12 (1 − 2e−p + e−2p ) a tedy obraz funkce f (t) je
F (p) =

1 − 2e−p + e−2p
.
p2 (1 − e−3p )

Použili jsme vzorce pro obraz periodické funkce s periodou T = 3 a vztah 1 , p1 .
Neřešené úlohy na obraz periodické funkce.
Určete obraz F (p) periodické funkce f (t), která je vytvořena impulsem fT (t) a má
periodu T.

1, 0 ≤ t ≤ 1,
1. fT (t) =
[F (p) = (1+e1−p ) ]
0, 1 < t < 2, T = 2.
2. fT (t) = sin t,
*
3. fT (t) =

t,
2 − t,
t − 4,

4. fT (t) = 1 − t,

0 ≤ t < π, T = π
0 ≤ t ≤ 1,
1 < t ≤ 3,
3 < t < 4, T = 4.
0 ≤ t < 1, T = 1.

−πp

1+e
[F (p) = (p2 +1)(1−e
−πp ) ]

−p

−3p

+2e
−e
[F (p) = 1−2ep2 (1−e
−4p )

−4p

]

1
1
[F (p) = p(1−e
−p ) − p2 ]

6. Řešení lineárních diferenciálních rovnic.
Laplaceovu tramsformaci můžeme použít k řešení lineárních diferenciálních rovnic s konstatními koeficienty nebo jejich soustav. Pomocí vztahů mezi obrazem funkce a obrazem jejich
derivací lze rovnici převést na lineární rovnici nebo soustavu lineárních rovnic pro obraz či obrazy
řešení. Obrazem řešení obvykle bývá racionální funkce. Jak se hledá předmět k takové funkci
jsme ukázali v odstavci 2. Obecně lze řešení zapsat jako konvoluci „ pravé strany rovnice ÿ a
předmětu k racionální funkci.
Budeme hledat řešení diferenciální rovnice
(♣)

x(n) (t) + a1 x(n−1) (t) + . . . + an x(t) = f (t)

v intervalu t ∈ h0, ∞), které vyhovuje počáteční podmínce
(♠)

x(0) = x1 , x0 (0) = x2 , . . . , x(n−1) (0) = xn .

Jestliže označíme
L {x(t)} = X(p),
pak
L {x0 (t)} = pX(p) − x1 , L {x00 (t)} = p2 X(p) − px1 − x2 , . . . ,
L {x(n) (t)} = pn X(p) − pn−1 x1 − . . . − xn .
Po dosazení do rovnice (♣) dostaneme rovnici pro obraz řešení ve tvaru
(pn + a1 pn−1 + . . . + an )X(p) − Q(p) = L {f (t)},
kde Q(p) je nějaký polynom stupně nejvýše (n − 1). Odtud dostaneme obraz řešení ve
tvaru
X(p) =

L {f (t)}
pn + a1 pn−1 + . . . + an

+

Q(p)
pn + a1 pn−1 + . . . + an

.

Odtud lze vyjádřit řešení ve tvaru
x(t) = f (t) ∗ v(t) + w(t), t ≥ 0,
kde
v(t) ,

1
pn + a1 pn−1 + . . . + an

a

w(t) ,

Q(p)
pn + a1 pn−1 + . . . + an

jsou předměty k uvedeným racionálním funkcím. Je- li předmět L {f (t)} = F (p) racionální
funkcí dostaneme řešení jako předmět k racionální funkci a není třeba využívat jeho vyjádření
pomocí konvoluce. Je pak
x(t) = L −1 {

Q(p)
F (p)
} + L −1 {
},
P (p)
P (p)

kde P (p) = pn + a1 pn−1 + . . . + an .
Poznamenejme, že z rozboru postupu vyplývá, že první člen ve vzorci je řešením rovnice (♣)
za nulových počátečních podmínek a druhý člen je řešením homogenní rovnice příslušné rovnici
(♣), které vyhovuje počátečním podmínkám (♠).
Rt
Stejným způsobem můžeme řešit i rovnici tvaru (♣), která obsahuje ještě člen tvaru 0 x(u)du.
Rt
Zde použijeme vztahu L −1 { 0 x(u)du} = p1 X(p) a pro obraz řešení X(p) dostaneme analogické vyjádření.

Obdobně můžeme postupovat při řešení soustav diferenciálních rovnic, kde dostaneme soustavu lineárních rovnic pro obrazy řešení. Po jejím vyřešení hledáme řešení soustavy jako předměty k funkcím výše popsaného tvaru.
Postup řešení jednotlivých úloh budeme ilustrovat na příkladech.
Řešené úlohy na diferenciální rovnice.
Nalezněte řešení dané rovnice v intervalu h0, ∞) , které vyhovuje uvedeným počátečním
podmínkám.
1. x0 + 2x = 3,

x(0) = 0.

Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
pX(p) − 0 + 2X(p) = p3 .
Odtud vypočteme, že
3
X(p) = p(p+2)
.

Předmět k funkci X(p) získáme postupem popsaným v odstavci 2. Funkci rozložíme na
součet parciálních zlomků
X(p) =

3
3
3
=
−
.
p(p + 2)
2p 2(p + 2)

Odtud plyne, že
3
x(t) = (1 − e−2t ), t ≥ 0.
2
1
Použili jsme vztah x0 (t) , X(p) − x(0) a vzorce 1 , p1 , e−2t , p+2
.

2. x0 + 4x = sin t,

x(0) = 3.

Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
X(p)(p + 4) − 3 = p22+4 .
Odtud vypočteme, že
3
2
X(p) = p+4
+ (p+4)(p
2 +4) .

Předmět k funkci X(p) získáme postupem popsaným v odstavci 2. Funkci rozložíme na
součet parciálních zlomků
1
1
− 10
p + 25
3
2
3
10
.
X(p) =
+
+
=
+
p2 + 4
p + 4 (p + 4)(p2 + 4)
p+4 p+4

Odtud plyne, že
x(t) =

1
1
31 −4t
e
−
cos 2t + sin 2t, t ≥ 0.
10
10
5

1
Použili jsme vztah x0 (t) , X(p) − x(0) a vzorce sin 2t , p22+4 , cos 2t , p2p+4 , e−4t , p+4
.

3. x00 − x0 − 6x = 2,

x(0) = 1, x0 (0) = 0.

Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
p2 X(p) − p.1 − 0 − (pX(p) − 1) − 6X(p) = p2 .

Odtud vypočteme, že
2

p −p+2
X(p) = p(p−3)(p+2)
.

Předmět k funkci X(p) získáme postupem popsaným v odstavci 2. Funkci rozložíme na
součet parciálních zlomků
X(p) =

4
8
−1
p2 − p + 2
= 3 + 5 + 15 .
p
p+2 p−3
p(p − 3)(p + 2)

Odtud plyne, že
x(t) =

1
(−5 + 12e−2t + 8e3t ), t ≥ 0.
15

Použili jsme vztahy x0 (t) , X(p) − x(0) , x00 (t) , p2 X(p) − px(0) − x0 (0) a vzorce
1
1 , p1 , eat , p−a
, a = −2, a = 3.
4. x00 − 6x0 + 9x = 0,

x(0) = 2, x0 (0) = −4.

Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
(p2 X(p) − 2p + 4) − 6(pX(p) − 2) + 9X(p) = 0.
Odtud vypočteme, že
X(p) = p22p−16
.
−6p+9
Předmět k funkci X(p) získáme postupem popsaným v odstavci 2. Funkci rozložíme na
součet parciálních zlomků
2p − 16

X(p) =

p2 − 6p + 9

=

2(p − 3) + 6 − 16
2
10
=
−
.
2
(p − 3)
(p − 3) (p − 3)2

Odtud plyne, že
x(t) = (2 − 10t)e3t , t ≥ 0.
Použili jsme vztahy x0 (t) , X(p) − x(0) , x00 (t) , p2 X(p) − px(0) − x0 (0) a vzorce
1
1
e3t , p−3
, te3t , (p−3)
2.
5. x00 + 2x0 + 2x = 0,

x(0) = 1, x0 (0) = 2.

Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
(p2 X(p) − p − 2) + 2(pX(p) − 1) + 2X(p) = 0.
Odtud vypočteme, že
p+4
.
X(p) = p2 +2p+2

Předmět k funkci X(p) získáme postupem popsaným v odstavci 2. Funkci rozložíme na
součet parciálních zlomků
X(p) =

p+4
p+1
3
= 2
+
.
p2 + 2p + 2
(p + 1) + 1 (p2 + 1) + 1

Odtud plyne, že
x(t) = e−t (cos t + 3 sin t), t ≥ 0.
Použili jsme vztahy x0 (t) , X(p) − x(0) , x00 (t) , p2 X(p) − px(0) − x0 (0),
eat f (t) , F (p − a), a = −1 a vzorce cos t , p2p+1 , sin t , p21+1 .

6. x00 − 9x = 2 − t,

x(0) = 0, x0 (0) = 1.

Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
(p2 − 9)X(p) − 1 = p2 − p12 .
Odtud vypočteme, že
2

p +2p−1
X(p) = p2 (p−3)(p+3)
.

Předmět k funkci X(p) získáme postupem popsaným v odstavci 2. Funkci rozložíme na
součet parciálních zlomků
X(p) =

6
1
7
1
− 27
+ 92 + 27 − 27 .
p
p
p−3 p+3

Odtud plyne, že
x(t) =

1
(−6 + 3t + 7e3t − e−3t ), t ≥ 0.
27

Použili jsme vztahy x0 (t) , X(p) − x(0) , x00 (t) , p2 X(p) − px(0) − x0 (0) a vzorce
1
1 , p1 , t , p12 , eat , p−a
, a = 3, a = −3.
7. x00 + 4x = 2 cos 2t,

x(0) = 0, x0 (0) = 4.

Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
(p2 + 4)X(p) − 4 = p22p+4 .
Odtud vypočteme, že
X(p) = p24+4 + (p22p
.
+4)2
Předmět k funkci X(p) získáme postupem popsaným v odstavci 2. Odtud plyne, že
1
x(t) = (4 + t) sin 2t, t ≥ 0.
2
Použili jsme vztahy x00 (t) , p2 X(p) − px(0) − x0 (0) a vzorce t sin 2t , (p24p
,
+4)2
sin 2t , p22+4 .
Rt
8. x0 + 0 x(τ ) dτ = 1,

x(0) = 1.

Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace a obrazem integrálu, tak pro obraz řešení dostaneme
rovnici
(p + p1 )X(p) − 1 = p1 .
Odtud vypočteme, že
X(p) = pp+1
2 +1 .
Předmět k funkci X(p) získáme postupem popsaným v odstavci 2.
X(p) =

p
1
+
.
p2 + 1 p2 + 1

Odtud plyne, že
x(t) = sin t + cos t, t ≥ 0.
Rt
Použili jsme vztahy x0 (t) , X(p) − x(0) , 0 x(τ ) dτ , p1 X(p) a vzorce 1 , p1 ,
sin t , p21+1 , cos t , p2p+1 .

Rt
9. x0 + 2x + 2 0 x(τ ) dτ = 3e−t ,

x(0) = 2.

Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace a obrazem integrálu, tak pro obraz řešení dostaneme
rovnici
3
(p + 2 + p2 )X(p) − 2 = p+1
.

Odtud vypočteme, že
2

2p +5p
X(p) = (p+1)(p
2 +2p+2) .

Předmět k funkci X(p) získáme postupem popsaným v odstavci 2. Funkci rozložíme na
součet parciálních zlomků
X(p) =

2p2 + 5p
−3
5p + 6
=
+ 2
.
2
(p + 1)(p + 2p + 2)
p + 1 p + 2p + 2

Úpravou dostaneme vyjádření
X(p) =

−3
5(p + 1)
1
+
+
.
2
p + 1 (p + 1) + 1 (p + 1)2 + 1

Odtud plyne, že
x(t) = −3e−t + e−t (5 cos t + sin t), t ≥ 0.
Rt
Použili jsme vztahy x0 (t) , X(p) − x(0) , 0 x(τ ) dτ , p1 X(p), e−t f (t) , F (p + 1) a
1
vzorce e−t , p+1
, sin t , p21+1 , cos t , p2p+1 .

2 − t, 0 ≤ t ≤ 2,
0
10. x − x = f (t), x(0) = −1, kde f (t) =
0,
t > 2.
Poznamenejme, že f (t) = (2 − t)[1(t) − 1(t − 2)] a postupem z odstavce 3 dostaneme
f (t) ,

2
1
− 2 (1 − e−2p ).
p p

Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
(p − 1)X(p) + 1 =

2
1
− (1 − e−2p ).
p p2

Odtud vypočteme, že
X(p) =

1
−p2 + 2p − 1
+ 2
e−2p .
2
p (p − 1)
p (p − 1)

Předmět k funkci X(p) získáme postupem popsaným v odstavci 2. Funkce rozložíme na
součet parciálních zlomků
1
1
X(p) = 2 − +
p
p



−1
1
1
− 2+
p
p
p−1



e−2p .

Použijeme postupů, které jsme probrali v úlohách v odstavcích 2 a 4 a dostaneme pro
řešení vzorec
x(t) = (t − 1)1(t) + (−1 − (t − 2) + e(t−2) )1(t − 2), t ≥ 0.

Řešení lze také zapsat pomocí vzorce

x(t) =

t − 1,
et−2 ,

0 ≤ t ≤ 2,
t > 2.

Použili jsme vztahy x0 (t) , X(p) − x(0), větu o translaci z odstavce 3 a vzorce
1
1 , p1 , t , p12 , et , p−1
.

1, 0 ≤ t ≤ 1,
00
0
11. x + x = f (t), x(0) = 1, x (0) = −1, kde f (t) =
0, t > 1.
Poznamenejme, že f (t) = 1(t) − 1(t − 1), tedy L f (t) = p1 (1 − e−p ), kde obraz k funkci
f (t) získáme pomocí věty o translaci. Postup jsme ukázali v úlohách v odstavci 3.
Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
(p2 + 1)X(p) − p + 1 = p1 (1 − e−p ).
Dále vypočteme, že
2

X(p) = p −p+1−e
p(p2 +1)

−p

.

Předmět k funkci X(p) získáme postupem popsaným v odstavcích 2 a 4. Funkci rozložíme
na součet parciálních zlomků
1
1
X(p) = − 2
−
p p +1



1
p
− 2
p p +1



e−p .

Odtud plyne, že
x(t) = (1 − sin t)1(t) − (1 − cos (t − 1))1(t − 1), t ≥ 0.
Řešení lze také zapsat pomocí vzorce

x(t) =

1 − sin t,
sin t(sin 1 − 1) + cos t cos 1,

0 ≤ t ≤ 1,
t > 1.

Použili jsme vztahy x00 (t) , p2 X(p) − px(0) − x0 (0), větu o translaci z odstavce 3 a vzorce
1 , p1 , sin t , p+1 1 , cos t , p+p 1 .

1, 0 ≤ t ≤ 1,
12. x00 + 4x0 + 3x = f (t), x(0) = 0, x0 (0) = 0, kde f (t) =
0, t > 0.
Poznamenejme, že f (t) = 1(t) − 1(t − 1), tedy L f (t) = (1 − e−p ) p1 , kde obraz k funkci
f (t) získáme pomocí věty o translaci. Postup jsme ukázali v úlohách v odstavci 3.
Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
X(p)(p2 + 4p + 3) = (1 − e−p ) p1 .
Dále vypočteme, že
−p

X(p) = p(p1−e
2 +4p+3) .
Předmět k funkci X(p) získáme postupem popsaným v odstavcích 2 a 4. Funkci rozložíme
na součet parciálních zlomků

X(p) =

1
1
1
−
+
3p 2(p + 1) 6(p + 3)



(1 − e−p ).

Odtud plyne, že




1 1 −(t−1) 1 −3(t−1)
1 1 −t 1 −3t
− e + e
1(t) −
− e
+ e
1(t − 1), t ≥ 0.
x(t) =
3 2
6
3 2
6
Řešení lze také zapsat pomocí vzorce

x(t) =

1
1 −t
+ 16 e−3t ,
3 − 2e
1
−t + 1 (1 − e3 )e−3t ,
2 (e − 1)e
6

0 ≤ t ≤ 1,
t > 1.

Použili jsme vztahy x0 (t) , X(p) − x(0) , x00 (t) , p2 X(p) − px(0) − x0 (0), větu o translaci
1
z odstavce 3 a vzorce 1 , p1 , eat , p−a
, a = −1, a = −3.
13. x00 + x = f (t),

* 1,
−1,
x(0) = 0, x0 (0) = 0, kde f (t) =
0,

0 ≤ t ≤ 1,
1 < t ≤ 2,
t > 2.
−p

−2p

Poznamenejme, že f (t) = 1(t) − 21(t − 1) + 1(t − 2), tedy L f (t) = 1−2e p+e , kde
obraz k funkci f (t) získáme pomocí věty o translaci. Postup jsme ukázali v úlohách v
odstavcích 3.
Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
−p

(p2 + 1)X(p) = 1−2e p+e

−2p

.

Dále vypočteme, že
−p

−2p

+e
X(p) = 1−2e
p(p2 +1)

.

Předmět k funkci X(p) získáme postupem popsaným v odstavcích 5, 6 a 12. Funkci
rozložíme na součet parciálních zlomků

X(p) =

1
p
−
p p2 + 1



(1 − 2e−p + e−2p ).

Odtud plyne, že
x(t) = (1 − cos t)1(t) − 2(1 − cos (t − 1))1(t − 1) + (1 − cos (t − 2))1(t − 2), t ≥ 0.
Řešení lze také zapsat pomocí vzorce
*
x(t) =

1 − cos t,
−1 + (2 cos 1 − 1) cos t + 2 sin 1 sin t,
cos t(2 cos 1 − 1 − cos 2) − (sin 2 − 2 sin 1) sin t,

0 ≤ t ≤ 1,
1 < t ≤ 2,
t > 2.

Použili jsme vztahy x0 (t) , X(p) − x(0) , x00 (t) , p2 X(p) − px(0) − x0 (0), větu o translaci
z odstavce 8 a vzorce 1 , p1 , sin t , p21+1 , cos t , p2p+1 .

0,
0 ≤ t ≤ 1,
00
0
0
14. x + 2x + 2x = f (t), x(0) = 0, x (0) = 0, kde f (t) =
−t
e , t > 1.
−1 −p

e
Poznamenejme, že f (t) = e−t 1(t − 1) = e−1 e−(t−1) 1(t − 1), tedy L f (t) = e p+1
, kde
obraz k funkci f (t) získáme pomocí věty o translaci. Postup jsme ukázali v úlohách v
odstavci 3.

Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici

−1 −p

e
(p2 + 2p + 2)X(p) = e p+1
.

Dále vypočteme, že
−1 −p

e e
X(p) = (p+1)(p
2 +2p+2) .

Předmět k funkci X(p) získáme postupem popsaným v odstavcích 2 a 4. Funkci rozložíme
na součet parciálních zlomků
X(p) = e

−1



1
p+1
−
p (p + 1)2 + 1



e−p .

Odtud plyne, že
x(t) = e−1 (1 − e−(t−1) cos (t − 1))1(t − 1), t ≥ 0.
Řešení lze také zapsat pomocí vzorce

x(t) =

0,
e−1 − e−t (cos 1 cos t + sin 1 sin t),

0 ≤ t ≤ 1,
t > 1.

Použili jsme vztahy x0 (t) , X(p) − x(0) , x00 (t) , p2 X(p) − px(0) − x0 (0), větu o translaci
1
z odstavce 3 a vzorce cos t , p2p+1 , e−t , p+1
a vztah f (t)e−t , F (p + 1).
* 2t,
15. x00 + 4x = f (t),

x(0) = 0, x0 (0) = 0,

kde f (t) =

2(t − 2),
0,

0 ≤ t ≤ 1,
1 < t ≤ 2,
t > 2.

Poznamenejme, že f (t) = 2t(1(t) − 1(t − 1)) + 2(t − 2)(1(t − 1) − 1(t − 2)) = 2t1(t) −
4(t − 1)1(t − 1) + 2(t − 2)1(t − 2), tedy L f (t) = (1 − 2e−p + e−2p ) p22 , kde obraz k funkci
f (t) získáme pomocí věty o translaci. Postup jsme ukázali v úlohách v odstavci 3.
Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
(p2 + 4)X(p) = (1 − 2e−p + e−2p ) p22 .
Dále vypočteme, že
X(p) = (1 − 2e−p + e−2p ) p2 (p22 +4) .
Předmět k funkci X(p) získáme postupem popsaným v odstavcích 2 a 4. Funkci rozložíme
na součet parciálních zlomků

X(p) =

1
1
− 2
2
p
p +4



1 − 2e−p + e−2p
.
2

Odtud plyne, že
1
x(t) =
2






1
1
t − sin 2t 1(t) − (t − 1) − sin 2(t − 1) 1(t − 1)+
2
2


1
1
(t − 2) − sin 2(t − 2) 1(t − 2), t ≥ 0.
2
2

Řešení lze také zapsat pomocí vzorce
* 1 t − 1 sin 2t,
2

x(t) =

4

1 − 12 t + sin 2t( 12 cos 2 − 14 ) − 12 sin 2 cos 2t,
sin 2t(− 41 + 12 cos 2 − 14 cos 4) + ( 14 sin 4 − 12 sin 2) cos 2t,

0 ≤ t ≤ 1,
1 < t ≤ 2,
t > 2.

Použili jsme vztahy x0 (t) , X(p) − x(0) , x00 (t) , p2 X(p) − px(0) − x0 (0), větu o translaci
z odstavce 3 a vzorce 1 , p1 , t , p12 ,
sin 2t , p22+4 , cos 2t , p2p+4 .
16. x0 + 5x = f (t),


x(0) = 1, kde f (t) =

5 cos 2t,
0,

0 ≤ t ≤ π2 ,
t > π2 .

Poznamenejme, že
f (t) = 5 cos 2t [1(t) − 1(t −

π
π
π
)] = 5 cos 2t 1(t) + 5 cos 2(t − )1(t − ),
2
2
2

π

tedy L f (t) = p25p+4 (1 + e− 2 p ), kde obraz k funkci f (t) získáme pomocí věty o translaci.
Postup jsme ukázali v úlohách v odstavci 2.
Označme X(p) , x(t) obraz řešení. Jestliže využijeme linearitu transformace a vztah
mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
π

(p + 1)X(p) − 1 = p25p+4 (1 + e− 2 p ).
Dále vypočteme, že
π

5p
1
X(p) = (p2 +4)(p+1)
(1 + e− 2 p ) + p+1
.

Předmět k funkci X(p) získáme postupem popsaným v odstavcích 2 a 4. Funkci rozložíme
na součet parciálních zlomků
X(p) =

p+4
+
p2 + 4



p+4
1
−
p2 + 4 p + 1



π

e− 2 .

Odtud plyne, že


π
π
π
π
x(t) = (cos 2t + 2 sin 2t)1(t) + cos 2(t − ) + 2 sin 2(t − ) − e−(t− 2 ) 1(t − ), t ≥ 0.
2
2
2
Řešení lze také zapsat pomocí vzorce

x(t) =

cos 2t + 2 sin 2t,
π
−e 2 e−t ,

0 ≤ t ≤ π2 ,
t > π2 .

Použili jsme vztahy x0 (t) , pX(p) − x(0), větu o translaci z odstavce 3 a vzorce
1
cos 2t , p2p+4 , sin 2t , p22+4 , e−t , p+1
.
Řešení rovnice se dá také vyjádřit jako konvoluce. Toto vyjádření můžeme použít ve
dvou případech. Buď je funkce na pravé straně rovnice složitá pro hledání obrazu a
nebo chceme vyjádřit řešení rovnice pro obecnou pravou stranu. Při výpočtu konkrétního řešení pak zbývá vypočítat integrál, kterým je konvoluce zapsaná. Využijeme vztahu
L −1 {F (p)G(p)} = L −1 {F (p)} ∗ L −1 {G(p))}. Dostaneme stejné vyjádření řešení, které
získáme metodou variace konstant. Postup řešení úlohy budeme ilustrovat na příkladech.
17. x00 + 3x0 + 2x = f (t),

x(0) = 0, x0 (0) = 0.

Označme X(p) , x(t) obraz řešení a F (p) , f (t). Jestliže využijeme linearitu transformace a vztah mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
(p2 + 3p + 2)X(p) = F (p)
a odtud dostaneme pro řešení rovnice vyjádření
X(p) =

F (p)
.
p2 + 3p + 2

Protože je
1

=

p2 + 3p + 2

1
1
−
, (e−t − e−2t ),
p+1 p+2

je
x(t) = f (t) ∗ (e

−t

−e

−2t

Z t
)=

f (u)(e−t+u − e−2t+2u ) du, t ≥ 0.

0

18. x00 + 4x0 + 5x = f (t),

x(0) = 1, x0 (0) = 0,

Označme X(p) , x(t) obraz řešení a F (p) , f (t). Jestliže využijeme linearitu transformace a vztah mezi obrazem funkce a její derivace, tak pro obraz řešení dostaneme rovnici
(p2 + 4p + 5)X(p) − p − 4 = F (p)
a odtud dostaneme pro řešení rovnice vyjádření
F (p)

X(p) =

p2 + 4p + 5

+

p+4
p2 + 4p + 5

.

Protože je
1
p2 + 4p + 5
a

p+4
p2 + 4p + 5

=

=

1
, e−2t sin t
(p + 2)2 + 1

p+2
2
+
, e−2t (cos t + 2 sin t)
2
(p + 2) + 1 (p + 2)2 + 1

je
x(t) = e−2t (cos t + 2 sin t) + f (t) ∗ e−2t sin t
Z t
−2t
= e (cos t + 2 sin t) +
f (u)e−2(t−u) sin (t − u) du, t ≥ 0.
0

Rt

19. x0 + 2x + 10 0 x(u)du = f (t),

x(0) = 1,

Označme X(p) , x(t) obraz řešení a F (p) , f (t). Jestliže využijeme linearitu transformace a vztah mezi obrazem funkce a její derivace a integrálu, tak pro obraz řešení
dostaneme rovnici
10
(p + 2 + )X(p) − 1 = F (p)
p
a odtud dostaneme pro řešení rovnice vyjádření
X(p) =

pF (p)
p2 + 2p + 10

+

p
p2 + 2p + 10

.

Protože je
p
p2 + 2p + 10

=

p+1
1
1
−
, e−t (cos 3t − sin 3t),
2
2
(p + 1) + 9 (p + 1) + 9
3

je
x(t) = e−t (cos 3t −
1
= e (cos 3t − sin 3t) +
3
−t

Z t
0

1
1
sin 3t) + f (t) ∗ e−t (cos 3t − sin 3t)
3
3

f (u)e−t+u (cos 3(t − u) −

1
sin 3(t − u))du, t ≥ 0.
3

Rt
20. x0 + 6x + 9 0 x(u)du = f (t),

x(0) = 1,

Označme X(p) , x(t) obraz řešení a F (p) , f (t). Jestliže využijeme linearitu transformace a vztah mezi obrazem funkce a její derivace a integrálu, tak pro obraz řešení
dostaneme rovnici
9
(p + 6 + )X(p) − 1 = F (p)
p
a odtud dostaneme pro řešení rovnice vyjádření
X(p) =

pF (p)
p2 + 6p + 9

+

p
p2 + 6p + 9

.

Protože je
p
p
1
3
=
=
−
, e−3t (1 − 3t),
p2 + 6p + 9
(p + 3)2
p + 3 (p + 3)2
je
x(t) = e−3t (1 − 3t) + f (t) ∗ (e−3t (1 − 3t)) =
Z t
−3t
e (1 − 3t) +
f (u)(e−3(t−u) (1 − 3(t − u)))du, t ≥ 0.
0

Neřešené úlohy na diferenciální rovnice.
Nalezněte řešení rovnice, které vyhovuje uvedeným počátečním podmínkám.
1. x0 + 3x = 0,

[x(t) = 5e−3t , t ≥ 0]

x(0) = 5;

2. x00 − 2x0 + 2x = 0,

x(0) = 1, x0 (0) = 1;

3. x00 + 3x0 + 2x = 4e−3t ,

[x(t) = et cos t, t ≥ 0]

x(0) = 0, x0 (0) = 0;

[x(t) = 2e−3t − 4e−2t + 2e−t , t ≥ 0]
[x(t) = 51 (e−2t − cos t + 2 sin t), t ≥ 0]

4. x0 + 2x = sin t,

x(0) = 0;

5. x00 + 3x0 = e−t ,

x(0) = 0, x0 (0) = −1;

[x(t) = 21 (e−3t − e−t ), t ≥ 0]

6. x00 + 4x = cos t,

x(0) = 0, x0 (0) = 0;

[x(t) = 31 (cos t − cos 2t), t ≥ 0]

7. x00 + 2x0 = t sin t,

x(0) = 0, x0 (0) = 0;
1
[x(t) = 25
(2e−2t − 10t cos t − 5t sin t − 2 cos t + 14 sin t), t ≥ 0]

8. x00 + 2x0 + x = sin t,
9. x00 − 2x0 + 2x = 1,

x(0) = 0, x0 (0) = 0;

[x(t) = 12 (te−t + e−t − cos t), t ≥ 0]

x(0) = 0, x0 (0) = 0;

[x(t) = 21 (1 − et (cos t − sin t)), t ≥ 0]

10. x00 + x = cos t, x(0) = −1, x0 (0) = 1;
Rt
11. x0 + 5x + 6 0 x(τ ) dτ = 0, x(0) = 1;
Rt
12. x0 + 2x + 0 x(τ ) dτ = sin t, x(0) = 0;

[x(t) = 12 t sin t − cos t + sin t, t ≥ 0]
[x(t) = 3e−3t − 2e−2t , t ≥ 0]
[x(t) = 12 (te−t + sin t), t ≥ 0]

13.

x0 = −x + y + et , x(0) = 0,
y 0 = x − y + et ,
y(0) = 0;

14.

x0 = −y,
x(0) = 1,
0
y = 2x + 2y, y(0) = 1;

[x(t) = et (cos t − 2 sin t), t ≥ 0]
[y(t) = et (cos t + 3 sin t), t ≥ 0]

15.

x0 = −x + 3y,
x(0) = 1,
0
−2t
y = x + y + e , y(0) = 1;

3 −2t
3 −2t
2t
− 16
[x(t) = 19
e , t ≥ 0]
16 e − 4 te
19 2t
1 −2t
3 −2t
− 16 e , t ≥ 0]
[y(t) = 16 e + 4 te

[x(t) = et − 1, t ≥ 0]
[y(t) = et − 1, t ≥ 0]

16. x00 − 4x = 4t,

x(0) = 1, x0 (0) = 0;

17. x00 − 4x = 4e2t ,

[x(t) = 41 (3e2t + e−2t − 4t), t ≥ 0]

x(0) = 0, x0 (0) = 0;

[x(t) = te2t − 41 e2t + 14 e−2t , t ≥ 0]

18. x00 + x = t3 + 6t,

x(0) = 0, x0 (0) = 0;

[x(t) = t3 , t ≥ 0]

19. x00 + x = sin 2t,

x(0) = 0, x0 (0) = 0;

[x(t) = 13 (2 sin t − sin 2t), t ≥ 0]

20. x00 + x = cos t + sin 2t,

x(0) = 0, x0 (0) = 0;

[x(t) = 12 (4 + e−t + sin t − 5 cos t), t ≥ 0]

21. x00 + x = 2 + e−t , x(0) = 0, x0 (0) = 0;
Rt
22. x0 + 6x + 9 0 x(τ ) dτ = 0, x(0) = 1;
Rt
23. x0 + 2x + 2 0 x(τ ) dτ = 0, x(0) = 1;
24.

x0 − 2x = f (t),

[x(t) = 16 ((3t + 4) sin t − 2 sin 2t), t ≥ 0]

[x(t) = (1 − 3t)e−3t , t ≥ 0]
[x(t) = e−t cos t, t ≥ 0]


x(0) = −3;

f (t) =

8 − 4t,
0,

0 ≤ t ≤ 2,
t > 2.

[x(t) = (2t − 3)1(t) + (e2(t−2) − 2t + 3)1(t − 2), t ≥ 0]

25. x00 + x = f (t), x(0) = 1, x0 (0) = 1;

[x(t) = 2t − 3, 0 ≤ t ≤ 2, x(t) = e2(t−2) , t > 2]

t, 0 ≤ t ≤ π,
f (t) =
0, t > π.

[x(t) = (t − cos t)1(t) − (t + sin t + π cos t)1(t − π), t ≥ 0]

26.

27.

28.

29.

30.

[x(t) = t + cos t, 0 ≤ t ≤ π, x(t) = cos t − sin t − π cos t, t > π]

1, 0 ≤ t ≤ π4 ,
00
0
x + 4x = f (t), x(0) = 1, x (0) = 0; f (t) =
2, t > π4 .

 1

(3 cos 2t + 1),
0 ≤ t ≤ π4 ,
4
x(t) =
1
π
4 (2 + 3 cos 2t − sin 2t), t > 4 .
 −t
2e , 0 ≤ t ≤ π2 ,
00
0
x + x = f (t), x(0) = 0, x (0) = −1; f (t) =
0,
t > π2 .


 −t
e − cos t,
0 ≤ t ≤ π2 ,
π
x(t) =
− cos t + e− 2 (cos t + sin t), t > π2 .

9t, 0 ≤ t ≤ 1,
x0 + 3x = f (t), x(0) = 1; f (t) =
9, t > 1.

 −3t

2e
− 1 + 3t,
0 ≤ t ≤ 1,
x(t) =
2e−3t + 3 − e3 e−3t , t > 1.

5 sin 2t, 0 ≤ t ≤ π2 ,
0
x − x = f (t), x(0) = 1; f (t) =
0,
t > π2 .


 t
3e − 2 cos 2t − sin 2t, 0 ≤ t ≤ π2 ,
π
x(t) =
3et + 2et− 2 ,
t > π2 .

sin t, 0 ≤ t ≤ π,
x00 + 9x = f (t), x(0) = 0, x0 (0) = 0; f (t) =
0,
t > π.


 1
(3 sin t − sin 3t), 0 ≤ t ≤ π,
24
x(t) =
0,
t > π.

31. x00 + 2x0 + 10x = 0,

x(0) = 0, x0 (0) = 6;

[x(t) = 2e−t sin 3t, t ≥ 0]

32. x00 + 2x0 = 0,

x(0) = 1, x0 (0) = 2;

33. x00 + 3x0 + 2x = 0,
34. x00 − x0 = 2 − 2t,
35. x00 + x = 4et ,

[x(t) = 2 − e−2t , t ≥ 0]

x(0) = 1, x0 (0) = 0;

[x(t) = 2e−t − e−2t , t ≥ 0]

x(0) = 1, x0 (0) = 1;

[x(t) = et + t2 , t ≥ 0]

x(0) = 4, x0 (0) = −3;

36. x00 + x = 3 sin 2t,

x(0) = 1, x0 (0) = 1;

37. x00 + 9x = 5 cos 3t,

x(0) = 2, x0 (0) = −1;

38. x00 + x0 = 2t − 3,

x(0) = 0, x0 (0) = 1;

39. x00 + 6x0 + 9x = (2t + 1)et ,

[x(t) = 2et + 2 cos t − 5 sin t, t ≥ 0]
[x(t) = cos t + 3 sin t − sin 2t, t ≥ 0]
[x(t) = 2 cos 3t − 31 sin 3t + 56 t sin 3t, t ≥ 0]

x(0) = 5, x0 (0) = 81 ;

[x(t) = 6(1 − e−t ) + t2 − 5t, t ≥ 0]
[x(t) = 5e−3t + 15te−3t + 18 tet , t ≥ 0]

