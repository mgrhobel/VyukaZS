---
title: "mannWhitneyTest.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomové práce/mannWhitneyTest.pdf"
date: 2010-01-02
type: PDF (text-based)
---

UNIVERZITA PALACKÉHO V OLOMOUCI

PŘÍRODOVĚDECKÁ FAKULTA
KATEDRA MATEMATICKÉ ANALÝZY A APLIKACÍ MATEMATIKY

BAKALÁŘSKÁ PRÁCE
Porovnání k skupin pozorování

Vedoucí bakalářské práce:
Mgr. Jana Vrbková
Rok odevzdání: 2008

Vypracoval:
Gabriela Cielepová
M - E, III. ročník

Prohlášení
Prohlašuji, že jsem vytvořila tuto bakalářskou práci samostatně za vedení
Mgr. Jany Vrbkové a že jsem v seznamu použité literatury uvedla všechny zdroje
použité při zpracování práce.

V Olomouci dne 17. dubna 2008

Poděkování
Ráda bych na tomto místě poděkovala vedoucí bakalářské práce Mgr.Janě
Vrbkové za obětavou spolupráci i za čas, který mi věnoval při konzultacích. Dále si
zaslouží poděkování můj počítač, že vydržel moje pracovní tempo, a typograﬁcký
systém TEX, kterým je práce vysázena. A nakonec bych nejvíce chtěla poděkovat
mé rodině, která mě při mém studiu velice podporovala.

Obsah
Úvod

4

1 Porovnávání dvou skupin pozorování
1.1 Parametrická metoda - dvouvýběrový t-test . . . . . . . . . . . .
1.2 Neparametrická metoda – dvouvýběrový Wilcoxonův test (Mann
- Whitney test nebo-li U test) . . . . . . . . . . . . . . . . . . . .

5
5

2 Porovnávání více než dvou skupin
2.1 ANOVA . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
2.2 Lineární modely . . . . . . . . . . . . . . . . . . . . . . . . . . . .
2.2.1 Model s plnou hodností . . . . . . . . . . . . . . . . . . . .
2.2.2 Příklad (vážený průměr) . . . . . . . . . . . . . . . . . . .
2.2.3 Model s neúplnou hodností . . . . . . . . . . . . . . . . . .
2.3 Testování submodelů . . . . . . . . . . . . . . . . . . . . . . . . .
2.4 Předpoklady použití analýzy rozptylu . . . . . . . . . . . . . . . .
2.4.1 Testy normality . . . . . . . . . . . . . . . . . . . . . . . .
2.4.2 Bartlettův test . . . . . . . . . . . . . . . . . . . . . . . .
2.4.3 Leveneův test homogenity rozptylu . . . . . . . . . . . . .
2.5 Jednofaktorová analýza rozptylu (ANOVA1) . . . . . . . . . . . .
2.6 Testy mnohonásobného porovnání . . . . . . . . . . . . . . . . . .
2.6.1 Scheﬀého metoda . . . . . . . . . . . . . . . . . . . . . . .
2.6.2 Tukeyova metoda . . . . . . . . . . . . . . . . . . . . . . .
2.7 Neparametrická ANOVA – Kruskal-Wallisův test . . . . . . . . .

11
11
11
12
13
13
16
20
20
21
22
23
28
28
30
33

3 SAS
3.1 DATA step . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
3.2 PROC step . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
3.2.1 Procedura BOXPLOT . . . . . . . . . . . . . . . . . . . .
3.2.2 Procedura UNIVARIATE . . . . . . . . . . . . . . . . . .
3.2.3 Procedura TTEST . . . . . . . . . . . . . . . . . . . . . .
3.2.4 Procedura ANOVA . . . . . . . . . . . . . . . . . . . . . .
3.2.5 Procedura GLM . . . . . . . . . . . . . . . . . . . . . . . .
3.2.6 Procedura NPAR1WAY . . . . . . . . . . . . . . . . . . .

38
39
41
41
43
44
49
54
59

Závěr

69

Přílohy
Příloha 1: CD s kódy a daty pro výpočet příkladů v SASu . . . . . . .

70
70

Literatura

71

7

Úvod
Tato práce se zabývá porovnáváním k skupin pozorování. Chceme zjistit, zda
je možné více nezávislých výběrových souborů považovat za realizaci jedné náhodné veličiny. Přístupy k řešení tohoto úkolu lze rozdělit podle počtu porovnávaných skupin, tj. porovnáváme-li pouze dva výběry nebo více než dvě skupiny
pozorování. Dalé lze metody dělit podle toho, je-li nám známo něco o rozdělení
zkoumané náhodné veličiny, pak mluvíme o tzv.parametrickém přístupu nebo neparametrickém přístupu. Jako příklad metod pro porovnávání dvou skupin pozorování ve své práci uvádím dvouvýběrový t-test patřící mezi parametrické metody
a Wilcoxonův dvouvýběrový test náležející do skupiny neparametrických testů.
Pro více skupin pozorování potom představuji jednoduchou analýzu rozptylu,
známou jako metodu ANOVA a její neparametrickou obdobu - Kruskal-Wallisův
test. Poněvadž parametrické metody vyžadují splnění určitých předpokladů, uvádím v práci i vybrané metody pro testování těchto vlastností výběrových souborů.
Přestože jsou v práci obsažené potřebné teoretické poznatky, předpokládám u čtenáře znalosti z alespoň základního kurzu matematiky a statistiky. Jednotlivé metody porovnávání skupin dat jsem aplikovala na příklady spočítané jednak ručně,
ale také s pomocí softwaru SAS. Proto v závěru práce uvádím popis použitých
procedur softwaru SAS i s příklady kódů programů.

4

1

Porovnávání dvou skupin pozorování

1.1

Parametrická metoda - dvouvýběrový t-test

Jedná se o parametrický test (předpokládáme, že data pocházejí z normálního
rozdělení s parametry µ1 , σ 2 a µ2 , σ 2 ), kdy teoretickým základem je následující
věta.
Věta 1.1 Nechť X1 , . . . , Xn je výběr z N(µ1 , σ 2 ) a nechť Y1 , . . . , Ym je výběr z
N(µ2 , σ 2 ). Nechť tyto dva výběry jsou na sobě nezávislé. Předpokládáme, že n ≥ 2,
2
m ≥ 2, σ 2 > 0. Označme X, SX
a Y , SY2 charakteristiky těchto výběrů. Potom

r

X − Y − (µ1 − µ2 )
T =p
2
(n − 1)SX
+ (m − 1)SY2

nm(n + m − 2)
∼ tn+m−2
n+m

,

kde tn+m−2 je studentovo t-rozdělení o n + m − 2 stupních volnosti.

Důkaz:

viz. [1], strana 76.

Poznámka 1.1 Použité vzorce:
n

1X
X=
Xi ,
n i=1
m

Y =

1X
Yj ,
n j=1

n
1 X 2
2
(Xi − nX ) ,
n − 1 i=1

2
SX
=

SY2 =

m
1 X 2
2
(Y − mY ) .
m − 1 j=1 j

Chceme-li za předpokladů uvedených ve větě při neznámém σ 2 > 0 testovat
hypotézu H0 : µ1 − µ2 = ∆ proti H1 : µ1 − µ2 6= ∆, vypočteme
X −Y −∆

T =p
2
(n − 1)SX
+ (m − 1)SY2

r

nm(n + m − 2)
n+m

Jestliže |T | ≥ tn+m−2 (α), zamítneme H0 na hladině α.

5

.

Jedním z předpokladů pro použití dvouvýběrového t-testu je požadavek shodnosti rozptylů obou rozdělení. I když jeho mírné porušení nebývá závažné, přesto
je nutné zmínit další postupy užívané v takových případech.
Nechť X1 , . . . , Xn je výběr z N(µ1 , σ12 ) a Y1 , . . . , Ym je výběr z N(µ2 , σ22 ) nezávislý na prvním výběru. Je-li m ≥ n, utvoříme rozdíly X1 − Y1 , . . . , Xn − Yn .

Na ně lze aplikovat jednovýběrový t-test, neboť jednotlivé rozdíly jsou na sobě
nezávislé a každý z nich má rozdělení N(µ1 − µ2 , σ12 + σ2 2).

Nevýhodou tohoto postupu je však nejen ztráta m − n veličin Y-ových, ale i
neefektivní využití informace z veličin zbývajících.

V praxi často využíváme Welch - Satterthwaiteův t-test: Nejprve se vypočte:
2
SX
,

SY2 ,

S=

r

2
SX
S2
+ Y ,
n
m

υX =

2
SX
,
n

υY =

SY2
m

Testuje-li se hypotéza H0 : µ1 − µ2 = 0 proti H1 : µ1 − µ2 6= 0, pak se H0

zamítá v případě, že platí nerovnost

kde

( n11 + nu2 )2
µ −µ
q 1 2 22 ≥
,
2
1
s1
s2
+ n2 (nu2 −1)
n21 (n1 −1)
+
2
n1
n2
u=

s22
.
s21

Tento test má přibližně hladinu α
Příklad 1.1 Na dvou analytických váhách bylo provedeno vážení 10 vzorků s
výsledky (xi ; yi ) = (25; 28) , (30; 31) , (28; 26) , (50; 52) , (20; 24) , (40; 36) ,
(32; 33) , (36; 35) , (42; 45) , (38; 40) (mg). Na hladině významnosti 0, 01 zjistěte,
zda rozdílné výsledky jsou statisticky nevýznamné za předpokladu, že mají normální rozdělení.
Postup
Testujeme nulovou hypotézu H0 : µ1 = µ2 proti alternativní hypotéze H1 : µ1 6=
µ2 .

6

Nejprve sečteme všechny hodnoty x-ové a vydělíme počtem měření, tím získáme
průměr hodnot x, to samé uděláme i u hodnot y-ových.

xi
yi

1
25
28

2 3 4 5 6 7
30 28 50 20 40 32
31 26 52 24 36 33

8 9 10
36 42 38
35 45 40

P

341
350

průměr
x = 34, 1
y = 35

Dále vypočteme rozptyly náhodných veličin [viz Poznámka 1.1]:
P
2
s2x = ( Xi2 − nX )/(n − 1) = (12337 − 11628, 1)/9 = 78, 767
P
2
s2y = ( Yi2 − mY )/(m − 1) = (12936 − 12250)/9 = 76, 222 ,

kde n a m jsou počty vzorků jednotlivých vah.

Hodnoty dosadíme do vzorce testové statistiky T a zjistíme její hodnotu:

T =p

34, 1 − 35

(10 − 1)78, 767 + (10 − 1)76, 222

r

100(18)
= −0, 2286
10 + 10

Jestliže |T | ≥ tn+m+2 (α), zamítáme nulovou hypotézu.
Z tabulek kritických hodnot určíme podle stupňů volnosti na zvolené hladině
významnosti kritickou hodnotu, která se v tomto případě rovná 2, 878.
Závěr
Můžeme tedy říci, že nulovou hypotézu na zvolené hladině významnosti nezamítáme , tedy rozdíly středních hodnot jsou statisticky nevýznamné. Je jedno na
které z těchto dvou vah bychom vážili.

1.2

Neparametrická metoda – dvouvýběrový Wilcoxonův
test (Mann - Whitney test nebo-li U test)

