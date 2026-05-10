---
title: "kombinatorika.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/DIZ3/kombinatorika.pdf"
date: 2010-01-12
type: PDF (text-based)
---

Pravděpodobnost a statistika

Kombinatorika

1. KOMBINATORIKA
Průvodce studiem

Na střední škole se někteří z vás seznámili se základními pojmy z kombinatoriky. V této
kapitole tyto pojmy zopakujeme a prohloubíme vaše znalosti.
Předpokládané znalosti

Množiny. Faktoriál.
Cíle

Cílem této kapitoly je objasnit pojmy variace, permutace, kombinace.

Výklad

KOMBINATORIKA
Zkoumá skupiny (podmnožiny) prvků vybraných z jisté základní množiny. Podle toho, zda se
prvky v jednotlivých skupinách mohou či nemohou opakovat, rozdělujeme skupiny prvků
na skupiny s opakováním a skupiny bez opakování.

Poznámka
Skupiny, kde se prvky nemohou opakovat, si lze tedy představit tak, že prvky, které vybíráme
ze základní skupiny do ní nevracíme zpět a nemůžeme je tedy použít při dalším výběru.
Naopak skupiny, kde se prvky mohou opakovat, vznikají tak, že vybrané prvky vracíme
do základní skupiny a v dalším výběru je můžeme znovu použít.

Rozlišujeme tři základní způsoby výběru:
1.1. Variace k-té třídy z n prvků
- uspořádané skupiny po k prvcích z daných n prvků

-1-

Pravděpodobnost a statistika

Kombinatorika

Řešené úlohy

Příklad 1.1.1. Je dána množina M = {1,2,3,4,5}. Z prvků této množiny máme vytvářet
dvojice, přičemž záleží na pořadí a prvky se nemohou opakovat.
Řešení: Vytváříme tedy variace druhé třídy z pěti prvků. Všechny možnosti:
V2(5): (1,2) (2,1) (1,3) (3,1) (1,4) (4,1) (1,5) (5,1)
(2,3) (3,2) (2,4) (4,2) (2,5) (5,2)
(3,4) (4,3) (3,5) (5,3)
(4,5) (5,4)
Takže počet všech možností je 20.
Příklad 1.1.2. Na startu běžeckého závodu je 8 atletů. Kolika způsoby mohou být
obsazeny stupně vítězů?
Řešení:

Jednoduchou úvahou dojdeme k tomu, že na prvním místě se může umístit

kdokoliv z 8-mi startujících. Jestliže některý z atletů už doběhl první, druhé místo
obsadí někdo ze zbývajících 7-mi závodníků. Jsou-li obsazena první dvě místa, je
zřejmé, že pro třetí místo máme 6 možností.
Celkem tedy: V3(8) = 8.7.6 = 336 možností
Obdobně můžeme postupovat při odvození obecného vzorce pro počet variací k-té
třídy z n prvků bez opakování:
Ptáme se:
Z kolika prvků máme na výběr pro 1.člen k-tice?: n
Z kolika prvků máme na výběr pro 2.člen k-tice?: n - 1
...
Z kolika prvků máme na výběr pro k-tý člen k-tice?: n - k + 1
Proto:
Vk ( n ) = n. ( n − 1) ... ( n − k + 1) =
= n. ( n − 1) ... ( n − k + 1) .
=

( n − k ) . ( n − k − 1) ...2.1 =
( n − k ) . ( n − k − 1) ...2.1

n!
( n − k )!

Takže:

-2-

Pravděpodobnost a statistika

Kombinatorika

1.1.1. Počet variací k-té třídy z n prvků bez opakování
Vk ( n ) =

n!
( n − k )!

Řešené úlohy

Příklad 1.1.3. Kolik existuje trojciferných čísel, které lze zapsat užitím cifer 1, 2, 3, 4, 5.
Řešení:

Jedná se o příklad na variace s opakováním - záleží na pořadí cifer a cifry se

