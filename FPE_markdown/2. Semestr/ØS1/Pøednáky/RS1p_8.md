---
title: "RS1p_8.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/ØS1/Pøednáky/RS1p_8.pdf"
date: 2008-08-24
type: PDF (text-based)
---

4.5 Stabilita lineárních dynamických systémů (LDS)
Jedna z nejdůležitějších vlastností LDS.
Stabilita: schopnost systému vrátit se do rovnovážného stavu, jestliže skončilo působení
signálu, který jej z rovnovážného stavu vyvedl.
V kapitole 2 jsme definovali matici přechodových funkcí
Φ( p ) = ( pI − A ) −1 =

1
adj( pI − A )
det( pI − A )

adj (pI-A) – adjungovaná matice (sestavená z algebraických doplňků příslušné
transponované matice).
det (pI-A) – determinant matice (pI-A).
Víme: kořeny char. rovnice det (pI-A) = 0 jsou vlastní čísla matice A, jsou to póly přenosové
funkce
Definice:
Lineární SAŘ bude stabilní, leží-li všechny póly jeho přenosové funkce F(p) a tedy vlastní
čísla matice A v levé komplexní polorovině, vyjma imaginární osy.
Systém je na mezi stability, leží-li alespoň jeden pól (dvojice komplexně sdružených pólů) na
imaginární ose a zbylé póly leží v levé komplexní polorovině.
Systém je nestabilní, leží-li alespoň jeden pól (dvojice komplexně sdružených pólů) v pravé
komplexní polorovině

4.5.1 Algebraická kritéria stability
Vychází se z analýzy charakteristické rovnice systému. Algebraická kritéria umožňují zjistit
stabilitu na základě znalosti hodnot koeficientů charakteristické rovnice.
Hurwitzovo kriterium
Mějme charakteristickou rovnici systému n-tého řádu
anpn + … + a1p +a0 = 0

1

Aby tato charakteristická rovnice měla kořeny se zápornou reálnou částí, je nutné, aby
koeficienty ai splňovaly následující podmínky:
Definice:
Systém je stabilní právě tehdy, když:
1. Všechny koeficienty ai jsou nenulové a mají stejné znaménko (nutná podmínka).
2. Hurwitzův determinant a všechny hlavní subdeterminanty v Hurwitzově matici jsou
kladné.
an −1
an
0

an −3
an − 2
an −1

an −5
an − 4
an −3

0
0
0

0
0
0

Hn =
0
0
0

L
L
L

M
L a2
L a3
L a4

0
0
0
ao
a1
a2

0
0
ao

Příklad:
a3p3 + a2p2 + a1p + a0 = 0
Podmínky stability:
1. a3>0; a2>0; a1>0; a0>0
2. D1=a2>0
D2 = det

a2
a3

ao
= a 2 a1 − a 3 a o > 0
a1

a2
D3 = det a 3
0

ao
a1
a2

0
0 >0
ao

Příklad:
Určete, zda je systém s přenosem F( p ) =

5
stabilní.
3p + 5p + 4p2 + 3p +1
4

3

Řešení:
Char. rovnice:
3p4 + 5p3 + 4 p2 + 3p + 1 = 0
1. a i > 0
5
3
2. H =
0
0

∀i
3
4
5
3

0
1
3
4 1
2

D1, D2, D3, D4 >0 ⇒ stabilní

4.5.2 Frekvenční kritika stability Michajlovo kritérium.
Kritérium vychází z charakteristické rovnice uzavřeného obvodu.
H ( P ) = a n p n + ... + a1 p 1 + a o = 1 + Fo ( P ) = 0
kde Fo je přenos otevřeného obvodu.
Dosadíme p → jω a utvoříme H(jω)
H ( jω ) = a n ( jω ) + ... + a1 ( jω ) + a o
n

Definice: Uzavřený obvod bude stabilní, jestliže se při změně frekvence ω∈<0;∞) vektor
H(jω) otočí o úhel n

π
, kde n je stupeň charakteristické rovnice.
2

Geometrické místo, které opisuje konec vektoru H ( jω ) v komplexní rovině při změně
frekvence ω ∈ 0; ∞ ) se nazývá hodograf. Lineární SAŘ bude stabilní, jestliže hodograf
začíná na kladné reálné ose komplexní roviny a postupně projde (při změně frekvence od
0 do ∞ ) v kladném smyslu n – kvadrantů.
Př. Hodografy stabilních a nestabilních systémů

stabilní

nestabilní

4.6 Syntéza optimálních systémů automatického řízení (SAŘ)
Stabilita je nutnou, nikoliv postačující podmínkou správné funkce systému automatického
řízení. Rozhodující je kvalita chování systému automatického řízení.
Syntézou optimálního systému automatického řízení rozumíme stanovení struktury a
parametrů SAŘ tak, aby jeho chování vykazovalo kvalitu odpovídající zvolenému kritériu
kvality (optimality).
Kritéria kvality
3

Formalizací a objektivizací kvalitativních požadavků kladených na dynamiku regulačního
pochodu byla formulována řada kritérií kvality (optimality) z nichž nejvýhodnější jsou
integrální kritéria využívaná pro syntézu optimálních SAŘ.
Úkolem syntézy je navrhnout takové parametry řídícího systému, aby zvolené kritérium
kvality regulace bylo minimální.
a) Integrální kriterium lineární
∞

I = ∫ e ( t ) dt → min
0

kde: e(t ) = y (t ) − y (∞) je regulační odchylka.
b) Integrální kritérium absolutní hodnoty
∞

I = ∫ e ( t ) dt → min
0

c) Integrální kritérium kvadratické regulační plochy
∞

I = ∫ e2 (t ) dt → min
0

Definice (základní úloha optimálního řízení)
Je dán:
a) dynamický systém
x& = f ( x, n, t )
y = g ( x, n, t )
b) počáteční stav systému
xo=x(to)
c) cílová množina χ
d) třída přípustných řízení U
e) kritérium optimálního řízení
tk

J (u ) = φ ( xk , tk ) + ∫ L ( x (τ ) , u (τ ) ,τ ) dτ
to

Úlohou je nalezení takového řízení u = u*, které:
1. Převádí (xo,to) do χ
2. Patří do třídy přípustných řízení U
3. Minimalizuje kritérium optimálního řízení J(u*)=min J(u); u ∈ U

4