Tento test používáme v případě, kdy výběry pocházejí ze souborů, které nemají normální rozdělení nebo o jejich rozdělení nic nevíme. Výhodou tohoto neparametrického testu je tedy jeho nezávislost na tvaru rozdělení. Nevýhodou, jako u
7

ostatních neparametrických testů, je menší schopnost odhalení nesprávných testových hypotéz pro danou hladinu významnosti α.
Jedná se vlastně o neparametrickou obdobu dvouvýběrového t-testu. Testujeme
hypotézu, kdy dva nezávislé výběry pocházejí ze stejného základního souboru.
Nechť X1 , . . . , Xm je náhodný výběr ze spojitého rozdělení s distribuční funkcí
F a nechť Y1 , . . . , Yn je na něm nezávislý náhodný výběr ze spojitého rozdělení s
distribuční funkcí G. Je třeba testovat hypotézu H0 : F = G.
Všech m + n veličin X1 , . . . , Xm , Y1 , . . . , Yn (tzv. sdružený výběr ) uspořádáme
vzestupně podle velikosti. Označme T1 součet pořadí hodnot X1 , . . . , Xm a T2
součet pořadí hodnot Y1 , . . . , Yn . Je jasné, že
1
T1 + T2 = (m + n)(m + n + 1) .
2
Testování následuje výpočtem veličiny U1 a U2 :
1
U1 = mn + m(m + 1) − T1
2
1
U2 = mn + n(n + 1) − T2
2
přitom platí, že U1 +U2 = mn. Pokud min(U1 , U2 ) je menší nebo rovno tabelované
kritické hodnotě, zamítá se nulová hypotéza.
Příklad 1.2 Statistické analýze byl podroben soubor dat naměřených hodnot
parametru, který je uveden v tabulce, celkem u 14-ti pacientů s tyreotoxikózou a
27-mi pacienty z kontrolní skupiny.
Postup
Použijeme neparametrický dvouvýběrový Wilcoxonův test, z důvodu malého počtu pozorování, neboť pozorovaná data nepocházejí z normálního rozdělení.
Data setřídíme vzestupně podle velikosti a přiřadíme jim jejich pořadí, pokud
se nám některá hodnota vyskytuje více než jednou, tak sečteme pořadí těchto
8

hodnot a vydělíme jejich počtem, tím získáme průměrnou hodnotu, kterou použijeme pro všechny hodnoty.
skupina
hodnota
pořadí

tx
tx
tx
tx
tx
tx
tx
tx
0, 001 0, 002 0, 003 0, 006 0, 01 0, 016 0, 023 0, 025
1
2
3
4
5
6
7
8

skupina
hodnota
pořadí

tx
tx
k0
tx
tx
tx
tx
k0
k0
0, 027 0, 03 0, 03 0, 034 0, 042 0, 058 0, 09 0, 53 0, 55
9
10, 5 10, 5
12
13
14
15
16
17

skupina
hodnota
pořadí

k0
k0
k0
k0
k0
k0
k0
k0
0, 552 0, 57 0, 57 0, 829 0, 866 0, 878 0, 98 1
18
19, 5 19, 5
21
22
23
24 25

skupina
hodnota
pořadí

k0
k0
k0
k0
k0
k0
k0
1, 29 1, 32 1, 37 1, 529 1, 553 1, 887 1, 91
27
28
29
30
31
32
33

skupina
hodnota
pořadí

k0
k0
k0
k0
k0
k0
2, 194 2, 3 2, 75 3, 39 3, 42 3, 8
36
37
38
39
40
41

k0
1, 028
26

k0
k0
2 2, 102
34
35

Sečteme hodnoty pořadí u jednotlivých skupin, T1 = 109, 5 a T2 = 751, 5.
Počet hodnot ve skupině tx je m = 14 a počet hodnot ve skupině k0 je n = 27.
Nyní si ověříme zda jsme přiřadili jednotlivým hodnotám správné pořadí:
1
T1 + T2 = (m + n)(m + n + 1)
2
1
751, 5 + 109, 5 = (27 + 14)(27 + 14 + 1)
2
861 = 861
Vypočteme veličiny U1 = 4, 5, U2 = 373, 5 a opět si ověříme, zda jsme počítali
správně:
U1 + U2 = mn
4, 5 + 373, 5 = 378
Zvolíme si min(U1 , U2 ) = 4, 5 a porovnáme s kritickou hodnotou Wilcoxonova
testu o m, n stupních volnosti a hladinou významnosti α = 0, 01 ⇒ W27,14 = 474.
9

Závěr Jestliže je min(U1 , U2 ) ≤ Wm,n , pak nulovou hypotézu, že se obě dis-

tribuční funkce rovnají, zamítáme. V tomto příkladě je na první pohled jasné, i
bez výpočtů, že distribuční funkce zkoumaných skupin se od sebe výrazně liší.

10

2

Porovnávání více než dvou skupin

2.1

ANOVA

Analýza rozptylu, ANOVA (z anglického Analysis of Variance), se zabývá
porovnáváním k skupin pozorování. Pokud se k = 2 můžeme použít dříve zmíněný dvouvýběrový t-test, při větším počtu pozorování se nám může zdát, že stačí
použít dvouvýběrový t-test postupně na každou z k(k −1)/2 možných dvojic sku-

pin pozorování. Pravděpodobnost zamítnutí nulové hypotézy, že střední hodnoty
výběrů se nám rovnají (H0 : µ1 = . . . = µk ), je-li správná, je však pro k ≥ 3 větší

než hladina významnosti α jednotlivých t-testů. Proto použijeme ANOVU, která
danou hladinu α dokáže udržet. Podstatou je rozložit variabilitu souboru dat na
příspěvky, které pocházejí od změny úrovně faktoru a které jsou způsobené náhodnými chybami. Pokud nulovou hypotézu zamítneme je třeba ještě zjistit, které
výběry se od sebe liší. To provádíme pomocí metod mnohonásobného porovnání.
Poněvadž ANOVA využívá metod testování submodelů lineárních modelů,
považuji za nezbytné seznámit čtenáře alespoň ve zkratce vybranými základními
pojmy a tvrzeními.

2.2

Lineární modely

Deﬁnice 2.1 Mějme náhodný vektor Y = (Y1 , . . . , Yn )′ . Nechť Xn×k je daná
matice a β = (β1 , . . . , βk )′ vektor parametrů. Řekneme, že se Y řídí lineárním
modelem, jestliže platí:
(a) EY = Xβ;
(b) varY = V existuje a nezávisí na β, kde EY je střední hodnota náhodného
vektoru Y a varY je jeho varianční matice.
Dále budeme předpokládat, že k < n. Řekneme, že b je lineárním odhadem vektoru β, existuje-li taková matice Uk×n , že b = UY.
Lineární odhad b vektoru β je nestranný, jestliže Eb = β.

11

Věta 2.1 Lineární odhad je nestranný tehdy a jen tehdy platí-li
UX = I.

(1)

[1], strana 193.

Důkaz:

Řekneme, že b je nejlepším nestranným lineárním odhadem (NNLO) vektoru
β, platí-li:
a) b je nestranný lineární odhad parametru β
b) je-li b∗ jiný nestranný lineární odhad β, pak platí varb∗ - var b ≥ 0 (tj. rozdíl
uvedených dvou variančních matic musí být matice pozitivně semideﬁnitní).
2.2.1

Model s plnou hodností

Je-li hodnost matice X rovna počtu jejich sloupců, tj. h(X) = k a varianční
matice V je regulární, pak hovoříme o modelu s plnou hodností.
Nejlepší nestranný lineární odhad vektoru β v takovém modelu stanovíme na
základě následující věty.
Věta 2.2 (Gaussova–Markovova) Nechť h(X) = k a nechť V=varY je regulární. Pak nejlepší nestranný lineární odhad (NNLO) b pro β je roven
b = (X ′V −1 X)X ′V −1 Y

(2)

b = (X ′V −1 X)−1 .

(3)

a má varianční matici

Důkaz:

[1], strana 194.

Věta 2.3 Nechť h(X) = k a nechť varY = V je regulární. Pak NNLO θ̂ parametru θ = c′ β je θ̂ = c′ b, kde b je NNLO vektoru β.
Důkaz:

[1], strana 194.

12

2.2.2

Příklad (vážený průměr)

Nechť Y1 , . . . , Yn jsou takové nezávislé nahodné veličiny, že
EYi = β,

varYi = σi2 > 0,

(4)

kde β je neznámý parametr a σ12 , . . . , σn2 jsou neznámá čísla. Máme tedy EY =
Xβ, varY = V, kde
V = Diag{σ12 , . . . , σn2 }.

X = (1, . . . , 1)′ = 1,

P
Označíme-li υ = ( ni=1 σi−2 )−1 , pak z Gaussovy–Markovovy věty dostaneme

NNLO pro β a jeho rozptyl

b=υ

n
X

σj−2 Yj ,

var b = υ .

j=1

Hodnota b představuje vážený průměr s vahami σ1−2 , . . . , σn−2 .
Věta 2.4 Jestliže se nezávislé náhodné veličiny Y1 , . . . , Yn řídí modelem (4) a
přitom mají normální rozdělení , pak b ∼ N(β, v) a při n > 1 platí
Z=

n
X
i=1

Důkaz:
2.2.3

σi−2 (Yi − b)2 ∼ χ2n−1

.

(5)

[1], strana 195.
Model s neúplnou hodností

Má-li matice Xn×k hodnost menší než k, tj. h(X) < k, mluvíme o modelu s
neúplnou hodností. Předpokládejme, že platí varY = σ 2 I, kde σ 2 > 0 je nějaký
neznámý parametr.
Nestranný lineární odhad vektoru β hledáme jako řešení speciální soustavy
rovnic, které nemusí být jednoznačné, ale minimalizuje reziduální součet čtverců
(obdoba metody nejmenších čtverců).
13

Věta 2.5 Výraz
(Y - Xb)′ (Y - Xb)

(6)

nabývá vzhledem k b nejmenší hodnoty v případě, že b je řešením soustavy rovnic
X′ Xb = X′ Y

(7)

.

Hodnota výrazu (6) je stejná pro všechna b, která jsou řešením soustavy (7).
Důkaz:

[1], strana 197.

Je-li b0 nějaké řešení soustavy (7), potom Se = (Y − Xb0 )′(Y − Xb0 )
nazýváme reziduální součet čtverců.
Věta 2.6 Soustava (7) je ekvivalentní se soustavou
∂
(Y − Xb)′(Y − Xb) = 0,
∂bj
Důkaz:

j = 1, . . . , k

(8)

.

[1], strana 197.

Soustavě (7), stejně jako soustavě (8), se říká soustava normálních rovnic.
Pokud nás zajímá jen určitá lineární kombinace parametrů β1 , . . . , βk , a je-li
hodnost matice menší než k, pak nemusí být každá kombinace dostatečně vhodná.
Nechť c = (c1 , . . . , ck )′ je daný vektor. Řekneme, že parametr θ = c1 β1 +. . .+ck βk
je odhadnutelný , existuje-li pro θ alespoň jeden lineární nestranný odhad. To
znamená, že chceme, aby existoval alespoň jeden vektor u = (u1 , . . . , un )′ , takový,
že Eu′Y = θ. Tento vzorec píšeme ve tvaru
u′(EY ) = θ

