---
title: "kap07.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/moje materialy/Parametricke testy na normalitu/priklady/kap07.pdf"
date: 2010-01-20
type: PDF (text-based)
---

7

Parametrické testy

Mnohdy je nejlepšı́m způsobem analýzy a zveřejněnı́ výsledků použitı́ intervalů spolehlivosti., protože v rámci takto zveřejněných výsledků je zdůrazněn vliv nejistoty a neurčitosti. Často použı́vaný
statistický přı́stup je však též statistické testovánı́ hypotéz.
Většina statistických hypotéz zahrnuje porovnánı́ různých způsobů léčby, metod či skupin nebo
přı́padů.
Statistické hypotézy jsou jednoduše a jednoznačně formulované domněnky o populaci, jejichž pravdivost lze ověřovat (testovat) pomocı́ výběrů. Typickou statistickou hypotézou je tvrzenı́, že průměr
bı́lkovinného séra je stejný pro muže i ženy nebo že dvě léčby bolesti hlavy jsou stejně efektivnı́.

7.1

Formulovánı́ nulové a alternativnı́ hypotézy

Pokud budeme tedy testovat hypotézy statistickými metodami, musı́me na začátku práce formulovat
dvě hypotézy:
nulová hypotéza H0 je tvrzenı́ o populaci (parametru populace), o jehož platnosti chceme rozhodnout (nenı́ rozdı́l, nezávisı́, má dané rozdělenı́, . . . ); nulová hypotéza je obvykle opakem toho,
co chceme výzkumem dokázat (koresponduje s tvrzenı́m, že efekt je nulový);
alternativnı́ hypotézu H1 vymezuje situaci, do jaké se dostaneme, když neplatı́ H0 (nepřipouštı́me
tedy situace, že by existovala dalšı́ možnost - bud’ platı́ H0 nebo neplatı́ H0 , ale pak platı́ H1 ).

7.2

Chyby 1. a 2. druhu při testovánı́, hladina významnosti testu, sı́la
testu

Ověřujeme-li určitou hypotézu týkajı́cı́ se nějaké náhodné veličiny na základě realizace náhodného
výběru rozsahu n, můžou nastat následujı́cı́ situace
skutečnost H0 platı́
skutečnost H0 neplatı́
rozhodnutı́ H0 zamı́tnout (reject)
chyba 1. druhu (α)
správné rozhodnutı́ (1 − β)
rozhodnutı́ H0 přijmout (accept) správné rozhodnutı́ (1 − α)
chyba 2. druhu (β)
Chyba 1. druhu (α) je rozhodnutı́ zamı́tnout nulovou hypotézu H0 , když platı́ (tj. falešně prokázat
alternativnı́ hypotézu H1 );
Chyba 2. druhu (β) je rozhodnutı́ nezamı́tnout nulovou hypotézu H0 , když platı́ H1 ;
Hladina testu α (zpravidla 5% nebo 1%) je maximálnı́ dovolená pravděpodobnost chyby 1. druhu;
volı́ se před pokusem, nezávisle na výsledku;
Sı́la testu 1 − β je pravděpodobnost zamı́tnutı́ neplatné nulové hypotézy H0 ; sı́la testu závisı́ na
formulaci nulové a alternativnı́ hypotézy a na použitém testu;
Dosažená hladina významnosti testu, p − hodnota je za platnosti H0 určená pravděpodobnost,
že naše data“ podporujı́ hypotézu H0 .
”
1

