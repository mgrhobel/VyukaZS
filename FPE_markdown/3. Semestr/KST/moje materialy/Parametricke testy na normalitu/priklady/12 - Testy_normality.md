---
title: "12 - Testy_normality.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/moje materialy/Parametricke testy na normalitu/priklady/12 - Testy_normality.pdf"
date: 2010-01-20
type: PDF (text-based)
---

Národní informační středisko
pro podporu jakosti

OVĚŘOVÁNÍ PŘEDPOKLADU
NORMALITY

Doc. Ing. Eva Jarošová, CSc.
Ing. Jan Král

Používané metody
n

statistické testy:
Chí-kvadrát test dobré shody
n Kolmogorov - Smirnov
n Shapiro - Wilk
n Anderson - Darling
n Ryan - Joiner
n

n

grafické metody:
Histogram
n Pravděpodobnostní graf
n Q - Q graf
n P - P graf
n

Histogram
Histogram sestrojený na základě dostatečného
počtu hodnot pocházejících z normálního
rozdělení má charakteristický tvar, jehož
modelem je Gaussova křivka.
Příklad histogramu sestrojeného z 10 000
hodnot z normálního rozdělení se střední
hodnotou µ=30 a směrodatnou odchylkou σ=3
je na následujícím obrázku.

30,0

0
41,3

40,3

39,3

38,3

37,3

36,3

35,3

34,3

33,3

32,3

31,3

30,3

29,3

28,3

27,3

26,3

25,3

24,3

23,3

22,3

21,3

20,3

19,3

18,3

Histogram

800

700

600

500

400

300

200

100

Výběry rozsahu n = 25
ze základního souboru s normálním rozdělením µ = 30 a σ = 3
9

9

9

8

8

8

7

7

7

6

6

6

5

5

5

4

4

4

3

3

3

2

2

2

1

1

1

0

0
20

22

24

26

28

30

32

34

36

38

40

0
20

22

24

26

28

30

32

34

36

38

40

9

9

9

8

8

8

7

7

7

6

6

6

5

5

5

4

4

4

3

3

3

2

2

2

1

1

1

0

0
20

22

24

26

28

30

32

34

36

38

40

22

24

26

28

30

32

34

36

38

40

20

22

24

26

28

30

32

34

36

38

40

20

22

24

26

28

30

32

34

36

38

40

0
20

22

24

26

28

30

32

34

36

38

40

9

8

9

8

7

8

7

6

6

20

7
6

5

5

5
4
4

4
3

3

3

2

2

2

1

1

1

0

0

20

22

24

26

28

30

32

34

36

38

40

0
20

22

24

26

28

30

32

34

36

38

40

Výběry rozsahu n = 50
ze základního souboru s normálním rozdělením µ = 30 a σ = 3
18

18

18

16

16

16

14

14

14

12

12

12

10

10

10

8

8

8

6

6

6

4

4

4

2

2

2

0

0
20

22

24

26

28

30

32

34

36

38

40

0
20

22

24

26

28

30

32

34

36

38

40

18

18

18

16

16

16

14

14

14

12

12

12

10

10

10

8

8

8

6

6

6

4

4

4

2

2

2

0

0
20

22

24

26

28

30

32

34

36

38

40

22

24

26

28

30

32

34

36

38

40

18

18

16

16

16

14

14

14

12

12

12

10

10

10

8

8

8

6

6

6

4

4

4

2

2

2

0

0
22

24

26

28

30

32

34

36

38

40

22

24

26

28

30

32

34

36

38

40

20

22

24

26

28

30

32

34

36

38

40

20

22

24

26

28

30

32

34

36

38

40

0
20

18

20

20

0

20

22

24

26

28

30

32

34

36

38

40

Výběry rozsahu n = 100
ze základního souboru s normálním rozdělením µ = 30 a σ = 3
35

35

35

30

30

30

25

25

25

20

20

20

15

15

15

10

10

10

5

5

5

0

0

0
20

22

24

26

28

30

32

34

36

38

40

20

22

24

26

28

30

32

34

36

38

40

35

35

35

30

30

30

25

25

25

20

20

20

15

15

