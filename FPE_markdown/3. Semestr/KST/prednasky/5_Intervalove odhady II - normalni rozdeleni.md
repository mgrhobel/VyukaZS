---
title: "5_Intervalove odhady II - normalni rozdeleni.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/5_Intervalove odhady II - normalni rozdeleni.pdf"
date: 2009-12-27
type: PDF (text-based)
---

3.1 Konstrukce intervalových odhadů pro případ normálního
rozdělení
Předpokládáme , že náhodný výběr pochází z populace , která je popsána pomocí
rozdělení N( µ ; σ2 ) . Protože toto rozdělení je jednoznačně určeno dvěma parametry ,
musíme při konstrukci intervalů spolehlivosti vždy rozlišovat dva případy pro známý či
neznámý druhý parametr.
Nejdříve začněme konstrukcí intervalů spolehlivosti pro střední hodnotu µ. Budeme
tedy rozlišovat dva případy :
1.Parametr σ2 je známý . Podle znalostí z předchozích kapitol víme, že náhodná

 σ2 
X −µ
N  µ ;  , proto je po znormování
. n N ( 0;1) .
σ
n 

Můžeme tedy na konstrukci intervalového odhadu použít právě tuto funkci . Budeme
dále symbolem uβ označovat β kvantil normovaného normálního rozdělení. Potom je interval

veličina X

x −u α.
1−

2

σ
n

< µ < x +u α.
1−

2

σ

(3.7)

n

100(1- α )% - ním oboustranným intervalem spolehlivosti . Hodnota x nyní i dále
je realizace náhodné veličiny X pomocí náhodného výběru.
Podobně nyní odvoďme i jednostranné intervaly spolehlivosti. Pravostranný
−∞ < µ < x + u1-α .

σ

(3.8)

n

a levostranný
x − u1−α .

σ
n

< µ < +∞

(3.9)

Na základě takto stanovených intervalů spolehlivosti spočteme několik příkladů.
Příklad 3.1
Nechť jsou dána data z populace typu normální rozdělení s σ2 =3. Data jsou uvedena
v následující tabulce :
X
četnos
t

2

3

4

5

6

7

8

9

1

3

3

8

9

6

5

2

Stanovíme nejprve hodnotu bodového odhadu střední hodnoty , ta je rovna
x 5,8649 , dále stanovíme hodnotu n = 39. V dalším zjistíme hodnoty nejprve
oboustranných intervalů spolehlivosti pro různé hodnoty α , výsledky uvedeme v tabulce
1-α
0,95
0,96

A
B
5,31 6,42
5,28 6,45

0,99 5,13 6,60
0,995 5,07 6,66
Podobně do stejné tabulky vložíme hodnoty mezí pro levostranné a pravostranné
intervaly spolehlivosti
levostranný interval
A
1-α
0,9
5,50
0,95
5,40
0,99
5,20
0,995
5,13

pravostranný interval
B
1-α
0,9
6,23
0,95
6,33
0,99
6,53
0,995
6,60

2.Parametr σ2 není známý.
Potom je opět z předchozích kapitol známo, že náhodná veličina

X −µ
. n je typu
s

studentova rozdělení s n-1 stupni volnosti - t(n-1). Odtud již můžeme opět provést konstrukci
jednotlivých typů intervalů spolehlivosti. Tedy
x −t α.
1−

2

s
s
< µ < x +t α.
1
−
n
n
2

(3.10)

je oboustranný 100(1- α )% - ní interval spolehlivosti. Dále
s
(3.11)
−∞ < µ < x + t1-α .
n
je pravostranným 100(1-α)% intervalem spolehlivosti a
s
(3.12)
x − t1−α .
< µ < +∞
n
je levostranným 100(1-α)% intervalem spolehlivosti . Hodnoty tβ jsou příslušné
kvantily studentova rozdělení s (n-1) stupni volnosti. Podotkněme, že pro hodnoty n > 35
většinou provádíme náhradu studentova rozdělení rozdělením normálním normovaným. Jistě
můžeme tuto náhradu provést vždy pro n > 100.
Příklad 3.2
Nechť máme nyní dány stejné hodnoty jako v předchozím příkladu s tím , že nemáme
informaci o velikosti rozptylu σ2 populace. Potom musíme příslušné hodnoty daných
intervalů spočítat přímo ze vztahů (3.10) – (3.12). Výsledky se opět budeme snažit zobrazit
přímo v tabulkách , samostatně pro oboustranný interval spolehlivosti a pro jednostranné
intervaly.
1-α
0,95
0,96
0,99

