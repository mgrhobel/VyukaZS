---
title: "proc-bash-perl.html"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/SSPGM/internet/unix-lekce/proc-bash-perl.html"
date: 2009-05-01
type: HTML
---

# Proč se zabývat shellem a perlem?

V čem psát ukázkové skripty na cvičeních?

-   Bash je nejen shell, ale i skriptovací jazyk, a lze v něm vyřešit
    celou řadu úloh. Jeho moc ale spočívá především v kombinaci s mnoha
    systémovými utilitami, jako jsou sed, grep, awk, diff, cmp, atd.
    Základy se naučíme poměrně snadno, protože shell je na Unixech
    všudypřítomný. Je silně spjat s jádrem systému samotného, příkazy
    shellu mají často přímý ekvivalent ve službách jádra.
-   Perl je velice mocný skriptovací jazyk s výbornou podporou
    regulárních výrazů. Programátorům zvyklým na Javu se v něm
    programuje lépe než v shellu, nespoléhá se na externí utility, i
    když v něm jdou snadno použít. Je to vyšší jazyk (např. i s podporou
    OOP), přesto si zachovává blízkost k systému. Většina příkazů Perlu
    má ekvivalenty ve službách jádra.
-   Jazyk C je jazykem, v němž je napsáno samo jádro OS a většina
    systémových utilit. Není ale úplně snadné se jej naučit.
-   Java je šikovný vyšší programovací jazyk, běží ale na Java Virtual
    Machine, která programy efektivně odstiňuje od systému samotného,
    což pro účely našeho předmětu není to pravé ořechové.

Volba tedy padla na bash a hlavně na Perl.

Další důvody, proč volit Perl (David N. Blank-Edelman, Perl for System
Administrators, O´Reilly):

-   Perl vychází z UNIXovských shellů a jazyka C, tj. z nástrojů, na
    které jsou administrátoři zvyklí.
-   Perl je dostupný na valné většině OS, včetně UNIXů, Linuxů, Windows,
    atd.
-   Perl má skvělé nástroje pro práci s textem, pro práci s databázemi a
    pro síťové prostředí.
-   Perl je vhodný pro nejrůznější úpravy na Windowsovských systémech
    (viz [Roth Consulting](http://www.roth.net/perl/scripts/)), kde
    skvěle nahrazuje chybějící skriptovací administrátorský jazyk (pokud
    za něj nepovažujeme Visual Basic, který ovšem není na ostatních
    platformách k dispozici).
