---
title: "testy_hypotez.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/moje materialy/Parametricke testy na normalitu/testy_hypotez.pdf"
date: 2010-01-21
type: PDF (text-based)
---

Testování statistických hypotéz
- Testování hypotéz je postup, sloužící k ověření předpokladů o ZS (hypotéz) na základě výběrových dat
(tj. hodnot z výběrového souboru).
- Hypotéza = určitý předpoklad o základním souboru; tvrzení o neznámém parametru ZS (parametrické testy)
nebo o různých vlastnostech ZS (neparametrické testy).
- Testování umožňuje rozhodnout, zda určitou hypotézu zamítneme (event. přijmeme), a to s malým, předem
zvoleným rizikem.
Symbolika: H0 ... nulová (testovaná ) hypotéza
H1 ... alternativní hypotéza
Testové kriterium (t): - vhodná charakteristika, která má při platnosti H0 známé pravděpodobnostní rozdělení;
- prostor hodnot testového kriteria rozdělíme na dva disjunktní obory (W a V).
Kritický obor (W): je tvořen hodnotami TK, které jsou při platnosti H0 tak extrémní, že pravděpodobnost jejich
výskytu je velmi malá.
Obor přijetí (V): je tvořen všemi hodnotami TK mimo kritický obor.
Hladina významnosti (α)= pravděpodobnost chyby 1. druhu: pravděpodobnost že zamítneme H0, ačkoli platí.
Pravděpodobnost chyby 2. druhu (β): pravděpodobnost, že nezamítneme H0, ačkoli neplatí.
Síla testu (1- β): pravděpodobnost správného zamítnutí H0 (schopnost testu zamítnout neplatnou H0).

Standardní testovací postup:
- obecný, bez ohledu na konkrétní typ testu;
- provádí se v několika krocích.
1.

Formulace hypotéz H0 a H1.

2.

Volba testového kritéria: zvolíme vhodnou charakteristiku, jejíž rozdělení při platnosti H0 známe.

3.

Vymezení kritického oboru: je omezen kvantily rozdělení TK při platnosti H0 (= kritické hodnoty).

4.

Výpočet hodnoty TK z výběrových dat.

5.

Formulace závěru o výsledku testu: velmi důležité, existují dvě možnosti.
I. TK leží v kritickém oboru (TK Є W): pak zamítáme H0, tzn. prokázali jsme H1.
II. TK leží v oboru přijetí (TK Є V): pak nezamítáme H0, tzn. neprokázali jsme H1.

Některé parametrické testy hypotéz
Test parametru μ normálního rozdělení
1. Formulace hypotéz
H 0 : µ = µ0
a) H1 : µ ≠ µ 0
b) H1 : µ > µ 0
c) H1 : µ < µ 0

oboustranná alternativní hypotéza
pravostranná alternativní hypotéza
levostranná alternativní hypotéza

1

2. Volba testového kritéria
Rozlišujeme tři případy:
1) známe rozptyl ZS σ2

U=

x − µ0
σ
n

≈ N (0,1)

2) neznáme rozptyl ZS σ2; výběr má malý rozsah

t=

x − µ0
s
n

≈ t (n − 1)

3) neznáme rozptyl ZS σ2 ; výběr má velký rozsah

U=

x − µ0
s
n

≈ N (0,1)

3. Stanovení kritického oboru
Pro případy 1) a 3) a různé typy alternativních hypotéz :



a) W ≡ u; u ≤ u α ∪ u ≥ u α 
1−

2
2 
b) W ≡ {u; u ≥ u1−α }
c) W ≡ {u; u ≤ uα }
Pro případ 2) a různé typy alternativních hypotéz :



a) W ≡ t ; t ≤ t α (n − 1) ∪ t ≥ t α (n − 1)
1−

2
2

b) W ≡ {t ; t ≥ t1−α (n − 1)}
c) W ≡ {t ; t ≤ tα (n − 1)}

Test parametru π alternativního rozdělení
Je třeba mít k dispozici výběr dostatečně velkého rozsahu; to je zajištěno splněním podmínky nπ (1 − π ) > 9 .
1.