v čísle mohou opakovat:
Na první pozici v čísle se může vyskytovat libovolná cifra z daných pěti - tzn. 5
možností. Vzhledem k tomu, že cifry se v čísle mohou opakovat, dostáváme stejný
počet možností i na druhé a třetí pozici. Počet všech možností:
V3*(5) = 5.5.5 = 53 = 125
Pokud tuto úvahu opět zobecníme dostaneme vzorec pro:

1.1.2. Počet variací k-té třídy z n prvků s opakováním
Vk*(n) = nk

Řešené úlohy

Příklad 1.1.4. Kolik různých značek teoreticky existuje v Morseově abecedě, sestavují-li
se tečky a čárky do skupin po jedné až pěti?
Řešení:

Máme k dispozici dva znaky: • −

Z těchto znaků vytváříme postupně jeden znak, dvojice, trojice, čtveřice a pětice.
Záleží na pořadí, znaky se samozřejmě mohou opakovat, jedná se tedy o variace s
opakováním, přičemž n = 2 a k = 1, 2, 3, 4, 5:
z = V1*(2) + V2*(2) + V3*(2) + V4*(2) + V5*(2) = 21 + 22 + 23 + 24 + 25 =
= 2 + 4 + 8 + 16 + 32 = 62

-3-

Pravděpodobnost a statistika

Kombinatorika

1.2. Permutace n prvků
- každá uspořádaná n-tice vybraná z n prvků
Řešené úlohy

Příklad 1.2.1. Najděte všechny permutace bez opakování z prvků množiny M = {1,7,9}
Řešení:

Všechny permutace bez opakování z těchto tří prvků P(3):

(1,7,9), (1,9,7), (7,1,9), (7,9,1), (9,1,7), (9,7,1)
Příklad 1.2.2. Využijeme zadání příkladu 1.1.2., přičemž nás bude zajímat, kolika způsoby
budou obsazena všechna místa.
Řešení:

Vytváříme tedy osmice vybrané z osmi prvků, což přesně odpovídá pojmu

permutace.
Úloha se dá vyřešit stejnou úvahou, jako příklad 1.1.2.. Na prvním místě máme 8
možností, na druhém 7 možností (první místo je již obsazeno), na třetím místě 6
možností, . . ., na osmém místě tedy zbývá pouze jediná možnost.
Výsledek je tedy P(8) = 8.7.6.5.4.3.2.1 = 8! = 40320 možností
Takže:

1.2.1. Počet permutací n prvků bez opakování
P ( n ) = n ! = n. ( n − 1) . ( n − 2 ) ...3.2.1.

Řešené úlohy

Příklad 1.2.3. Mějme n různých korálků, které budeme navlékat na niť. Její konce pak
svážeme, takže vytvoříme kruh (náhrdelník). Kolika způsoby lze korálky do kruhu
uspořádat? Tzn. uspořádání, které se liší pouze otočením kruhu nepovažujeme za různé.
Řešení:

Pokud bychom konce niti nesvázali, odpovídal by počet všech možností počtu

permutací bez opakování z n prvků, těch je n! Ovšem v kruhu by některá z
uspořádání byla shodná. Proveďme tedy následující úvahu. Uvažujme nějaké
uspořádání v kruhu a zvolme si libovolný korálek, o kterém prohlásíme, že je první.
Ostatní korálky očíslujeme např. ve směru hodinových ručiček. Celé uspořádání teď
pootočíme ve směru hodinových ručiček o jeden korálek (první se dostane na místo
-4-

Pravděpodobnost a statistika

Kombinatorika

druhého, druhý na místo třetího, ...), čímž v rámci kruhu dostaneme shodné
uspořádání. Takto můžeme s korálky pootočit n krát a vždy dostaneme shodné
uspořádání. Všechna tato shodná uspořádání jsou ale započítána do počtu n! (počet
uspořádání před svázáním konců niti). Výsledek je tedy:
x=

n ! n. ( n − 1) !
=
= ( n − 1) !
n
n

Příklad 1.2.4. Kolik různých šesticiferných čísel lze vytvořit z číslic 1, 2, 2, 3, 3, 3?
Řešení:

Mezi danými šesti číslicemi se některé opakují. Pokud by se číslice