Interpretaci dosažené hladiny významnosti testu (p−hodnoty) lze vysvětlit následujı́cı́m přı́kladem.
Když porovnáváme dvě léčby a dostaneme vysokou hodnotu p (napřı́klad 10% a vı́ce), pak můžeme
tvrdit, že taková data, jako jsou naše, bychom dostali celkem často i v přı́padě platnosti nulové
hypotézy. Při vysokých hodnotách p se tedy přiklánı́me k nulové hypotéze.
Naopak velmi malá hodnota p (napřı́klad 1% a méně) nám ukazuje, že nulová hypotéza je téměř“
”
nemožná, protože naše data by sotva mohla vzniknout, kdyby nulová hypotéza platila. Při nı́zkých
hodnotách p tedy můžeme tvrdit, že nulová hypotéza neplatı́ a přijı́máme hypotézu alternativnı́.
V praxi často předem stanovujeme meznı́ hranici α (obvykle 5% nebo 1%) a pokud p − hodnota
je menšı́ než tato hranice, zamı́táme hypotézu H0 . Jinými slovy, výsledek, který bychom mohli za
platnosti nulové hypotézy dostat méně než jednou z dvaceti přı́padů, vede k zamı́tnutı́ hypotézy.
Je-li p − hodnota menšı́ než zvolená hladina významnosti (α = 5%), pak výsledek je statisticky
významný, je-li p − hodnota menšı́ než zvolená hladina významnosti (α = 1%) mluvı́me o vysoké
statistické významnosti.
Obvyklá praxe je pokládat statisticky významný výsledek za skutečný efekt a v důsledku toho též
za klinicky důležitý a naopak. Tato interpretace však nemusı́ být oprávněná. Někdy může být rozdı́l
statisticky významný, ale klinicky nevýznamný a naopak.
Pokud klinicky významný rozdı́l populačnı́ch průměrů je dán překročenı́m konstanty ∆, můžeme
tuto skutečnost interpretovat pomocı́ 95% intervalu spolehlivosti pro rozdı́l populačnı́ch dat. Na obrázku ukážeme možnosti, které mohou nastat a jejich interpretace.
Chyba 1. druhu a chyba 2. druhu jsou úzce provázány, snı́ženı́m chyby jednoho druhu docházı́
ke zvýšenı́ druhé chyby. Obvykle pevně volı́me akceptovatelnou hodnotu pro chybu 1. druhu (α) a
chybu druhého druhu můžeme ovlivňovat pouze prostřednictvı́m zvoleného testu, přı́padně můžeme
tuto chybu snı́žit zvýšenı́m rozsahu použitých dat.

2

Obrázek demostruje různé možnosti vztahu mezi statistickou významnostı́ a klinickou významnostı́:
0
∆
a)

u

b)

u

c)

u

d)
e)
f)

u
u
u

Možnost Statistická významnost Klinická významnost
a)
ne
možná
b)
ne
možná
c)
ano
možná
d)
ano
ano
e)
ne
ne
f)
ano
ne

7.3

Postup při použitı́ statistického testovánı́

Při aplikaci statistických hypotéz postupujeme v následujı́cı́ch krocı́ch
1. Formulujeme nulovou hypotézu H0 . Typickým přı́kladem parametrické nulové hypotézy je hypotéza H0 : µ = 0.
2. Formulujeme alternativnı́ hypotézu H1 . Alternativnı́ hypotéza u parametrických testů může být
dvoustranná H1 : µ 6= 0 nebo jednostranná H1 : µ > 0 ev. H1 : µ < 0. U neparametrických testů
bývá alternativnı́ hypotéza tvaru H1 : nonH0 .
3. Zvolı́me vhodnou statistiku, pomocı́ které budeme hypotézy testovat. Statistika je hodnota spočtená z dat, které máme k dispozici T = T (x1 , x2 , . . . , xn ). Statistiku volı́me tak, abychom byly
schopni odvodit statistické vlastnosti této statistiky při platnosti nulové hypotézy.
4. Podle statistických vlastnostı́ testovacı́ statistiky určı́me kritický obor (obor hodnot testovacı́
statistiky, kdy zamı́táme hypotézu H0 ) a obor přijetı́ (obor hodnot testovacı́ statistiky, kdy H0
nezamı́táme). Pro určovánı́ kritických oborů a oborů přijetı́ využı́váme statistické vlastnosti
testovacı́ statistiky (znalost jejı́ho rozdělenı́ při platnosti hypotézy H0 ).
5. Zjistı́me, zda hodnota testovacı́ statistiky ležı́ v oboru kritických hodnot ⇒ přijı́máme alternativnı́ hypotézu nebo zda ležı́ v oboru přijetı́ ⇒ přijı́máme nulovou hypotézu.
3

6. Alternativně můžeme zjistit p − hodnotu testu a pro nı́zkou p − hodnotu přijı́máme hypotézu
alternativnı́ a pro vysoké p − hodnoty přijı́máme hypotézu nulovou.

7.4

Test o průměru při známém rozptylu -z-test

Předpokládáme, že máme k dispozici náhodný výběr n jednotek (x1 , x2 , . . . , xn ) , u nichž měřı́me
nějakou spojitou statistickou veličinu (napřı́klad hmotnost osoby, výšku, hladinu účinné látky v krvi
a podobně). Pokud předpokládáme, že měřená spojitá náhodná veličina má charakter normálnı́ho
rozdělenı́ s parametry µ a σ můžeme k testu o střednı́ hodnotě použı́t následujı́cı́ z-test.
Nulová hypotéza H0 : µ = µ0 odpovı́dá situaci, kdy data náhodného výběru pocházı́ z rozdělenı́ se
stejnou střednı́ hodnotu jako je hodnota µ0 .
Dvoustranná alternativnı́ hypotéza H1 : µ 6= µ0 odpovı́dá situaci, kdy data náhodného výběru
pocházı́ z rozdělenı́ se střednı́ hodnotou odlišnou od µ0 .
Jednostranná alternativnı́ hypotéza H1 : µ < µ0 odpovı́dá situaci, kdy data náhodného výběru
pocházı́ z rozdělenı́, jehož střednı́ hodnota je menšı́ než µ0 . (analogicky může být střednı́ hodnota
náhodného výběru většı́).
Testovacı́ kritérium má ve všech předcházejı́cı́ch přı́padech tvar
T =