15

10

10

10

5

5

5

0

0
20

22

24

26

28

30

32

34

36

38

40

22

24

26

28

30

32

34

36

38

40

35

35

30

30

30

25

25

25

20

20

20

15

15

15

10

10

10

5

5

5

0
20

22

24

26

28

30

32

34

36

38

40

22

24

26

28

30

32

34

36

38

40

20

22

24

26

28

30

32

34

36

38

40

20

22

24

26

28

30

32

34

36

38

40

0

20

35

0

20

0
20

22

24

26

28

30

32

34

36

38

40

Výběry rozsahu n = 200
ze základního souboru s normálním rozdělením µ = 30 a σ = 3
60

60

60

50

50

50

40

40

40

30

30

30

20

20

20

10

10

10

0

0
20

22

24

26

28

30

32

34

36

38

40

0
20

22

24

26

28

30

32

34

36

38

40

60

60

60

50

50

50

40

40

40

30

30

30

20

20

20

10

10

10

0

0
20

22

24

26

28

30

32

34

36

38

40

22

24

26

28

30

32

34

36

38

40

60

60

50

50

50

40

40

40

30

30

30

20

20

20

10

10

10

0
20

22

24

26

28

30

32

34

36

38

40

22

24

26

28

30

32

34

36

38

40

20

22

24

26

28

30

32

34

36

38

40

20

22

24

26

28

30

32

34

36

38

40

0
20

60

0

20

0
20

22

24

26

28

30

32

34

36

38

40

Zhodnocení
Všechny uvedené histogramy představují náhodné
výběry z normálního rozdělení se střední hodnotou µ = 30
a směrodatnou odchylkou σ = 3.
Vidíme, že čím je větší rozsah výběru n, tím lépe
odpovídá výběrové rozdělení, znázorněné histogramem,
rozdělení v základním souboru, znázorněnému hustotou
pravděpodobnosti.
Při běžně používaném rozsahu n=100 nemusí být
vizuální posouzení objektivní a tvar histogramu může být
navíc ovlivněn volbou mezí intervalu.

Testy dobré shody
Pomocí testů dobré shody objektivně posoudíme, zda je možno
považovat předpoklad normálního rozdělení za splněný.
Testovaná hypotéza
H0: Náhodný výběr pochází ze základního souboru s normálním
rozdělením
Rozlišují se dva případy:
a) Model normálního rozdělení je plně specifikován, tj. jsou dány
střední hodnota µ a rozptyl σ2.
b) Model normálního rozdělení není plně specifikován, střední
hodnota a rozptyl se odhadnou z výběrových hodnot.
Rozdíl mezi plně a neúplně specifikovaným modelem se projeví
na rozdělení testové statistiky a tedy při rozhodování o tom, zda
vypočtená hodnota testové statistiky je či není v kritickém oboru.
Alternativní hypotéza
a) H1: náhodný výběr nepochází ze základního souboru s normálním
rozdělením s danými parametry µ a σ.
b) H1: náhodný výběr nepochází ze základního souboru s normálním
rozdělením

Chí - kvadrát test
§
§

Náhodný výběr rozsahu n je rozdělen do k intervalů s četnostmi
nj (j = 1, 2, ... , k), horní meze intervalů označíme xj.
Vypočteme teoretické třídní četnosti za předpokladu, že výběr
pochází ze základního souboru s normálním rozdělením N(µ, σ2):
Horní meze xj třídních intervalů převedeme na hodnoty normované
proměnné

uj =

xj − µ
σ

,

§

Není-li model plně specifikován, použijeme místo parametru µ
výběrový průměr x a místo parametru σ výběrovou
směrodatnou odchylku s ;

§

Pro každé j vyhledáme odpovídající hodnoty distribuční funkce
normovaného normálního rozdělení φ(uj);

§

Určíme teoretické relativní a absolutní třídní četnosti
πj = φ(uj) – φ(uj-1)

§

a

n πj ;

Intervaly, jejichž teoretická absolutní četnost
n·πj ≤ 5 sloučíme se sousedními intervaly tak, aby byla
splněna podmínka n·πj > 5

§

