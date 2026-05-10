---
title: "dukazy znamych tvrzeni.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Státnice/new/MAT/ru/dukazy/dukazy znamych tvrzeni.pdf"
date: 2010-05-25
type: PDF (text-based)
---

Matematický ústav Slezské univerzity v Opavě
Učebnı́ texty k přednášce ALGEBRA II, letní semestr 2000/2001
Michal Marvan

16. Skalárnı́ součin
Vektory obecně jsme definovali jako prvky vektorového prostoru. Algebraická struktura
vektorového prostoru určuje, jak se vektory sčı́tajı́ a násobı́ skaláry. V geometrii (např. v prostorech E 2 , E 3 ) se s vektory spojujı́ dalšı́ užitečné veličiny, např. délka vektoru či odchylka
dvou vektorů, které nejsou odvoditelné z pouhých algebraických operacı́ vektorového prostoru.
Tyto veličiny mohou být zavedeny i v přı́padě obecného vektorového prostoru, je k tomu ovšem
potřebná ještě jistá dodatečná struktura s vlastnı́mi axiomy. Přı́slušné axiomy vycházejı́ velmi
jednoduše, je-li onou dodatečnou strukturou skalárnı́ součin. Je to speciálnı́ zobrazenı́, které
dvojici vektorů přiřazuje skalár. Obecný skalárnı́ součin nejen obohacuje algebru o geometrické
ideje, ale má i důležité fyzikálnı́ aplikace.
Definice. Bud’ V vektorový prostor nad polem reálných čı́sel R. Eukleidovský skalárnı́ součin
na V je zobrazenı́ g : V × V → R, splňujı́cı́ pro libovolnou trojici vektorů u, v, w ∈ V a
libovolný skalár a ∈ R
1◦ g(u +v, w) = g(u, w)+g(v, w) a g(au, w) = ag(u, w) (linearita v prvnı́m argumentu);
2◦ g(u, v) = g(v, u) (symetrie);
3◦ Jestliže u = 0, pak g(u, u) > 0 (pozitivnı́ definitnost).
Cvičenı́. (1) Ukažte, že eukleidovský skalárnı́ součin je lineárnı́ i v druhém argumentu.
(2) Ukažte, že pro libovolný vektor u platı́ g(0, u) = g(0, u) = 0. Návod: g(0, u) = g(0 · u, u).
(3) Důsledek: g(u, u) ≥ 0 pro každé u ∈ V , přičemž g(u, u) = 0 ⇔ u = 0.
Přı́klad. Ve vektorovém prostoru E 3 nad polem R uvažujme o dvou vektorech u, v. Kolmý průmět
vektoru u do podprostoru [[v]] označme u [[v]] . Je-li φ odchylka vektorů u, v a |u| délka vektoru u, je
|u| cos φ = ±|u [[v]] | délka vektoru u [[v]] opatřená znaménkem + nebo − podle toho, jsou-li vektory u [[v]]
a v orientovány souhlasně či opačně.
Součin
❆❑❆ u
❆
g(u, v) = ±|u [[v]] | |v| = |u||v| cos φ
☛ ❆ φ
·✛ ❆
✲
[[v]]
v
splňuje axiomy 1◦ –3◦ skalárnı́ho součinu (cvičenı́).
u [[v]]
Přı́klad. Pro vektory u = (u 1 , . . . , u n ), v = (v1 , . . . , vn ) ∈ Rn položme g(u, v) = u 1 v1 + · · · + u n vn .
Pak g je skalárnı́ součin na Rn . Nazývá se standardnı́ skalárnı́ součin na Rn .

Kromě standardnı́ho skalárnı́ho součinu máme na Rn ještě nekonečné množstvı́ dlašı́ch
skalárnı́ch součinů.
Cvičenı́. Bud’te a1 , . . . , an kladná reálná čı́sla. Pro vektory u = (u 1 , . . . , u n ), v = (v1 , . . . , vn ) ∈ Rn
položme g(u, v) = a1 u 1 v1 + · · · + an u n vn . Pak g je skalárnı́ součin na Rn .

