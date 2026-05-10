---
title: "cv11_Hobel.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/moje prace/cv11_Hobel.txt"
date: 2009-04-29
type: TXT
---

1. NE.

2. ANO.

3. 
Vystup Master roury je treba presmerovat na vstup Slave roury.
Vystup Slave roury je treba presmerovat na vstup Master roury.


4. 1)read slave 2)write master 3)read master 4)write slave 

5. 
Potomka je nutne ukoncit.
Proces je ukoncen, pokud jsou ukonceny vsechny deskriptory roury, se kterou prislusny proces pracuje.

6. Potomek bude zapisovat do roury, ta se naplni a nedocházelo by k odbìru procesem Master, nastane CHYBA.

7. Systémové hledisko - 
   Fork- Aby šel vytvoøit proces potomek z pøíslušného procesu.
   Funkcni hledisko - Aby pøíslušný proces skonèil.

8. Neukonci se ani master ani slave proces.

9. Proces slave se neukonci, zustane v behu. Ukonci se pouze master proces.