(9)

u′Xβ = c′β

(10)

nebo ve tvaru

14

Má-li předchozí vzorec platit pro libovolný vektor β, musí být u′X = c′ , tj.
(11)

c = X ′u

Na základě uvedených vlastností lze vyslovit větu, která shrnuje podmínky,
za kterých je parametr θ odhadnutelný.
Věta 2.7 (a) Parametr θ = c′β je odhadnutelný právě tehdy, je-li c nějakou
lineární kombinací řádků matice X.
(b) Parametr θ = c′β je odhadnutelný právě tehdy, je-li θ nějakou lineární kombinací složek vektoru EY.
Důkaz:

Část (a) plyne ze vztahu (11), část (b) ze vztahu (9).

Máme-li vektor parametrů θ = (θ1 , . . . , θp )′ se složkami typu θj = c′j β,
pak můžeme říci, že tento vektor je odhadnutelný, je-li odhadnutelná každá jeho
složka.
Pro potřeby odvození vztahů pro testování submodelů vyslovíme větu, která
upravuje vyjádření reziduálního součtu čtverců.
Věta 2.8 Pro reziduální součet čtverců Se = (Y − Xb)′(Y − Xb) platí

Důkaz:



Se = Y ′ I − X(X ′X)−X ′ Y

.

(12)

[1], strana 200.

Věta 2.9 Nechť Y ∼ N(Xβ, σ 2 I) a nechť r = h(X).
Pak σS2e ∼ χ2n−r a s2 =
Důkaz:

Se
je nestranným odhadem parametru σ 2 .
(n−r)

[1], strana 200.

Pro konstrukci statistiky ve větě 2.11, o níž dokážeme, že má F-rozdělení, budeme potřebovat následující větu.
15

Věta 2.10 Má-li vektor Y normální rozdělení , pak vektor X ′Y a veličina Se
jsou nezávislé. Rovněž vektor b a veličina s2 jsou nezávislé.
Důkaz:

2.3

[1], strana 200.

Testování submodelů

Někdy musíme vzít současně se základním lineárním modelem v úvahu i několik speciálních případů, kterým se říká submodely. Submodely se volí tak, aby
měly při popisu dané situace přímou a snadnou interpretaci. Zde se budu zabývat jen základními teoretickými vlastnostmi submodelů, jejich využití pro účely
porovnání k skupin pozorování popíši pozdějí v samostatné kapitole.
Celý postup ukážu na příkladu, kdy máme lineární model a jeho dva submodely.
Případ více submodelů je už zcela analogický.
Mějmě náhodný vektor Y = (Y1 , . . . , Yn )′ a předpokládejme, že platí model
M:

Y ∼ N(Xα, σ 2 I) ,

kde X je matice typu n × k, α je k –rozměrný vektor neznámých parametrů, σ 2 je

též neznámý parametr a I je matice typu n × n. Současně s modelem M uvažujme
modely

M1 :

Y ∼ N(Uβ, σ 2 I)

M2 :

Y ∼ N(Tγ, σ 2 I) ,

a

kde U je matice typu n × k1 , vektorβ má k1 složek, T je matice typu n × k2 a
vektor γ má k2 složek. Nechť h(X) = r, h(U) = r1 , h(T) = r2 .

Řekneme, že M1 je submodelem modelu M, jestliže každý sloupec matice U
patří do lineárního obalu sloupců matice X a jestliže r > r1 . První podmínka
bude splněna právě tehdy, bude-li existovat matice Kk×k1 tak, že
16

U = XK

.

(13)

Zcela analogicky řekneme, že M2 je submodelem modelu M1 , jestliže každý
sloupec matice T patří do lineárního obalu sloupců matice U a jestliže r1 > r2 .
První podmínka bude splněna právě tehdy, bude-li existovat matice Lk1 ×k2 tak,
že
T = UL

.

(14)

V takovém případě samozřejmě dostaneme T = UL = XKL. Téměř vždy se
volí submodely tak, že platí k > k1 > k2 ≥ 1.

Poznámka 2.1 M1 je speciálním případem modelu M. Platí-li tudiž pro Y model M1 , platí pro Y automaticky také model M. Platí-li pro Y model M2 , platí
též M1 i M2 .
NNLO pro EY v případě platnosti modelu M je
µ̂ = X(X ′X)−X ′ Y ,

(15)

v případě platnosti modelu M1
υ̂ = U (U ′U )−U ′ Y ,

(16)

v případě platnosti modelu M2
τ̂ = T (T ′ T )−T ′ Y .

(17)

Model M vybíráme tak bohatý, abychom si mohli být jistí, že popisuje dobře
chování Y. Potom však chceme zjistit, zda lze použít jednodušší model M1 o
méně parametrech nebo zda lze dokonce zredukovat až na model M2 . Platí-li
M1 , pak rozšíření na M nepřinese podstatné změny a vektory υ̂ a µ̂ by se neměli
podstatně lišit. Pokud ale tyto vektory budou od sebe významně odlišně, svědčí to
proti možnosti redukce M na M1 . Analogicky platí to samé i pro ostatní vektory.
17

Věta 2.11 Platí-li pro Y model M1 , má náhodná veličina

F1 =

(µ̂ − υ̂)′(µ̂ − υ̂) 1
r − r1
s2

(18)

rozdělení Fr−r1 ,n−r . Platí-li model M2 , pak

F2 =

(υ̂ − τ̂ )′(υ̂ − τ̂ ) 1
r1 − r2
s2

(19)

má rozdělení Fr1 −r2 ,n−r .
Důkaz:

Protože U = XK a T = U L = XKL, můžeme vyjádřit
υ̂ = U (U ′U )−K ′ X ′ Y ,

τ̂ = T (T ′T )−L′K ′ X ′Y .

(20)

Potom je vidět, že µ̂ − υ̂ i υ̂ − τ̂ je funkcí vektoru X ′Y . Z toho důvodu jsou
(µ̂ − υ̂)′ (µ̂ − υ̂) a s2 nezávislé (Věta 2.10). Nechť platí Y ∼ N(U β, σ 2 I). Pak
vzhledem k (15) a (13) je

E(µ̂ − υ̂) = E µ̂ − E υ̂ = E(X(X ′X)−X ′ Y ) − E(U (U ′U )−U ′ Y ) =
= X(X ′X)−X ′ EY − U (U ′U )−U ′EY =
=

X(X ′X)−X ′U
{z
}
|

U=XK⇒X(X′ X)− X′ XK

β − U (U ′U )−U ′U β = U β − U β = 0
|
{z
}
U

Užitím vzorce X ′X[(X ′ X)−]′X ′ = X ′ dostaneme



′
varX(X ′X)−X ′Y = X(X ′X)−X ′ varY X(X ′X)−X ′ =
′

= [X(X ′X)−X ′ ] σ 2 I [X(X ′ X)−X ′] =
′

= σ 2 X(X ′X)−X ′X [(X ′X)−] X ′ = σ 2 X(X ′ X)−X ′ .
Analogicky se získá



′
varU (U ′U )−U ′Y = U (U ′U )−U ′ varY U (U ′U )−U ′ =
′

= [U (U ′U )−U ′ ] σ 2 I [U (U ′U )−U ′ ] =
′

= σ 2 U (U ′ U )−U ′U [(U ′U )−] U ′ = σ 2 U (U ′U )−U ′ .
Dále
cov(υ̂, µ̂) = σ 2 U (U ′U )−K ′X ′ X[(X ′X)−]′ X ′
= σ 2 U (U ′U )−K ′X ′ = σ 2 U (U ′U )−U ′ .
18

Vzhledem k tomu, že Matice A(A′A)−A′ je vždy symetrická (viz [1], str. 324,
Věta A.21) je cov(µ̂, υ̂) = [cov(υ̂, µ̂)]′ = cov(υ̂, µ̂). Odtud máme
var(µ̂ − υ̂) = varµ̂ − cov(µ̂, υ̂) − cov(υ̂, µ̂) + varυ̂ =
= σ 2 [X(X ′X)−X ′ − U (U ′U )−U ′ ] .

Užitím vztahu
U (U ′U )−U ′ X(X ′X)−X ′ = U (U ′U )−K ′X ′X(X ′X)−X ′ =
= U (U ′U )−K ′X ′ = U (U ′U )−U ′
snadno dostaneme, že matice σ −2 var(µ̂ − υ̂) je idempotentní a symetrická. Proto
jednou z pseudoinverzních matic k ní je jednotková matice (viz [1], str. 323, Věta
A.15), a tak můžeme říci, že
(µ̂ − υ̂)′ [var(µ̂ − υ̂)]− (µ̂ − υ̂) = σ −2 (µ̂ − υ̂)′ (µ̂ − υ̂)
má χ2 rozdělení (věta 4.15, Anděl 2005, str. 68). Matice X(X ′ X)−X ′ je symetrická a idempotentní a platí [X(X ′X)−X ′]X = X ⇒ h[X(X ′ X)−X ′] =
h(X) = r. Analogické tvrzení platí i pro matici U. Vzhledem k symetrii a indempotentnosti, hodnost idempotentní matice se rovná její stopě, máme
h[σ2 (X(X′ X)− X′ −U(U ′ U)− U ′ )]

}|
{
z
′
−
′
′
− ′
h [var(µ̂ − υ̂)] = h X(X X) X − U (U U ) U =

= Tr [X(X ′X)−X ′ − U (U ′ U )−U ′] =
= TrX(X ′X)−X ′ − TrU (U ′U )−U ′ = r − r1 .

Poněvadž s2 = σS2e má dle věty 2.9 rozdělení χn−r , s2 a (µ̂−υ̂)′ (µ̂−υ̂) jsou nezávislé
a dokázali jsme, že σ −2 (µ̂ − υ̂)′ (µ̂ − υ̂) má rozdělení χr−r1 , pak z toho plyne, že
náhodná veličina F1 má rozdělení Fr−r1 ,n−r .

Důkaz druhé části věty je podobný. Platí-li M2 , je E(υ̂ − τ̂ ) = 0 a dále se
dostane


var(υ̂ − τ̂ ) = σ 2 U (U ′U )−U ′ − T (T ′T )−T ′



Poznámka 2.2 Pro veličiny Se , µ̂, υ̂ a τ̂ platí
Se = Y ′Y − µ̂′µ̂
19

,

(21)

(µ̂ − υ̂)′(µ̂ − υ̂) = µ̂′µ̂ − υ̂ ′υ̂
(υ̂ − τ̂ )′(υ̂ − τ̂ ) = υ̂ ′υ̂ − τ̂ ′ τ̂ .
Poznámka 2.3 Veličiny Se , µ̂, υ̂ a τ̂ splňují identitu
Se + (µ̂ − υ̂)′(µ̂ − υ̂) + (υ̂ − τ̂ )′(υ̂ − τ̂ ) = Y ′Y − τ̂ ′ τ̂ .

2.4

(22)

Předpoklady použití analýzy rozptylu

Před použitím analýzy rozptylu musí být ověřeny následující předpoklady
o výběru:

1. Data mají normální rozdělení: náhodné chyby ǫij jsou náhodné veličiny
s normálním rozdělením a střední hodnotou chyb rovnou nule,
tj. ǫij ∼ N(0, σ 2 ).
2. Rozptyly v jednotlivých porovnávaných skupinách σ 2 jsou stejné (homoskedasticita), tj. máme k dispozici výběry z rozdělení N(µ1 , σ 2 ), . . . , N(µk , σ 2 ).
3. Výběry, tj. data jednotlivých skupin jsou nezávislá - nezávislost.
Zatímco 3. podmínka je splněna na základě konstrukce pokusu, k ověření
podmínek normality a homoskedasticity používáme speciální testy.
2.4.1

Testy normality

Nechť ξ1 , . . . , ξn je náhodný výběr. Chceme testovat hypotézu H0 , že jde o
výběr z N(µ, σ 2 ), kde parametry µ a σ nejsou známy. Nejprve se vytvoří třídy

(−∞, b1 ) ,

hb1 , b2 ) ,