V kapitole o kvadratických formách zı́skáme úplný popis všech skalárnı́ch součinů na
vektorovém prostoru V dimenze n > 1.

16. Skalárnı́ součin

V matematické analýze se zavádějı́ důležité skalárnı́ součiny na nekonečněrozměrných vektorových
prostorech. Studujı́ se různé prostory Lebesgueovsky integrovatelných funkcı́, jako je prostor L 2 (a, b)
b 2
všech funkcı́
 b f takových, že existuje a f d x. Skalárnı́ součin dvou takových funkcı́ se definuje formulı́
( f, g) = a f g d x.
V takových prostorech pak hrajı́ důležitou roli i otázky konvergence a spojitosti. V algebře se proto
budeme držet konečněrozměrných vektorových prostorů. Tvrzenı́ a věty však budeme formulovat a
dokazovat v největšı́ dostupné obecnosti.

Existuje ještě hermiteovský skalárnı́ součin ve vektorových prostorech nad polem komplexnı́ch čı́sel C. Hermiteovská geometrie má fyzikálnı́ aplikace zejména v kvantové mechanice.
Definice. Bud’ V vektorový prostor nad polem C. Hermiteovský skalárnı́ součin na V je zobrazenı́
g : V × V → C, splňujı́cı́ pro libovolnou trojici vektorů u, v, w ∈ V a skalár a ∈ C
1◦ g(u + v, w) = g(u, w) + g(v, w) a g(au, w) = ag(u, w) (linearita v prvnı́m argumentu);
2 g(u, v) = g(v, u)∗ (kosá symetrie; ∗ označuje komplexnı́ sdruženı́);
3◦ Jestliže u = 0, pak g(u, u) > 0 (pozitivnı́ definitnost).
Cvičenı́. Bud’te a1 , . . . , an kladná reálná čı́sla. Pro vektory u = (u 1 , . . . , u n ), v = (v1 , . . . , vn ) ∈ Rn
položme g(u, v) = a1 u 1 v1∗ + · · · + an u n vn∗ . Pak g je hermiteovský skalárnı́ součin na Cn .
Hermiteovský skalárnı́ součin nenı́ lineárnı́ ve druhém argumentu:
Cvičenı́. Pro hermiteovský skalárnı́ součin platı́ v druhém argumentu aditivita g(u, v +w) = g(u, v)+
g(u, w), ale namı́sto homogenity máme rovnost g(u, av) = a ∗ g(u, v).
Cvičenı́. Ukažte, že pro hermiteovský skalárnı́ součin je g(u, u) vždy reálné čı́slo. Proto se v axiomu
3◦ smı́ vyskytnout nerovnost. (Pro u = v nerovnost g(u, v) ≥ 0 obecně nemá smysl!)

Vektorový prostor s eukleidovským skalárnı́m součinem se nazývá eukleidovský prostor,
s hermiteovským skalárnı́m součinem se nazývá hermiteovský nebo unitárnı́ prostor. Oba dva
typy prostorů budeme společně nazývat prostor se skalárnı́m součinem.
Předpokládejme nadále, že je dán vektorový prostor V s pevně zvoleným skalárnı́m součinem g. Zjednodušı́me si označenı́ a symbol g budeme vynechávat. Tedy (u, v) = g(u, v).
Definice. Bud’ v ∈ V . Označme
v =



(v, v)

(odmocnina se bere s kladným znaménkem; připomeňme, že (v, v) ≥ 0). Čı́slo v se nazývá
délka vektoru v. Vektor délky 1 se nazývá jednotkový nebo normovaný.
Délka vektoru je zřejmě reálné čı́slo i v přı́padě hermiteovského skalárnı́ho součinu.
Cvičenı́. (1) v = 0 právě tehdy, když v = 0.
(2) Pro každý vektor v = 0 je vektor v/v normovaný:


 v 


 v  = 1.
