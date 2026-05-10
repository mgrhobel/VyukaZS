---
title: "Elaborát.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/petr/Elaborát.doc"
date: 2009-04-29
type: DOC
---

**Elaborát**

\

1\. **Zalezi, zda se rodicovsky proces z volani fork vrati drive nez
potomek?**

Ne

2\. **Zalezi na poradi procesu pri vstupu do cyklu?**

Ano

3\. **Popiste synchronizaci procesu pri cinnosti pres obe roury.**

Výstup master se přesměruje na vstup slave.

Výstup slave se přesměruje na vstup master.

4\. **Napiste poradi vykonavani cinnosti read, write obou procesu v
obou**

**rourach?**

read slave

write master

read master

write slave

\

5\. **Popiste ukonceni procesu**

Ukončení procesu potomek se provede na základě splnění podmínky o
naplnění bufferu.

\

6\. **Co by se stalo, kdyby potomek zapisoval do roury po tom,**

**co rodic skoncil?**

Potomek by zapisoval do roury, která by se postupně zaplnila a
nedocházelo by k odběru procesem master. Nastala by chyba.

\

7\. **Proc je zadouci(nutne) uzavrit nepotrebne deskriptory?**

\- systemove hledisko(tabulka otevrenych souboru procesu)

\- hlediska dalsiho fork, exec

\- hledisko funkcni

\

Ze systémového hlediska: Potomek by zdědil deskriptory, které by
odkazovaly na procesy, které by byly ukončeny.

Hledisko dalšího fork: Potomek by zdědil deskriptory, které by
odkazovaly na procesy, které by byly ukončeny.

Hledisko funkční: Z heldiska funkčnosti programu nemá uzavření
deskriptorů u rodiče význam. Jedná se spíše o programátorskou čistotu
kódu.

\

8\. **Co se stane, kdyz potomek neuzavre deskriptor zapisu do roury
to_slave?**

\

Otevřený deskriptor to slave[\[1\], j]{lang="en-US"}ádro proto
předpokládá, že se bude ještě do bufferu zapisovat. Proto nechává
puštěný proces potomek, i když je podmínka pro jeho ukončení splněna.

\

9\. **Co se stane, kdyz potomek neuzavre deskriptory zapisu do roury
to_master?**

\

Na funkci programu nemá neuzavření deskriptorů při zápisu do roury
to_master vliv.

\

\