Pro redukovaný počet tříd k° vypočteme výrazy

( n − nπ )
j

2

;

j

nπ j
§

Jejich součtem (přes redukovaný počet tříd k°) dostaneme
hodnotu testové statistiky
ko

( n − nπ )

j =1

nπ j

χ =∑
2

j

j

2

§ Kritický obor pro test normality, na hladině významnosti α , je

χ2

>

χ12−α ( k o − c − 1)

kde χ1−α ( k − c − 1) je (1-α) - kvantil rozdělení χ2
pro ν = k° - c - 1 stupňů volnosti, c je počet odhadovaných
parametrů
2

o

§ U plně specifikovaného modelu je c = 0.
§ Ověřujeme-li jen tvar normálního rozdělení (neúplně specifikovaný
model) a parametry µ a σ2 odhadujeme z výběrových hodnot,
je c = 2.

PŘÍKLAD 1
V následující tabulce je demonstrován postup výpočtu testové
charakteristiky χ2 pro náhodný výběr rozsahu n = 100, ve kterém
pozorované hodnoty byly roztříděny do k = 8 intervalů. První interval je
(- ∞; 3,94), dalších 6 intervalů má šířku h = 0,02 a poslední interval je
(4,06; ∞). Ze 100 hodnot byl určen výběrový průměr x = 3,999 a
výběrová směrodatná odchylka s = 0,030.
Vzhledem k tomu, že krajní intervaly nesplňují požadavek nπj ≥ 5,
sloučíme je se sousedními intervaly. Redukovaný počet tříd je k° = 6.
Pro počet stupňů volnosti ν = k° - 3 = 3 a pro hladinu významnosti α =
0,05 je kritická hodnota χ20,95(3) = 7,815.
Jelikož vypočtená hodnota testové charakteristiky χ2 = 1,477
nespadá do kritického oboru (není větší než kritická hodnota 7,815),
nemáme důvod zamítnout hypotézu o tom, že výběr pochází z normálního rozdělení.

Schéma výpočtu testové statistiky chí-kvadrát

horní mez
třídního
intervalu

třídní
četnosti
nj

3,940

(n·πj - nj)2
n·πj

uj

Φ(uj)

πj

n·πj

2

-1,93130

0,02672

0,02672

2,67232

3,960

9

-1,27529

0,10110

0,07438

7,43808

10,11040

11

0,07827

3,980

20

-0,61928

0,26787

0,16676

16,67627

16,67627

20

0,66245

4,000

23

0,03673

0,51465

0,24678

24,67837

24,67837

23

0,11415

4,020

21

0,69274

0,75576

0,24111

24,11133

24,11133

21

0,40149

4,040

17

1,34875

0,91129

0,15553

15,55274

15,55274

17

0,13467

4,060

5

2,00476

0,97751

0,06621

6,62145

8,87089

8

0,08550

4,080

3

0,02249

2,24944

χ2=

1,47653

n·πj

nj

Kolmogorovův-Smirnovův test dobré shody
H0: náhodný výběr rozsahu n pochází ze základního souboru
s normálním rozdělením N(µ, σ2) s distribuční funkcí F(x) (plně
specifikovaný model)
Uvažujeme-li pozorování uspořádaná podle velikosti x(i),

x(1) ≤ x( 2) ≤ ... ≤ x( n )
je testovou statistikou

i −1
i 

Dn = max | F ( x(i ) ) −
| , | F ( x(i ) ) − | , i = 1, 2, …, n.
n
n 

Η0 se zamítá, je-li

Dn ≥ Dα

Kritické hodnoty Dα jsou tabelovány (Tab. 1)

Modifikovaný Kolmogorovův-Smirnovův test

Nejsou-li parametry normálního rozdělení známy (neúplně
specifikovaný model), nahradí se odhady. Při rozhodování
se musí použít jiné kritické hodnoty (Tab. 2).

Tab. 1 Kritické hodnoty Dn(α) maximální odchylky
empirické distribuční funkce od teoretické

Tab. 2 Upravené kritické hodnoty dle Lilieforse

Rozsah
výběru n
4
5
6
7
8
9
10
11
12
13
14
15