x − µ0 √
· n,
σ

kde x je aritmetický průměr hodnot x1 , x2 , . . . , xn , n je počet jednotek a σ je směrodatná odchylka
základnı́ho souboru (předpokládáme, že tuto hodnotu známe z jiných statistických šetřenı́). Testovacı́
kritérium porovnáváme s kritickou hodnotou, v přı́padě, že testovacı́ kritérium překročı́ kritickou
hodnotu, přijı́máme hypotézu alternativnı́ a zamı́táme hypotézu nulovou. Kritické hodnoty z-testu
jsou odvozeny od kvantilů normovaného normálnı́ho rozdělenı́.
Pro dvoustrannou alternativnı́ hypotézu H1 : µ 6= µ0 přijı́máme alternativnı́ hypotézu, pokud
α
testovacı́ kritérium T je v absolutnı́ hodnotě většı́ než 1 − procentnı́ kvantil normálnı́ho rozdělenı́.
2
Tedy pokud
|T | > u1− α2 ⇒ H1 .
Pro jednostrannou alternativnı́ hypotézu H1 : µ < µ0 přijı́máme alternativnı́ hypotézu, pokud
testovacı́ kritérium T je menšı́ než α procentnı́ kvantil normálnı́ho rozdělenı́. Tedy pokud
T < −u1−α ⇒ H1 .
Pro jednostrannou alternativnı́ hypotézu H1 : µ > µ0 přijı́máme alternativnı́ hypotézu, pokud
testovacı́ kritérium T je většı́ než 1 − α procentnı́ kvantil normálnı́ho rozdělenı́. Tedy pokud
T > u1−α ⇒ H1 .

4

Přı́klad: Výběr 100 pacientů s rakovinou plic má léčených novým lékem má průměrnou dobu přežitı́
27,5 měsı́ců. Z předchozı́ch studiı́ je známo, že průměrné přežitı́ takovýchto pacientů bez podávánı́
nového léku je 22,2 měsı́ce a směrodatná odchylka je 25,0 měsı́ců. Předpokládáme, že směrodatná
odchylka bude zachována i při podávánı́ nového léku. Lze na základě těchto dat usoudit, že nový lék
statisticky prodlužuje přežitı́ ?
Z dat, která máme k dispozici n = 100, σ = 25, 0, µ0 = 22, 2 a x = 27, 5 spočteme hodnotu
testovacı́ho kritéria
x − µ0 √
27, 5 − 22, 2 √
· n=
· 100 = 2, 12.
T =
σ
25, 0
Formulujeme nulovou H0 : µ = 22, 2 a alternativnı́ H1 : µ > 22, 2 hypotézy (chceme dokázat, že
nový lék prodlužuje přežitı́, tedy alternativnı́ hypotéza ve formě jednostranné nerovnosti), zvolı́me
hodnotu α = 5% a ve statistických tabulkách najdeme hodnotu kvantilu normálnı́ho rozdělenı́ u0,95 =
1, 64.
Protože hodnota testovacı́ho kritéria je většı́ než hodnota kvantilu 2, 12 > 1, 64 přijı́máme alternativnı́ hypotézu na hladině α = 5% a můžeme tedy považovat rozdı́l v době přežitı́ za statisticky
významný.
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . ..
V Excelu najdeme hodnotu uα pomocı́ funkce N ORM SIN V (α), napřı́klad N ORM SIN V (0.95) ⇒
1.64
V Excelu také můžeme použı́t funkci ZT EST (data; µ0 ; σ), která vracı́ p-hodnotu jednostranného
alternativnı́ho testu H1 : µ > µ0 . Pokud chceme použı́t dvoustrannou alternativnı́ hypotézu je třeba
určit p-hodnotu vztahem 2 · M IN (ZT EST (data; µ0 ; σ)); 1 − ZT EST (data; µ0 ; σ))).
. ................................................................................................ .

7.5

Test o průměru při neznámém rozptylu t-test pro jeden výběr