hb2 , b3 ) ,

,

...,

hbk−2 , bk−1 ) ,

hbk−1 , ∞)

,

kde k ≥ 4. Pro stručnost označíme i-tou třídu symbolem Ji . Pravděpodobnost
pi , že daná veličina ξj (j = 1, . . . , n) padne do Ji , je rovna
20

pi = pi (µ, σ) =

Z

f (x)dx ,

Ji

kde


1
(x − µ)2
f (x) = √
exp −
2σ 2
2πσ

.

Předpokládejme,že máme soustavu
k

1 X Xi
µ=
n i=1 pi

Z

k

xf (x)dx ,

Ji

1 X Xi
σ =
n i=1 pi
2

Z

Ji

(x − µ)2 f (x)dx ,

která se řeší iteračně. Nezapomeňme, že na µ i σ závisejí pi i f (x), které jsou na
pravých stranách těchto rovnic. Řešení soustavy označíme µ̂ a σ̂. Potom vypočteme

2

χ =

k
X
[Xi − npi (µ̂, σ̂)]2
i=1

npi (µ̂, σ̂)

.

Pokud vyjde χ2 > χ2k−3 (α), zamítáme hypotézu H0 . Uvedený test patří do skupiny
tzv. χ2 testů dobré shody.
Normalita se také často testuje pomocí výběrové šikmosti a výběrové
špičatosti - viz [1], str. 275
2.4.2

Bartlettův test

Bartlettův test lze využít k hodnocení homoskedasticity jak u vyvážených
(tj. stejný počet pozorování u všech porovnávaných k skupin), tak i u nevyvážených souborů (tj. rozdílný počet pozorování v porovnávaných k skupinách), proto
v tomto smyslu mluvíme o univerzálním testu. Bartlettův test využíváme tedy
k testování hypotézy:
H0 : σ12 = σ22 = · · · = σk2
21

,

HA : non H0

.

Testovým kritériem Bartlettova testu je veličina B, která je deﬁnovaná jako
k
X
1
2
B = [(n − k) ln s −
(ni − 1) ln s2i ]
C
i=1

(23)

,

mající za předpokladu platnosti H0 a pro i = 1, . . . , k, ni ≥ 6 přibližně rozdělení
χ2k−1 . Testovanou hypotézu zamítáme pokud platí:
B ≥ χk−1 (α)
Při výpočtu testové statistiky B užíváme tyto vztahy:

s2i =

ni
1 X
(yij − yi. )2
ni − 1 j=1

i = 1, . . . , k

,

(24)

yi. = průměr i-tého řádku,
ni
k
1 XX
s=
(yij − yi. )2
N − 1 i=1 j=1

C =1+

Pk

1
1
i=1 ni −1 − N −k

3(k − 1)



,

.

(25)

(26)

Bartlettův test je však poměrně slabý a dosti citlivý na porušení normality souborů. To může být velký problém především u souborů s malým počtem pozorování. Z tohoto důvodu se dnes spíše používá Leveneův test.

2.4.3

Leveneův test homogenity rozptylu

Tento test v podstatě provádí analýzu rozptylu na reziduích a není tak citlivý
na porušení předpokladu normality. Vytvoří se k skupin náhodných veličin a to

22

|Y11 − y1. |
..
.

...
..
.

|Y1n1 − y1. |
..
.

|Yi1 − yi. |
..
.

...
..
.

|Yini − yi. |
..
.

|Yk1 − yk.|

. . . |Yknk − yk. |

Využívá se přitom proměnná zij = yij − yi.

pro i = 1, 2, . . . , k a

j = 1, 2, . . . , ni . Na tyto uvedene skupiny se použije analýza rozptylu jednoduchého třídění. Pokud tato analýza vyjde signiﬁkantně, zamítne se hypotéza o
shodnosti rozptylu. Pro jisté případy jsou navrženy i modiﬁkace Leveneova testu
(např. v případě šikmosti souboru lze využít místo yi. mediánu).
Je třeba zdůraznit, že test je pouze aproximativní, protože nejsou splněny předpoklady pro použití analýzy rozptylu či její neparametrické varianty. Je tomu
tak proto, že veličiny Yij − yi. nejsou nezávislé a absolutní hodnoty těchto veličin
nemají normální rozdělení.

2.5

Jednofaktorová analýza rozptylu (ANOVA1)

Máme nezávislé výběry z rozdělení N(µ1 , σ 2 ), . . . , N(µk , σ 2 ). Testujeme hypotézu H0 : µ1 = . . . = µk , přičemž parametr σ 2 není znám.
Náhodný výběr z rozdělení N(µi , σ 2 ) označme Yi1 , . . . , Yini . Jeho rozsah je tedy
ni . Všechny výběry dohromady mají N = n1 + . . . + ni členů. Dále se označuje
P i
P P i
Yi. = nj=1
Yij
Y.. = ki=1 nj=1
Yij .
Průměry budeme označovat pomocí písmene y, u něhož tečky znamenají obor,
přes který se průměr stanovuje. Speciálně tedy:

yi. =

Yi.
,
ni

y.. =

23

Y..
n

Situaci k nezávislých výběrů lze zachytit v následující tabulce:

Schéma výchozí situace

číslo
výběru

počet
prvků

zjištěné hodnoty
sledovaného znaku

průměr

rozptyl

1
2
..
.

n1
n2
..
.

y11 , y12 , . . . , y1j , . . . , y1n1
y21 , y22 , . . . , y2j , . . . , y2n2

y1.
y2.
..
.

s21
s22
..
.

i
..
.

ni
..
.

yi1 , yi2, . . . , yij , . . . , yini

yi.
..
.

s2i
..
.

k

nk

yk1, yk2 , . . . , ykj , . . . , yknk

yk.

s2k

Výběr z N(µ1 , σ 2 ) . . . N(µk , σ 2 )
Předpoklady, které jsme učinili o veličinách Yij , můžeme ekvivalentně vyjádřit
takto:
Yij = µ + αi + ǫij ,

j = 1, . . . , ni ;

i = 1, . . . , k ,

(27)

kde µ, αi a σ 2 jsou neznámé parametry, Yij - náhodná veličina(např. užitkovost
j-tého potomka po i-tém otci u hospodářských zvířat), µ-průměrná úroveň všech
faktorů, ǫij -nezávislé náhodné veličiny s rozdělením N(0, σ 2 ).
Místo µi máme nyní µ + αi , což znamená, že jsme zavedli o jeden parametr
více; model jsme přeparametrizovali. Následkem této úpravy jsme dostali soustavu rovnic se singulární maticí a tak samotné parametry µ, α1 , . . ., αi budou
neodhadnutelné. Jedná se o lineární model s neúplnou hodností. Nejprve odvo-

24

díme soustavu normálních rovnic
k

n

k

n

i
∂ XX
(Yij − µ − αi )2 = 0 ,
∂µ i=1 j=1
i
∂ XX
(Yij − µ − αi )2 = 0 ,
∂αt i=1 j=1

t = 1, . . . , k

odtud po úpravě dále dostaneme:
Nµ +

k
X

ni αi = Y.. ,

(28)

i=1

nt µ + nt αt = Yt.

t = 1, . . . , k

(29)

Tato soustava má singulární matici, což si můžeme potvrdit tím, že součet rovnic
(29) přes všechna t dává rovnici (28).
Přidáme-li podmínku:
k
X

ni αi = 0

(30)

i=1

bude soustava (28), (29) a (30) řešitelná. Řešení označíme jako µ0 , αi0 , dostáváme
µ0 = y.. ,

αi0 = yi. − y.. ,

i = 1, · · · , k .

Každý parametr EYij = µ + αi je odhadnutelný (Věta 2.7). Odhad tohoto parametru je stále stejný, ať už za µ a αi dosadíme jakékoli řešení normálních rovnic
(Věta 2.6). Nejlepším nestranným lineárním odhadem µ + αi je tedy yi. . Libovolná lineární kombinace hodnot EYij je rovněž odhadnutelná. Odtud vidíme, že
parametr αi − αt = EYi1 − EYt1 je odhadnutelný a jeho NNLO je yi. − yt. .
Testovanou hypotézu H0 : µ1 = . . . = µk pak můžeme zapsat
H0 : α1 = α2 = . . . = αk = 0
25

a interpretovat jako test shodnosti efektů αi . Za platnosti H0 bude mít model
Yij = µ + αi + ǫij tvar
Yij = µ + ǫij

,

(31)

což je jeho submodel.
V případě tohoto submodelu µ odhadneme z rovnice
k

n

i
∂ XX
(Yij − µ)2 = 0
∂µ i=1 j=1

(32)

z níž dostaneme, že NNLO pro µ je y.. .
Nyní můžeme přistoupit k aplikaci vět o lineárním modelu s neúplnou hodností. V případě modelu (24) je NNLO pro EYij veličina µ̂ij = yi. , v případě
submodelu (28) je NNLO pro EYij veličina υ̂ij = y.. .
Y = (Y11 , . . . , Y1n1 , . . . , Yk1, . . . , Yknk )′ , podobnou strukturu mají přislušné odhady µ̂ a υ̂ vektoru středních hodnot EY.
Klasická jednofaktorová analýza rozptylu dat porovnává střední hodnoty dvou
či více úrovní faktoru A za účelem určit, zda alespoň jedna střední hodnota se
liší od ostatních. Statistická významnost je testována F -testem tak, že nulová
hypotéza H0 nám říká „Všechny střední hodnoty jsou stejnéÿ proti alternativní
HA „Alespoň jedna střední hodnota se odlišuje od ostatníchÿ.
Rozklad celkové variability
Celková měnlivost (variabilita) se rozkládá na měnlivost způsobenou úrovněmi
třídícího faktoru a měnlivost způsobenou opakováním pokusu pro jednotlivé úrovně
tříděného faktoru. Celkovou variabilitu ST rozdělíme na dva sčítance, variabilitu
meziskupinovou(SA ) a variabilitu vnitroskupinovou(Se ). Viz Poznámka v kapitole
2.2.
ST = SA + Se

26

SA = (µ̂ − υ̂)′ (µ̂ − υ̂)
ST = (Y − υ̂)′ (Y − υ̂)
Se = (Y − µ̂)′ (Y − µ̂)
ni
k X
X
i=1 j=1

2

(yij − y.. ) =

|

{z

ST

}

k
X

|i=1

2

ni (yi. − y.. ) +
{z

SA

}

ni
k X
X
i=1 j=1

|

(yij − yi. )2
{z

}

Se

Nulovou hypotézu pak zamítáme na zvolené hladině významnosti α, pokud testová statistika

