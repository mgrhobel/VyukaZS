---
title: "NeurcIntegral-u%c4%8dText.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/1. Semestr/SM/Projekty/webMathematica/1.pokus/NeurcIntegral-u%c4%8dText.pdf"
date: 2008-12-19
type: PDF (text-based)
---

Primitivní funkce, neurčitý integrál, základní integrály

1

Primitivní funkce, neurčitý integrál, základní integrály
1. Definice Říkáme, že F (x) je v intervalu (a, b) primitivní funkcí k funkce f (x), jestliže pro všechna
x ∈ (a, b) platí F 0 (x) = f (x).
2. Věta Ke každé funkci f (x) spojité na (a, b) existuje v (a, b) primitivní funkce. Je jich dokonce
nekonečně mnoho. Je-li F (x) jedna z nich, pak všechny ostatní mají tvar
F (x) + C,
kde C je integrační konstanta, která je libovolná.
3. Poznámka Používáme formální zápis
Z
f (x) dx = F (x) + C,
R

f (x) dx znamená množinu všech primitivních funkcí k funkce f (x) a nazývá se neurčitý integrál
funkce f (x).

4. Poznámka Je zvykem pracovat se symbolem
výsledku připsat integrační konstantu C.
R
0
5. Platí: (F (x) + C) = f (x) ⇔ F (x) = f (x) dx.

R

f (x) dx jako s jednou z primitivních funkcí a ve

6. Příklad
0
(sin x + 5) = cos x;
0
(sin x R− 6) = cos x.
Tedy cos x dx = sin x + C.
7. Věta Přehled základních integračních vzorců
R
n+1
1. xn dx = xn+1 + C, x > 0, n ∈ R, n 6= −1.
R
2. x1 dx = ln |x| + C, x 6= 0.
R
3. ex dx = ex + C.
R
x
4. ax dx = lna a + C, a > 0, a 6= 1.
R
5. sin x dx = − cos x + C.
R
6. cos x dx = sin x + C.
R
7. sin12 x dx = −cotg x + C, x 6= kπ, k ∈ Z.
R
8. cos12 x dx = tg x + C, x 6= π2 + kπ, k ∈ Z.
R 1
9. 1+x
2 dx = arctg x + C1 = −arccotg x + C2 .
R
1
10. √1−x
dx = arcsin x + C1 = −arccos x + C2 , x ∈ (−1, 1).
2
11.
12.
13.

R
R

√ 1
dx = ln
x2 +a

¡

x+

√

¢
x2 + a + C, a > 0.

1
1
x
x2 +a2 dx = a arctg a + C,

a 6= 0.

R f 0 (x)

f (x) dx = ln |f (x)| .

Mgr. Jana Hoderová, Ph.D.

ÚM FSI v Brně, 27. 11. 2005

Primitivní funkce, neurčitý integrál, základní integrály

2

8. Poznámka Přestože ke každé spojité funkci existuje primitivní funkce, nelze v mnoha případech tuto
primitivní funkci vyjádřit pomocí elementárních funkcí.

Integrační metody
9. Věta Existují-li k funkcím f1 (x), f2 (x), f (x) primitivní funkce, pak
R
R
R
1. (f1 (x) ± f2 (x)) dx = f1 (x) dx ± f2 (x) dx.
R
R
2. k · f (x) dx = k f (x) dx, kde k je konstanta.
Jednou z integračních metod je přímá integrace.
10. Příklad Spočtěte integrály:
R 2
1. 5x√x−3 dx.
´
R³ 2
2.
3x − 2x + √1x3 dx.
3.
4.
5.
6.
7.

R 3x cos2 x−5
cos2 x

R

dx.

cotg x dx.
R √
R
R

x4 +2+x−4
dx.
x3

1
xln x dx.

x(x − 2)(x − 3) dx.

Další možností je řešení integrálů substituční metodou. Tu si ukážeme na následujících příkladech.
11. Příklad
R
1. cos(5x + 6) dx.
R
2. xln1 x dx.
R
3. sin2 x cos x dx.
R √
4. x x2 + 1 dx.
R √
3 arctg x
5.
1+x2 dx.
R
sin x
√
6.
dx.
3
1+2 cos x
R
√ 1
7.
dx.
2
x

