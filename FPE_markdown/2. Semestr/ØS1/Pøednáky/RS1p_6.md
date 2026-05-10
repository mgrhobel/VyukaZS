---
title: "RS1p_6.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/ØS1/Pøednáky/RS1p_6.pdf"
date: 2008-08-24
type: PDF (text-based)
---

4.2 Algebra blokových schémat
Blokové schéma slouží ke znázornění struktury a funkce regulačního obvodu. Cílem je určení
výsledného přenosu. Pravidla podle nichž vytváříme výsledný přenos z výchozího blokového
schématu nazýváme blokovou algebrou.
Sériové spojení

u (t )

u1

F1 ( p )

y1 = u 2

F2 ( p )

y2

Platí: u = u1
y = yn
u i +1 = y i

i = 1, 2 K n − 1

Z definice přenosu platí pro jednotlivé bloky:
Y1 ( p ) = F1 ( p ) ⋅ U 1 ( p ) = F1 ( p ) ⋅ U ( p )
…
Y ( p ) = Yn ( p ) = Fn ( p ) ⋅ U n ( p ) = Fn ( p ) ⋅ Yn -1 ( p )
Postupným dosazováním:
F ( p) =

n
Y ( p)
= F1 ( p ) ⋅ F2 ( p ) ⋅ KK ⋅ Fn ( p ) = ∏ Fi ( p )
U ( p)
i =1

Pořadí bloků nemá vliv na výsledný přenos.

1

un

Fn ( p )

yn

y (t )

Paralelní spojení

u (t )

u1

F1 ( p )

y1

u2

F2 ( p )

y2

Σ
un

Fn ( p )

yn

u = u1 = u 2 = ... = u n
n

y = y1 + y2 + ... + yn = ∑ yi
i =1

n

Y ( p ) = ∑ Yi ( p ) = [F1 ( p ) + F2 ( p ) + ... + Fn ( p )]× U ( p )
i =1

F ( p) =

n
Y ( p)
= F1 ( p ) + F2 ( p ) + ... + Fn ( p ) = ∑ Fi ( p )
U ( p)
i =1

Antiparalelní spojení
(zpětnovazební zapojení)

Platí:
u1 = u ± y2
y = y1 = u2

Y ( p) = F1 ( p) × U1 ( p) = F1 ( p)[U ( p) ± Y2 ( p)] =
= F1 ( p)[U ( p) ± F2 ( p) × Y ( p)] ⇒

⇒ Y ( p) × [1 m F1 ( p) × F2 ( p)] = F1 ( p) × U ( p) ⇒
⇒ F ( p) =

Y ( p)
F1 ( p )
=
U ( p) 1 m F1 ( p ) × F2 ( p )
2

y (t )

Pravidlo pro stanovení celkového přenosu „složitého“ obvodu:

Do čitatele přenos přímé cesty. Do jmenovatele jedničku a pak se přičtou (pro kladnou vazbu
odečtou) přenosy všech zpětnovazebních cest (smyček).
F ( p) =

F1 F2
1 + F2 − F1 F2 F3 + F1 F2 F4

3

