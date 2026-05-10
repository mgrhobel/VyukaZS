---
title: "t_prubHobel.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/testy/t_prubHobel.doc"
date: 2009-05-03
type: DOC
---

SSPGM -- test č. 2

\

1.  

Co je fork, popište, deklarujte (3)

\

2.  

Napište program v jazyce C pro kompletní ošetření forku

Použijte přepínač switch (3)

\

3.  

Co je rodič -- potomek v hierarchii procesů, v čem se liší,

v čem se shodují (3)

4.  

Popište adresový prostor procesu (3)

5.  

Co se stane, když v hierarchii procesů rodič - potomek,

a\)

Rodič skončí a potomek pokračuje

b\)

Potomek skončí a rodič pokračuje

\

Popř. dokladujte ukázkou při spuštění procesů (3+3(c))

\

\

\

\

1\]

Příkaz, který vytvoří nový proces (potomek), který je kopií procesu,
který jej zavolal, spustil (rodič). Tzn. Vytvoří se kopie původního
(rodičovského) procesu, která je téměř identická s rodičem.

\

Běh programu pokračuje ve dvou větvích. Na základě návratové hodnoty je
možné rozlišit, ve které větvi se program nachází.

\

\

2\]

**#include \<stdio.h\>**

**#include \<sys/types.h\>**

\

**int main(void)**

**{ pid_t pid;**

\

**pid = fork();**

\

**switch (pid) {**

\

**case -1:**

**fprintf(stderr,**

**\"chyba ve forku\\n\");**

**//exit(1);**

**break;**

\

**case 0:**

**printf(\"vytvoren proces potomek\\n\");**

**//exit(0);**

**break;**

\

**default:**

**printf(\"spusten proces rodic\\n\", pid);**

**//exit(0);**

**break;**

**}**

**}**

\

3\)

Hierarchie procesů lze vypsat příkazem pstree.

\

Rodič v hierarchii procesů -- se nachází vždy o jednu úroveň výš, než
daný proces.

\

Potomek v hierarchii procesů -- se nachází vždy o jednu úroveň níže, než
daný proces. Přitom platí, že jeden rodič může mít více potomků.

\

Liší se:

Číslem procesu.

Mohou mít různý zdroje (kód a data) - potomek a rodič jsou samostatné
procesy, které nic nesdílí.

\

Shodují se:

Mohou mít stejné zdroje (kód a data) -- potomek a rodič sdílejí zdroje
původně vlastněné rodičem

Odkazem na otevřené file deskriptory.

\

\

4\)

Adresový prostor procesu

Je sada paměťových stránek, které jádro označilo pro využiti daným
procesem. Obsahuje

kód a knihovny, které proces provozuje, proměnné procesu, jeho
zásobníky, které jádro potřebuje během doby, kdy proces běží.

\

Každý proces má svůj vlastní adresový prostor. Ke komunikace mezi
procesy je třeba použít např. roury.

\

5\)

a\) Rodič skončí a potomek pokračuje

Potomek je přirazen pod proces init, který jej zdědil. PPID potomka = 1.
Ten jej po ukončení odstraní z pamětí.

\

b\) Potomek skončí a rodič pokračuje

\

Pokud přímo rodič nečeká ve stavu WAIT na ukončení potomka, pak -\>

Potomek už prakticky neexistuje (má už uzavřené deskriptory a
odalokovanou paměť), ale je stále evidován systémem. Dostal se do stavu
mátoha.

\

Příklad

\

\
