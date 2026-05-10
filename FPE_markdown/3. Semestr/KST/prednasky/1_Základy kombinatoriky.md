---
title: "1_Základy kombinatoriky.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/1_Základy kombinatoriky.pdf"
date: 2009-12-27
type: PDF (text-based)
---

1.1 Základní pojmy kombinatoriky
V této části budeme předpokládat, že veškeré množiny , s kterými budeme pracovat
jsou konečné.
Definice 1.1
Nechť množina A má celkem n > 0 prvků. Permutací nazveme uspořádání prvků
množiny A tak, že v tomto uspořádání je každý prvek uveden právě jednou. Počet
takovýchto uspořádání nazýváme počtem permutací ( nebo počtem permutací bez
opakování ) množiny A. Tento počet P(n) = n! ( součin všech přirozených čísel od 1
do čísla n ).
Příklad 1.1
Ve skupině 6 studentů chceme zjistit počet všech možných pořadí přihlášení na
zkoušku.
Řešení:
Student se na zkoušku hlásí 1x tedy hledáme počet permutací tedy P(6) = 6! = 120.
Studenti se můžou přihlásit celkem 120 možnými způsoby.
Definice 1.2
Nechť množina A má celkem n > 0 prvků. Permutací s opakováním nazveme
uspořádání prvků množiny A tak, že v tomto uspořádání se každý prvek může
opakovat 0 až n krát. Celkový počet prvků takovéhoto uspořádání je roven n. Počet
takovýchto uspořádání nazýváme počtem permutací s opakováním množiny A. Tento
počet P’(n) = nn .
Příklad 1.2
Podržme zadání stejné jako v předchozím případu. Zjistěme jaký počet různých
uspořádání je možné nalézt za těchto podmínek.
Řešení :
Podle předchozího je tento počet roven P’(6) = 66 = 46 656. V tomto případě se
studenti mohou přihlásit celkem 46 656 způsoby.
Definice 1.3
Nechť množina A má celkem n > 0 prvků. Variací k – té třídy bez opakování
nazveme libovolnou k člennou podmnožinu V množiny A takovou, že v tomto
uspořádání je každý prvek uveden nejvýše jednou a dále v daném uspořádání záleží na
pořadí prvků. Počet takovýchto uspořádání nazýváme počtem Variací k – té třídy bez
opakování množiny A. Tento počet je roven
n!
Vkn =
= n.(n − 1)...(n − k + 1)
(n − k )!
Příklad 1.3
Určete počet všech přirozených čísel menších než 500, v jejichž zápisu jsou pouze
číslice 4, 5, 6, 7, a to každá nejvýše jednou.
Řešení:
Počet jednomístných přirozených čísel je roven počtu variací první třídy ze čtyř prvků;
pro dvojmístná přirozená čísla je počet roven variacím druhé třídy ze čtyř a konečně
jediná trojmístná přirozená čísla , která splňují zadání jsou čísla začínající 4, jejich

počet je tedy roven počtu variací bez opakování druhé třídy ze čtyř prvků. Celkově
4!
4!
3!
x = V14 + V24 + V23 =
+
+
= 4 + 12 + 6 = 22
(4 − 1)! (4 − 2)! (3 − 2)!
tedy bude
.
Podmínky splňuje 22 přirozených čísel.

Definice 1.4
Nechť množina A má celkem n > 0 prvků. Variací k – té třídy s opakování nazveme
libovolné k členné uspořádání prvků množiny A takové, že v tomto uspořádání záleží
na pořadí prvků a každý prvek uveden nejvýše jednou. Počet takovýchto uspořádání
nazýváme počtem Variací k – té třídy s opakování množiny A. Tento počet je roven
n

V ´' k = n k

Příklad 1.4
Předpokládejme, že první dva znaky SPZ automobilu v naší republice se skládají ze
dvou znaků abecedy, a zbylých pět členů kombinace jsou čísla. Určete počet Všech
SPZ.
Řešení:
První část se skládá z dvojice písmen ( je jich 26 ), která mohou libovolně
opakovat, přičemž záleží na pořadí ( jde o uspořádanou dvojici ). Celkově jich je tedy
jako počet variací s opakováním druhé třídy z 26 prvků. Druhá část SPZ je tvořena
uspořádanou pěticí čísel, jejich počet je roven počtu variací s opakováním 5 třídy z 10
prvků.
Celkový počet značek je proto roven :
10
2
5
x = V ' 26
2 .V '5 = 26 .10 = 67600000

Definice 1.5
Nechť množina A má celkem n > 0 prvků. Kombinací k – té třídy bez opakování
nazveme libovolnou k člennou podmnožinu V množiny A takovou, že v tomto
uspořádání je každý prvek uveden nejvýše jednou a dále v daném uspořádání nezáleží
na pořadí prvků. Počet takovýchto uspořádání nazýváme počtem kombinací k – té
třídy bez opakování množiny A. Tento počet je roven
C kn = ( nk ) =

n!
k!.(n − k )!

Příklad 1.5
Zjistěte počet možností výběru správné šestice při hře sportka.
Řešení:
Celkový počet těchto šestic je roven počtu kombinací šesté třídy z 49 prvků.
49!
49!
49.48.47.46.45.44
x = ( 649 ) =
=
=
= 49.4.47.46.3.11 = 13 983 816
6!.(49 − 6)! 6!.43!
1.2.3.4.5.6

.

Definice 1.6
Nechť množina A má celkem n > 0 prvků. Kombinací k – té třídy s opakováním
nazveme libovolnou k člennou podmnožinu V množiny A takovou, že v tomto
uspořádání je každý prvek uveden nejvýše k krát a dále v daném uspořádání nezáleží
na pořadí prvků. Počet takovýchto uspořádání nazýváme počtem kombinací k – té
třídy s opakování množiny A. Tento počet je roven

 n + k −1  (n + k − 1)!
=
C ' nk + k −1 = 

 k  k!.(n − 1)!

Příklad 1.6
Hra domino představuje soubor kostek , z nichž je každá kostka rozdělena na dvě
poloviny a každá polovina je samostatně označena body 0 až 8. Každá kostka se ve
hře vyskytuje pouze jednou. Určete počet kostek jedné hry.
Řešení:
Jde o kombinace druhé třídy s opakováním z devíti prvků ( nezáleží nám na pořadí
výběru dané dvojice , prvky se mohou opakovat a celých čísel od 0 do 8 je devět ).
Podle výše uvedeného vztahu je počet kostek jedné hry roven
 9+ 2−1   10  10!
= =
C ' = 
= 45.

 2   2  2!.8!
9
2