(3) Ukažte, že av = |a|v pro každý vektor v a skalár a; |a| přitom označuje absolutnı́ hodnotu
čı́sla a.
Vše platı́ i v přı́padě hermiteovského skalárnı́ho součinu.

2

16. Skalárnı́ součin

Nerovnosti
Následujı́cı́ Cauchy–Buňakovského–Schwarzova nerovnost je základem mnoha dalšı́ch výsledků. V literatuře se vyskytujı́ různé důkazy; uvedeme jeden, který se snadno pamatuje.
Tvrzenı́ (Cauchy–Buňakovského–Schwarzova nerovnost). Pro libovolné dva vektory u, v ∈ V
platı́
|(u, v)| ≤ uv.
Rovnost nastává právě tehdy, když jsou vektory u, v závislé.
Důkaz. Je-li u = 0 nebo v = 0, pak jsou u, v závislé a zřejmě platı́ i (ne)rovnost.
Necht’tedy u = 0 a v = 0. Stačı́ dokazovat přı́pad u = v = 1; obecný se na něj převede
záměnou u za u/u a v za v/v (cvičenı́). V eukleidovském přı́padě pak máme


0 ≤ 12 u ± v2 = 12 (u ± v, u ± v) = 12 (u, u) ± (u, v) ± (v, u) + (v, v)



= 1 ± (u, v).
Odtud ∓(u, v) ≤ 1, a tedy |(u, v)| ≤ 1.
Jestliže platı́ rovnost |(u, v)| = 1, pak (u, v) = ±1, načež 0 = 1 ∓ (u, v) = 12 u ∓ v2 , a
tedy u ∓ v = 0 a u, v jsou závislé.
V hermiteovském přı́padě je důkaz složitějšı́. Začneme výpočtem


0 ≤ 12 u − v2 = 12 (u − v, u − v) = 12 (u, u) − (u, v) − (v, u) + (v, v)


= 1 − 12 (u, v) + (u, v)∗ = 1 − re(u, v).
V této formuli smı́me vektor u vydělit libovolným čı́slo φ ∈ C takovým, že |φ| = 1, ježto tı́m zůstane
zachována podmı́nka u = 1; dostaneme

2



1
u
u


0 ≤  − v  = 1 − re
,v .
2 φ
φ
Přı́pad (u, v) = 0 je triviálnı́ (nerovnost zřejmě platı́), předpokládejme tedy, že (u, v) = 0. Nynı́ zvolı́me
φ = (u, v)/|(u, v)|. Pak skutečně |φ| = 1 (cvičenı́), načež


(u, v)
u
|(u, v)| = re |(u, v)| = re
= re
, v ≤ 1.
φ
φ
Platı́-li rovnost |(u, v)| = 1, pak (při stejném φ jako nahoře) máme re(u/φ, v) = |(u, v)| = 1, načež
0 = 1 − re(u/φ, v) = 12 u/φ − v2 , a tedy u/φ − v = 0 a u, v jsou závislé.

Následujı́cı́ tvrzenı́ lze interpretovat jako známou nerovnost mezi stranami trojúhelnı́ka:
Tvrzenı́ (Trojúhelnı́ková nerovnost). Necht’ u, v ∈ V . Pak
u + v ≤ u + v
a rovnost platı́ právě tehdy, jsou-li vektory u, v závislé.
Důkaz. Eukleidovský přı́pad: u + v2 = u2 + 2(u, v) + v2 ≤ u2 + 2uv + v2 =
(u + v)2 . Zbytek: cvičenı́.
3

16. Skalárnı́ součin

Odchylka vektorů
V eukleidovském přı́padě lze Cauchy–Buňakovského–Schwarzovu nerovnost zapsat i ve
tvaru
(u, v)
−1 ≤
≤ 1.
uv
Goniometrická funkce cos známá z matematické analýzy je spojitá a klesajı́cı́ na intervalu
[0, π] a nabývá na něm všech hodnot z intervalu [−1, 1], každé právě jednou.
Definice. Pro každou dvojici nenulových vektorů u, v eukleidovského vektorového prostoru
se jediné reálné čı́slo φ takové, že 0 ≤ φ ≤ π a
cos φ =

