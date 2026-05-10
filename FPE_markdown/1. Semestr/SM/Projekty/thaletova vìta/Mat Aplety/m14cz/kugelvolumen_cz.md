---
title: "kugelvolumen_cz.htm"
source: "/mnt/f/git/mgr/FPE_navazujici/1. Semestr/SM/Projekty/thaletova vìta/Mat Aplety/m14cz/kugelvolumen_cz.htm"
date: 2006-05-06
type: HTML
---

# Výpoèet objemu koule [(Cavalieriùv princip)]{.small}

Pro výpoèet objemu polokoule o polomìru *r* (v apletu vlevo nahoøe)
použijeme \"náhradní\" tìleso (vpravo nahoøe), u kterého je výpoèet
objemu jednodušší: Zde se jedná o rotaèní válec s polomìrem podstavy *r*
a výškou také *r*, ze kterého je vyjmut rotaèní kužel také s polomìrem
podstavy *r* a výškou *r*.

Lze nyní ukázat, že polokoule a \"náhradní\" tìleso mají stejný objem.
Pøedstavme si, že obì tìlesa øízneme rovinou rovnobìžnou s podstavou
tìlìsa. V pøípadì polokoule vznikne jako plocha øezu kružnice (zelená),
v pøípadì \"náhradního\" tìlesa mezikruží (oranžové). Vzdálenost *h*
roviny øezu od roviny podstavy je v každém pøípadì hodnota mezi *0* a
*r*. Pomocí pohybu myši (se stisknutým tlaèítkem) lze v apletu tuto
vzdálenosti *h* mìnit. V dolní èásti jsou pak vidìl obì plochu øezu
ve skuteèné velikosti.

Známe-li *r* a *h*, dokážeme obì plochy øezu vypoèítat.

Obsah zelené plochy øezu nejdøíve vyjádøíme S~1~  =  s^2^p. Nyní si
uvìdomíme, že trojúhelník vlevo nahoøe v apletu je pravoúhlý. Dosazením
do Pythagorovy vìty s^2^ + h^2^  =  r^2^, dostáváme
s^2^  =  r^2^ - h^2^. Z toho tedy plyne, že obsah zelené plochy je
S~1~  =  (r^2^ - h^2^) p.

Ještì jednodušší je výpoèet oranžovì vyznaèené plochy øezu: Vezme si
obsah vnìjší kruhové plochy bez obsahu vnitøní kruhové plochy a tím
dostaneme S~2~  =  r^2^p - h^2^p  =  (r^2^ - h^2^) p.

Obsahy obou ploch øezu se shodují a to pro každou hodnotu *h* mezi *0* a
*r*. Podle *Cavalieriho principu* se musí tedy také shodovat i objemy
obou tìles - polokoule a \"náhradního\" tìlesa.

V~polokoule~  =  V~\"náhr.\" tìleso~  =  V~Válec~ - V~Kužel~  =  r^2^p · r - (1/3) r^2^p · r  =  (2/3) r^3^p

Jestliže chceme vypoèítat objem celé koule, je nutné tento výsledek
ještì zdvojnásobit.\
Definitivní vzorec tedy zní:

::: {#Abstand}
 
:::

+-----------------------------------+-----------------------------------+
| Objem koule s polomìrem r:        | +------------------------------+  |
|                                   | | +-------+-------+-------+    |  |
|                                   | | | V =   | 4     |  p    |    |  |
|                                   | | |       |       |  r^3^ |    |  |
|                                   | | +-------+-------+-------+    |  |
|                                   | | |       | ---   |       |    |  |
|                                   | | +-------+-------+-------+    |  |
|                                   | | |       | 3     |       |    |  |
|                                   | | +-------+-------+-------+    |  |
|                                   | +------------------------------+  |
+-----------------------------------+-----------------------------------+

::: {#Abstand}
 
:::

::: {#Abstand}
 
:::

------------------------------------------------------------------------

::: {#Abstand}
 
:::

  --------------------------------------------------------------------
  [![Mathematik](../m14_gifs/javamath.gif){hspace="10"}](index.html)
  [Matematické aplety](index.html)
  --------------------------------------------------------------------

URL: www.walter-fendt.de/m14cz/kugelvolumen_cz.htm\
© Walter Fendt, 4. September 2000\
© Pøeklad do èeštiny: Miroslav Panoš, Gymnázium J. Vrchlického, Klatovy\
Poslední zmìna: 14. bøezna 2006