neopakovaly, vytvořili bychom 6! čísel. V našem případě se počet čísel zmenší:
Z důvodu, že tam máme dvě dvojky se počet možností sníží dvakrát - jedna možnost
2 2 namísto dvou možností X 2, 2 X (permutace ze dvou prvků) v případě, že by
číslice byly různé.
V důsledku tří trojek se počet čísel zmenší šestkrát - jedna možnost 3 3 3 namísto
permutace ze tří různých číslic.
Počet všech možností je tedy:
P* ( 6 ) =

6!
2!.3!

Při zobecnění naší úvahy je:

1.2.2. Počet permutací n prvků s opakováním
P* ( n ) =

n!
n1 !n2 !...nk !

Jestliže se mezi n prvky vyskytuje: první prvek n1 krát
druhý prvek n2 krát
…

⇒ n1 + n2 + ... + nk = n

k-tý prvek nk krát

Řešené úlohy

Příklad 1.2.5. Zjistěte, kolik různých pěticiferných čísel lze vytvořit použitím cifer
1, 2, 3, 4, 5 (cifry se v čísle mohou opakovat).
-5-

Pravděpodobnost a statistika

Řešení:

Kombinatorika

Při řešení této úlohy se často můžeme setkat s následující chybou: řešitel si

všimne, že z pětiprvkové množiny máme vytvářet pětice a automaticky se úlohu snaží
řešit pomocí permutací. Zde ale dochází ke kolizi, neboť o permutace bez opakování
se jednat nemůže (cifry se v čísle mohou opakovat) a permutace s opakováním to být
také nemohou (není určeno, kolikrát se který prvek má opakovat).
Zadání úlohy totiž přesně koresponduje s pojmem variace s opakováním, kde k = n,
takže počet všech možností je:
V5*(5) = 55 = 3125
1.3. Kombinace k-té třídy z n prvků
- skupiny o k prvcích vybraných z n prvků
Poznámka
Vybíráme bez zřetele na uspořádání: tzn., že v daných n-ticích nezáleží na pořadí prvků!

Řešené úlohy

Příklad 1.3.1. Najděte všechny kombinace druhé třídy z množiny M = {1,2,3,4,5}
Řešení:
C2(5): (1,2) (1,3) (1,4) (1,5)
(2,3) (2,4) (2,5)
(3,4) (3,5)
(4,5)
Počet všech možností je tedy 10.
Příklad 1.3.2. Odvoďte počet kombinací k-té třídy z n prvků
Řešení:

Umíme spočítat počet uspořádaných k-tic z n prvků - pomocí variací. Některé z

těchto k-tic se však liší pouze pořadím prvků. Kolik jich je? Vezmeme libovolnou ktici a vytvoříme všechny její obměny pouze s jejími prvky (tedy permutaci). Všechny
k-tice, které jsme takto vytvořili, se budou lišit pouze pořadím prvků. Odtud je
zřejmé, že počet kombinací k-té třídy z n prvků je:
Ck(n) = Vk(n)/P(k):

-6-

Pravděpodobnost a statistika

Kombinatorika

1.3.1. Počet kombinací k-té třídy z n prvků bez opakování
Ck ( n ) =

⎛n⎞
n!
=⎜ ⎟
( n − k )!.k ! ⎝ k ⎠

Poznámka
⎛n⎞
⎜ ⎟ ... kombinační číslo, čteme n nad k
⎝k ⎠
Pro ruční výpočet kombinačních čísel je často vhodné použít následující odvození:



n. ( n − 1) ... ( n − k + 1) . ( n − k ) ! n. ( n − 1) ... ( n − k + 1)
⎛n⎞
n!
=
=
⎜ ⎟=
k !( n − k ) !
k!
⎝ k ⎠ k !( n − k ) !
k − členů

Takže například:
⎛ 7 ⎞ 7.6.5.
= 35
⎜ ⎟=
⎝ 3 ⎠ 3.2.1

1.3.2. Počet kombinací k-té třídy z n prvků s opakováním
⎛ n + k − 1⎞
Ck* ( n ) = ⎜
⎟
⎝ k ⎠
Řešené úlohy