(u, v)
uv

nazývá odchylka vektorů u, v.
V hermiteovském vektorovém prostoru máme alespoň
0≤

|(u, v)|
≤ 1.
uv

Druhá mocnina tohoto čı́sla má pravděpodobnostnı́ interpretaci v kvantové mechanice.

Ortogonalita
Výklad se opět týká eukleidovského i hermiteovského přı́padu.
Definice. Řı́káme, že vektory u, v ∈ V jsou kolmé čili ortogonálnı́, je-li (u, v) = 0. Zapisujeme
u ⊥ v.
Cvičenı́. Dva vektory jsou kolmé tehdy a jen tehdy, je-li jejich odchylka π/2.

Definice. Soustava vektorů u 1 , . . . , u n se nazývá ortogonálnı́, je-li u i ⊥ u j pro všechna i = j.
Ortogonálnı́ soustava normovaných vektorů se nazývá ortonormálnı́.
Cvičenı́. Ukažte, že pro ortogonálnı́ soustavu u 1 , . . . , u n platı́ Pythagorova věta v podobě
u 1 + · · · + u n 2 = u 1 2 + · · · + u n 2 .

Gramm–Schmidtova ortogonalizace
Tvrzenı́. V každém konečněrozměrném vektorovém prostoru se skalárnı́m součinem existuje
ortonormálnı́ báze.
Důkaz je založen na proceduře zvané Gramm–Schmidtova ortogonalizace.
4

16. Skalárnı́ součin

Důkaz. Bud’ u 1 , . . . , u n libovolná báze ve V . Nalezneme vektory e1 , . . . , en podle následujı́cı́ho návodu:
1) Položı́me e1 = u 1 .
2) Jsou-li již stanoveny (navzájem kolmé) vektory e1 , . . . , ek , položı́me
ek+1 = u k+1 −

(u k+1 , ei )
ei .
i=1 (ei , ei )
k

Pak ek ⊥ el pro všechna l = k. Dokažme to pro dvojice l < k indukcı́ vzhledem ke k. Pro
k = 1 nenı́ co dokazovat, protože žádné l neexistuje. Je-li tvrzenı́ již dokázáno pro nějaké k,
máme pro l < k + 1 (tj. l ≤ k)


(ek+1 , el ) = u k+1 −

(u k+1 , ei )
ei , el
i=1 (ei , ei )
k



(u k+1 , ei )
(ei , el )
i=1 (ei , ei )
k

= (u k+1 , el ) −

= (u k+1 , el ) − (u k+1 , el )
= 0,
protože (ei , el ) = 0 pro i = l (indukčnı́ předpoklad).
Nakonec normalizujeme: položı́me ēi = ei /ei . Protože soustava vektorů ē1 , . . . , ēn vzniká elementárnı́mi úpravami báze u 1 , . . . , u n , je rovněž bazı́.
Cvičenı́. Ukažte, že při Gramm–Schmidtově ortogonalizaci platı́ [[ē1 , . . . , ēn ]] = [[e1 , . . . , en ]] =
[[u 1 , . . . , u n ]].

Geometrická podstata Gramm–Schmidtovy ortogonalizace je následujı́cı́: k vektoru u k+1
přičı́táme vhodný vektor wk+1 z podprostoru [[e1 , . . . , ek ]] tak, aby vzniklý součet ek+1 byl
k
kolmý ke všem vektorům e1 , . . . , ek . Přičı́taný vektor wk+1 = − i=1
(u k+1 , ei )ei /(ei , ei ) je
shodou okolnostı́ jediný možný (cvičenı́).
❖❈
❈

e1 = u 1 ❈

✒❈

❈ w2 ∈ [[e1 ]]
❈
✿❈
✘✘

