---
title: "2706_Rovnice_vyssich_radu.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Státnice/new/MAT/ru/3,4,5/2706_Rovnice_vyssich_radu.pdf"
date: 2010-05-25
type: PDF (text-based)
---

2.7.6

Rovnice vyšších řádů

Předpoklady: 2507, 2705
Pedagogická poznámka: Pokud mám jenom trochu čas probírám látku této hodiny ve dvou
vyučovacích hodinách. V první probíráme separaci kořenů, v druhé pak snížení
stupně.
Přehled rovnic:
Řád rovnice

Tvar

Název

1

ax + b = 0

lineární

2

ax 2 + bx + c = 0

kvadratická

3
4

ax3 + bx 2 + cx + d = 0
ax 4 + bx 3 + cx 2 + dx + e = 0
ax 5 + bx 4 + cx 3 + dx 2 + ex + f = 0
….

kubická

5 a vyšší

způsob řešení (vzorec)
b
a ≠ 0, x = −
a

−b ± b2 − 4ac
2a
Cardanovy vzorce
Cardanovy vzorce

a ≠ 0 , x1,2 =

neexistuje

Cardanovy vzorce jsou velice složité, proto je nebudeme pro rovnice třetího a vyšších řádů
používat a zkusíme jiné metody.

1. Numerická metoda separace kořenů
S počítačem jednoduché, s kalkulačkou snesitelné, s papírem smrt, ale jde u všech
algebraických rovnic. Výsledek je pouze přibližný (ale snadno ho zjistíme na libovolný počet
desetinných míst).
Hledáme řešení rovnice x3 − 2 x + 5 = 0 .
Hodnoty levé strany nám přiblíží funkce y = x3 − 2 x + 5 . Jak vypadá?
• Pro velká záporná čísla jsou hodnoty záporné (kvůli zápornému výsledku třetí
mocniny x).
• Pro velká kladná čísla jsou hodnoty kladné (kvůli kladnému výsledku třetí mocniny x).
⇒ Graf funkce musí projít přes osu x. Hodnota x, kde k tomu dojde, je řešením rovnice.
Hledáme toto místo dosazováním:
Dosadíme 0
03 − 2 ⋅ 0 + 5 = 5
⇒ kořen je záporné číslo.

⇒ kořen je v intervalu ( −3; 0 ) .
( −3) − 2 ⋅ ( −3) + 5 = −16
3
Dosadíme -2 ( −2 ) − 2 ⋅ ( −2 ) + 5 = 1
⇒ kořen je v intervalu ( −3; −2 ) .
3
Dosadíme –2,5 ( −2,5 ) − 2 ⋅ ( −2,5 ) + 5 = −5, 625
⇒ kořen je v intervalu ( −2,5; −2 ) .
3
Dosadíme –2,1 ( −2,1) − 2 ⋅ ( −2,1) + 5 = −0, 061 ⇒ kořen je v intervalu ( −2,1; −2, 0 ) .
Dosadíme -3

3

A tak bychom se dosazovali dál, dokud bychom nezjistili kořen s dostatečnou přesností.

Pedagogická poznámka: Při výkladu mám na tabuli nakreslenou soustavu souřadnic a
postupně do ní dokresluji křížky s aktuálně spočítanou hodnotou. Tak je nejlépe

1

vidět, ve kterém intervalu se kořen rovnice nachází. Už od dosazování –3
diskutujeme se studenty, které číslo je nejvýhodnější vyzkoušet.

Př. 1:

Urči kořen rovnice x3 − 2 x + 5 = 0 s přesností na tři desetinná místa.

Pokračuje v dosazování z předchozího postupu:
Dosadíme –2,09

( −2,1; −2, 09 ) .
Dosadíme –2,095

( −2, 095; −2,090 ) .
Dosadíme –2,094

( −2, 09 ) − 2 ⋅ ( −2, 09 ) + 5 = 0, 0508
3

⇒ kořen je v intervalu

( −2, 095 ) − 2 ⋅ ( −2, 095 ) + 5 = −0, 005 ⇒ kořen je v intervalu
3

( −2, 094 ) − 2 ⋅ ( −2, 094 ) + 5 = 0, 0061 ⇒ kořen je v intervalu
3

( −2, 095; −2,094 ) ⇒ určili jsme kořen s přesností na tři desetinná čísla.