Příklad 1.3.3. Zjistěte, kolik existuje různých kvádrů, pro něž platí, že délka každé jejich
hrany je přirozené číslo z intervalu 2,15
Řešení:

Přirozených čísel v tomto intervalu je 14. Kvádr je jednoznačně určen třemi

hodnotami (délka, šířka, výška) u nichž nezáleží na pořadí (je jedno, jak je kvádr
"natočený"). Hodnoty v trojici se mohou opakovat (i krychle je speciální případ
kvádru).
Takže se jedná o kombinace s opakováním, n = 14, k = 3:
⎛14 + 3 − 1⎞ ⎛16 ⎞
C3* (14 ) = ⎜
⎟ = ⎜ ⎟ = 560
3
⎝
⎠ ⎝3⎠

-7-

Pravděpodobnost a statistika

Kombinatorika

1.3.3. Základní pravidla pro kombinační čísla
Symetrie
⎛n⎞ ⎛ n ⎞
⎜ ⎟=⎜
⎟
⎝k ⎠ ⎝n−k ⎠
Okrajová vlastnost
⎛n⎞ ⎛n⎞
⎜ ⎟ = ⎜ ⎟ =1
⎝0⎠ ⎝n⎠
Sčítání
⎛ n ⎞ ⎛ n ⎞ ⎛ n + 1⎞
⎜ ⎟+⎜
⎟=⎜
⎟
⎝ k ⎠ ⎝ k + 1⎠ ⎝ k + 1⎠

Řešené úlohy

Příklad 1.3.4. Řešte rovnici:
⎛ x + 2 ⎞ ⎛ x + 3⎞
⎜
⎟+⎜
⎟ = 64
⎝ x ⎠ ⎝ x +1⎠
Řešení:
⎛ x + 2 ⎞ ⎛ x + 3⎞
⎜
⎟+⎜
⎟ = 64
⎝ x ⎠ ⎝ x +1⎠
⎛ x + 2 ⎞ ⎛ x + 3⎞
⎜
⎟+⎜
⎟ = 64
⎝ 2 ⎠ ⎝ 2 ⎠

( x + 2 ) . ( x + 1) + ( x + 3) . ( x + 2 ) = 64

2.1
2.1
2
2
x + 3 x + 2 + x + 5 x + 6 = 128
2 x 2 + 8 x + 8 − 128 = 0
x 2 + 4 x − 60 = 0

( x + 10 ) . ( x − 6 ) = 0
x=6

(kořen x = -10 nelze použít, x musí být přirozené číslo)

-8-

Pravděpodobnost a statistika

Kombinatorika

1.4. Řešené příklady, kombinatorika - souhrnně

Příklad 1.4.1. Jsou dány cifry 1, 2, 3, 4, 5. Cifry nelze opakovat. Kolik je možno vytvořit
z těchto cifer čísel, která jsou:
a) pětimístná, sudá
b) pětimístná, končící dvojčíslím 21
c) pětimístná, menší než 30000
d) trojmístná lichá
e) čtyřmístná, větší než 2000
f) dvojmístná nebo trojmístná
Řešení:
ad a)
Sudá - to v tomto případě znamená, že končí ciframi 2 nebo 4 (XXXX2, XXXX4) tzn. dvě možnosti. Na zbývajících čtyřech pozicích permutují zbývající čtyři cifry,
takže výsledek:
a = 2.P(4) = 48
ad b)
Máme číslo XXX21. Tedy na třech pozicích permutují tři cifry:
b = P(3) = 6
ad c)
Menší než 30000, to jsou čísla začínající ciframi 1 nebo 2, tedy dvě možnosti. Na
zbývajících čtyřech pozicích permutují zbývající čtyři cifry:
c = 2.P(4) = 48
ad d)
Lichá, tedy končí ciframi 1, 3, 5 - tři možnosti. Na zbývajících dvou pozicích se
mohou vyskytovat některé ze zbývajících čtyř cifer, přičemž záleží na pořadí - jedná
se o variace druhé třídy ze čtyř prvků.
d = 3.V2(4) = 36
ad e)
obdobně jako u předchozích:
e = 4.V3(4) = 96
ad f)
f = V2(5) + V3(5) = 80