0,2
0,303
0,289
0,269
0,252
0,239
0,227
0,217
0,208
0,200
0,193
0,187
0,181

α
0,1
0,346
0,319
0,297
0,280
0,265
0,252
0,241
0,231
0,222
0,215
0,208
0,201

0,05
0,376
0,343
0,323
0,304
0,288
0,274
0,262
0,251
0,242
0,234
0,226
0,219

0,01
0,413
0,397
0,371
0,351
0,333
0,317
0,304
0,291
0,281
0,271
0,262
0,254

Rozsah
výběru n
16
17
18
19
20
25
30
40
100
400
900

0,2
0,176
0,171
0,167
0,163
0,159
0,143
0,131
0,115
0,074
0,037
0,025

α
0,1
0,195
0,190
0,185
0,181
0,176
0,159
0,146
0,128
0,082
0,041
0,028

0,05
0,213
0,207
0,202
0,197
0,192
0,173
0,159
0,139
0,089
0,045
0,030

0,01
0,247
0,240
0,234
0,228
0,223
0,201
0,185
0,162
0,104
0,052
0,035

PŘÍKLAD 2
Bylo provedeno n = 12 měření zatížení vlákna do přetržení:
i
1
2
3
4
5
6
7
8
9
10
11
12
prumer
rozptyl
sm.odch

xi
2,104
2,222
2,247
2,286
2,327
2,367
2,388
2,512
2,707
2,751
3,158
3,172
2,520083
0,126343
0,355447

i/n
0,083333
0,166667
0,250000
0,333333
0,416667
0,500000
0,583333
0,666667
0,750000
0,833333
0,916667
1,000000

(i-1)/n
0,000000
0,083333
0,166667
0,250000
0,333333
0,416667
0,500000
0,583333
0,666667
0,750000
0,833333
0,916667

F(x)
|F(x)-(i-1)/n| |F(x)-i/n|
0,120882
0,120882 0,037548
0,200843
0,117509 0,034176
0,221160
0,054493 0,028840
0,255089
0,005089 0,078244
0,293492
0,039842 0,123175
0,333351
0,083315 0,166649
0,355096
0,144904 0,228237
0,490928
0,092405 0,175738
0,700509
0,033842 0,049491
0,742041
0,007959 0,091292
0,963648
0,130315 0,046982
0,966679
0,050012 0,033321
max

0,130315 0,228237

Závěr :
Vzhledem k tomu, že maximální absolutní diference mezi
empirickou distribuční funkcí a teoretickou distribuční funkcí není větší
než kritická hodnota Dn(α), nemáme důvod zamítnout testovanou
hypotézu H0 : výběr pochází ze základního souboru s normálním
rozdělením.

Grafický test
Do

pravděpodobnostního

papíru

zakreslíme

průběh

empirické

distribuční funkce, tj. body [ x(i) ; i/n ] a přímku odpovídající průběhu
odhadu distribuční funkce rozdělení N(µ, σ2) F̂( x ) .
K odhadu teoretické distribuční funkce zakreslíme meze konfidenčního
intervalu, tj. body
[ x ; F̂( x ) ± Dn(α) ] .
Vzniklé dvě křivky představují konfidenční interval distribuční funkce
F(x) s konfidenční úrovní 1-α .
Testovaná hypotéza H0 se zamítá, na hladině významnosti α, jestliže
alespoň pro jednu hodnotu x empirická distribuční funkce, znázorněná
na grafu body, leží vně zakresleného pásma.

Aplikace testu normality, pomocí pravděpodobnostního papíru

PŘÍKLAD 2 pokračování:
Na obrázku je vedle pravděpodobnostní stupnice y = 100 F(x) ještě
stupnice

u,

odpovídající

kvantilům

normovaného

normálního

rozdělení N(0, 1). ( Platí tedy 100 φ(u) = y .)
Přímku představující odhad distribuční funkce

hypotetického

normálního rozdělení N( µ = 2,520 ; σ2 = 0,3552) proložíme body
( x = 2,520 ; u = 0 ) a

( x + s = 2,875 ; u = 1 ) .

