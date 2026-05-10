---
title: "4_Intervalove odhady I.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/4_Intervalove odhady I.pdf"
date: 2009-12-27
type: PDF (text-based)
---

3. Intervalové odhady
V předchozí kapitole jsme odhadovali funkci γ ( Θ ) parametru Θ hodnotou vhodné
statistiky S. Jestliže nahradíme skutečnou hodnotu γ ( Θ ) jejím odhadem S dopustíme se
chyby S − γ ( Θ ) ( tzv. výběrová chyba ). Vzhledem k charakteru definice statistiky S je i tato
výběrová chyba náhodná veličina. Takovouto náhodnou chybu je možno vyšetřovat
( známe – li její rozdělení ). Toto šetření je většinou příliš komplikované, proto se
zaměřujeme spíše na metodu intervalového odhadu.
Úlohou intervalového odhadu je najít interval ( řešíme tedy jednorozměrný případ –
parametr je právě jen jeden ) , v němž leží hledaná funkce γ ( Θ ) s předem danou
pravděpodobností 1- α. O tomto intervalu budeme dále předpokládat, že jeho meze
( resp. aspoň jedna mez ) jsou závislé na náhodných veličinách ( většinou na volené statistice
S ). V dalším zjednodušíme situaci tak , že funkce γ ( Θ ) = Θ . Intervaly takto zkonstruované
se nazývají většinou intervaly spolehlivosti s koeficientem spolehlivosti 1- α nebo také
100(1- α)% - ním intervalem spolehlivosti. Někdy se dále používá název konfidenční
intervaly.

3.1 Intervalový odhad –teoretické základy
Budeme tedy v dalším hledat interval
A<Θ<B
(3.1)
pro který je splněno pro každé Θ z parametrického prostoru

P ( A < Θ < B) = 1 − α

