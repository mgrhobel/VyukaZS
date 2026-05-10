---
title: "cv5.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/FPE Volume P/cv5.txt"
date: 2006-10-03
type: TXT
---

Cviceni SSPGM 5. tyden

1. Dokonceni p11.c

2. Dokonceni p5.c

3. Napiste program s volanim fork()
a osetrenim vsech chybovych stavu a vyuzitim prikazu switch (0 - potomek, default - rodic)

a) potomek pri argc>1

{funkce main(int argc, char *argv[])
kde argc je pocet argumentu prikazove radky, argc=1 ... samotny prikaz bez argumentu, ...
argv[], jednotlive argumenty prikazove radky,
*argv[0] = nazev prikazu, *argv[1] = prvni argument prikazu ... 
}

zustane v nekonecne smycce ( pouzijte napr. prikazu for(;;) )
(ukonceni signalem), pouzijte prikaz kill -2 PID

b) potomek pro argc <= 1 je ukoncen exitem (volani exit(n), int n)

pricemz rodic ceka ve volani jadra wait ( int wait(int *status) ) na ukonceni potomka

Vypiste
- cislo procesu potomka
- navratovou hodnotu ukonceni procesu a to jak signalem tak i exitem