u2
❈

✘
❈✘✘✘e2

Gramm–Schmidtova ortogonalizace může probı́hat i souběžně s normalizacı́, podle vzorců
ek+1 = u k+1 −

k

(u k+1 , ēi )ēi ,

ēi =

i=1

ei
.
ei 

Uvědomme si však, že vektory ēi mohou obsahovat iracionality (odmocniny) i v přı́padech,
kdy jsou vektory u i celočı́selné či racionálnı́. V takových přı́padech je při praktickém počı́tánı́
výhodnějšı́ odložit normalizaci až nakonec, tj. postupovat podle procedury uvedené v důkazu.
5

16. Skalárnı́ součin

Cvičenı́. Ukažte, že každá ortogonálnı́ soustava nenulových vektorů je lineárně nezávislá.
Návod: Rovnici c1 e1 + · · · + cn en = 0 skalárně násobte jednotlivými vektory e1 , . . . , en .
Cvičenı́. Ukažte, že pokud jsou vektory u i závislé, pak při Gramm–Schmidtově ortogonalizaci některý
z vektorů ei vyjde nulový. (Návod: využijte výsledek předchozı́ho cvičenı́.)

V ortonormálnı́ch bazı́ch počı́táme souřadnice vektoru u jako skalárnı́ součiny s vektory
báze:
Cvičenı́. Souřadnice (x1 , . . . , xn ) vektoru u v ortonormálnı́ bázi e1 , . . . , en jsou xi = (u, ei ).
Cvičenı́. Jsou-li (x1 , . . . , xn ) souřadnice vektoru u a (y1 , . . . , yn ) souřadnice vektoru v v některé
ortonormálnı́ bázi, pak
(1) v eukleidovském přı́padě (u, v) = x1 y1 + · · · + xn yn ;
(2) v hermiteovském přı́padě (u, v) = x1 y1∗ + · · · + xn yn∗ .

Ortogonálnı́ doplněk
Definice. Je-li U ⊆ V podprostor vektorového prostoru V se skalárnı́m součinem, položı́me
U ⊥ = {v ∈ V | v ⊥ u pro všechna u ∈ U }.
Podmnožina U ⊥ ⊆ V se nazývá ortogonálnı́ doplněk podprostoru U .
U⊥
U
Tvrzenı́. Ortogonálnı́ doplněk U ⊥ je podprostor ve V .
Důkaz. Cvičenı́.
Tvrzenı́. Je-li prostor V konečněrozměrný, dim V = n, pak V = U +̇ U ⊥ a platı́
dim U ⊥ = n − dim U.
Důkaz. Necht’dim U = m. Zvolme bázi u 1 , . . . , u m v U a doplňme ji vektory u m+1 , . . . , u n do
báze ve V . Ortonormalizacı́ necht’vzniknou vektory e1 , . . . , en . Přitom U = [[u 1 , . . . , u m ]] =
[[e1 , . . . , em ]] (soustava e1 , . . . , em vzniká elementárnı́mi úpravami soustavy u 1 , . . . , u m ).
Ukažme, že U ⊥ = [[em+1 , . . . , en ]]. Inkluze U ⊥ ⊇ [[em+1 , . . . , en ]] platı́, protože každý
vektor ei , i = m + 1, . . . , n, je kolmý ke všem vektorům ei , i = 1, . . . , m, a potažmo i ke
všem vektorům podprostoru [[e1 , . . . , em ]] = U (cvičenı́).
Nynı́ dokážeme inkluzi U ⊥ ⊆ [[em+1 , . . . , en ]]. Necht’ v = y1 e1 + · · · + yn en ∈ U ⊥ . Pak
v ⊥ ei pro i = 1, . . . , m, a tedy 0 = (v, ei ) = (y1 e1 + · · · + yn en , ei ) = yi (ei , ei ) = yi pro
i = 1, . . . , m. Tudı́ž, v = ym+1 em+1 + · · · + yn en ∈ [[em+1 , . . . , en ]].
Odtud dim U ⊥ = n − m a též V = [[e1 , . . . , en ]] = [[e1 , . . . , em ]] +̇ [[em+1 , . . . , en ]] =
U +̇ U ⊥ .
6