(3.2)
Interval (3.1) budeme nazývat intervalem spolehlivosti. Číslo 1- α ( 0 < α < 1 )
budeme nazývat koeficientem spolehlivosti . Tento koeficient můžeme považovat
za spolehlivost ( pravděpodobnost ) tvrzení , že Θ ∈ ( A, B ) . Protože ve většině úloh
vyžadujeme vysokou pravděpodobnost odhadu, volíme číslo 1- α velmi blízké jedné. Jak ale
uvidíme , čím je žádána vyšší pravděpodobnost odhadu , tím je zkonstruovaný interval širší .
Proto je vždy nutno volit vhodný kompromis mezi velikostí 1- α a šíří intervalu.
V praxi volíme hodnoty 1- α rovné buď 90% , 95% , 99% nebo 99,5%. Nejčastější
volbou je právě 95% - ní interval spolehlivosti.. Je zřejmé , že interval (3.1) není hodnotou 1α jednoznačně určen ( vyplývá většinou z povahy náhodných veličin jak spojitého typu , tak i
diskrétního typu – z hlediska obecného jde o plochu dané velikosti, která má obsahovat daný
bod , je zřejmé, vzhledem ke spojitosti změn plochy při změnách mezí intervalu, že lze najít
více intervalů, které vyhovují (3.1) i (3.2).
Přirozená otázka je najít takový interval, který je pro dané 1- α nejkratší. Ukazuje se ,
že takovýto interval je určen pomocí následujících pravidel
α
P (Θ ≤ B) =
2
(3.3)
α
P ( Θ ≥ A) =
2
(3.4)
Takto určený interval (A,B) nazveme dvoustranným intervalem spolehlivosti. Tento
interval je symetrický se středem rovným bodovému odhadu parametru Θ .

Existují úlohy, kdy je přirozené odhadovat parametr Θ pomocí intervalů , které nejsou
omezené buď zdola nebo shora . Takovéto intervaly spolehlivosti nazýváme potom jako
jednostranné intervaly spolehlivosti ( nebo někdy pravostranné nebo levostranné ) intervaly
spolehlivosti .
Jejich konstrukci si nyní objasníme . Postupujeme velmi podobně jako v předchozím
případě , ovšem vezmeme v úvahu jednostrannou neomezenost konstruovaného intervalu.
Tedy
P (Θ ≤ B) = 1−α
(3.5)
odtud vyvodíme interval (-∞ ,B) , který nazveme pravostranným intervalem
spolehlivosti . Opět tento interval obsahuje bodový odhad parametru Θ , navíc je zdola
neomezený.
P ( Θ ≥ A) = 1 − α
(3.6)
odtud opět odvodíme interval (A , +∞ ) . tento interval nazveme levostranným
intervalem spolehlivosti . Tento interval obsahuje opět bodový odhad parametru Θ , navíc je
shora neomezený.
Při skutečném určování hodnot A a B jako mezí výše uvedených intervalů většinou
vycházíme z konstrukce náhodných veličin známých vlastností a pomocí kvantilů těchto
veličin odvozujeme právě dané hodnoty A a B . Detailní způsoby si uvedeme v dalších
částech této kapitoly.

3.2

Konstrukce intervalových odhadů pro případ normálního
rozdělení

Předpokládáme , že náhodný výběr pochází z populace , která je popsána pomocí
rozdělení N( µ , σ2 ) . Protože toto rozdělení je jednoznačně určeno dvěma parametry ,
musíme při konstrukci intervalů spolehlivosti vždy rozlišovat dva případy pro známý či
neznámý druhý parametr.
Nejdříve začněme konstrukcí intervalů spolehlivosti pro střední hodnotu µ. Budeme
tedy rozlišovat dva případy :
1.Parametr σ2 je známý . Podle znalostí z předchozích kapitol víme, že náhodná

 σ2 
X −µ
N  µ, 
. n
n

 , proto je po znormování
σ

X
veličina

N ( 0,1)

. Můžeme tedy
na konstrukci intervalového odhadu použít právě tuto funkci . Budeme dále symbolem u β

označovat β kvantil normovaného normálního rozdělení. Potom je interval
x −u α.
1−

2

σ
n

< µ < x +u α.
1−

2

σ
n

(3.7)

100(1- α )% - ním oboustranným intervalem spolehlivosti . Hodnota x nyní i dále
je realizace náhodné veličiny X pomocí náhodného výběru.
Podobně nyní odvoďme i jednostranné intervaly spolehlivosti. Pravostranný
−∞ < µ < x + u1-α .

σ
n

(3.8)

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
četnost

2
1

3
3

4
3

5
8

6
9

7
6

8
5

9
2

Stanovíme nejprve hodnotu bodového odhadu střední hodnoty , ta je rovna
5,8649 , dále stanovíme hodnotu n = 39. V dalším zjistíme hodnoty nejprve
oboustranných intervalů spolehlivosti pro různé hodnoty α , výsledky uvedeme v tabulce
A
B
1-α
0,95 5,31 6,42
0,96 5,28 6,45
0,99 5,13 6,60
0,995 5,07 6,66
Podobně do stejné tabulky vložíme hodnoty mezí pro levostranné a pravostranné
intervaly spolehlivosti
levostranný interval
pravostranný interval
A
B
1-α
1-α
0,9
5,50
0,9
6,23
0,95
5,40
0,95
6,33
0,99
5,20
0,99
6,53
0,995
5,13
0,995
6,60
x

2.Parametr σ2 není známý.

X −µ
. n
s
je typu
Potom je opět z předchozích kapitol známo, že náhodná veličina
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
−∞ < µ < x + t1-α .
n
(3.11)
je pravostranným 100(1-α)% intervalem spolehlivosti a
s
x − t1−α .
< µ < +∞
n
(3.12)

je levostranným 100(1-α)% intervalem spolehlivosti . Hodnoty t β jsou příslušné
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
0,995

A
5,20
5,18
5,02
4,95

B
6,53
6,55
6,71
6,78

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
jako normální rozdělení N( µ , σ2 ). Budeme opět rozlišovat dva případy :
1.Střední hodnota µ je známa. Potom využijeme vztahu (10.6) tzv. výběrového
rozptylu při známé střední hodnotě µ . Tuto statistiku je možno použít k bodovému odhadu σ2
n.s02

. Podle konstrukce obecných rozdělení je zřejmé, že σ je typově rozdělení χ s n stupni
volnostmi . Pro ověření tuto náhodnou veličinu napište jako součet nezávislých náhodných
2

2

veličin typu ( N ( 0,1) ) . Tuto znalost nyní využijeme nejdříve pro konstrukci oboustranného
2

100(1-α)% -ního intervalu spolehlivosti :
n.s02

χ2α
1−

2

<σ2 <

n.s02

χ α2

2

Podobně provedeme konstrukci intervalu pravostranného
n.s 2
0 < σ 2 < 20
χα
(3.14)

(3.13)

a levostranného
n.s 02
< σ 2 < +∞
2

χ1−α

(3.15).

Hodnoty χ β je hodnota kvantilu β rozdělení χ o n stupních volnosti. Je nutno ovšem
upozornit, že případy kdy známe střední hodnotu populace a neznáme naopak rozptyl
populace se v reálné praxi prakticky vůbec nevyskytují , proto je nebudeme dále brát v úvahu.
2

2

2.Střední hodnota µ není známa. Populace je však popsána jako rozdělení typu
N( µ , σ2 ). K bodovému odhadu hodnoty σ2 používáme podle předchozí kapitoly statistiku s ,
která je definována v předchozí kapitole vztahem (10.7) . Pokud provedeme úpravu náhodné
( n − 1) .s 2
2
σ2
veličiny s na
získáme náhodnou veličinu typu χ o n-1 stupních volnosti .
Na základě znalosti tohoto rozdělení je tedy možno provést konstrukci všech typů intervalů
spolehlivosti . Nejdříve tedy odvodíme oboustranný 100(1-α)% - ní interval spolehlivosti (
2
2
opět jako v předchozích vztazích bude χ β hodnota kvantilu β rozdělení χ tentokrát
o n - 1 stupních volnosti):

(n − 1).s 2

χ2α
1−

2

<σ2 <

(n − 1).s 2

χ α2
2

(3.16)

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
Provedli jsme náhodný výběr z populace N(µ,σ2) , hodnota n = 20 , dále jsme zjistili
hodnotu s = 0,1. Sestrojme 95% oboustranný interval spolehlivosti pro rozptyl.
Řešení:
Protože neznáme střední hodnotu µ použijeme vzorce (3.16). Zjistěme nejdříve dané
hodnoty, které potřebujeme pro stanovení vztahu (3.16). Tedy:
2
2
S2 = 0,121 ; χ 0,025 = 8,91 ; χ 0,975 = 32,9 ; n – 1 = 19 , po dosazení do vzorce
0, 006 < σ 2 < 0, 021 neboli 0, 07746 < σ < 0,144914 .
V našem případě se snažíme naměřená data diskrétního charakteru převést na model
spojitý , velmi často za podmínky použití odmocniny z konečnostního násobitele viz věta 11.7
n
≤ 0, 05
, tedy za podmínky , že N
provedeme úpravy výrazů (3.7) až (3.12) tak, že je

N −n
násobíme N − 1 . Této úpravě se někdy říká také oprava na výběr bez vracení. Například
výraz (3.10) s danou opravou je
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

x −t α.
1−

3.3

2

(3.10’).

Konstrukce intervalových odhadů pro případ binomického
( alternativního )rozdělení

Předpokládejme, že náhodný výběr pochází z populace popsané alternativním
rozdělením s neznámým parametrem π . Jak jsme již odvodili v předchozí kapitole je
n

∑X

p = X = i =1
n
nejlepším nezkresleným odhadem parametru π výběrová relativní četnost
n
k
m = ∑ Xi =
n má rozdělení Bi(n;π).
i =1
navíc výběrový úhrn
Je zřejmé , že pro sestrojení intervalu spolehlivosti se nejlépe hodí funkce

∑ ( ni ) .π .(1 − π )
k

i

i

,

n −i

(3.18)

i =0

Obecně je tato distribuční funkce binomického rozdělení dosti komplikovaná , naštěstí
existuje určitý zajímavý vztah mezi distribuční funkcí Fischer – Snedecorova rozdělení a
distribuční funkcí rozdělení binomického .
Meze oboustranného intervalu spolehlivosti π a π jsou dány vztahy

∑ ( ni ) .π .(1 − π )
k

i

n −i

=

i =0

∑ ( ni ) .π .(1 − π )
n

i

n −i

=

i=k

α
2

(3.19)

α
2

(3.20)

Vztah mezi distribučními funkcemi je následující

∑ ( ni ) .π .(1 − π )

k +1 1 − π 

= P F <
.

n-k π 

i =0
(3.21),
kde F je F(2.(n-k);2.(k+1))-rozdělení , jde tedy o Fischer – Snedecorovo rozdělení
s 2.(n-k) a 2.(k+1) stupni volnosti. Využijeme – li nyní vztahu (3.21) získáme
k

i

n −i

∑ ( ni ) .π .(1 − π )

k +1 1 − π 

= P F <
.

2
n-k π 

i =0
Odtud získáme horní mez
k

i

n −i

=

α

(3.22)

π =

F α . ( k + 1)
1−

2

n − k + ( k + 1) .F α
1−

2

(3.23)

Symbolem Fβ označujeme příslušný kvantil rozdělení F s 2.(k+1) ; 2.(n-k) stupni
volnosti . Podobně upravíme (3.20) a získáme
k −1
k
1−π 
n .π i .(1 − π ) n −i = P  F <
.
∑


i
n - k +1 π 
i =0

(3.24)

()

Tedy dolní mez odhadu je
k
π=
F α . ( n − k + 1) + k
1−

(3.25)

2

Symbolem Fβ označujeme příslušný kvantil rozdělení F s 2.(n – k + 1) ; 2.k stupni
volnosti .
Příklad 3.4
Při kontrole jakosti bylo z velké série vyrobených televizorů vybráno náhodně n = 400
výrobků , z toho bylo 25 vadných . Sestrojte oboustranný 95% interval spolehlivosti pro podíl
vadných výrobků v sérii všech vyrobených!
Řešení .
Použijeme výše uvedené hodnoty (3.23) a (3.25) , v kterých dosadíme k = 25 a n=400 .
Po dosazení získáme hodnoty (0,044; 0,086 ) .
Ve většině případů můžeme

k vyšetřování intervalových odhadů
k
p=
n ,
alternativního rozdělení ( binomického rozdělení ) jinak. Označíme – li symbolem
bodový odhad hledané pravděpodobnosti π, potom je ( pro dostatečně velká n ( n > 30))

π−p
π . (1 − π )
n

přisoupit

N ( 0,1)
.

(3.26)

Nepříjemné je , že jmenovatel v (3.26) závisí na odhadované hodnotě. Tuto závadu
odstraníme , nahradíme – li pro tento případ π jeho bodovým odhadem. Celkově tedy bude
intervalový odhad roven:
p −u α .
1−

2

p. (1 − p )
p. (1 − p )
<π < p+u α.
1−
n
n
2

(3.27)

Podotkněme, že tento odhad budeme akceptovat , jestliže hodnota
9
n>
p. (1- p )
(3.28)
dále budeme předpokládat , že n > 30. Ve výrazu (3.27) provádíme velmi často tzv.
korekci na spojitost ( nahrazujeme diskrétní rozdělení spojitým ), tím získáme nový odhad
p−

p. (1 − p )
p. (1 − p )
1
1
−u α.
<π < p+
+u α.
2.n 1− 2
n
2.n 1− 2
n

(3.29).

Všechny předchozí úvahy jsme prováděli za jednoho podstatného předpokladu, poměr
n
≤ 0, 05
vybíraných výrobků z celé série je maximálně 5% nebo jinak N
, kde n je počet
vybíraných výrobků a N je celkový počet výrobků.
Je – li tento předpoklad porušen, musíme upravit navíc také vztahy (3.27) resp. (3.29) ,
tím , že použijeme konečnostní koeficient . Potom budou tedy tyto odhady následující
p −u α .
1−

2

p. (1 − p ) N − n
p. (1 − p ) N − n
.
<π < p+u α.
.
1−
n
N −1
n
N −1
2

(3.30)

a
p−

p. (1 − p ) N − n
p. (1 − p ) N − n
1
1
−u α.
.
<π < p+
+u α.
.
2.n 1− 2
n
N −1
2.n 1− 2
n
N − 1 (3.31)

Pomocí našich nových vztahů provedeme opět zjištění hodnot intervalových odhadů
n
≤ 0, 05
pro příklad 3.4. Protože byl výběr učiněn z velké série , předpokládáme, že hodnota N
. Budeme tedy používat vztahy (3.27) a (3.29). Platí vztah (3.28) neboť n= 400. Tedy nové
intervalové odhady jsou (0,039;0,086) , s korekcí na spojitost (0,037;0,087).
Všimněme si, že na rozdíl od intervalových odhadů střední hodnoty pro normální
rozdělení neleží bodový odhad pravděpodobnosti π ve středu intervalového odhadu!
Příklad 3.5
Použijeme upravený příklad 3.4. Změníme data tak, že výběr n=400 výrobků
provádíme z celkem N=4000 výrobků.
Nyní bude odhad převodem na normální rozdělení roven (0,040 ; 0,085 ) . Odhad
s korekcí na spojitost bude činit celkem ( 0,039; 0,086 ).
Uvedené příklady je možno také řešit pomocí speciálního statistického grafu , který je
konstruován právě pomocí výše uvedených principů a je uveden dále

1

0,9
n=1000

0,8
n=500
0,7

n=200
n=100

0,6
n=80
0,5
n=50
0,4
n=30

0,3

0,2
n=10
0,1

0
0

0,1

0,2

0,3

0,4

0,5

0,6

0,7

0,8

0,9

1

Konstrukce je provedena pro 95% intervaly spolehlivosti pro různé hodnoty
výběrových podílů ( jsou uváděny na ose x ) , příslušný interval získáme tak , že zvolíme
hodnotu n , dále na ose x označíme nalezený výběrový podíl , vztyčíme kolmici a uvedené
průsečíky s danými grafy vyznačí hledaný interval.
Blíže jsou uvedené intervaly vypočítány v následující tabulce ( vše počítáno pro
interval spolehlivosti 95%).

3.4

Konstrukce intervalových odhadů pro případ Exponenciálního
rozdělení

Při konstrukci intervalových odhadů pro tento typ rozdělení budeme důsledně
vycházet z následujícího tvrzení.
Věta 3.6
Nechť náhodný výběr pochází z populace popsané pomocí exponenciálního rozdělení
s parametry 0 a δ potom je náhodná veličina

2.n. X

δ

(3.32)

rozdělení χ ( 2.n ) ( tedy chi –kvadrát s 2n stupni volnosti ).
2

Větu dokazovat nebudeme, odkazujeme např. na .
Pomocí tohoto tvrzení je možno sestrojit oboustranný (1-α)% interval spolehlivosti
parametru δ podle následujícího vztahu

2.n.x

χ α
2

1−

2

<δ <

2.n.x

χ α2
2

(3.33),

χ2α

χ α2

kde − 2 a 2 jsou příslušné kvantily rozdělení chi kvadrát s 2.n stupni volnosti .
Je – li hodnota prvního parametru A exponenciálního rozdělení X různá od nuly,
nahradíme ji náhodnou veličinou X – A , která je opět exponenciální a navíc má vlastnosti
obsažené ve větě 3.6.
Podobným způsobem můžeme provést i konstrukce levostranných či pravostranných
intervalů spolehlivosti.
Uvedené skutečnosti budeme ilustrovat na konkrétním příkladě.
1

Příklad 3.7
Doba čekání ve frontě má exponenciální rozdělení s parametrem A = 5 minut .
Sestrojte 95% interval spolehlivosti pro parametr δ , jestliže součet dob čekání náhodně
vybraných 10 klientů byl roven 100 minut.
Řešení :
Nejdříve zjistíme hodnotu x , protože hodnota A = 5 je různá od nuly budeme muset
100 − 10.5 50
x=
=
=5
10
10
nejdříve provést posun parametrů. Tedy
, nyní již můžeme dosadit do
intervalového odhadu (3.33).
2.10.5
2.10.5
<δ <
⇔ 2,92 < δ < 10, 43
34, 2
9.59
.
Podobně bychom mohli konstruovat intervaly spolehlivosti pro další typy rozdělení
např. Poissonovo rozdělení , hypergeometrické a další, pro detaily odkazujeme na .

3.5

Intervaly spolehlivosti pro rozdíl dvou středních hodnot

V další části této kapitoly se budeme zabývat případy dvou nezávislých výběrů a
budeme především nalézat intervaly spolehlivosti pro jejich rozdíl. Nejdříve začneme
nejjednoduššími případy .

3.5.1 Rozptyl hledaných populací je známý a populace jsou normální
Předpokládejme , že jsou známé rozptyly daných populací . Tento případ je v praxi
2
2
prakticky vyloučen , přesto ho budeme diskutovat. Známe tedy hodnoty σ 1 a σ 2 . Podle
předchozí kapitoly jsou tedy náhodné veličiny

X 1 − µ1

X 2 − µ2

. n2 N ( 0,1)
σ2
a
. V tomto okamžiku nás ale zajímá
odhad rozdílu neznámých středních hodnot, proto uvedené vztahy přepočteme takto:

σ1

N ( 0,1)

. n1

( X − X ) -(µ − µ )
1

2

σ

2
1

n1

1

+

σ

2
2

n2

2

N ( 0,1)

(3.34).

Z takovéhoto vztahu již můžeme provést konstrukci např. oboustranných (1-α)%
intervalů spolehlivosti jako:

σ 12

( X1 − X 2 ) - u α .
1-

n1

2

+

σ 22
n2

< ( µ1 − µ 2 ) < ( X 1 − X 2 ) + u α .
1-

2

σ 12
n1

+

σ 22
n2

(3.35),

kde jako obvykle symbol uα znamená α - tý kvantil rozdělení N(0,1). Podobně bychom
mohli odvodit i vztahy pro jednostranné odhady rozdílu středních hodnot.

3.5.2 Rozptyl hledaných populací je neznámý a populace jsou normální
Nejdříve budeme studovat případ , kdy rozptyl z neznámých populací je sice neznámý ,
ale je stejný a roven σ2 . Potom použijeme podobné kroky jako při konstrukci studentova
rozdělení . Budeme opět předpokládat , že chceme zkonstruovat (1-α)% oboustranný interval
spolehlivosti . Totiž náhodná veličina (3.36) je typu studentovo rozdělení s ( n1 + n2 – 2 )
stupni volnosti

( X − X ) -(µ − µ )
1

2

1

2

( n1 − 1) .s + ( n2 − 1) .s . 1 + 1
n1 + n2 − 2
n1 n2
2
1

2
2

tn1 + n2 − 2
(3.36)

Z tohoto vztahu již můžeme snadno odvodit všechny typy intervalových odhadů, je zřejmé
, že budou záviset mimo jiné na kvantilech studentova rozdělení. První odmocnina ve výrazu
(3.36) se někdy označuje jako sp .
Z uvedeného postupu vyplývá , že je nutné ověřit rovnost obou rozptylů. V případě , kdy
se totiž tyto rozptyly nerovnají , neplatí ani (3.36). Naštěstí existuje možnost jak ověřit
rovnost rozptylů u dvou náhodných výběrů. K tomuto ověření používáme Fischer –
Snedecorovo rozdělení .
Podle tvrzení uvedených v kapitole 2. totiž platí:
A1
n
F = 1 F (n1 , n2 )
A2
n2
, jsou – li A1 a A2 nezávislé náhodné veličiny postupně typu

χ 2 ( n1 ) a χ 2 ( n2 ) . Zvolíme – li za uvedené náhodné veličiny A a A , hodnoty výběrových

rozptylů , které jsou typu chi kvadrát získáme:

1

2

S12

F=

σ 12
S22

σ 22

(3.37),
je tedy Fischer – Snedecorovo rozdělení s ( n1 – 1, n2 – 1) stupni volnosti . Tyto
vztahy jsou odvozeny za předpokladu , že rozptyly obou populací jsou shodné .
Jestliže chceme ověřit rovnost dvou rozptylů , využijeme vztah (3.37), provedeme - li
intervalový odhad na hladině významnosti (1-α)% , musí tento interval obsahovat číslo 1.
Nebude – li ho obsahovat , nemůžeme rovnost rozptylů potvrdit.
V tomto případě nebo v případě , že z jiných informací máme potvrzenu nerovnost
obou rozptylů , pak použijeme metodu s redukovanými stupni volnosti . Náhodná veličina

( X − X ) -(µ − µ )
1

2

1

2
1

2
2

2

s
s
+
n1 n2

tr

(3.38)

kde počet stupňů volnosti r spočteme podle následujícího předpisu ( Welchův způsob )
2

 s12 s22 
 + 
n n
r =  12 2  2 − 2
 s12   s22 
   
 n1  +  n2 
n1 + 1 n2 + 1

(3.39),

v případě, že daná hodnota r není celé číslo , zaokrouhlíme ji nahoru k nejbližšímu
celému číslu.
Ve všech případech , které jsme vyšetřovali v této části po využití vztahů (3.36) a
(3.38) přejdeme postupně k oboustrannému intervalovému odhadu
n1 − 1) .s12 + ( n2 − 1) .s22 1 1
(
.
+
< ( µ1 − µ 2 ) <
( X 1 − X 2 ) - t1-α .
n1 + n2 − 2

2

n2

( n1 − 1) .s12 + ( n2 − 1) .s22 . 1 + 1

< ( X1 − X 2 ) + t α .
1-

n1

n1 + n2 − 2

2

n1

n2

(3.40),

pro případ vztahu (3.36) a rovnosti rozptylů, t je studentovo rozdělení o
n1 + n2 − 2 stupních volnosti.
2
1

2
2

1

2

2
1

2
2

1

2

( X − X ) - t α . sn + ns < ( µ − µ ) < ( X − X ) + t α . sn + ns
1

2

1-

2

1

2

1

2

1-

2

(3.41)

pro případ vztahu (3.38) , kdy nemáme zaručenou rovnost rozptylů populací, t je
studentovo rozdělení s redukovaným počtem stupňů volnosti podle (3.39).

3.5.3 Populace jsou popsány jako alternativní ( binomické ) rozdělení
Podobně jako v části 3.3 můžeme odvodit velmi podobné vzorce jako jsou (3.27) a
(3.29) . Bez opravy na spojitost ( nutno podržet platnost vztahu (3.28) pro oba výběry ) je
takový odhad roven
p1. (1 − p1 ) p2 . (1 − p2 )
+
< π1 − π 2 <
n1
n2

p1 − p2 − u α .
1−

2

< p1 − p2 + u α .
1−

2

p1. (1 − p1 ) p2 . (1 − p2 )
+
n1
n2

(3.42)

Pro případ korekce ( opravy ) na spojitost se používají následující vztahy
p1 − p2 −

p . (1 − p1 ) p2 . (1 − p2 )
1
1
−
−u α. 1
+
< π1 − π 2 <
2.n1 2.n2 1− 2
n1
n2

< p1 − p2 +

p . (1 − p1 ) p2 . (1 − p2 )
1
1
+
+u α. 1
+
2.n1 2.n2 1− 2
n1
n2

(3.43)

3.6 Konstrukce intervalových odhadů na základě velkých výběrů
Při konstrukci takovýchto intervalových odhadů , kdy není předem známo rozdělení
populace , je možno u velkých náhodných výběrů vyjít z centrální limitní věty.
Předpokládáme, že rozdělení populace má konečnou střední hodnotu E(X) = µ a konečný
rozptyl VAR(X) = σ2 . Potom můžeme považovat rozdělení
X −µ

σ

n

(3.44)

asymptoticky za N(0,1). Odtud tedy , pokud známe hodnotu směrodatné odchylky
použijeme tento vztah. Pokud neznáme hodnotu σ nahradíme ji v předchozím vztahu
konzistentním odhadem tohoto parametru např. hodnotou s. Potom máme tedy příslušné
intervalové odhady rovny
x −u α.
1−

2

σ
n

< µ < x +u α.
1−

2

σ
n

(3.45)

a
s
s
< µ < x +u α.
1−
1−
n
n
2
2
(3.46)
V této a předchozí kapitole jsme se zabývali především oboustrannými intervalovými
odhady , tvorba jednostranných odhadů probíhá stejným způsobem jako v části 3.2.
x −u α.

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
Intervalový odhad metodou Bootstrap
4500
4000
3500
3000
2500
2000
1500
1000
500
0
4,6

4,8

5

5,2

5,4

5,6

5,8

3.

INTERVALOVÉ ODHADY

3.1

Intervalový odhad –teoretické základy

3.2

Konstrukce intervalových odhadů pro případ normálního rozdělení

3.3

Konstrukce intervalových odhadů pro případ binomického ( alternativního )rozdělení

3.4

Konstrukce intervalových odhadů pro případ Exponenciálního rozdělení

3.5 Intervaly spolehlivosti pro rozdíl dvou středních hodnot
3.5.1
Rozptyl hledaných populací je známý a populace jsou normální
3.5.2
Rozptyl hledaných populací je neznámý a populace jsou normální
3.5.3
Populace jsou popsány jako alternativní ( binomické ) rozdělení
3.6

Konstrukce intervalových odhadů na základě velkých výběrů

3.7

Metoda bootstrap

