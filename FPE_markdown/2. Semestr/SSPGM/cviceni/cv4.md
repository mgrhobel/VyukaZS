---
title: "cv4.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/cviceni/cv4.txt"
date: 2009-02-19
type: TXT
---

Cviceni SSPGM 4. tyden

1. Vypiste posloupnost fork pri vasem prihlaseni pres telnet
a zduvodnete

2. Program p11.c (/home/tmp/p11.c) prelozte (gcc p11.c -o p11),
analyzujte a zduvodnete chovani viz vypisy, zdrojak.
Oznacte, ktery proces co vypisuje.
Urcete matematicky vztah mezi poctem potomku a volanim fork.
Zvyste podobne pocet forku na 4 a analyzujte.
Navod:
a) cat p11.c >p11.1
b) spustte program p11 >p11.3 a zaroven na druhem terminalu ps -aef |grep p11 >p11.2
c) cat p11.1 >p11.txt; cat p11.2 >>p11.txt; cat p11.3 >>p11.txt
Vysledek podobny viz p11.txt na webu. Vysledky odevzdejte v pisemne podobe. 

3. Napiste program pro uplne osetreni volani jadra fork
(osetreni chyb). Pouzijte knihovny errno.h a externi
promenne int errno.

4. Napiste program pro analyzu ukonceni potomka
- exitem(n)
- signalem (napr. SIGINT)
Pouzijte knihovnu signal.h

5. Analyzujte program p5.c (/home/tmp/p5.c)