Pro n = 12 a α = 0,05 je Dn(α) = D12(0,05) = 0,37543 . Tedy
hranice zakreslené na obrázku jsou (F(x) ± 0,375) *100 .

Závěr :

Ani jeden bod neleží mimo zakreslené meze, nemáme

důvod zamítnout testovanou hypotézu H0 .

Testy normality v MINITABu
Kolmogorov – Smirnov
n Anderson – Darling
n

n

testová statistika A2 (A squared)

hodnoty větší než kritické svědčí proti normalitě
n

Ryan – Joiner
n

testová statistika R
podobný Shapiro-Wilkově testu (viz dále)
hodnoty menší než kritické svědčí proti normalitě

Použití p-hodnoty
Na výstupu každé procedury pro statistický
test je kromě hodnoty testové statistiky
uvedena tzv. p-hodnota (p-value)
n Platí-li:
p-hodnota < α,

n

zamítneme testovanou hypotézu na hladině
významnosti α.

Pravděpodobnostní graf v MINITABu
osa x – naměřené hodnoty x(i) sledované veličiny uspořádané podle
velikosti
osa y – hodnoty empirické distribuční funkce vynášené na nelineární
stupnici, vycházející z předpokladu normality
y-ová souřadnice bodu odpovídá kvantilu u(i) rozdělení N(0,1)
červeně proložena regresní přímka

E{x(i ) } = µ + σ u(i )
Normálnímu rozdělení veličiny X odpovídají vynesené body ležící
v blízkosti přímky a nevykazující nápadný nelineární trend.
Graf je buď doplněn výsledkem některého z uvedených testů
normality nebo 95% pásem spolehlivosti.

Testy normality ve Statistice
chí-kvadrát
n Kolmogorov – Smirnov
n Shapiro-Wilk
n

n

testová statistika W
čím blíže 1, tím více svědčí pro normalitu

Grafické metody ve Statistice
n

pravděpodobnostní graf
osa x – naměřené hodnoty x(i) seřazené
podle velikosti
n osa y – kvantily u (i) rozdělení N(0,1)
n

Q - Q graf
osa x - kvantily u(i) rozdělení N(0,1)
n osa y - naměřené hodnoty x(i) seřazené
podle velikosti
n vynesenými body je proložena regresní
přímka
n z rovnice regresní přímky se odhadnou
parametry

n

P - P graf
osa x – hodnoty teoretické distribuční
funkce (lineární stupnice)
n osa y – hodnoty empirické distribuční
funkce (lineární stupnice)
n v grafu vyznačena přímka se směrnicí 1

n

Výhoda grafických metod
Naznačují, o jaké rozdělení se ve skutečnosti
jedná. I v případě, že testy vycházejí
nevýznamné, může nelineární trend v grafu
prozradit vhodnost jiného než normálního
rozdělení.
n Někdy umožňují lépe posoudit, zda
nepřijatelnost hypotézy o normalitě je
důsledkem existence několika extrémních
pozorování, nebo zda je výběrové rozdělení
skutečně jiné než normální.
n

PŘÍKLAD 3

V rámci SPC se v montážním závodě kontroluje
vzdálenost aktuální pozice bodu na klikovém
hřídeli od základní pozice.
Každý den se provedlo 5 měření, k dispozici
jsou hodnoty za 25 dní.
Před výpočtem indexu způsobilosti je třeba
ověřit, zda lze rozdělení hodnot měřené
vzdálenosti považovat za normální.

Příklad 3 - MINITAB
Normal Probability Plot

,999
,99

Probability

,95
,80
,50
,20
,05
,01
,001
-8

-6

-4

-2

0

2

4

6

8

AtoBDist
Average: 0,441704
StDev: 3,49136
N: 125

Anderson-Darling Normality Test
A-Squared: 0,891
P-Value: 0,022

Příklad 3 - Výsledky různých testů normality

Příklad 3 - MINITAB
Normal Probability Plot for AtoBDist
ML Estimates - 95% CI

ML Estimates
99

Percent

95
90

Mean

0,441704

StDev

3,47736

Goodness of Fit

80
70
60
50
40
30
20

AD*

10
5
1

-10

0

