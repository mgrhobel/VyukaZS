---
title: "8_Intervalove odhady rozdilu.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/8_Intervalove odhady rozdilu.pdf"
date: 2009-12-27
type: PDF (text-based)
---

3.4

Intervaly spolehlivosti pro rozdíl dvou středních hodnot

V další části této kapitoly se budeme zabývat případy dvou nezávislých výběrů a
budeme především nalézat intervaly spolehlivosti pro jejich rozdíl. Nejdříve začneme
nejjednoduššími případy .

3.4.1 Rozptyl hledaných populací je známý a populace jsou normální
Předpokládejme , že jsou známé rozptyly daných populací . Tento případ je v praxi
prakticky vyloučen , přesto ho budeme diskutovat. Známe tedy hodnoty σ 12 a σ 22 . Podle
předchozí kapitoly jsou tedy náhodné veličiny

X 1 − µ1

σ1

N ( 0;1) a

. n1

X 2 − µ2

σ2

N ( 0;1) .

. n2

V tomto okamžiku nás ale zajímá odhad rozdílu neznámých středních hodnot, proto
uvedené vztahy přepočteme takto:

( X − X ) -(µ − µ )
1

2

1

σ 12

σ 22

n1

+

N ( 0;1)

2

(3.34).

n2

Z takovéhoto vztahu již můžeme provést konstrukci např. oboustranných (1-α)%
intervalů spolehlivosti jako:

( X − X ) - u α . σn + σn < ( µ − µ ) < ( X − X ) + u α . σn + σn
1

2

1-

2

2
1

2
2

1

2

1

2

1

2

1-

2

2
1

2
2

1

2

(3.35),

kde jako obvykle symbol uα znamená α - tý kvantil rozdělení N(0;1). Podobně bychom
mohli odvodit i vztahy pro jednostranné odhady rozdílu středních hodnot.

3.4.2 Rozptyl hledaných populací je neznámý a populace jsou normální
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
Podle tvrzení uvedených v teorii pravděpodobnosti totiž platí:
A1
n
F = 1 F (n1 , n2 ) ,
A2
n2
jsou – li A1 a A2 nezávislé náhodné veličiny postupně typu χ 2 ( n1 ) a χ 2 ( n2 ) .
Zvolíme – li za uvedené náhodné veličiny A1 a A2 , hodnoty výběrových rozptylů , které jsou
typu chí kvadrát získáme:

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

( n1 − 1) .s + ( n2 − 1) .s . 1 + 1
2
1

< ( X1 − X 2 ) + t α .
1-

n1

n1 + n2 − 2

2

(3.40),

2
2

n1

n2

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

3.4.3 Populace jsou popsány jako alternativní ( binomické ) rozdělení
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

p1. (1 − p1 )
n1

+

p2 . (1 − p2 )

(3.42)

n2

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

1
1
+
+u α.
2.n1 2.n2 1− 2

p1. (1 − p1 )
n1

+

p2 . (1 − p2 )
n2

(3.43)