FA =

SA
(k−1)
Se
(N −k)

=

s20
∼ Fk−1,N −k
s2

překročí příslušný kvantil Fischerova-Snedecorova rozdělení. Formálně zapsáno:
FA ≥ Fk−1,N −k (1 − α)
Výsledky analýzy rozptylu se zapisují do tzv. tabulky analýzy rozptylu. Při
překročení kritické hodnoty F - rozdělení pro hladinu významnosti α = 0, 05 se
v tabulce analýzy rozptylu u hodnoty FA píše hvězdička (α = 0, 01 · · · dvě hvěz-

dičky, α = 0, 001 · · · tři hvězdičky).

Její nejjednodušší forma má tvar:

Tabulka analýzy rozptylu jednoduchého třídění
Variabilita

mezi skupinami
reziduální
celková

Součet
čtverců
(SS)
SA
Se
ST

Počet stupňů
volnosti
(df)
k−1
N −k
N −1
27

Podíl
MS= SS
df
s20
s2
–

Testová
statistika
F= Ms2S
FA
–
–

Pokud k = 2, pak se výsledek získaný metodou analýzy rozptylu shoduje s
výsledkem dvoustranného t–testu. Tímto způsobem však nelze testovat jednostranné hypotézy, které t-testem studovat lze.
Pokud dojde k zamítnutí nulové hypotézy, musíme ještě rozhodnout, které
výběry se od sebe liší. K tomu se používá některá z metod mnohonásobného
porovnání.

2.6

Testy mnohonásobného porovnání

Mezi často používané metody mnohonásobného (párového) porovnávání patří
Scheﬀého a Tukeyho metoda.
2.6.1

Scheﬀého metoda

Tato metoda mnohonásobného porovnávání je založena na použití následující
věty.
Věta 2.12 (Scheﬀého) Nechť X= (X1 , . . . , Xm ) ′ ∼ N(µ, σ 2 V ), kde V > 0 je

známá matice a σ 2 neznámý kladný parametr. Budiž A nějaký t-rozměrný podprostor prostoru Rm , přičemž t > 0. Nechť s2 je nezávislý odhad pro σ 2 s υ stupni
2

volnosti; to znamená, že υs
∼ χ2υ a že s2 a X jsou nezávislé. Pak pravděpodobσ2
nost, že nerovnost

|a ′ X − a ′µ| ≤

q
ts2 Ft,υ (α)a ′V a

platí pro všechna a ∈ A současně, je rovna 1 − α .
Důkaz:

[1], strana 206.

Testujeme hypotézu
H0 : µ i = µ j ,
HA : µi 6= µj .
28

Zavedeme vektory aij , které mají i -tou složku rovnu 1, j -tou složku rovnou −1

a ostatní složky rovny 0. Pak µi = µj platí právě tehdy když a′ij µ = 0. Protože
t= m − 1, aij ′ X= Xi − Xj , a′ij V aij = υii + υjj − υij − υji, podle Scheﬀého věty
platí nerovnost

|Xi − Xj | ≤

q

(m − 1)s2 (υii + υjj − υij − υji)Fm−1,υ (α) .

Pro všechny dvojice (i, j) s pravděpodobností ≥ 1 − α. (Pravděpodobnost splnění

této nerovnosti nemusí být vždy rovna 1 − α, protože vektory aij nevyužívají

celého prostoru A.) Pokud tedy pro nějakou dvojici (i0 , j0 ) platí obrácená nerovnost

q
|Xi0 − Xj0 | > (m − 1)s2 (υi0 i0 + υj0j0 − υi0 j0 − υj0i0 )Fm−1,υ (α) ,

(33)

potom hypotézu H0 zamítáme. V praxi se často setkáváme s tím, že složky vektoru
X jsou nezávislé, pak matice V je diagonální a nerovnost se redukuje na
q
|Xi0 − Xj0 | > (m − 1)s2 (υi0 i0 + υj0j0 )Fm−1,υ (α) .

(34)

Obecně můžeme říci, že rovnost středních hodnot µi. , µj. zamítáme na hladině
α, když platí

|Xi. − Xj. | ≥

s

1
1  Se
+
(k − 1)Fk−1,N −k α
ni nj N − k

(35)

kde Fk−1,N −k α je kritická hodnota Fischer-Snedecorova rozdělení.
Scheﬀého metoda je velmi výhodná pro svou obecnost, ale na druhou stranu
není tak citlivá, jako další metoda, kterou teď uvedem.

29

2.6.2

Tukeyova metoda

Nejdříve zavedeme tzv. studentizované rozpětí.
Lemma 2.1 Nechť X1 , X2 , . . . , Xm je náhodný výběr z rozdělení N(µ, σ 2 ), kde
σ 2 > 0. Označme R= max Xi −min Xi rozpětí. Nechť s2 je nezávislý odhad pro σ 2

s υ stupni volnosti; to znamená, že υs2/σ 2 ∼ χ2υ a že s2 a X= (X1 , · · · , Xm ) ′ jsou
nezávislé. Označme Q = R/s náhodnou veličinu, které se říká studentizované

rozpětí. Pak rozdělení náhodné veličiny Q, které označujeme symbolem qm,υ
nezávisí na µ a σ.
Důkaz:

[1], strana 209.

Tukeyho metoda je založena na přímém využití následující věty.
Věta 2.13 (Tukeyova) Nechť X1 , . . . , Xm jsou nezávislé náhodné veličiny a nechť
Xi ∼ N(µi , b2 σ 2 )

, i = 1, · · · , m, kde b je známá kladná konstanta. Nechť s2 je

nezávislý odhad pro σ 2 s υ stupni volnosti; to znamená, že υs2 /σ 2 ∼ χ2υ a že s2

a X jsou nezávislé. Pak pravděpodobnost, že platí

Xi − Xj − bsqm,υ (α) ≤ µi − µj ≤ Xi − Xj + bsqm,υ (α)
pro všechny dvojice (i, j) současně, je rovna 1 − α.
Důkaz:

[1], strana 209.

Tento test lze použít v případě vyváženého třídění (tj. stejný počet pozorování
u všech porovnávaných k skupin), je tak méně obecnější než Scheﬀého metoda,
ale za to více citlivější.
Obecně můžeme říci, že rovnost středních hodnot µi. , µj. zamítneme na hladině α, když platí následující nerovnice:
|Xi. − Xj. | ≥

s

Se
qk,N −k (1 − α)
P (N − k)
30

(36)

pro případ vyváženého třídění tj. P = n1 = . . . = nk .
V případě nevyváženého třídění, lze využít modiﬁkaci Tukeyova testu
s
1
1
Se
|Xi. − Xj. | >
+
qk,N −k (1 − α)
2(N − k) ni nj

(37)

kde qk,N −k (1 − α) je kvantil studentizovaného rozpětí.
Příklad 2.1 ANOVA - komplexní příklad
Zadání získáno z on-line zdroje:
[http : //www2.bakersf ieldcollege.edu/mrozell/documents/Math%20B22/
Ch%2015%20Application.pdf ]
Tři náhodně vybrané skupiny kuřat byly krmené třemi různými dávkami krmení. Výsledné hodnoty, získané během určitého časového období, jsou uvedeny
v následující tabulce (předpokládáme data z normálního rozdělení):
P
1 2 3 4 5 6 7 8 9 10 11 12 13
skupina 1 4 4 7 3 2 5 4 5 2 3 6 4 5
54 y1. = 4, 154
skupina 2 3 4 5 4 6 4 5 6 7 6 5 5 5
65 y2. = 5
skupina 3 6 7 7 7 6 8 5 6 7 6 7 5 6
83 y3. = 6, 385
202 y.. = 5, 18
V následující tabulce jsou uvedeny výpočty získané pomocí vzorců uvedených
v teorii:
variabilita
skupinová
reziduální
celková
ni
k X
X
i=1 j=1

SS
df
MS
32, 9822 2 16, 4911
48, 769 36 1, 3547
81, 7436 38

(yij − y.. )2 =

k
X
i=1

ni (yi. − y.. )2 +

F
12, 1732

ni
k X
X
i=1 j=1

(yij − yi. )2

ST = SA + Se
V tabulce kvantilů Fischer-Snedecorova rozdělení jsme zjistili, že pro α = 0, 05
je F2,36 = 3, 25945. Nulovou hypotézu tedy zamítáme na zvolené hladině významnosti α, protože testová statistika překročila příslušný kvantil. Musíme tedy ještě
31

rozhodnout, které výběry se od sebe liší. Stačí použít jen jednu ze dvou nejčastěji používaných metod, Scheﬀého nebo Tukeyho. Postupně užijeme názorně obě
metody:
Scheﬀého metoda Pokud je

|Yij − Yj. | ≥

s

(

1
Se
1
+ )
(k − 1)Fk−1,N −k (1 − α)
ni nj N − 1

zamítáme nulovou hypotézu, že střední hodnoty dvou výběrů se nám rovnají.
1
1
2

2
3
0, 846 2, 231
1, 385
s

(

1
1
Se
+ )
(k − 1)Fk−1,N −k (1 − α) = 1, 135
ni nj N − 1

Díky tomu můžeme říci, že nulovou hypotézu zamítáme v případě 1. a 3.
skupiny a také v případě 2. a 3. skupiny.
Tukeyova metoda Použije se stejný postup jako u Scheﬀého metody, pouze
rozdíly středních hodnot se porovnají s kvantilem studentizovaného rozpětí.
s

Se
qk,N −k (1 − α) = 1, 117
P (N − k)

Vyšel stejný výsledek jako u Scheﬀého metody, tím jsme si jen potvrdili správnost výsledků.
Bartlettův test Slouží k ověření homoskedasticity výběrů, testujeme hypotézu H0 : σ12 = . . . = σk2 proti alternativní hypotéze HA : nonH0 . Nejprve si
vypočteme hodnotu C, následně rozptyly jednotlivých výběrů s2i a celkový rozptyl s:
C=

28
;
27

s21 = 2, 141;

7
s22 = ;
6
32

s23 = 0, 7564;

s = 1, 2834

Hodnoty nyní dosadíme do vzorce pro testovou statistiku B a vyjde, že B =
1, 2995. Nulová hypotéza se zamítá, jestli je testová statistika B ≥ χk−1 (α) =
5, 99 ⇒ nulovou hypotézu nelze zamítnout.

Leveneův test homogenity rozptylů

Využívá se přitom proměnné zij , kde zij = |Yij − yi. |, která nahradí původní data

a dále se na tyto data aplikuje klasická jednofaktorová analýza rozptylu.

skupina 1
skupina 2
skupina 3
skupina 1
skupina 2
skupina 3

1
2
3
4
5
6
7
8
0, 154 0, 154 2, 846 1, 154 2, 154 0, 846 0, 154 0, 846
2
1
0
1
1
1
0
1
0, 385 0, 615 0, 615 0, 615 0, 385 1, 615 1, 385 0, 385
P
9
10
11
12
13
průměr
2, 154 1, 154 1, 846 0, 154 0, 846 14, 462 y1. = 1, 113
2
1
0
0
0
10
y2. = 0, 769
0, 615 0, 385 0, 615 1, 385 0, 385 9, 385 y3. = 0, 722
33, 847 y.. = 0, 868
variabilita
skupinová
reziduální
celková

