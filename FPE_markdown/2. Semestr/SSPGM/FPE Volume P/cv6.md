---
title: "cv6.txt"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/FPE Volume P/cv6.txt"
date: 2006-10-03
type: TXT
---

Cviceni SSPGM 6. tyden



1. Napiste program s vami definovanym handlerem
pro zachytavani signalu SIGINT

- signal SIGINT vysilejte vsem procesum ve skupine odesilatele
- handler deklarujte tez jako externi funkci
- v handleru aktivujte, neaktivujte obsluhu signalu, nastavte default hodnotu

Vysvetlete chovani, ukonceni procesu.

2. Napiste program se zachytavanim signalu ukonceni potomka.

A) uvedomime jadro o handleru pro ukonceni potomka
B) neuvedomime jadro o handleru pro ukonceni potomka

Rodic
 1) standardne ukoncen pres wait
 2) zustava v pause

Potomek po 8 s konci exitem

Handler pro obsluhu signalu bude vypisovat
"Rodic zachytil signal .."


Analyzujte vsechny stavy A1, A2, B1, B2

3. Analyzujte program (proces) p26_1.c pro soubeh zachytavani
signalu SIGINT.
- mente prioritu procesu Rodic a zduvodnete soubehy
- z dalsi konzole vysleme SIGINT procesu potomek - vysvetlete chovani, vypisy procesu
- z dalsi konzole vysleme SIGKILL potomku, SIGKILL rodici
Co ukonci rodice i potomka?
Vyslete signal SIGHUP skupine odesilatele
Zmente chovani SIGINT na default a porovnejte.