Ve většině přı́padů však neznáme přı́mo hodnotu rozptylu, resp. směrodatné odchylky σ a musı́me
n
1 X 2
x − (x)2 . Tı́m zaneseme do
použı́t jejı́ odhad - výběrovou směrodatnou odchylku s2 =
n − 1 i=1 i
našeho rozhodovánı́ dalšı́ nejistotu, kterou musı́me brát v úvahu.
Formulace nulové hypotézy a alternativnı́ hypotézy je stejná jako v přı́padě z-testu, testovacı́
kritérium je obdobné
x − µ0 √
T =
· n.
s
Testovacı́ kritérium má v tomto přı́padě Studentovo t-rozdělenı́ a proto je tento test znám pod
názvem jednovýběrový t-test.
Testovacı́ kritérium porovnáváme s přı́slušnými kvantily Studentova t-rozdělenı́ se stupni volnosti
n − 1.
Pro dvoustrannou alternativnı́ hypotézu H1 : µ 6= µ0 přijı́máme alternativnı́ hypotézu, pokud
α
testovacı́ kritérium T je v absolutnı́ hodnotě většı́ než 1 − procentnı́ kvantil Studentova t-rozdělenı́.
2

5

Tedy pokud
|T | > t1− α2 (n − 1) ⇒ H1 .
Pro jednostrannou alternativnı́ hypotézu H1 : µ < µ0 přijı́máme alternativnı́ hypotézu, pokud
testovacı́ kritérium T je menšı́ než α procentnı́ kvantil Studentova t-rozdělenı́. Tedy pokud
T < −t1−α (n − 1) ⇒ H1 .
Pro jednostrannou alternativnı́ hypotézu H1 : µ > µ0 přijı́máme alternativnı́ hypotézu, pokud
testovacı́ kritérium T je většı́ než 1 − α procentnı́ kvantil Studentova t-rozdělenı́. Tedy pokud
T > t1−α (n − 1) ⇒ H1 .
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . ..
V Excelu najdeme hodnotu tα (n) pomocı́ funkce T IN V (a; n), kde a odpovı́dá hodnotě 2 · (1 − α), napřı́klad t0.95 (10) spočteme v Excelu vztahem T IN V (0.10; 10) ⇒ 1.81 a T IN V (0.10; 1000000) ⇒ 1.64
. ................................................................................................ .

7.6

Test o rozptylu

Předpokládejme opět, že máme k dispozici náhodný výběr náhodný výběr n jednotek (x1 , x2 , . . . , xn ),
který pocházı́ z normálnı́ho rozdělenı́, a chceme testovat shodu rozptylu.
Nulová hypotéza má následujı́cı́ tvar H0 : σ 2 = σ02 a charakterizuje situaci, kdy rozptyl náhodného
výběru odpovı́dá předem zvolené hodnotě σ02 .
Alternativnı́ hypotézy majı́ tvar H1 : σ 2 6= σ02 , resp. H1 : σ 2 < σ02 , resp. H1 : σ 2 > σ02 .
Testovacı́ kritérium má podobu
(n − 1)s2
,
χ2 =
σ02
n
1 X 2
2
kde s =
xi − (x)2 je výběrová směrodatná odchylka dat.
n − 1 i=1
Testovacı́ kritérium porovnáváme s kvantily χ2 rozdělenı́ se stupni volnosti n − 1.
Pro dvoustrannou alternativnı́ hypotézu H1 : σ 2 = σ02 přijı́máme alternativnı́ hypotézu, pokud
α
α
testovacı́ kritérium χ2 je v většı́ než 1 − procentnı́ kvantil χ2 rozdělenı́ nebo menšı́ než procentnı́
2
2
kvantil χ2 rozdělenı́. Tedy pokud
χ2 > χ21− α (n − 1) nebo χ2 < χ2α (n − 1) ⇒ H1 .
2

2

2

< σ02 přijı́máme alternativnı́ hypotézu, pokud
2

Pro jednostrannou alternativnı́ hypotézu H1 : σ
testovacı́ kritérium χ2 je menšı́ než α procentnı́ kvantil χ rozdělenı́. Tedy pokud
χ2 < χ2α (n − 1) ⇒ H1 .

Pro jednostrannou alternativnı́ hypotézu H1 : σ 2 > σ02 přijı́máme alternativnı́ hypotézu, pokud
testovacı́ kritérium χ2 je většı́ než 1 − α procentnı́ kvantil χ2 rozdělenı́. Tedy pokud
χ2 > χ21−α (n − 1) ⇒ H1 .
6

