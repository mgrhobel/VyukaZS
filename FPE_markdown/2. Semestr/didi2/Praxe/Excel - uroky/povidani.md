---
title: "povidani.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/didi2/Praxe/Excel - uroky/povidani.doc"
date: 2009-04-29
type: DOC
---

Funkce PLATBA počítá splátky, které jsou potřeba k tomu, abyste snížili
postupně určitou

částku (souč_hod) na nulu nebo na nějakou jinou částku (bud_hodn).

Syntaxe je následující:

\

PLATBA(**sazba**;**pper**;**souč_hod**;bud_hod;typ)

\

\

V našem příkladě si chcete koupit auto za 640 000 Kč a potřebujete
vypočítat, jaké budou

měsíční splátky. Máte vlastní prostředky 80 000 Kč a prodejce vám nabízí
splátkový prodej

na 4 roky a úrok 2,1% (viz obrázek 11.7).

=PLATBA(0,021/12;4\*12;560000;0;0)

\

Vzorec vrací 12 173,73 Kč. Takže pokud utáhnete takovou splátku každý
měsíc, můžete

\

vypůjčených 560 000 Kč vrátit v 48 splátkách.

\