Data

10

1

Příklad 3 - Statistica
Histogram (Spreadsheet1 in Workbook1 1v*125c)
AtoBDist = 125*2*normal(x; 0,4417; 3,4914)
30

25

No of obs

20

15

10

5

0
AtoBDist:
SW-W = 0,976469418, p = 0,0279; N = 125, Mean = 0,4417036, StdDv = 3,49135701,
-10
-8 = -7,30286;
-6
-2
4
6
8
10
Max = 8,02322,
Min
D -4
= 0,0943695246,
p0 < n.s., 2
Lilliefors-p < 0,00999999978
AtoBDist

Příklad 3 - Statistica
Normal Probability Plot of AtoBDist (Spreadsheet1 in Workbook1 1v*125c)
3

Expected Normal Value

2

1

0

-1

-2

-3
-8

-6

-4

-2

0

2

AtoBDist: SW-W = 0,976469418, p = 0,0279 Observed Value

4

6

8

10

Příklad 3 - Statistica
Quantile-Quantile Plot of AtoBDist (Spreadsheet1 in Workbook1 1v*125c)
Distribution: Normal
AtoBDist = 0,4417+3,488*x
0,01

0,05

0,25

0,50

0,75

0,90

0,99

12
10
8

Observed Value

6
4
2
0
-2
-4
-6
-8
-10
-3

-2

-1

0
Theoretical Quantile

1

2

3

Příklad 3 - Statistica
Probability-Probability Plot of AtoBDist (Spreadsheet1 in Workbook1 1v*125c)
Distribution: Normal(0,441704, 3,49136)
1,4
1,2

Empirical cumulative distribution

1,0
0,8
0,6
0,4
0,2
0,0
-0,2
-0,4
-0,2

0,0

0,2

0,4

0,6

Theoretical cumulative distribution

0,8

1,0

1,2

Příklad 4
n

Při elektronickém testování ozubených
kol se sleduje maximální odchylka
profilu od ideálního tvaru.

Příklad 4 - MINITAB
Normal Probability Plot

,999
,99

Probability

,95
,80
,50
,20
,05
,01
,001
55

65

75

85

95

105

115

x
Average: 77,55
StDev: 14,1625
N: 20

Anderson-Darling Normality Test
A-Squared: 0,455
P-Value: 0,240

Příklad 4
Normal Probability Plot for x
ML Estimates - 95% CI

99

ML Estimates

95

Mean

77,55

StDev

13,8039

90

Goodness of Fit

Percent

80

AD*

70
60
50
40
30
20
10
5
1
32

42

52

62

72

82

Data

92

102

112

122

0,997

Příklad 4 - Výsledky různých testů normality

Příklad 5
n

25 vzorků materiálu pro operační
přístroje bylo testováno na obsah
kovových příměsí.

Příklad 5 - MINITAB
Normal Probability Plot

,999
,99

Probability

,95
,80
,50
,20
,05
,01
,001
5

15

25

35

x
Average: 10,32
StDev: 8,57185
N: 25

Anderson-Darling Normality Test
A-Squared: 1,276
P-Value: 0,002

Příklad 5 - MINITAB
Normal Probability Plot for x
ML Estimates - 95% CI

99

ML Estimates

95

Mean

10,32

StDev

8,39867

90

Goodness of Fit

Percent

80

AD*

70
60
50
40
30
20
10
5
1
-10

0

10

Data

20

30

1,649

Příklad 5 - Výsledky různých testů normality

Příloha – vzorce 1
• Anderson - Darling
1 n
A = − ∑ (2i − 1) [ ln Φ i + ln(1 − Φ n−i+1 ) ] − n
n i=1
2

Φ i = Φ (u( i ) )
1 n
σ̂ = ∑ ( x( i ) − x ) 2
n i =1
2

x( i ) − x
u( i ) =
σˆ
maximálně věrohodný odhad σ2

Příloha – vzorce 2
• Shapiro - Wilk
u x )
(
∑
W=
∑u ∑(x − x )
2

(i ) (i )

2
(i )

2

(i )

 i −3/8 
u( i ) = Φ 

n
+
1
/
4


−1

