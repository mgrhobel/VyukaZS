---
title: "komentar.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/moje prace/cv9/komentar.txt"
date: 2009-05-10
type: TXT
---

exec pouze na zaklade cesty (napr. /bin/date) a nazvu spousteciho souboru (napr. date) spusti program tak, ze prepise (nikokliv rozdvoji) stavajici proces, prototo je vhodne pro exec vytvorit novy proces pomoci fork.

u4@hana:~/bin> p6
Ne kvì 10 20:19:15 CEST 2009


u4@hana:~> ps -aefl|grep p6
0 S u4       18618  8066  0  78   0 -   353 sigact 20:19 pts/0    00:00:00 p6
0 S u4       18621  8638  0  76   0 -   521 pipe_w 20:19 pts/1    00:00:00 grep 