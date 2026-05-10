---
title: "deadlock.html"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/unix-lekce/deadlock.html"
date: 2009-05-01
type: HTML
---

# Dead-lock

Dostali jste se už někdy do situace, kdy jste se v úzkých dveřích s
někým potkali, oba jste ustoupili stranou a dávali jste si vzájmeně
přednost? Pak jste zažili dead-lock. Kdyby jeden z vás nezměnil
strategii, čekáte u těch dveří dodnes.

Dead-lock je situace, kdy dva nebo více procesů nemůže pokračovat ve
svém běhu, protože každý z nich čeká na něco, co má udělat další z nich.
Běžným příkladem je např. program, který chce komunikovat se serverem.
Program čeká, že od serveru dostane potvrzovací hlášku o tom, že je
připojen a že může posílat požadavky. Jenže server žádnou takovou zprávu
neposílá a čeká na požadavky ihned. Oba čekají, až jim ten druhý pošle
nějaká data. (Tomuto určitému typu dead-locku se říká „starvation
dead-lock" (hladovění), ačkoli termínem „starvation" je správnější
označovat situaci, kdy program nemůže běžet proto, že nikdy nemá
dostatečně vysokou prioritu, aby mu byl přidělen procesor.) Jiným typem
dead-locku označovaným jako „constipation" (zácpa) je situace, kdy se
proces snaží odeslat data jinému procesu, ale všechny buffery jsou plné,
protože nikdo nic nečte.

Následující sada perlovských skriptů demonstruje vznik dead-locku.
Použity jsou dva perlovské skripty `p1` a `p2`. Skript `p1` otevře
soubor `f1` pro zápis a nastaví na něj blokující zámek pomocí `flock()`.
Voláním `sleep()` se následně simuluje nějaká práce. Poté se otevírá pro
zápis soubor `f2` a nastavuje se na něm zámek. Následně se oba soubory
odemykají a uzavírají. Tento kód je umístěn ve smyčce, čímž se simuluje
častá práce s oběma soubory. Skript `p2` je stejný jako skript `p1` jen
s tím rozdílem, že soubory `f1` a `f2` otevírá a uzamyká v opačném
pořadí.

Pokud spustíte jeden nebo druhý skript, proběhne vše v pořádku. Dokonce
i v případě, že spustíte více instancí stejného skriptu najednou, jak je
demonstrováno v shellovském skriptu `runme`, proběhne vše také bez
závad. (Proč? Protože všechny procesy zamykají soubory ve stejném
pořadí.) Pokud ale spustíte oba skripty najednou (shellovský skript
`runme2`), dojde po nějaké době k dead-locku.

Co se stane, když jeden z procesů násilně ukončíte zasláním SIGKILL?

Ke stažení:

-   Perlovské skripty
    [`p1`](http://labe.felk.cvut.cz/%7Eposik/osa/deadlock/p1) a
    [`p2`](http://labe.felk.cvut.cz/%7Eposik/osa/deadlock/p2).
-   Shellovské dávky
    [`runme`](http://labe.felk.cvut.cz/%7Eposik/osa/deadlock/runme) a
    [`runme2`](http://labe.felk.cvut.cz/%7Eposik/osa/deadlock/runme2).

```{=html}
<!-- -->
```
