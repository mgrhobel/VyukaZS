---
title: "hobel_P08N0091P.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/SVVT/Toman/hobel_P08N0091P.doc"
date: 2009-12-18
type: DOC
---

![](hobel_P08N0091P_html_53beec22.gif){#Image1 align="left" width="211"
height="105"}\
![](hobel_P08N0091P_html_84a5d263.png){#Image2 align="left" width="169"
height="81"}\
\

\

\

\

\

\

\

\

\

\

\

\

\

\

**KVD/SVVT**

**Diffie-Hellman algoritmus**

\

\

\

\

**Josef Hobel, P08N0091P**

## Princip {#princip .western lang="cs-CZ" align="left" style="line-height: 150%; orphans: 2; widows: 2"}

Diffie-Hellmanův algoritmus slouží k domluvě společného klíče (například
pro symetrickou kryptografii) po nezabezpečeném kanálu (kanál může být
odposloucháván). Tento algoritmus zaručí výměnu společného klíče takovým
způsobem, že pokud bude tuto komunikaci odposlouchávat útočník, tak
nebude schopen klíč na základě odposlechnutých informací zrekonstruovat.

## Zadání {#zadání .western lang="cs-CZ" style="line-height: 150%"}

-   účastnící si zvolí - sdělí - domluví se na číslech m (modulo) a z
    (základ), tyto hodnoty jsou veřejně sdělitelné

-   každý účastník si zvolí svůj exponent e (nesoudělný modulem) --
    tajný

-   každý účastník vypočte šifrovací klíč

## Skupina {#skupina .western lang="cs-CZ" style="line-height: 150%"}

Jiří Vohradský (A), Josef Hobel (B), Miroslav Vild (C) a Zdeněk Kleisner
(D)

## Postup {#postup .western lang="cs-CZ" style="line-height: 150%"}

Čerpali jsme ze zdroje:
http://www.algoritmy.net/article/84/Diffie-Hellman

\

-   Domluvili jsme se na modulu **m = 19** a základu **z = 2**

-   Zvolil jsem si exponent **e = 5**

\

1.  První krok výpočtu vychází ze vzorce \|z^e^\|mod 19, v mém případě
    \|2^5^\|~19~ = 13

2.  Tento výsledek pošlu účastníkovi C a současně přijmu výsledek 4 od
    účastníka A, který opět vložím do vzorce \|4^5^\|~19~ = 17

3.  Tento výsledek pošlu účastníkovi C a současně přijmu výsledek 11 od
    účastníka A, který opět vložím do vzorce \|11^5^\|~19~ = 7

4.  Tento výsledek opět pošlu účastníkovi C a současně přijmu výsledek 1
    od účastníka A, který opět vložím do vzorce \|1^5^\|~19~ = 1

\

Tento výsledek je již konečný, ostatním účastníkům také vyšel výsledek
roven jedné. Vyplývá z toho, že počet výpočtů je roven počtu účastníků
ve skupině.

\

\

***Kontrolní ov***ěř***ení výpo***č***tu***

***e=e1\*e2\*e3\*e4***

**e=2\*5\*3\*6=180**

\

**kde** ***e1,e2,e3, e4*** **jsou zvolené exponenty jednotlivých
účastníků skupiny.**

\

**Ks=Ze** **Q=2**^**180**^ **mod=19=1**

\

\

\

***Zdroje***

http://www.algoritmy.net/article/84/Diffie-Hellman

\

\

\