-9-

Pravděpodobnost a statistika

Kombinatorika

Příklad 1.4.2. Kolik různých státních poznávacích značek OSB XX-XX existuje s aspoň
dvěmi trojkami?
Řešení:

Aspoň dvě trojky, to jsou 2, 3 nebo 4 trojky. Začneme nejjednodušší možností:

4 trojky:
Tzn. jediná možnost OSB 33-33, takže x4 = 1
3 trojky:
Existují 4 možnosti, jak seskládat tři trojky na čtyřech pozicích (333X, 33X3, 3X33,
X333). Obecně to lze vyjádřit jako počet permutací 4 prvků s opakováním, přičemž
trojka se opakuje třikrát:
P* ( 4 ) =

4!
=4
3!

Dále existuje 9 možností (zbývajících devět cifer), které mohou být na čtvrté pozici.
Obecně lze vyjádřit např. jako počet variací první třídy z devíti prvků:
V1(9) = 9
Takže výsledný počet pro 3 trojky: x3 = P*(4).V1(9) = 4.9 = 36
P

2 trojky:
Existuje opět P*(4) možností, jak seskládat dvě trojky na čtyři pozice, přičemž
P

tentokrát se trojka opakuje dvakrát a zbývající dvě pozice nerozlišujeme mezi sebou,
takže se také dvakrát opakují (33XX, 3X3X, 3XX3, X33X, X3X3, XX33):
P* ( 4 ) =

4!
=6
2!.2!

Na zbývajících dvou pozicích se může střídat zbývajících devět cifer, přičemž v dané
dvojici záleží na pořadí cifer a cifry se mohou i opakovat. To se dá vyjádřit jako počet
variací druhé třídy z devíti prvků s opakováním:
V2*(9) = 92 = 81
Takže výsledný počet pro 2 trojky: x2 = P*(4).V2*(9) = 6.81 = 486
P

Tzn., že počet státních poznávacích značek OSB XX-XX s aspoň dvěmi trojkami je:
x = x4 + x3 + x2 = 1 + 36 + 486 = 523

- 10 -

Pravděpodobnost a statistika

Kombinatorika

Úlohy k samostatnému řešení

1.1. Zjednodušte a vypočtěte:

⎛ 4⎞ ⎛6⎞ ⎛7⎞
⎜⎜ ⎟⎟ + ⎜⎜ ⎟⎟ − ⎜⎜ ⎟⎟ =
⎝ 2⎠ ⎝ 2⎠ ⎝ 2⎠
⎛6⎞ ⎛6⎞ ⎛7⎞
⎜⎜ ⎟⎟ + ⎜⎜ ⎟⎟ + ⎜⎜ ⎟⎟ =
⎝3⎠ ⎝ 4⎠ ⎝5 ⎠

(n + 3)! + (n + 1)! − 2(n + 2)! =
(n + 1)! (n − 1)!
n!
1
3
n2 − 4
−
−
=
n! ( n + 1)! ( n + 2)!
(n + 2)! 2( n + 1)!
n!
−
+
=
( n − 1)! ( n − 2)!
n!

⎛ x + 2 ⎞ ⎛ x + 3⎞
⎟⎟ = 64
⎜⎜
⎟⎟ + ⎜⎜
⎝ x ⎠ ⎝ x +1⎠
⎛ x + 3⎞ ⎛ x + 2 ⎞ ⎛ x + 4 ⎞
⎟⎟ = 75
⎜⎜
⎟⎟ − 2⎜⎜
⎟⎟ + 3⎜⎜
⎝ x + 1 ⎠ ⎝ x ⎠ ⎝ x + 2⎠
1.2. Kolik třítónových akordů je možné zahrát z 8 tónů?
1.3. Kolik různých optických signálů je možno dát vytahováním 5 různých barevných

vlajek, je-li vždy všech pět vlajek nahoře?
1.4. Zjistěte, kolik existuje různých kvádrů, pro něž platí, že délka každé jejich hrany je

přirozené číslo z intervalu 2,15 .
1.5. V obchodě mají tři druhy bonbónů v sáčcích po 100g. Kolika způsoby může zákazník