Pedagogická poznámka: Můžete vyhlásit soutěž o odhalení kořenu na minimální počet
dosazení. Při kontrole pak dávám pozor nejen na pochopení základního algoritmu,
ale i na logickou volbu čísel na dosazování.
Správná hodnota na 8 desetinných míst je K = {−2, 094551482} .
Graf funkce y = x3 − 2 x + 5 je na obrázku.

2

Najdi pomocí metody separace kořenů, alespoň jeden kořen rovnice
2 x 3 − 9 x 2 − 14 x + 60 = 0 s přesností na jedno desetinné místo.

Př. 2:

Rovnice má určitě alespoň jeden kořen (funkce y = 2 x 3 − 9 x 2 − 14 x + 60 je pro velká kladná x
kladná pro velká záporná x záporná ⇒ musí projít přes nulu).
Spočítáme hodnoty pro několik jednoduchých čísel:
x=0
2 ⋅ 03 − 9 ⋅ 02 − 14 ⋅ 0 + 60 = 60 ⇒ v intervalu ( 0; ∞ ) není žádný nebo jsou tam dva kořeny.
x = −3
2 ⋅ ( −3) − 9 ⋅ ( −3 ) − 14 ⋅ ( −3) + 60 = −33 ⇒ v intervalu ( −3; 0 ) je alespoň jeden kořen.
3

2

x = −2
3
2
2 ⋅ ( −2 ) − 9 ⋅ ( −2 ) − 14 ⋅ ( −2 ) + 60 = 36 ⇒ v intervalu ( −3; −2 ) je alespoň jeden kořen.
x = −2,5
2 ⋅ ( −2,5 ) − 9 ⋅ ( −2,5 ) − 14 ⋅ ( −2,5 ) + 60 = 7,5 ⇒ v intervalu ( −3; −2,5 ) je alespoň jeden
kořen.
x = −2, 6
3

2

2 ⋅ ( −2, 6 ) − 9 ⋅ ( −2, 6 ) − 14 ⋅ ( −2, 6 ) + 60 = 0, 408 ⇒ v intervalu ( −3; −2, 6 ) je alespoň jeden
kořen.
x = −2, 65
3

2

2 ⋅ ( −2, 65 ) − 9 ⋅ ( −2, 65 ) − 14 ⋅ ( −2, 65 ) + 60 = −3, 3.. ⇒ kořen je v intervalu ( −2, 65; −2, 6 )
3

2

⇒ zaokrouhleno na jedno desetinné místo má hledaný kořen hodnotu x = −2, 6 .
x=3

2 ⋅ ( 3) − 9 ⋅ ( 3) − 14 ⋅ ( 3) + 60 = −9 ⇒ rovnice má ještě dva kořeny:
3

•
•

2

v intervalu ( 0;3) - přesná hodnota 2,5,

v intervalu ( 3;∞ ) - přibližná hodnota 4,6.

S přesností na deset desetinných míst můžeme napsat
K = {−2, 605551275; 2,5; 4, 605551275} .

2. Metoda snížení stupně uhádnutím kořene (kořenů)
U kvadratických rovnic:
Když rozložíme rovnici na součin, najdeme kořeny:
x 2 − 3 x − 4 = 0 ⇒ ( x − 4)( x + 1) = 0 ⇒ x1 = 4 , x2 = −1
Opačně, když najdeme kořeny, můžeme rozložit na součin.
Máme rovnici: x3 − 6 x 2 + 11x − 6 = 0 .
Zkusíme uhádnout dosazováním jeden z kořenů a využít ho na rozklad ⇒ druhá část
rozkladu bude už pouze kvadratická a půjde řešit vzorcem.
Hledáme kořen: zkoušíme čísla, která se snadno dosazují - 0,1,-1,2,-2 atd. (většinou nemá
smysl zkoušet za 3 a –3).
Snadno uhádneme, že jeden z kořenů je 1: 13 − 6 ⋅12 + 11 ⋅1 − 6 = 0
Musí platit: x3 − 6 x 2 + 11x − 6 = ( x − x1 )( x 2 + px + q ) = ( x − 1)( x 2 + px + q ) .
3

Problém: Neznáme druhý člen v rozkladu. Jak určit čísla p a q ?
a) vydělením
Upravíme rovnost:
x3 − 6 x 2 + 11x − 6 = ( x − 1)( x 2 + px + q) / : ( x − 1)