SS
df
MS
1, 184
2 0, 592
18, 214 36 0, 506
19, 398 38

F
1, 17

Z tabulky kvantilů F-rozdělení opět zjistíme pro α = 0, 05 F2,36 = 3, 25945.
Nulovou hypotézu tedy nemůžeme zamítnout na zvolené hladině významnosti α.

2.7

Neparametrická ANOVA – Kruskal-Wallisův test

Jedná se o neparametrický test pro jednoduché třídění, který lze použít,
nejsou-li splněny předpoklady parametrické analýzy rozptylu (ANOVA1). Jde
zejména o případy, kdy máme výběry z rozdělení značně se lišících od normálního.
Nechť Yi1 , . . . , Yini je výběr z nějakého rozdělení se spojitou distribuční funkcí
Fi , i = 1, . . . , k. Nechť všechny tyto výběry jsou na sobě nezávislé. Budeme testovat hypotézu
H0 : F1 (x) = F2 (x) = . . . = FK (x)
33

pro všechna x

proti alternativě H1 , že H0 neplatí. Všechny veličiny Yij dohromady vytvoří sdružený náhodný výběr o rozsahu N = n1 + . . . + ni .
Podstatou testu je, že ze všech N hodnot utvoříme rostoucí posloupnost a
každé veličině Yij přiřadíme její pořadí Rij , tato pořadí se použijí místo pozorovaných hodnot. Pokud jsou tato pořadí dostatečně „promíchanáÿ, pak můžeme
uvažovat o shodě mediánů. Pokud máme dostatečně velké četnosti jednotlivých
souborů, můžeme použít testovou statistiku:

Q=

k
X
12
Ti2
− 3(N + 1)
N(N + 1) i=1 ni

přičemž symbol Ti představuje součet pořadí v i –tém souboru, tj.
Ti =

ni
X

Rij

pro i = 1, . . . , k.

j=1

Tabulka: Kruskalův–Wallisův test
Výběr
1
2
···
k

Pořadí veličin ve sdruženém
náhodném výběru
R11 R12 · · · R1n1
R21 R22 · · · R2n2
··· ··· ··· ···
Rk1 Rk2 · · · Rknk

Součet
pořadí
T1
T2
···
Tk

Celkový součet všech pořadí je T1 + . . . + Tk = N(N + 1)/2.
Nulovou hypotézu zamítáme na hladině významnosti α ve prospěch alternativní hypotézy pokud:
Q ≥ χ2k−1(α)
Je-li v datech více jak 25 % shod, používá se korigovaná statistika
Qkorig =

Q
1 − (N 3 − N)−1
34

P 3
(ti − ti )

,

kde t1 , t2 , . . . jsou počty shodných pozorování v jednotlivých skupinách veličin
majících tutéž hodnotu.
Za platnosti H0 má Q asymptoticky χ2 rozdělení, když všechna ni rostou nade
všechny meze. Jelikož EQ= k − 1, půjde o χ2 rozdělení mající k − 1 stupňů vol-

nosti. Z tohoto důvodu nulovou hypotézu zamítáme, když Q ≥ χ2k−1 (α).

Kruskalův-Wallisův test je lokálně nejsilnější pořadový test pro jednoduché
třídění v případě, že výběry pocházejí z logistického rozdělení a mohou se lišit
pouze posunutím.
Kruskalův–Wallisův test je zejména citlivý na případy, kdy se jednotlivé distribuční funkce od sebe liší posunutím. Zamítne-li se nulová hypotéza, je třeba ještě
zjistit, které dvojice výběrů se od sebe signiﬁkantně liší. Označme ti = nTii ,
i = 1, . . . , k. Nechť hk−1 (α) je kritická hodnota Kruskalova-Wallisova testu na
hladině α. Při malých rozsazích použijeme speciální tabulky, při velkých rozsa.
zích využijeme již zmíněné aproximace, kdy hk−1 (α) = χ2k−1 (α). Řekneme, že
distribuční funkce k-tého a j-tého výběru se od sebe významně liší, jestliže platí
s
11
1
|ti − tj | >
+
N(N + 1)hk−1 (α) .
(38)
12 ni nj
Je-li rozsah všech výběrů stejný n1 = . . . = nk = m (jedná se o vyvážené třídění),
pak můžeme použít Neményiovy metody založené na Tukeyově metodě použité
u analýzy rozptylu. Pro menší hodnoty m a k jsou kritické hodnoty |Ti − Tj |

tabelovány. Při větších hodnotách použijeme následující postup. Nechť qk,∞ (α)
je kritická hodnota rozpětí k nezávislých náhodných veličin s rozdělením N(0, 1).
Je-li ξ1 , . . . , ξk výběr z N(0, 1). Označme R = ξ(k) − ξ(1) jeho rozpětí. Pak qk,∞ (α)
je číslo deﬁnované podmínkou

P [R ≥ qk,∞ (α)] = α .
Prohlásíme, že Fi a Fj se od sebe významně liší, když
r
1
|ti − tj | > qk,∞ (α)
k(km + 1) .
12
35

(39)

I když při vyváženém třídění můžeme použít obou uvedených metod, dáváme
přednost spíše Neményiově metodě, jelikož je citlivější.

Příklad 2.2 Máme 16 skupin myší, data reprezentují dobu přežití několika skupin myší, které byly imunizovány různými látkami. Našim úkolem je zjistit, zda
se jednotlivé skupiny myší od sebe neliší.
skupina
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
13
14
15
16

1 7
1 1
1 6
10 10
11
4 1
1 7
3 3
3 1
3 14
3 14
4 12
3 14
8 14
4 1
14 10

1 1
1 1
1 1
1 7 3
1 6 1
4 7 4
1 7 6
8 4 8
1 1 9
14 1 1
2 3 14
3 12 14
1 14 1
6 4 14
4 14 4

8
1
16
7
10
1
10
1
14
14
4 4

Postup: Z dat utvoříme sdružený výběr a každému číslu přiřadíme pořadí, obdoba Wilcoxonova dvouvýběrového t-testu. Pokud se nám hodnota vícekrát opakuje, tak opět vypočítáme průměr pořadí a přiřadíme každé stejné hodnotě to
samé pořadí.

36

skupina
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
13
14
15
16

10, 5 55, 5 10, 5
10, 5 10, 5 10, 5
10, 5 50, 5 10, 5
66
66 10, 5
69 10, 5
43 10, 5 43
10, 5 55, 5 10, 5
33
33 60, 5
33 10, 5 10, 5
33
78
78
33
78
28
43 70, 5 33
33
78 10, 5
60, 5 78 50, 5
43 10, 5 43
78
66

10, 5
10, 5
10, 5
55, 5
50, 5
55, 5
55, 5
43
10, 5
10, 5
33
70, 5
78
43
78

33
10, 5
43
50, 5
60, 5
63
10, 5
78
78
10, 5
78
43

60, 5
10, 5
85
55, 5
66
10, 5
66
10, 5
78
78
43

Ti
97, 5
56
92, 5
295
161, 5
283, 5
245
296
152
217
316
309
295
388
43 307
144

ni
4
4
4
6
5
6
6
6
6
5
6
6
6
6
7
2

Ověříme si zda jsme správně přiřadilli pořadí:
T1 + . . . + Tk = N(N + 1)/2
97, 5 + 56 + 92, 5 + . . . + 307 + 144 = 85(85 + 1)/2
3655 = 3655

Nyní můžeme vypočítat testovou statistiku
Q=

k
X
12
Ti2
− 3(N + 1) ⇒ Q = 24, 803
N(N + 1) i=1 ni

Závěr: Nulovou hypotézu zamítáme na zvolené hladině α = 0, 05, jestliže testová
statistika Q ≥ χ2k−1 (α). Z tabulek jsme zjistili, že kritická hodnota χ2k−1 = 25,

proto můžeme říci, že nulovou hypotézu nelze zamítnout. Způsob imunizace nemá
na počet dní do úmrtí myši vliv.

37

3

SAS
SAS (Statistical Analysis System) je jeden z nejpoužívanějších statistických

softwarů, sloužící jako plnohodnotný prostředek pro správu, analýzu a prezentaci
dat.
Prostředí SASu v OS Windows
V OS Windows se po otevření SASu na obrazovce automaticky objeví tato okna:
Editor: okno tzv. enhanced obsahuje editor programů SASu se zvýrazněním syntaxe
Log: obsahuje poznámky, varování a hlášení týkající se aktuálního sezení
Output: tiskové výstupy programů SASu tak jak byly postupně spouštěny
Results: strom hierarchicky seřazených výstupů provedených procedur SASu v
okně Output
Explorer: průzkumník souborů a knihoven v SASu
Program v SASu je sekvencí příkazů prováděných po řadě tak, jak jsou zapsány. Každý příkaz musí být ukončen středníkem, a samozřejmě i každý program
musí být ukončen, k tomu nám slouží příkaz run. V případě graﬁckých procedur
je třeba použít příkaz quit. Příkazy mohou být zapsány malými i velkými písmeny, rozděleny do několika řádků a začínat v libovolném sloupci.
Datové množiny - Data Sets Datové soubory SASu se vytvářejí pomocí
tzv. DATA stepu nebo procedur SASu, které nějakým způsobem manipulují s
již vytvořenými datovými množinami (např. procedura UPDATE) či importují
data (procedura IMPORT). Pro provádění analýz načítá SAS data ze speciální
struktury - SAS data set, který obsahuje popisné informace, indexy a vlastní
data organizována podobně jako v relačních databázových systémech: řádky odpovídají pozorováním a sloupce odpovídají proměnným. SAS data sety mohou
být dočasné (uloženy v knihovně WORK a po ukončení sezení vymazané) i stálé
(uložené na disku počítače).
38

SAS rozeznává dva datové typy proměnných: numerický a znakový datový typ.
Numerický datový typ slouží pro reprezentaci kladného nebo záporného čísla, desetinného čísla (desetinná část se odděluje tečkou). Chybějící numerická hodnota
je reprezentována tečkou. Znakový datový typ může obsahovat jak znaky, tak i
číslice a chybějící hodnota je reprezentována prázdnou buňkou.
Všechny datové soubory jsou uloženy v SAS knihovnách, rozlišujeme dva typy:
dočasné a stálé. Dále máme knihovnu automaticky vytvořenou SASem (např.
knihovna WORK) a knihovnu, kterou si můžeme vytvořit sami. Vlastní knihovnu
tvoříme pomocí příkazu LIBNAME, vytvoří se odkaz na existující adresář se soubory SASu pod daným jménem.
Syntaxe příkazu:
LIBNAME název-knihovny ’adresář’;,
kde název knihovny odpovídá pravidlům pojmenování v SASu a ’adresář’
je cesta k fyzickému umístění knihovny, tj. adresář v počítači.
Hlavní dvě části programu v SASu jsou DATA step(s) a PROC step(s).

3.1

DATA step

