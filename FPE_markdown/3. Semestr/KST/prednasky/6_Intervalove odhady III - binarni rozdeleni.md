---
title: "6_Intervalove odhady III - binarni rozdeleni.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/6_Intervalove odhady III - binarni rozdeleni.pdf"
date: 2009-12-27
type: PDF (text-based)
---

3.2

Konstrukce intervalových odhadů pro případ binomického
( alternativního )rozdělení

Předpokládejme, že náhodný výběr pochází z populace popsané alternativním
rozdělením s neznámým parametrem π . Jak jsme již odvodili v předchozí kapitole je
n

∑ Xi
,
nejlepším nezkresleným odhadem parametru π výběrová relativní četnost p = X = i =1
n
n
navíc výběrový úhrn m = ∑ X i = k má rozdělení Bi(n;π).
n
i =1
Je zřejmé , že pro sestrojení intervalu spolehlivosti se nejlépe hodí funkce

∑ ( ni ) .π .(1 − π )
k

i

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

(3.19)

2

α

(3.20)

2

Vztah mezi distribučními funkcemi je následující

∑ ( ni ) .π .(1 − π )
k

i

n −i

i =0

k +1 1 − π 

= P F <
.

n-k π 


(3.21),

kde F je F(2.(n-k);2.(k+1))-rozdělení , jde tedy o Fischer – Snedecorovo rozdělení
s 2.(n-k) a 2.(k+1) stupni volnosti. Využijeme – li nyní vztahu (3.21) získáme

∑ ( ni ) .π .(1 − π )
k

i =0

i

n −i

=

α

k +1 1 − π 

= P F <
.

2
n-k π 


Odtud získáme horní mez
F α . ( k + 1)
1−
2
π=
n − k + ( k + 1) .F α
1−

(3.22)

(3.23)

2

Symbolem Fβ označujeme příslušný kvantil rozdělení F s 2.(k+1) ; 2.(n-k) stupni
volnosti . Podobně upravíme (3.20) a získáme

∑ ( ni ) .π .(1 − π )
k −1
i =0

i

n −i


k
1− π 
.
= P F <

n - k +1 π 


(3.24)

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
Ve většině případů můžeme přistoupit k vyšetřování intervalových odhadů
alternativního rozdělení ( binomického rozdělení ) jinak. Označíme – li symbolem p = k ,
n
bodový odhad hledané pravděpodobnosti π, potom je ( pro dostatečně velká n ( n > 30))

π−p
π . (1 − π )

N ( 0;1) .

(3.26)

n
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

n>

9
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
vybíraných výrobků z celé série je maximálně 5% nebo jinak n ≤ 0, 05 , kde n je počet
N
vybíraných výrobků a N je celkový počet výrobků.
Je – li tento předpoklad porušen, musíme upravit navíc také vztahy (3.27) resp. (3.29) ,
tím , že použijeme konečnostní koeficient . Potom budou tedy tyto odhady následující
p −u α.
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
(3.31)
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
N −1

Pomocí našich nových vztahů provedeme opět zjištění hodnot intervalových odhadů
pro příklad 3.4. Protože byl výběr učiněn z velké série , předpokládáme, že hodnota n ≤ 0, 05
N
.
Budeme tedy používat vztahy (3.27) a (3.29). Platí vztah (3.28) ,neboť n= 400. Tedy
nové intervalové odhady jsou (0,039;0,086) , s korekcí na spojitost (0,037;0,087).
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

