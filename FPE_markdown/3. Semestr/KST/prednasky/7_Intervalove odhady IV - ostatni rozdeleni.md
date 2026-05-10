---
title: "7_Intervalove odhady IV - ostatni rozdeleni.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/prednasky/7_Intervalove odhady IV - ostatni rozdeleni.pdf"
date: 2009-12-27
type: PDF (text-based)
---

3.3 Konstrukce intervalových odhadů pro případ Exponenciálního
rozdělení
Při konstrukci intervalových odhadů pro tento typ rozdělení budeme důsledně
vycházet z následujícího tvrzení.
Věta 3.6
Nechť náhodný výběr pochází z populace popsané pomocí exponenciálního rozdělení
s parametry 0 a δ potom je náhodná veličina

2.n. X

(3.32)

δ
rozdělení χ 2 ( 2.n ) ( tedy chi –kvadrát s 2n stupni volnosti ).

Větu dokazovat nebudeme, odkazujeme např. na [1] strana .
Pomocí tohoto tvrzení je možno sestrojit oboustranný (1-α)% interval spolehlivosti
parametru δ podle následujícího vztahu

2.n.x

χ α
2

1−

<δ <

2

2.n.x

χ α2

(3.33),

2

kde χ 2 α a χ α2 jsou příslušné kvantily rozdělení chi kvadrát s 2.n stupni volnosti .
1−

2

2

Je – li hodnota prvního parametru A exponenciálního rozdělení X různá od nuly,
nahradíme ji náhodnou veličinou X – A , která je opět exponenciální a navíc má vlastnosti
obsažené ve větě 3.6.
Podobným způsobem můžeme provést i konstrukce levostranných či pravostranných
intervalů spolehlivosti.
Uvedené skutečnosti budeme ilustrovat na konkrétním příkladě.
Příklad 3.7
Doba čekání ve frontě má exponenciální rozdělení s parametrem A = 5 minut .
Sestrojte 95% interval spolehlivosti pro parametr δ , jestliže součet dob čekání náhodně
vybraných 10 klientů byl roven 100 minut.
Řešení :
Nejdříve zjistíme hodnotu x , protože hodnota A = 5 je různá od nuly budeme muset
nejdříve provést posun parametrů. Tedy x = 100 − 10.5 = 50 = 5 , nyní již můžeme dosadit do
10
10
intervalového odhadu (3.33).
2.10.5
2.10.5
<δ <
⇔ 2,92 < δ < 10, 43 .
34, 2
9.59
Podobně bychom mohli konstruovat intervaly spolehlivosti pro další typy rozdělení
např. Poissonovo rozdělení , hypergeometrické a další, pro detaily odkazujeme na [4] .