Slouží k tvorbě a modiﬁkaci data setů SASu. V rámci data stepu je možné:
- vložit data z řádkového souboru do data setu
- vytvořit novou proměnnou nebo modiﬁkovat stávající (načtenou) proměnnou
- vytvořít novou datovou množinu jako podmnožinu původní
- sloučit více datových množin do jedné apod.
Načítat data můžeme různými způsoby. V případě mých výpočtů, jsem použila načítání dat z řádkového souboru pomocí příkazu INFILE, který načte data
ze speciﬁkovaného souboru způsobem, určeným příkazem INPUT a příkazu
IMPORT, který importuje data z různých typů souborů (řádkového, s oddělovači,
39

MS Excelu, MS Accessu, apod.). Jako ilustraci použiji data step z příkladu Uroky:
data uroky;
infile ’uroky.txt’;
input location $ 1. @;
do i = 1 to 4;
input urok @;
output;
end;
run;
Příkaz data uroky znamená, že se bude vytvářet datový soubor jménem uroky.
Příkaz infile speciﬁkuje název souboru, ze kterého budou čerpána data. Následuje příkaz input, kterým deﬁnujeme názvy jednotlivých načítaných veličin
pro datový soubor uroky. Hodnoty v souboru tvoří tzv. „řádková dataÿ = soubor obsahující pouze tisknutelné znaky, tabulátory, mezery a znaky konce řádků.
SAS načítá hodnoty zleva doprava postupně do uvedených proměnných. Data ve
stupním souboru musí být oddělena mezerou, popřípadě čárkou. Název znakové
proměnné musí být následován znakem $. Zápis dalšího pozorování do výstupního
souboru provede příkaz output. Příkaz do reprezentuje cyklus, který provádí pro
každou hodnotu proměnné cyklu příkazy těla cyklu zakončené klíčovým slovem
end. V našem případě načítáme ze souboru postupně hodnotu znakové proměnné
location (’ $ 1.’ je speciﬁkace formátu, v tomto případě řetězce o délce jednoho
znaku) a v rámci cyklu 4 hodnot proměnné urok. Znak @ přikazuje SASu, aby
pokračoval ve čtení proměnných na stejném řádku. Příkazem output vložíme
každé z pěti pozorování, tj. dvojici hodnot location a urok do datové množiny. Po provedení příkazu cyklu SAS pokračuje čtením dalšího řádku vstupního
souboru.
V případě načítání dat z excelu zvolíme z hlavního menu File / Import,
objeví se nám okno, kde si zvolíme formát dat, která se nám mají zkonvertovat
40

(např. MS Excel) a postupně doplníme potřebné informace: data, která mají
být importovaná, název budoucího souboru a místo, kam má být soubor uložen.
Konverze proběhne nejsnáze, jestliže má excelovská tabulka podobnou stavbu
jako datová množina SASu (ve sloupci veličiny, v řádcích pozorování) a obsahuje
v prvním řádku jména proměnných. Po ukončení konverze je nejlépe zkontrolovat
importovaná data pomocí příkazu proc print, který vykreslí výsledná data.

3.2

PROC step

Jedná se o část programu v SASu, ve kterém probíhá zpracování a analýza
dat z data setů prostřednictvím procedur SASu. V následujícím textu stručně
popíšu procedury použité při porovnávání několika skupin pozorování.
3.2.1

Procedura BOXPLOT

Tato procedura vytváří tzv. krabičkový graf (někdy nazývaný krabička s
vousy) pro jednu nebo více skupin dat (porovnávací boxplot). Krabička s vousy,
nebo-li boxplot, znázorňuje dolní a horní kvartil (hranice krabičky), medián (čára
uvnitř krabičky), průměr (znak uvnitř krabičky) a pak dle typu krabičkového
grafu maximum, minimum a odlehlá pozorování pro zvolená data. Já používám
typ grafu SCHEMATIC, který jako hranice tzv. „vousůÿ vyznačuje minimum
(dolní vous), resp. maximum (horní vous), případně 1,5 násobek mezikvartilového
rozpětí (hodnota rovnající se rozdílu mezi horním a dolním kvartilem - výška krabičky). Odlehlé hodnoty (přesahující 1,5 násobek mezikvartilového rozpětí) jsou
naznačeny samostatnými body.
Zjednodušená syntaxe:
proc boxplot <options>;
plot analysis-variable*group-variable </options>;
run;
quit;

41

