---
title: "10_Bootstrap.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/10_Bootstrap.pdf"
date: 2009-12-27
type: PDF (text-based)
---

3.7 Metoda bootstrap
Jde o mnoho násobné využití simulace náhodných výběrů z množiny náhodných
výběrů. Předpokládejme , že jsme provedli náhodný výběr z populace , o níž nemáme žádné
informace. Tento výběr je složen z prvků x1, … ,xn . Jako první krok provedeme pomocí
generátoru náhodných čísel mnohonásobný výběr z této množiny o několika desítek tisíc
prvků ( nebo více) . Tím získáme dočasnou množinu M . Z této množiny budeme metodou
Monte Carlo vybírat konstantní počet prvků ( např. 10 ) a počítat jejich průměr ( je to bodový
odhad skutečné střední hodnoty ) . Takovéto hodnoty soustředíme v další množině T . Z této
množiny můžeme potom vytvářet obrazy intervalových odhadů pomocí popisu rozložení
prvků v T , na základě relativní četnosti.
Příklad 3.8
Níže uvedená data byla vybrána z populace .
4 5

4,3

5,2 6

5,5

4,8

4,2

4,3

7,5

4,6

4,5

5,2

5,3

5,2

5,1 6 5

Provedli jsme 26 000 výběrů z této 18 – ti členné množiny . Tím jsme získali 26 000
representantů . Z nich jsme metodou Monte Carlo vybrali náhodně vždy 10 prvků a z nich
jsme spočítali hodnotu průměru ( jde o bodový odhad střední hodnoty ) . Tuto metodu jsme
mnohokrát opakovali a získáme hodnoty , které můžeme zobrazit v histogramu nebo z nich
získat intervalový odhad na dané hladině významnosti.
Zpracovaná tabulka údajů, u hodnot a , b jsou uvedeny intervalové odhady provedené
pomocí (3.46) , hladina významnosti je uvedena u buňky alfa. V dalších sloupcích jsou
zobrazeny postupně nalezené hodnoty , jejich četnosti , kumulativní četnosti a relativní
kumulativní četnosti . Barevný proužek vpravo popisuje intervalový odhad na dané hladině
významnosti .

alfa=

0,05

4,2
0
0
4,3
0
0
4,4
6
6
4,5 58
64
a= 5,505749 4,6 248 312
4,7 837 1149
b= 4,68314 4,8 1873 3022
4,9 3058 6080
5 3889 9969
5,1 4119 14088
5,2 3733 17821
5,3 2946 20767
5,4 2115 22882
5,5 1379 24261
5,6 846 25107
5,7 445 25552
5,8 240 25792
5,9 121 25913
6 54 25967
6,1 23 25990
6,2 10 26000

0
0
0,000231
0,002462
0,012
0,044192
0,116231
0,233846
0,383423
0,541846
0,685423
0,798731
0,880077
0,933115
0,965654
0,982769
0,992
0,996654
0,998731
0,999615
1

Níže je sestrojen z uvedených údajů graf , který popisuje výše uvedený intervalový
odhad.

Graf četností
4200

3700

3200

2700

2200

1700

1200

700

200

-300

4,2

4,3

4,4

4,5

4,6

4,7

4,8

4,9

5

5,1

5,2

5,3

5,4

5,5