koupit 1 kg bonbónů?
1.6. Kolik různých státních poznávacích značek z jedné série existuje s aspoň dvěma

trojkami?
1.7. Ze 7 prvků bylo vytvořeno 2401 variací s opakováním stejné třídy. Kolik prvků

obsahuje jedna variace?
1.8. Jsou dány cifry: 1, 2, 3, 4, 5. Cifry nelze opakovat. Kolik je možno vytvořit z těchto

cifer čísel, která jsou
a) pětimístná, sudá
b) pětimístná, končící dvojčíslím 21

- 11 -

Pravděpodobnost a statistika

Kombinatorika

c) pětimístná, menší než 30 000
d) trojmístná, lichá
e) čtyřmístná, větší než 2000
f) čtyřmístná, začínající cifrou 2
g) čtyřmístná, sudá nebo končící cifrou 3
h) dvojmístná nebo trojmístná
1.9. Jsou dány cifry: 0, 1, 2, 3, 4. Splňte úkoly minulé úlohy (1.8.) tak, že cifry se nesmí

opakovat a číslo nemůže začínat nulou.
1.10. Kolik prvků obsahuje množina všech pěticiferných přirozených čísel?
1.11. Kolik různých značek teoreticky existuje v Morseově abecedě, sestavují-li se tečky a

čárky do skupin po jedné až pěti?
1.12. Kolik prvků dá 120 kombinací druhé třídy s opakováním?
1.13. Kolik je dáno prvků, jestliže variací třetí třídy z nich utvořených je pětkrát více než

variací druhé třídy?
1.14. Z kolika prvků lze vytvořit 90 variací druhé třídy?
1.15. Z kolika prvků lze vytvořit 55 kombinací druhé třídy?
1.16. Zmenší-li se počet prvků o dva, zmenší se počet permutací čtyřicetdvakrát. Určete

počet prvků.
1.17. Z kolika prvků lze vytvořit padesátkrát více variací třetí třídy než variací druhé třídy?
1.18. Zvětší-li se počet prvků o dva, zvětší se počet kombinací druhé třídy o 17. Určete počet

prvků.
1.19. Zvětší-li se počet prvků o 8, zvětší se počet kombinací druhé třídy jedenáctkrát. Určete

počet prvků.
1.20. Zmenší-li se počet prvků o 1, zmenší se počet permutací z těchto prvků desetkrát.

Určete počet prvků.
1.21. Kolik permutací z n prvků a1, a2, …, an obsahuje prvek a1 na prvé pozici.?
1.22. V prodejně si můžete vybrat ze sedmi druhů pohlednic. Kolika způsoby lze koupit

a) 10 pohlednic,
- 12 -

Pravděpodobnost a statistika

Kombinatorika

b) 5 pohlednic,
c) 5 různých pohlednic?
1.23. V knihkupectví prodávají 10 titulů knižních novinek. Kolika způsoby lze koupit

a) 4 knižní novinky,
b) 5 různých knižních novinek?
1.24. Na hokejovém turnaji, kterého se účastní 8 družstev, sehraje každý tým s ostatními

právě 1 utkání. Kolik zápasů bude celkem sehráno?
1.25. Z 5 bílých a 4 červených kuliček tvoříme trojice tak, aby v každé trojici byly vždy 2

bílé a 1 červená kulička.. Kolik trojic splňujících tuto podmínku lze vytvořit?
1.26. Hokejový tým odjel na OH s 23 hráči, a to s 12 útočníky, 8 obránci a 3 brankáři. Kolik

různých sestav může trenér teoreticky vytvořit?
1.27. Kolika přímkami lze spojit 7 bodů v rovině, jestliže

a) žádné tři z nich neleží v přímce,
b) tři z nich leží v jedné přímce?
1.28. Kolik kružnic je určeno 10 body v rovině, jestliže žádné tři z nich neleží na přímce a

žádné čtyři z nich neleží na kružnici?
1.29 Kolik různých hodů můžeme provést