3−ln x

12. Poznámka Počítáme-li integrály
úpravu:
sin2 x =

13. Příklad

R

R

sin2 x dx,

1 − cos 2x
,
2

R

cos2 x dx, tak před vlastní integrací nejprve použijeme

cos2 x =

1 + cos 2x
.
2

sin2 x dx.

Mgr. Jana Hoderová, Ph.D.

ÚM FSI v Brně, 27. 11. 2005

Primitivní funkce, neurčitý integrál, základní integrály

3

Velmi užitečná je i integrace per partes.
14. Věta Metoda per partes (po částech)
Mají-li funkce u(x) a v(x) v intervalu (a, b) spojitou derivaci, pak v intervalu (a, b) platí
Z
Z
u(x) · v 0 (x) dx = u(x) · v(x) − u0 (x) · v(x) dx.

(1)

15. Důkaz: Stačí si uvědomit, jak se derivuje součin funkcí u · v:
0
(u
u0 v +Ruv 0 . Nyní Robě strany rovnice zintegrujeme:
R · v) =
0
(u · v)R dx = uR0 v dx + uv 0 dx. Odtud:
u · v = u0 v dx + uv 0 dx, což je dokazované tvrzení.
16. Poznámka Z důkazu je jasně vidět, že integrace per partes může být zapsána v ekvivalentním tvaru
Z
Z
u0 (x) · v(x) dx = u(x) · v(x) − u(x) · v 0 (x) dx.

17. Poznámka Typické příklady, kdy je vhodné použít integraci per partes (pn (x) je polynom stupně n).
Značení
ze vztahu
(1):

R používáme
x
p
(x)
·
e
dx,

n
R
R pn (x) · sin x dx,  zde volíme za funkci „kterou budeme derivovatÿ polynom pn (x) = v(x).
pn (x) · cos x dx,

R

R pn (x) · ln x dx,
p
(x)
·
arcsin
x
dx,
zde volíme za funkci „kterou budeme integrovatÿ polynom pn (x) = u0 (x).
R n

pn (x) · arctg x dx,
18. Příklad
R
1. (1 + x)ex dx.
R
2. xe−x dx.
R
3. arctg x dx.
R
4. ln x dx.
R
5. cos(ln x) dx.
P (x)
Pokud integrujeme racionálně lomenou funkci R(x) = Q(x)
, pak ji nejprve převedeme na parciální
zlomky a ty již snadno zintegrujeme.

19. Příklad
R 4
2
+x−2
dx.
1. x +6x
x4 −2x3
R
x
2. (x−1)(x+1)
2 dx.
R
5
3. (2x−3)
7 dx.
4.

R 11x2 +2x−33
x2 −3

dx.

Mgr. Jana Hoderová, Ph.D.

ÚM FSI v Brně, 27. 11. 2005

Primitivní funkce, neurčitý integrál, základní integrály

4

R
Integrujeme-li goniometrické funkce, tj. R(sin x, cos x), pak nejčastěji postupujeme substitucí.
O vhodné volbě substituce rozhodneme až u konkrétního příkladu. Určitá pravidla ovšem platí obecně:
R(sinn x, cosm x), kde m je sudé číslo a n je liché číslo . . . substituce sin x = t;
R(sinn x, cosm x), kde m je liché číslo a n je sudé číslo . . . substituce cos x = t;
R(sinn x, cosm x), kde m je liché číslo a n je liché číslo . . . substituce tg x = t.
Ve všech případech lze využít tzv. univerzální substituci tg x2 = t.

20. Příklad
R
1. sin3 x dx;
R
5
x
2. cos
dx;
sin4 x
R sin x−cos x
3. sin
x+2 cos x dx;
R 2−sin x
4. 2+cos x dx.

Mgr. Jana Hoderová, Ph.D.

ÚM FSI v Brně, 27. 11. 2005