( x − 6 x + 11x − 6 ) : ( x − 1) = ( x + px + q)
3

2

2

Vydělíme: ( x 3 − 6 x 2 + 11 − 6) : ( x − 1) = x 2 − 5 x + 6
−( x 3 − x 2 )
−5 x 2 + 11x − 6
− ( −5 x 2 + 5 x )
6x − 6
−(6 x − 6)
0 Když nevyjde zbytek 0, pak jsme špatně dělili nebo hádali kořen.
3
2
( x − 6 x + 11x − 6 ) = ( x − 1)( x 2 − 5 x + 6) = 0
( x − 1)( x − 2)( x − 3) = 0 ⇒ K = {1, 2,3}

b) zpětným násobení
x3 − 6 x 2 + 11x − 6 = 0

( x − 1)( x 2 + px + q) = 0

Jsou to ty samé rovnice, když to roznásobíme, musí se rovnat.

( x − 1)( x 2 + px + q ) = x 3 + px 2 + qx − x 2 − px − q = x3 + x 2 ( p − 1) + x(q − p ) − q = 0
Teď napíšeme rovnice pod sebe a srovnáme je:
x3
− 6 x 2 + 11x − 6 = 0
.
x3 + x 2 ( p − 1) + x(q − p) − q = 0
Aby byly rovnice stejné musí být před stejnými mocninami x stejná čísla:
11 = q − p
−6 = p − 1
−6 = − q
11 = q − ( −5 )
−5 = p
6=q
6=q
Máme 3 rovnice pro 2 neznámé ⇒ poslední rovnice je kontrola správnosti předchozích kroků,
musí nám vyjít.
( x3 − 6 x2 + 11x − 6 ) = ( x − 1)( x 2 − 5 x + 6) = 0

( x − 1)( x − 2)( x − 3) = 0 ⇒ K = {1, 2,3}

Pedagogická poznámka: Při řešení následujících příkladů náhodně střídám obě metody. Po
studentech chci, aby si obě alespoň jednou samostatně vyzkoušeli a pak mohou
používat tu, která jim více vyhovuje.
Př. 3:

Vyřeš rovnici x3 + 3 x 2 + x − 2 = 0 .

Hádáme kořen: x1 = −2
x3 + 3 x 2 + x − 2 = ( −2 ) + 3 ( −2 ) + ( −2 ) − 2 = −8 + 12 − 2 − 2 = 0
Hledáme rozklad pomocí zpětného násobeni:
x3 + 3 x 2 + x − 2 = ( x + 2 ) ( x 2 + px + q ) = x3 + px 2 + qx + 2 x 2 + 2 px + 2q
3

2

4

x3 +

3x 2 +

1x − 2 = 0

x + ( p + 2 ) x + ( q + 2 p ) x + 2q = 0
3

2

1= q +2p

3= p+2

1= q +2
−1 = q

1= p

−2 = 2 q
−1 = q

x3 + 3 x 2 + x − 2 = ( x + 2 ) ( x 2 + x − 1) .
Určíme kořeny rovnice x 2 + x − 1 = 0 :
2
−b ± b 2 − 4ac −1 ± 1 − 4 ⋅1 ⋅ ( −1) −1 ± 5
x2,3 =
=
=
2a
2 ⋅1
2
−1 ± 5
−1 ± 5
x2 =
x3 =
.
2
2
−1 − 5 −1 + 5 

K = −2;
;

2
2 


Pedagogická poznámka: Při řešení následujících příkladů se snažím, aby se studenti sami
snažili vyrovnat s problémy, které další příklady přinášejí (6 před x3 v příkladu 4 a
x 4 v dalších příkladech) samostatně. Jde o cvičení adaptace na částečně se měnící
podmínky.
Př. 4:

Vyřeš rovnici 6 x 3 − 7 x 2 − x + 2 = 0 .

Hádáme kořen: x1 = 1
6 x3 − 7 x 2 − x + 2 = 6 ⋅13 − 7 ⋅12 − 1 + 2 = 6 − 7 − 1 − 2 = 0 .
Hledáme rozklad pomocí dělení mnohočlenů:
( 6 x3 − 7 x2 − x + 2 ) : ( x − 1) = 6 x2 − x − 2
− ( 6 x3 − 6 x 2 )

