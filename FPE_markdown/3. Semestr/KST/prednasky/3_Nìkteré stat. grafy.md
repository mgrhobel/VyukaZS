---
title: "3_Nìkteré stat. grafy.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/3_Nìkteré stat. grafy.pdf"
date: 2009-12-27
type: PDF (text-based)
---

2. Grafické zobrazení dat
Pro presentaci statistických údajů je velmi působivé používat různé grafické způsoby.
Každý typ grafického zobrazení hodnot má svoje omezení, ale zároveň i svoje výhody. Kromě
klasických typů se k zobrazování statistických dat hodí speciální grafy, jeden typ jsme už měli
možnost vidět v části 1.3 šlo o tzv. Box Plot neboli Krabicový graf. V dalším si ukážeme
možné grafy pro presentaci údajů.

Běžné grafy
2.1 Bodový graf
Znázorňuje hodnoty pomocí bodů,většinou v pravoúhlé soustavě. Používá se většinou
k zachycení závislostí právě dvou statistických znaků. Při více než dvou znacích jeho
jednoduchost mizí a stává se méně přehledným. Nelze pomocí něho vystihnout data s větší
četností.
Graf 2.1 – velikost nákladů v závislosti na pořadí
Náklady

Náklady

4000
3500
3000
2500
2000
1500
1000
500
0
0

5

10

15

20

25

30

2.2 Spojnicový graf
Jestliže chceme znázornit velké množství hodnot, chceme – li vystihnout průběh
časové řady hodí se k tomu více spojnicový graf. Používá se také k vyjádření předpokladu o
spojitosti vyšetřovaného znaku. Jestliže se pomocí něho vyjadřuje rozložení absolutních nebo
relativních četností ve výběru , nazýváme se polygon četností.

Graf 1.2 – sloupcový graf, vyjadřuje změnu nákladů
4000
3500
3000
2500
2000
1500
1000
500
0
0

5

10

15

Náklady

20

25

30

Po změně

2.3 Sloupcový graf
Sloupcový graf vyjadřuje jednoduché závislosti mezi dvěma hodnotami, velmi často
jsou jednotlivé prvky výběru seskupovány do tříd. Existuje několik typů těchto grafů –
klasické sloupcové, sloupcové s procentním rozložením, trojrozměrné sloupcové grafy.
Klasická ukázka je uvedena v grafu 2.3
Graf 2.3- rozdělení nákladů do tříd
Sloupcový graf četností
8
7
6
5
4
3
2
1
0
-1
50
0

-2
00
0

-2
50
0

-3
00
0

-3
50
0

-4
00
0

-4
50
0

0

0

0

0

0

0

0

15
0

20
0

25
0

30
0

35
0

40
0

00
0

10
0

-1
50
0

0

-5
0

0

četnost

2.4 Histogram
Svou definicí je to sloupcový graf , který se používá k znázornění absolutních nebo
relativních četností (většinou )spojitého znaku. Sloupce v grafu jsou zásadně vertikální,šířka
sloupce odpovídá velikosti třídy a celková plocha sloupce odpovídá četnosti prvků třídy ve
výběru.

Histogram

10000
8000
6000
4000
2000
0
500

1000

1500

2000

2500

3000

3500

4000

4500

2.5 Kruhový graf
Zobrazuje hodnoty jako výseče v kruhu a tím se zachytí struktura výběru. Předchozí
data jsou zobrazena v kruhovém grafu ( koláč, výsečový graf ) takto
2%

9%
9%

38%

6%
6%

11%
13%

500
1000
1500
2000
2500
3000
3500
4000
4500

6%

Speciální statistické grafy
Jedním z užívaných grafických způsobů je dříve uvedený histogram. V současné době
existuje mnoho profesionálních způsobů presentace statistických dat. V předchozí části jsme
zavedli velmi užitečný typ Box Plot – český ekvivalent názvu je Krabicový graf. Statistických
grafů existuje velké množství, zaměříme se na některé speciální.

2.6 Kvantilový graf
Jde typ grafu , kterým můžeme přehledně znázornit data, porovnat je se známými
rozděleními, najít vybočující hodnoty atd. Na osu x nanášíme pořadovou pravděpodobnost
teoretického rozdělení, na osu y skutečné kvantily daných dat. Na grafu níže je uvedeno
porovnání výběru s N(0,1). Data se s hodnotami teoretického rozdělení neshodují, zjevně
vybočují na krajích.

3
2
1
N(0,1)

0

výběr

-1
-2
-3
0

0,2

0,4

0,6

0,8

1

Tento typ grafu se velmi často užívá pro první porovnání údajů především
s normálním normovaným rozdělením. Dříve se k takovému porovnání používal tzv.
pravděpodobnostní papír, dnes ho provádíme s pomocí počítače.
Mezi základní statistická vyšetřování patří rozhodnutí, zda daný výběr patří nebo
nepatří k rozdělím symetrickým. K takovému rozhodnutí nám pomáhá následující typ grafu:

2.7 Graf polosum
Jeho konstrukce je založena na myšlence, že u symetrického rozdělení je aritmetický
průměr kvantilu p% a kvantilu (1-p)% stejný a je roven mediánu. Níže je uveden daný graf
pro data vyšetřovaná v předchozí části. Symetrická rozdělení jsou tedy charakterizována
přímkou y= x% . Celkově je zřejmé,že data pochází ze symetrického rozdělení.
75

70

65

60

55

50

0

10

20

30

40

50

60

70

80

90

100

45

40

35

30

25

2.8 Graf symetrie
Pomocí tohoto grafu je možno sledovat znak symetrie výběru. Na osu x nanášíme
u 2 Pi
i
hodnoty
a na osu y stejné hodnoty jako u předchozího grafu tedy hodnoty
pro Pi =
n +1
2
( x( n +1−i ) x(i ) )
2

osa x

50,37

25
0,12

0,17

0,22

0,27

0,32

0,37

Opět je zřejmé, že hodnoty výběru jsou symetrické , s výjimkou krajních hodnot.
Pomocí dalšího grafu je možno srovnávat parametr špičatosti s rozdělením N(0,1).

2.9 Graf špičatosti
Za předpokladu symetrie je pro normální rozdělení grafem přímka. Pokud leží body na
přímce s nenulovou směrnicí, je hodnota této směrnice odhadem výběrového parametru
špičatosti. Opět je zřejmé, že data odpovídají symetrii, navíc můžeme z grafu odhadnout
výběrovou špičatost.
0,4

0,35

0,3

0,25

0,2

0,15

0,1

0,05

0
4,1

4,2

4,3

4,4

4,5

4,6