16. Skalárnı́ součin

Tvrzenı́. Bud’ V konečněrozměrný vektorový prostor se skalárnı́m součinem, bud’te U, U1 , U2
jeho podprostory.
(i) Jestliže U1 ⊆ U2 , pak U1⊥ ⊇ U2⊥ .
(ii) U ⊥⊥ = U .
(iii) (U1 + U2 )⊥ = U1⊥ ∩ U2⊥ .
(iv) (U1 ∩ U2 )⊥ = U1⊥ + U2⊥ .
Důkaz. (i) Cvičenı́.
(ii) Každý vektor z U je kolmý ke každému vektoru z U ⊥ , a proto U ⊆ (U ⊥ )⊥ . Přitom
dimenze jsou stejné: dim(U ⊥ )⊥ = dim V − dim U ⊥ = dim V − (dim V − dim U ) = dim U .
Tudı́ž, (U ⊥ )⊥ = U .
(iii) a (iv): Pro i = 1, 2 máme Ui ⊆ U1 + U2 , a proto podle (i) je Ui⊥ ⊇ (U1 + U2 )⊥ . Pak
ale
(1)
U1⊥ ∩ U2⊥ ⊇ (U1 + U2 )⊥ .
Analogicky
U1⊥ + U2⊥ ⊆ (U1 ∩ U2 )⊥

(2)

(cvičenı́). Ale pro dvojici U1⊥ , U2⊥ platı́ (1) též: U1 ∩ U2 = U1⊥ ⊥ ∩ U2⊥ ⊥ ⊇ (U1⊥ + U2⊥ )⊥ ,
načež podle (i) je (U1 ∩ U2 )⊥ ⊆ (U1⊥ + U2⊥ )⊥⊥ = U1⊥ + U2⊥ . Odtud a z (2) pak dostáváme
rovnost (iii). Analogicky (iv).
Cvičenı́. Bud’V konečněrozměrný vektorový prostor, U1 , U2 jeho podprostory takové, že V = U1 +̇U2
a že u 1 ⊥ u 2 pro libovolné dva vektory u 1 ∈ U1 a u 2 ∈ U2 . Pak U2 = U1⊥ a U1 = U2⊥ .

Ortogonálnı́ projekce
Bud’ U podprostor v konečněrozměrném vektorovém prostoru V se skalárnı́m součinem;
uvažujme o přı́mém součtu V = U +̇ U ⊥ . Pro každý prvek v ∈ V máme jednoznačný rozklad
v = vU + vU ⊥ , kde vU ∈ U a vU ⊥ ∈ U ⊥ . Vektor vU se nazývá ortogonálnı́ projekce vektoru v
do prostoru U . Vzniká zobrazenı́ prU : V → U , v → vU , které nazveme ortogonálnı́ projekce
do podprostoru U . Analogicky vzniká zobrazenı́ prU ⊥ : V → U , v → vU ⊥ .
Cvičenı́. Ortogonálnı́ projekce prU je lineárnı́ zobrazenı́. Dokažte.

Tvrzenı́. Bud’e1 , . . . , em ortonormálnı́ báze v podprostoru U konečněrozměrného vektorového
prostoru V se skalárnı́m součinem. Pak pro každé v ∈ V máme
prU v = (v, e1 )e1 + · · · + (v, em )em .
Důkaz. Cvičenı́. Návod: Označme em+1 , . . . , en doplňujı́cı́ vektory do ortonormálnı́ báze ve V ,
pak v = (v, e1 )e1 + · · · + (v, em )em + (v, em+1 )em+1 + · · · + (v, en )en .
Cvičenı́. V přı́padě, že báze e1 , . . . , em je pouze ortogonálnı́, formule pro ortogonálnı́ projekci znı́
prU v =