H0 :π = π0
a) H 1 : π ≠ π 0
b) H 1 : π > π 0
c) H 1 : π < π 0
2

2. U =

3.

p −π0

≈ N (0,1)

π 0 (1 − π 0 )
n



a) W ≡ u; u ≤ u α ∪ u ≥ u α 
1−

2
2 
b) W ≡ {u; u ≥ u1−α }
c) W ≡ {u; u ≤ uα }

Test parametru σ2 normálního rozdělení
1.

H 0 : σ 2 = σ 02
a) H 1 : σ 2 ≠ σ 02
b) H 1 : σ 2 > σ 02
c) H 1 : σ 2 < σ 02

2.

V praxi je častější případ, kdy neznáme parametr μ, proto se na něj zaměříme.

χ2 =

(n − 1)s 2
σ

≈ χ

2
0



2

(n − 1)


≤ χ α2 (n − 1) ∪ χ 2 ≥ χ 2 α (n − 1)
1−


2
2
2
2
2
b) W ≡ χ ; χ ≥ χ 1−α (n − 1)

3. a) W ≡  χ ; χ
2

2

{
}
c) W ≡ {χ ; χ ≤ χ (n − 1)}
2

2

2
α

Některé neparametrické testy
χ2- test dobré shody
- Slouží k ověření shody mezi teoretickým a empirickým rozdělením.
- Je použitelný jen v případě velkých výběrů.
- Předpokladem testu je možnost roztřídit výsledky náhodného výběru do určitého počtu (k) disjunktních tříd
podle nějakého znaku.
- Nemáme-li k dispozici dostatečně velký výběr, použijeme místo tohoto testu Kolmogorovův-Smirnovův test.
Požadovaný rozsah výběru: Je nutné, aby rozsah výběru zajistil, že bude dostatečné obsazení ve všech
skupinách, do nichž je soubor roztříděn, tj. nπ 0 ,i > 5 pro i = 1, 2, ...., k.
Někdy bývá tato podmínka formulována mírn ěji : ve všech třídách musí platit nπ 0 ,i > 1 a alespoň v 80 % tříd
musí platit nπ 0 ,i > 5 .
! Nejsou-li výše uvedené podmínky splněny, je třeba sloučit některé třídy (např. sousední či věcně příbuzné).

3

Tento test se používá ve 2 situacích :
I. H0 udává proporce četností v jednotlivých skupinách (může být formulováno intuitivně).
II. H0 přepokládá, že ZS má rozdělení určitého typu:
a) Pokud H0 udává typ rozdělení i jeho parametry, jedná se o úplně specifikovaný model.
b) Pokud H0 udává pouze typ rozdělení bez specifikace parametrů, jde o neúplně specifikovaný
model.

Ad I.
1. H 0 : π i = π 0 ,i

pro i = 1, 2, ... , k

H 1 : non H 0
2. G =

k

∑

(n − nπ )

2

i

≈ χ

0 ,i

nπ 0 ,i

i =1

2

(k − 1)

kde ni ......... empirická (pozorovaná, výběrová) četnost

nπ 0,i ... teoretická (hypotetická) četnost, tj. teoretické obsazení i-té třídy.

{

}

3. W ≡ G; G ≥ χ 1−α (k − 1)
2

Ad II. a) - tj. úplně specifikovaný model
1. H 0 : výběr pochází z Po(2)

( například)

H 1 : non H 0
! Další postup (tj. body 2. a 3.) viz. případ I.

Ad II. b) - tj. neúplně specifikovaný model
1. H 0 : výběr pochází z Po ( například)

H 1 : non H 0
2. G =

k

∑
i =1

(n − nπ )

2

i

0 ,i

nπ 0 ,i

≈ χ

2

(k − p − 1)

kde p ..... počet parametrů rozdělení, které odhadujeme.

{

}

3. W ≡ G; G ≥ χ 1−α (k − p − 1)
2

Závěr testu: Pokud TK Є W, zamítáme H0 (tzn. přijímáme H1). V tom případě není rozdělení, specifikované
nulovou hypotézou, vhodným modelem pro empirická data. Shoda obou rozdělení (teoretického a empirického)
se na hladině významnosti α nepotvrdila.

4

