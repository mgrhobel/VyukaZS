---
title: "reciprok_rce.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Státnice/new/MAT/ru/3,4,5/reciprok_rce.pdf"
date: 2010-05-25
type: PDF (text-based)
---

Reciproké rovnice
Reciprokou rovnicı́ rozumı́me algebraickou rovnici, která je zadaná ve tvaru, jenž popisujı́ nı́že
uvedené definice. Jejı́ název je odvozen z vlastnosti jejı́ch kořenů, pro které platı́, že existujı́-li,
pak pouze nenulové a je-li čı́slo x kořenem reciproké rovnice, pak je jejı́m kořenem také čı́slo x1
(reciproká hodnota čı́sla x).
• Definice I:
Reciprokou rovnicı́ n-tého stupně I. druhu s neznámou x rozumı́me rovnici:
an xn + an−1 xn−1 + an−2 xn−2 + ... + a2 x2 + a1 x + a0 = 0

(1)

kde n ∈ N, an 6= 0 a kde ai ∈ Z a platı́, že ak = an−k , kde k ∈ {1, 2, . . . , n}.
Přı́kladem takové reciproké rovnice I. druhu je např. rovnice:
5x4 − 26x3 + 10x2 − 26x + 5 = 0
• Definice II:
Reciprokou rovnicı́ n-tého stupně II. druhu s neznámou x rozumı́me rovnici:
an xn + an−1 xn−1 + an−2 xn−2 + ... + a2 x2 + a1 x + a0 = 0

(2)

kde n ∈ N, an 6= 0 a kde ai ∈ Z a platı́, že ak = −an−k , kde k ∈ {1, 2, . . . , n}.
Přı́kladem takové reciproké rovnice II. druhu je např. rovnice:
12x4 − 25x3 + 25x − 12 = 0
Pro reciproké rovnice sudého stupně (n = 2m) zřejmě platı́, že v rovnici I. druhu může být
koeficient am libovolný, zatı́mco v rovnici II. druhu musı́ být am = 0.

Postup řešenı́ reciproké rovnice I. druhu:
A. Je-li stupeň rovnice sudé čı́slo n = 2m (m ∈ N):
1. Vydělı́me rovnici čı́slem xm .
2. Z prvnı́ho a poslednı́ho členu, druhého a předposlednı́ho členu atd. vytkneme jejich
společný koeficient.
1 a rovnici dořešı́me.
3. Zavedeme substituci y = x + x
B. Je-li stupeň rovnice liché čı́slo n = 2m + 1 (m ∈ N):
1. Rovnice má vždy jeden kořen x = −1.
2. Pomocı́ Hornerova schematu snı́žı́me stupeň zadané rovnice a zı́skáme reciprokou
rovnici I. druhu sudého stupně.
3. Rovnici dořešı́me viz bod A.
Postup řešenı́ reciproké rovnice II. druhu:
1. Rovnice má vždy jeden kořen x = 1.
2. Pomocı́ Hornerova schematu snı́žı́me stupeň zadané rovnice a zı́skáme reciprokou rovnici
I. druhu.
3. Rovnici dořešı́me viz body A. a B. pro řešenı́ reciproké rovnice I. druhu.
1:
Poznámka k zavedenı́ substituce y = x + x
Je zřejmé, že při zavedenı́ substituce také platı́:
x2 +

1
= y2 − 2
x2

x3 +

1
= y 3 − 3y
x3

x4 +

1
= y 4 − 4y 2 + 2
x4