(v, e1 )
(v, em )
e1 + · · · +
em .
(e1 , e1 )
(em , em )

Dokažte ji.

7

16. Skalárnı́ součin

Shodnosti a unitárnı́ transformace
Shodnost je lineárnı́ transformace, která zachovává skalárnı́ součin.
Definice. Bud’ V vektorový prostor se skalárnı́m součinem, bud’ f : V → V lineárnı́ transformace. Řekneme, že f je shodnost, jestliže platı́
( f (u), f (v)) = (u, v).
V hermiteovském přı́padě se shodnost nazývá unitárnı́ transformace, v eukleidovském přı́padě
se běžně užı́vá název ortogonálnı́ transformace.
Každá shodnost zřejmě zachovává i délky vektorů: platı́ rovnost  f (u) = u, protože
platı́ rovnost  f (u)2 = ( f (u), f (u)) = (u, u) = u2 a délky jsou nezáporná čı́sla.
Platı́ však i opačné tvrzenı́: zobrazenı́ zachovávajı́cı́ délky zachovává i skalárnı́ součin.
Tvrzenı́. Lineárnı́ transformace f : V → V je shodnost právě tehdy, když zachovává délky
vektorů.
Důkaz. Necht’ f zachovává délky vektorů. Ukažme, že f je shodnost. V eukleidovském přı́padě
máme u + v2 = (u + v, u + v) = u2 + 2(u, v) + v2 , načež


(u, v) = 12 u + v2 − u2 − v2



pro libovolné dva vektory u, v ∈ V . Odtud


( f (u), f (v)) = 12  f (u) + f (v)2 −  f (u)2 −  f (v)2


= 12  f (u + v)2 −  f (u)2 −  f (v)2


= 12 u + v2 − u2 − v2







= (u, v)
Podobně postupujeme v hermiteovském přı́padě, pouze vztah mezi skalárnı́m součinem a délkou je
složitějšı́. Máme u + v2 = u2 + (u, v) + (u, v)∗ + v2 = u2 + 2 re(u, v) + v2 , což stačı́
pouze k určenı́ reálné části re(u, v). Nicméně, potom u + iv2 = u2 + 2 re(u, iv) + iv2 =
u2 + 2 re i∗ (u, v) + v2 = u2 + 2 im(u, v) + v2 , což stačı́ k určenı́ imaginárnı́ části im(u, v).
(Dokončete důkaz jako cvičenı́.)
Přı́klad. Rotace kolem počátku je shodnost v eukleidovském prostoru E 2 . Podobně rotace kolem
libovolné osy v eukleidovském prostoru E 3 . Obě totiž zachovávajı́ délky vektorů.

Tvrzenı́. Každá shodnost v konečněrozměrném vektorovém prostoru je izomorfismus.
Důkaz. Bud’ f : V → V shodnost. Bud’ u ∈ Ker f libovolný vektor, tj. necht’ f (u) = 0.
Potom u =  f (u) = 0 = 0, a tedy u = 0. Odtud Ker f = 0 a f je injektivnı́.
Dále dim Im f = dim V − dim Ker f = dim V , a proto Im f = V a f je surjektivnı́.
Cvičenı́. Ukažte, že shodnosti konečněrozměrného vektorového prostoru se skalárnı́m součinem tvořı́
grupu vzhledem k binárnı́ operaci skládánı́ transformacı́.

8

16. Skalárnı́ součin