a) dvěma,
b) třemi různobarevnými kostkami?
1.30. V turistickém oddílu "Hbitý svišť" je 10 dívek a 8 chlapců. Určete, kolika způsoby

mohou sestavit volejbalový tým (má šest členů), ve kterém budou hrát
a) právě dvě dívky.
b) maximálně dva chlapci?
1.31. Kolik prvků obsahuje množina všech pěticiferných přirozených čísel?
1.32. Deset přátel si vzájemně poslalo pohlednice z prázdnin. Kolik pohlednic celkem

rozeslali?
1.33. Kolikrát více je variací k-té třídy z n prvků než kombinací k-té třídy z těchto prvků?
1.34. V plně obsazené lavici sedí 6 žáků a, b, c, d, e, f.

a) Kolika způsoby je lze přesadit?
- 13 -

Pravděpodobnost a statistika

Kombinatorika

b) Kolika způsoby je lze přesadit tak, aby žáci a, b seděli vedle sebe?
c) Kolika způsoby je lze přesadit tak, aby žák c seděl na kraji?
d) Kolika způsoby je lze přesadit tak, aby žák c seděl na kraji a žáci a, b seděli vedle
sebe?
1.35. Student má v knihovně 4 různé učebnice pružnosti, 3 různé učebnice matematiky a 2

různé učebnice angličtiny. Kolika způsoby je lze seřadit, mají-li zůstat učebnice
jednotlivých oborů vedle sebe?
1.36. Kolika způsoby lze rozdělit 8 účastníků finále v běhu na 100 m do 8 drah?
1.37. Kolik různých permutací lze vytvořit použitím všech písmen slova

a) statistika,
b) matematika?
1.38. Kolik různých signálů je možno vytvořit použitím pěti různobarevných praporků,

použijeme-li
a) pouze 3 praporky,
b) 2 praporky?
1.39. Četa vojáků má vyslat na stráž 4 muže. Kolik mužů má četa, je-li možno úkol splnit

210 způsoby?
1.40. Kolik úhlopříček má konvexní n-úhelník?
1.41. V zásobníku je 7 ostrých a 3 slepé náboje. Určete, kolika způsoby lze namátkou ze

zásobníku vyjmout 5 nábojů, z nichž alespoň 3 jsou ostré.
1.42. Kolika způsoby je možno na čtvercové šachovnici s 64 poli vybrat 3 pole tak, aby

všechna tři pole neměla stejnou barvu?
1.43. Kolika způsoby je možno na šachovnici s 64 poli vybrat 3 pole tak, aby všechna

neležela v jednom sloupci?
1.44. V prostoru jsou dány 2 mimoběžky a, b. Na přímce a je dáno m různých bodů A1, …

Am, na přímce b n různých bodů B1, …, Bn. Určete počet všech čtyřstěnů, jejichž
všechny vrcholy leží na přímkách a, b, a to v bodech Ai, Bj.

- 14 -

Pravděpodobnost a statistika

Kombinatorika

Výsledky úloh k samostatnému řešení

1.1. 0, 56, 2, 0, 2, 6, 4

1.23. C4(13); C5(10)

1.2. 56

1.24. 28

1.3. 120

1.25. 40

1.4. 560

1.26. 18 480

1.5. 66

1.27. 21; 19

1.6. 523

1.28. 120

1.7. 4

1.29. 36; 216

1.8. 48, 6, 48, 36, 96, 24, 72, 80

1.30. 3150; 8106

1.9. 60, 4, 48, 18, 72, 24, 78, 64

1.31. 90 000

1.10. 90 000

1.32. 90

1.11. 62

1.33. k!

1.12. 15

1.34. 720; 240; 240; 96

1.13. 7

1.35. 1 728

1.14. 10

1.36. 40 320

1.15. 11

1.37. 75 600 , 151200

1.16. 7

1.38. 60; 20

1.17. 52

1.39. 10

1.18. 8

1.40. n/2*(n-3)

1.19. 4

1.41. 231

1.20. 10

1.42. 31 744

1.21. (n-1)!

1.43. 41 216

1.22. C10(16); C5(11); 21

1.44. C2(m).C2(n)

- 15 -