− x2 − x + 2

− ( − x2 + x )

− 2x + 2
− ( −2 x + 2 )
0

( 6 x − 7 x − x + 2 ) = ( x − 1) ( 6 x − x − 2 ) .
3

2

2

Určíme kořeny rovnice 6 x 2 − x − 2 = 0 :

−b ± b 2 − 4ac 1 ± 1 − 4 ⋅ 6 ⋅ ( −2 ) 1 ± 49 1 ± 7
x2,3 =
=
=
=
2a
12
12
12
1+ 7 2
1− 7
1
x2 =
=
x3 =
=−
12
3
12
2
 2 1
K = 1; ; − 
 3 2

5

Poznámka: Pokud bychom zjišťovali rozklad zpětným násobením, musíme dát pozor:
( 6 x3 − 7 x 2 − x + 2 ) = ( x − 1) ( 6 x2 + px + q ) = 6 x3 + px2 + qx − 6 x 2 − px − q a dál jako předtím.
Před x 2 v hledaném kvadratickém trojčlenu musí být 6, abychom po zpětném násobení
získali 6 x3 .

Pedagogická poznámka: Někteří studenti sami (a to je třeba ocenit) zjistí, že 6 před x3 může
způsobit problémy a rovnici vydělí šesti. Tím vyřeší problém se šestkou, ale
v rovnici se objeví zlomky, které komplikují výpočty. Řešíme potom, který ze
způsobů řešení je z hlediska snadnosti výpočtu nejvýhodnější.
Vyřeš rovnici x 4 − 6 x 3 + 8 x 2 + 6 x − 9 = 0 .

Př. 5:

Hádáme kořen: x1 = 1 .

x 4 − 6 x 3 + 8 x 2 + 6 x − 9 = 14 − 6 ⋅13 + 8 ⋅12 + 6 ⋅1 − 9 = 1 − 6 + 8 + 6 − 9 = 0
Musíme uhádnout ještě jeden kořen, abychom stupeň rovnice snížili o dva.
Hádáme kořen: x1 = −1 .
x 4 − 6 x 3 + 8 x 2 + 6 x − 9 = ( −1) − 6 ⋅ ( −1) + 8 ⋅ ( −1) + 6 ⋅ ( −1) − 9 = 1 + 6 + 8 − 6 − 9 = 0
Hledáme rozklad pomocí zpětného násobeni:
x 4 − 6 x 3 + 8 x 2 + 6 x − 9 = ( x + 1)( x − 1) ( x 2 + px + q ) = ( x 2 − 1)( x 2 + px + q )
4

3

2

= x 4 + px3 + qx 2 − x 2 − px − q
x 4 − 6 x3 +

8x2 + 6 x − 9 = 0

x 4 + px3 + ( q − 1) x 2 − px − q = 0
8 = q −1
−6 = p
9=q

6 = −p

−9 = − q

−6 = p

9=q

x − 6 x + 8 x + 6 x − 9 = ( x + 1)( x − 1) ( x − 6 x + 9 ) = 0
4

3

2

2

Určíme kořeny rovnice x 2 − 6 x + 9 = 0 : x 2 − 6 x + 9 = ( x − 3) ⇒ x3 = x4 = 3
2

K = {1; − 1;3}

Pedagogická poznámka: Příklad je možné také řešit také ve dvou krocích vždy o jeden
stupeň. V takovém případě budeme při roznásobování hledat kubický čtyřčlen
x3 + px 2 + qx + r .
Př. 6:

Vyřeš rovnici 2 x 4 − 4 x3 − 3 x 2 + 7 x − 2 = 0 .

Hádáme kořen: x1 = 1 .
2 x 4 − 4 x3 − 3 x 2 + 7 x − 2 = 2 ⋅14 − 4 ⋅13 − 3 ⋅12 + 7 ⋅1 − 2 = 2 − 4 − 3 + 7 − 2 = 0
Musíme uhádnout ještě jeden kořen, abychom stupeň rovnice snížili o dva.
Hádáme kořen: x1 = 2 .
2 x 4 − 4 x 3 − 3 x 2 + 7 x − 2 = 2 ⋅ 24 − 4 ⋅ 23 − 3 ⋅ 22 + 7 ⋅ 2 − 2 = 32 − 32 − 12 + 14 − 2 = 0
Hledáme rozklad pomocí zpětného násobeni:

6

2 x 4 − 4 x 3 − 3 x 2 + 7 x − 2 = ( x − 1)( x − 2 ) ( 2 x 2 + px + q ) = ( x 2 − 3x + 2 )( 2 x 2 + px + q )
= 2 x 4 + px 3 + qx 2 − 6 x3 − 3 px 2 − 3qx + 4 x 2 + 2 px + q =
= 2 x 4 + ( p − 6 ) x 3 + ( q − 3 p + 4 ) x 2 + ( −3q + 2 p ) + q
− 4 x3

2x4

− 3x2

+ 7x − 2 = 0

2 x 4 + ( p − 6 ) x 3 + ( q − 3 p + 4 ) x 2 + ( −3q + 2 p ) x + q = 0
7 = −3q + 2 p
−3 = q − 3 p + 4
−4 = p − 6
7 = −3 ⋅ ( −1) + 2 ⋅ 2
−3 = q − 3 ⋅ 2 + 4
2= p
−1 = q
7=7
4
3
2
2
2 x − 4 x − 3 x + 7 x − 2 = ( x − 1)( x − 2 ) ( 2 x + 2 x − 1)

−2 = 2 q
−1 = q

Určíme kořeny rovnice 2 x 2 + 2 x − 1 = 0 :
2
−b ± b 2 − 4ac −2 ± 2 − 4 ⋅ 2 ⋅ ( −1) −2 ± 12 −2 ± 2 3 −1 ± 3
x3,4 =
=
=
=
=
2a
2⋅2
4
4
2
−1 − 3
−1 + 3
x3 =
x4 =
2
2
 −1 − 3 −1 + 3

K =
;
;1; 2 
2
 2


Př. 7:

Vyřeš rovnici 12 x 4 − 25 x 3 − 5 x 2 + 25 x − 7 = 0 .

Hádáme kořen: x1 = 1 .
12 x 4 − 25 x3 − 5 x 2 + 25 x − 7 = 12 ⋅14 − 25 ⋅13 − 5 ⋅12 + 25 ⋅1 − 7 = 12 − 25 − 5 + 25 − 7 = 0
Hledáme rozklad pomocí dělení mnohočlenů:
(12 x 4 − 25 x3 − 5 x2 + 25 x − 7 ) : ( x − 1) = 12 x3 − 13x2 − 18 x + 7

− (12 x 4 − 12 x 3 )

− 13 x3 − 5 x 2 + 25 x − 7

− ( −13 x3 + 13 x 2 )

− 18 x 2 + 25 x − 7

− ( −18 x 2 + 18 x )

7x − 7
− (7x − 7)
0

12 x − 25 x − 5 x + 25 x − 7 = ( x − 1) (12 x3 − 13 x 2 − 18 x + 7 ) ⇒
4

3

2

Řešíme rovnici: 12 x 3 − 13 x 2 − 18 x + 7 = 0
Hádáme kořen: x2 = −1
12 x 3 − 13 x 2 − 18 x + 7 = 12 ⋅ ( −1) − 13 ⋅ ( −1) − 18 ⋅ ( −1) + 7 = −12 − 13 + 18 + 7 = 0
Hledáme rozklad pomocí dělení mnohočlenů:
3

2

7

(12 x − 13x − 18 x + 7 ) : ( x + 1) = 12 x − 25 x + 7
− (12 x + 12 x )
3

2

3

2

2

− 25 x 2 − 18 x + 7

− ( −25 x 2 − 25 x )

7x + 7
− (7x + 7)
0

(12 x − 13x − 18x + 7 = 0 ) = ( x + 1) (12 x − 25 x + 7 )
3

2

2

Určíme kořeny rovnice 12 x 2 − 25 x + 7 = 0 :

−b ± b 2 − 4ac 25 ± 625 − ( 4 ⋅12 ⋅ 7 ) 25 ± 289 25 ± 17
=
=
=
2a
24
24
24
25 + 17
3
25 − 17 1
x3 =
=1
x4 =
=
24
4
24
3
3 1

K = 1; − 1;1 ; 
4 3

x3,4 =

Shrnutí: Rovnice třetího nebo vyššího řádu už neřešíme pomocí vzorců.

8