A
B
5,20 6,53
5,18 6,55
5,02 6,71

0,995 4,95 6,78
levostranný interval
A
1-α
0,9
5,29
0,95
5,10
0,99
5,861
0,995
5,02

pravostranný interval
B
1-α
0,9
6,44
0,95
6,63
0,99
5,868
0,995
6,71

V druhé části tohoto oddílu ukážeme konstrukci intervalu spolehlivosti
pro směrodatnou odchylku σ . Budeme opět vycházet z předpokladu , že populace je popsána
jako normální rozdělení N( µ ; σ2 ). Budeme opět rozlišovat dva případy :
1.Střední hodnota µ je známa. Potom využijeme vztahu (2.6) tzv. výběrového
rozptylu při známé střední hodnotě µ . Tuto statistiku je možno použít k bodovému odhadu σ2
n.s02
χ 2 s n stupni
je
typově
rozdělení
. Podle konstrukce obecných rozdělení je zřejmé, že
2

σ

volnostmi . Pro ověření tuto náhodnou veličinu napište jako součet nezávislých náhodných
veličin typu ( N ( 0;1) ) . Tuto znalost nyní využijeme nejdříve pro konstrukci oboustranného
2

100(1-α)% -ního intervalu spolehlivosti :
n.s02

χ2 α
1−

<σ2 <

2

n.s02

(3.13)

χ α2

2

Podobně provedeme konstrukci intervalu pravostranného
n.s 2
(3.14)
0 < σ 2 < 20

χα

a levostranného
n.s 02
< σ 2 < +∞
2

(3.15).

χ1−α

Hodnoty χ β2 je hodnota kvantilu β rozdělení χ o n stupních volnosti. Je nutno ovšem
2

upozornit, že případy kdy známe střední hodnotu populace a neznáme naopak rozptyl
populace se v reálné praxi prakticky vůbec nevyskytují , proto je nebudeme dále brát v úvahu.
2.Střední hodnota µ není známa. Populace je však popsána jako rozdělení typu
N( µ ; σ2 ). K bodovému odhadu hodnoty σ2 používáme podle předchozí kapitoly statistiku s ,
která je definována v předchozí kapitole vztahem (2.7) . Pokud provedeme úpravu náhodné
( n − 1) .s 2 získáme náhodnou veličinu typu χ 2 o n-1 stupních volnosti . Na
veličiny s na
2

σ

základě znalosti tohoto rozdělení je tedy možno provést konstrukci všech typů intervalů
spolehlivosti . Nejdříve tedy odvodíme oboustranný 100(1-α)% - ní interval spolehlivosti (

opět jako v předchozích vztazích bude χ β hodnota kvantilu β rozdělení χ tentokrát o n - 1
stupních volnosti):
2

(n − 1).s 2

χ2 α
1−

2

<σ2 <

( n − 1).s 2

χ α2

2

(3.16)

2

Podobně odvodíme také pravostranný interval spolehlivosti jako
(n -1).s 2
0<σ2 <
χα2
(3.17)
a levostranný interval spolehlivosti
(n -1).s 2
< σ 2 < +∞
2

χ1−α

(3.18)

Příklad 3.3
Provedli jsme náhodný výběr z populace N(µ ; σ2) , hodnota n = 20 , dále jsme zjistili
hodnotu s = 0,1. Sestrojme 95% oboustranný interval spolehlivosti pro rozptyl.
Řešení:
Protože neznáme střední hodnotu µ použijeme vzorce (3.16). Zjistěme nejdříve dané
hodnoty, které potřebujeme pro stanovení vztahu (3.16). Tedy:
2
2
S2 = 0,121 ; χ 0,025
= 8,91 ; χ 0,975
= 32,9 ; n – 1 = 19 , po dosazení do vzorce
0, 006 < σ 2 < 0, 021 neboli 0, 07746 < σ < 0,144914 .
V našem případě se snažíme naměřená data diskrétního charakteru převést na model
spojitý , velmi často za podmínky použití odmocniny z konečnostního násobitele viz věta 2.3 ,
tedy za podmínky , že n ≤ 0, 05 provedeme úpravy výrazů (3.7) až (3.12) tak, že je násobíme
N
N −n
. Této úpravě se někdy říká také oprava na výběr bez vracení. Například výraz
N −1
(3.10) s danou opravou je
x −t α.
1−

2

s
N-n
s
N-n
.
< µ < x +t α.
.
1−
n N -1
n N -1
2

(3.10’).