Je-li e1 , . . . , en ∈ V ortonormálnı́ báze, existuje jednoduchý způsob, jak rozeznat shodnost.
Tvrzenı́. Bud’ e1 , . . . , en ortonormálnı́ báze prostoru V , bud’ f : V → V lineárnı́
transformace. Pak f je shodnost právě tehdy, když f (e1 ), . . . , f (en ) je též ortonormálnı́ báze
Důkaz. Implikace ,,⇒“ je snadná (cvičenı́). ,,⇐“: Budt’e u, v ∈ V libovolné vektory o souřadnicı́ch (x1 , . . . , xn ), (y1 , . . . , yn ) ∈ Rn v bázi e1 , . . . , en . Pak (u, v) = x1 y1 + · · · + xn yn ,
protože báze e1 , . . . , en je ortonormálnı́. Počı́tejme ( f (u), f (v)). Máme u = x1 e1 + · · · xn en ,
načež f (u) = x1 f (e1 ) + · · · xn f (en ). Vidı́me, že vektor f (u) má v bázi f (e1 ), . . . , f (en )
tytéž souřadnice (x1 , . . . , xn ), a podobně vektor f (v). Báze f (e1 ), . . . , f (en ) je však podle
předpokladu také ortonormálnı́, a proto ( f (u), f (v)) = x1 y1 + · · · + xn yn , což je (u, v), jak
se mělo ukázat.
V následujı́cı́m tvrzenı́ budeme charakterizovat matice, které mohou být maticı́ shodného
zobrazenı́ v nějaké ortonormálnı́ bázi.
Definice. Čtvercová reálná matice A, splňujı́cı́ podmı́nku A A = E, se nazývá ortogonálnı́.
Tvrzenı́. Bud’ f : V → V lineárnı́ transformace eukleidovského vektorového prostoru V , bud’
A jejı́ matice v ortonormálnı́ bázi e1 , . . . , en . Pak f je shodnost právě tehdy, když je matice A
ortogonálnı́.
Důkaz. Sloupce Ak j , j = 1, . . . , n matice A jsou tvořeny souřadnicemi vektorů f (e1 ), . . . ,
f (en ) v bázi e1 , . . . , en :
f (e j ) =

n

A k j ek .

k=1

Protože e1 , . . . , en je ortonormálnı́ báze, máme (ei , e j ) = δi j , kde δi j je Kroneckerovo delta.
Podle předchozı́ho tvrzenı́ je f shodnost právě tehdy, když je f (e1 ), . . . , f (en ) ortonormálnı́
báze, tj. když platı́ podmı́nka




δi j = f (ei ), f (e j ) =

n
k=1

=

n

n

n

Aki ek ,

Aki Al j δkl =

k=1 l=1

Al j el =

l=1
n

Aki Ak j =

k=1

n

n

Aki Al j (ek , el )

k=1 l=1
n

Aik Ak j = (A A)i j ,

k=1

to jest, když A A je jednotková matice.
Cvičenı́. (1) Dokažte, že determinant ortogonálnı́ matice je ±1. Důsledek: každá ortogonálnı́ matice
je invertibilnı́.
(2) Dokažte, že ortogonálnı́ matice tvořı́ grupu vzhledem k násobenı́ matic.
Návod: (1) det(A A) = det A · det A = (det A)2 .

Grupa všech ortogonálnı́ch matic typu n/n se značı́ O(n), jejı́ podgrupa O(n) ∩ SL(n, R)
se značı́ SO(n).
9

16. Skalárnı́ součin

Cvičenı́. (1) Ukažte, že podmı́nka charakterizujı́cı́ matice unitárnı́ch transformacı́ hermiteovského
vektorového prostoru znı́
A∗ A = E,
kde ∗ označuje komplexnı́ sdruženı́. Komplexnı́ čtvercová matice A, která tuto podmı́nku splňuje, se
nazývá unitárnı́.
(2) Ukažte, že determinant unitárnı́ matice A splňuje | det A| = 1.
(3) Ukažte, že unitárnı́ matice tvořı́ grupu.

Grupa všech unitárnı́ch matic typu n/n se značı́ U (n), jejı́ podgrupa U (n) ∩ SL(n, C) se
značı́ SU(n).
Cvičenı́. Každá shodnost zachovává i odchylky vektorů, ale opačné tvrzenı́ neplatı́. Nalezněte přı́klad
zobrazenı́, které zachovává odchylky, ale přesto nenı́ shodnost.

10