Vybrané volby procedury BOXPLOT:
- DATA = speciﬁkuje vstupní datovou množinu.
Příkaz PLOT
- vykresluje daný krabicový graf pro proměnnou (nebo více proměnných)
analysis-variable (více proměnných se vypisuje po řadě za sebou do závorky,
např. (weight lenght)
- group-variable = speciﬁkuje skupinovou proměnnou, tj. proměnnou, která
rozděluje pozorování do skupin (pro porovnávací boxplot)
-volba BOXSTYLE speciﬁkuje typ krabicového grafu
Příkaz INSET
- vkládá požadované číselné chrakteristiky celého datového souboru (pro všechny
skupiny), určené klíčovými slovy (viz tabulka), pro analyzovanou proměnnou
přímo do grafu
- volba HEADER speciﬁkuje nadpis
- volba POS, resp. POSITION speciﬁkuje umístění vloženého rámečku (hodnota
TM = top margin, tj. horní okraj)
Tabulka klíčových slov pro číselné charakteristiky:
MEAN
MIN
MAX
NMIN
NMAX
NOBS
STDDEV

aritmetický průměr
minimum
maximum
nejmenší velikost skupiny
největší velikost skupiny
počet pozorování
směrodatná odchylka

Příkaz INSETGROUP
- funguje podobně jako příkaz INSET, ale zobrazuje charakteristiky pro každou
skupinu zvlášť, tj. pro každou vykreslenou krabičku s vousy
- využívá jiná klíčová slova pro číselné charakteristiky než INSET - viz tabulka.
42

Tabulka klíčových slov pro příkaz INSETGROUP
MEAN
MIN
MAX
N
NHIGH
NLOW
NOUT
Q1
Q2
Q3
RANGE
STDDEV
3.2.2

aritmetický průměr
minimum ve skupině
maximum ve skupině
počet pozorování ve skupině
počet odlehlých pozorování nad
počet odlehlých pozorování pod
počet odlehlých pozorování celkem
první kvartil
medián
třetí kvartil
rozpětí (rozdíl mezi maximem a minimem)
směrodatná odchylka pro skupinu

Procedura UNIVARIATE

Tato procedura obsahuje řadu možností, jak analyzovat jednorozměrnou proměnnou. Umožňuje výpočet číselných charakteristik (včetně výpočtu intervalů
spolehlivosti) datového souboru i testování základních hypotéz (jednovýběrový
t-test polohy, testy normality apod.). Kromě textového výstupu, je možné zobrazit i grafy: stem-and-leaf graf, boxplot a normální pravděpodobnostní graf pro
znakové tiskárny i qq graf, pravděpodobnostní graf a histogram pro graﬁcká výstupní zařízení.
Zjednodušená syntaxe:
proc univariate </options>;
class variables;
var variables;
run;
Vybrané volby procedury UNIVARIATE:
- DATA: speciﬁkuje vstupní datovou množinu
- ALPHA: speciﬁkuje hladinu významnosti alfa (implicitně 0,05)
43

- NORMALTEST požadavek na provedení testů normality dat
Příkaz CLASS
- speciﬁkuje jednu nebo více seskupovacích proměnných (proměnné můžou být
jak numerického, tak i znakového typu)
Příkaz VAR
- speciﬁkuje proměnné určené k analýze (vynecháme-li příkaz VAR, procedura
UNIVARIATE analyzuje všechny číselné proměnné

3.2.3

Procedura TTEST

Pomocí této procedury lze provádět výpočty jednovýběrového, dvouvýběrového a párového t-testu. V našem případě nás zajímá pouze dvouvýběrový t-test,
který porovnává střední hodnotu prvního výběru se střední hodnotou druhého
výběru. Oba výběry musí být samozřejmě nezávislé.
Zjednodušená syntaxe:
proc ttest </options>;
class variables;
var variables;
run;
quit;
Příkaz CLASS speciﬁkuje klasiﬁkační proměnné a příkaz VAR speciﬁkuje proměnné pro vlastní analýzu.
Za předpokladu, že rozptyly v porovnávaných skupinách dat nejsou shodné,
používá program SAS aproximaci t statistiky deﬁnovanou jako
x1 − x2
t′ = √
,
ω1 + ω2
44

kde
ω1 =

s21
,
n1

ω2 =

s22
n2

Asymptoticky má tato statistika Studentovo t-rozdělení se stupni volnosti
deﬁnovanými dle Satterthwaita předpisem
df =

(ω1 + ω2 )2
ω2

ω2

1
2
+ n2 −1
)
( n1 −1

Příklad 3.1 Z Českého statistického úřadu jsme získali průměrné roční teploty
v letech 1980 − 2000 naměřené ve městech Praha a Brno. Zkoumali jsme zda
existuje nějaký rozdíl mezi těmito naměřenými teplotami. Jako nulovou hypotezu
jsme zvolili, že střední hodnoty naměřených teplot se rovnají.
Vložení řádkových dat

Pro kontrolu, vypsání těchto hodnot do okna Output (výstupu)

45

Data v okně Output

Procedura BOXPLOT

46

Srovnávací krabicový graf s vybranými charakteristikami

Ověření testu normality, díky kterému se rozhodneme, zda použít parametrickou nebo neparametrickou metodu výpočtu

Praha

47

Brno

Jelikož nám v testech normality vyšlo, že výběry pocházejí z normálního rozdělení, tak použijeme paramaterickou metodu. Protože máme pouze dva výběry
aplikujeme na ně dvouvýběrový t-test, tím samozřejmě nevylučujeme použití i
analýzu rozptylu.

Výsledná tabulka

Závěr: Nulovou hypotézu zamítáme jelikož hodnota v posledním sloupci prv48

ního řádku výstupu testové procedury, tzv. p-hodnota, je menší než zvolená hladina významnosti α. První řádek výpisu odpovídá klasickému t-testu pro shodné
rozptyly. Že můžeme použít právě tuto variantu t-testu potvrzuje výsledek samostatného testu ekvivalence ve spodní části (p-hodnota = 0, 9663). Je známo, že
města s větší hustotou zalidnění mají i větší teploty ovzduší.
3.2.4

Procedura ANOVA

Je jedna z procedur dostupných v SASu pro výpočty analýzy rozptylu. Pomocí
procedury ANOVA lze analyzovat pouze vyvážený soubor dat (počet pozorování
v porovnávaných skupinách je shodný), zatímco další z použitelných procedur
- procedura GLM může být použita jak pro vyvážená, tak i nevyvážená data.
Protože procedura ANOVA počítá se speciální strukturou pro vyvážená data, je
rychlejší a tak i používanější než procedura GLM pro případ vyvážených dat.
Zjednodušená syntaxe:
PROC ANOVA <options>;
CLASS proměnná;
MODEL dependents = effects;
MEANS effects </options>;
V proceduře ANOVA jsou příkazy CLASS a MODEL vyžadované. Příkaz
CLASS, který speciﬁkuje klasiﬁkační proměnné, musí navíc být před příkazem
MODEL. Příkaz MODEL deﬁnuje, jak má model vypadat, dependents=popisuje
zavislé proměnné a effects= jednotlivé efekty. Příkaz MEANS se požívá pro
mnohonásobné porovnávání. Volba HOVTEST požaduje analýzu homoskedasticity (hodnota =BARTLETT pro Bartlettův test a =LEVENE pro Leveneův
test), volba SCHEFFE požaduje provedení mnohonásobného porovnávaní Scheﬀého metodou a TUKEY pomocí Tukeyho metody, volba CLDIFF zobrazí ve
výstupu porovnávané skupiny a označí ty páry, ve kterých byla mezi skupinami
pozorován významný rozdíl.
49

Příklad 3.2 Na internetové stránce Českého statistické úřadu jsme zjistili změnu
úrokových sazeb za léta 1997 − 2000 z korunových krátkodobých, střednědobých
a dlouhodobých úvěrů. Testovali jsme hypotézu, že střední hodnoty úrokových

sazeb se rovnají.
Pomocí tohoto příkazu

se načetly řádková data. Použitím následujícího příkazu slouží jako kontrola
načtených dat.

Graﬁcké znázornění dat provádíme pomocí příkazu boxplot,

který vykreslí tzv. krabičku s vousy nebo-li boxplot.
50

Na obrázku vidíme, že úrokové sazby jsou celkem vyrovnané. V tabulce máme
uvedené střední hodnoty, směrodatné odchylky, maxima a minima jak jednotlivých druhů úroků, tak i kompletních dat.
Nejdříve bylo nutné ověřit zda získaná data jsou z normálního rozdělení,
abychom mohli aplikovat analýzu rozptylu pro ověření nulové hypotézy. Procedura UNIVARIATE s volbou NORMALTEST umožní otestovat normalitu dat.

V následujícíh tabulkách jsou postupně výsledky normality sazby A, B a nakonec sazby C.

51

Krátkodobé úvěry

Střednědobé úvěry

Dlouhodobé úvěry

Jelikož jsme zjistili, že data mají normální rodělení, můžeme aplikovat analýzu rozptylu (používanou pro vyvážené třídění). Mezi možnosti jsme použili pro
názornost i Leveneův test homogenity rozptylů.
52

Jednotlivé výsledky analýzy rozptylu:
ANOVA

hodnota 2, 2492 odpovídá skupinové variabilitě a hodnota 81, 3069 odpovídá
reziduální variabilitě. SAS má automaticky předdeﬁnované α = 0, 05, kterou porovnáme s p-hodnotou. Nulová hypotéza se zamítá, je-li „kouzelné péčkoÿ menší
než zvolená hladina významnosti α.

53

Ani Leveneův test homogenity rozptylů nám nulovou hypotézu nezamítl, protože p-hodnota (0, 8844) je větší než zvolené α.
Závěr:
Na tento příklad jsme postupně aplikovali všechny metody související s analýzou rozptylu a dospěla jsem k závěru, že nulovou hypotézu nelze zamítnout.
Díky tomu, můžeme říct, že varianty se od sebe signiﬁkantně neliší. V podstatě
nezáleží na tom, který úvěr si vybereme.
3.2.5

Procedura GLM

Pomocí této procedury lze provádět regresní analýzu i analýzu rozptylu. Obecně
slouží k odhadu parametrů zobecněných lineárních modelů, ve kterých jedna nebo
několik závislých spojitých proměnných závisí na jedné nebo několika nezávislých
proměnných, které mohou být obecně klasiﬁkačními proměnnými nebo spojitými
proměnnými. Z našeho pohledu je nejdůležitější možnost provedení analýzy rozptylu, tj. tzv. ANOVA analýzy, a to jak pro vyvážené tak i nevyvážené skupiny
hodnot (výběry). Poněvadž parametrickou analýzu rozptylu pro vyvážené výběry
lze efektivně provádět pomocí již dříve zmíněné procedury - ANOVA, používám
proceduru GLM pouze pro výpočty v rámci nevyvážených výběrů.
Zjednodušená syntaxe:
PROC GLM <options>;
CLASS proměnná;
MODEL dependents = independents;
run;
Vybrané volby procedury GLM:
- DATA: speciﬁkuje vstupní datovou množinu (implicitně datová množina, se kterou bylo v rámci programu SASu naposledy manipulováno)
- ALPHA: speciﬁkuje hladinu významnosti alfa (implicitně 0, 05)

54

Příkaz CLASS speciﬁkuje klasiﬁkační proměnné modelu. Příkaz MODEL je jediný povinný příkaz procedury GLM. Dependents odpovídá závislé proměnné a
independents nezávislý proměnným lineárního modelu (v našem případě faktoru
- klasiﬁkační proměnné, která rozděluje vstupní data do skupin).
Příklad 3.3 Na internetové stránce Českého statistické úřadu jsme zjistili počet
sňatků v jednotlivých letech ve třech větších krajích ČR. Zkoumali jsme nulovou
hypotézu, že počet sňatků se v jednotlivých krajích od sebe významně liší.
Nejprve musíme načíst řádková data pomocí příkazu infile a následného
postupu:

Tento příkaz vypíše hodnoty do tabulky, což slouží jako kontrola, zda byla
správně vloženy.

55

Vypsané hodnoty:

Opět znázorníme data v graﬁcké podobě, pomocí příkazu BOXPLOT:

Výsledný boxplot včetně celkové tabulky s minimem, maximem a střední hodnotou, a následná tabulka mediánů(Q2 ), horních(Q1 ) a dolních(Q3 ) kvantilů jednotlivých krajů.

56

Zda zvolit parametrickou nebo neparametrickou metodu k výpočtu, jsme zjistili pomocí příkazu UNIVARIATE a k němu volby normaltest.

Středočeský kraj

57

Jihomoravský kraj

Moravskoslezský kraj

Jelikož data mají normální rozdělení, použijeme parametrickou metodu pro
testování. Jedná se o nevyvážená data, proto zvolíme metodu GLM, která je pro
to speciﬁcká.

58

Výsledná tabulka:

Protože p-hodnota je menší než zvolená hladina významnosti, nulovou hypotézu tedy zamítáme.
Závěr: Nulová hypotéza říká, že se skupiny neliší pokud je p-hodnota menší
než α, pak zamítáme nulovou hypotézu. Sňatkovitost se kraj od kraje liší.
3.2.6

Procedura NPAR1WAY

Tato procedura umožňuje provádění různých neparametrických testů. Pro porovnávání několika skupin pozorování procedura nabízí např. Wilcoxonův dvouvýběrový test a Kruskall-Wallisův test, které jsem popisovala v teoretické části
této práce. Kromě toho lze samozřejmě využít řadu dalších neparametrických
testů, které tato procedura nabízí na příklad pro testování polohy - Wilcoxonův
jednovýběrový test, mediánový test apod., anebo pro testování shody distribucí
více skupin pozorování - Kolmogorov-Smirnovův test, Cramer-von Mises test a
další.
Zjednodušená syntaxe:
proc npar1way </options>;
class variables;
var variables;
Vybrané volby procedury NPAR1WAY:
- DATA - analyzovaná datová množina
- WILCOXON - požadavek na provedení Wilcoxonova testu a Kruskal-Wallisova
59

testu
- MEDIAN - požadavek na provedení mediánového testu
Příkaz CLASS speciﬁkuje klasiﬁkační proměnné modelu a příkaz VAR speciﬁkuje proměnné pro analýzy.
Příklad
Data získaná z Českého statistického úřadu, obsahují průměrné měsíční srážky
(v mm) v roce 2000 ve čtyřech odlišných městech. Zkoumáme nulovou hypotézu,
že průměrné měsíční srážky na různých místech nejsou odlišné.
Vložení řádkových dat:

Vypsaní hodnot do tabulky pro kontrolu:

60

Tabulka

61

Graﬁcké znázornění pomocí boxplotů

Vygenerovaný graf spolu s použitými volbami, např. střední hodnota, maximum, minimum,. . .

Procedura UNIVARIATE k ověření normality výběrů

62

Brno

Cheb

Olomouc

63

Praha

Z testů normality vyplynulo, že ne všechny výběry mají normální rozdělení,
proto musíme použít neparametrickou metodu k ověření nulové hypotézy. Jelikož
porovnáváme více než dva výběry, použijeme Kruskal - Wallisův test, který je
obdobou parametrické analýzy rozptylu.

Výsledná tabulka

64

Závěr: Hodnota v posledním řádku výstupu pro Kruskal - Wallisův test je
větší než zvolená hladina významnosti proto můžeme říci, že se průměrné měsíční
srážky ve vybraných městech signiﬁkantně neliší.
Příklad 3.4 Z Českého statistického úřadu jsme získali údaje úmrtností podle
pohlaví ze čtyř let. Budeme zkoumat nulovou hypotézu, zda se úmrtnost mužů a
žen od sebe liší.
Vložení dat

Vykreslení do tabulky

Tabulka

Graﬁcké zobrazení

65

Graf

Testy normality, pro volbu parametrické nebo neparametrické metody

Muži

66

Ženy

Z testů normality jsme zjistili, že výběry nemají normální rozdělení, proto použijeme neparametrickou metodu pro dva výběry, tzn. dvouvýběrový Wilcoxonův
test.

Výsledná tabulka

67

Závěr: Poněvadž hodnota v řádku Two-sided P r > |Z| je větší než zvolená

hladina významnosti, nezamítáme nulovou hypotézu, tj. můžeme říci, že se úmrtnost žen a mužů ve sledovaných obdobích liší.

68

Závěr
Cílem této práce bylo porovnávat dvě a více než dvě skupiny pozorování, rozlišit při porovnávání parametrickou a neparametrickou metodu, ukázat principy
jednotlivých testů, všechny tyto poznatky demonstrovat na příkladech, naučit
se pracovat se statistickými daty a s programem SAS. Porovnávání skupin pomocí statistických metod má v technické praxi velké využití např. ve zpracování
různých laboratorních experimentů, ve sledování vlivů různých faktorů (teplota,
koncentrace) na výsledek reakce apod. . V této práci jsem se zaměřila zejména
na jednofaktorovou analýzu rozptylu, zajímavé by také bylo zabývat se dvoufaktorovou a trojfaktorovou ANOVOU, to ale přesahuje rámec této bakalářské práce.
Při psaní této práce jsem se naučila pracovat s vědeckou literaturou, programem TeX i SAS a prohloubila své znalosti v matematické statistice. Program
SAS bych ráda doporučila všem, kteří provádějí výpočty metodou ANOVA, jeho
zásadní předností je rychlost a různé možnosti načítání dat a bohaté spektrum
statistických analýz. Největším problémem, se kterým jsem se při psaní této práce
setkala, bylo zdánlivě jednoduché vkládání výstupů z programu SAS do TeXu.
Byla bych ráda, kdyby tato práce byla přínosem nejen pro mě, ale i pro všechny
studenty a zájemce o statistiku.

69

Příloha 1
CD s kódy a daty pro výpočet příkladů v SASu přiloženo na zadní straně
desek.

70

Literatura
[1] Anděl, J.: Základy matematické statistiky. MATFYZZPRESS, Praha 2005.
[2] Janko, Jaroslav: Statistické tabulky. Nakladatelství ČAV, Praha 1958.
[3] Karpíšek, Z.: Matematika IV. - statistika a pravděpodobnost. CERM, Brno
2002.
[4] http://www2.zf.jcu.cz/public/departments/kmi/MSMT 05/anova.pdf [online 16. 1. 2006] (Analýza rozptylu)
[5] http://www.czso.cz [online 20. 3. 2005] (Český statistický úřad)
[6] SAS Help and Documentation, [Program] SAS, [citováno 23. 2. 2008].

71

