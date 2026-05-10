---
title: "vohradsky_P08N0088P_oprava.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/SVVT/Toman/vohradsky_P08N0088P_oprava.pdf"
date: 2009-12-18
type: PDF (text-based)
---

KVD/SVVT
Diffie-Hellman algoritmus

Jiří Vohradský, P08N0088P

Diffie-Hellman algoritmus obecně
Diffie-Hellmanův algoritmus slouží k domluvě společného klíče (například pro symetrickou
kryptografii) po nezabezpečeném kanálu (kanál může být odposloucháván). Tento algoritmus
zaručí výměnu společného klíče takovým způsobem, že pokud bude tuto komunikaci
odposlouchávat útočník, tak nebude schopen klíč na základě odposlechnutých informací
zrekonstruovat.

Obrázek 1-Princip výpočtu Diffie-Hellman algoritmu (zdroj:http://www.algoritmy.net/image/id/1169)

Zadání
-

Účastnící si zvolí - sdělí - domluví se na číslech m (modulo) a z (základ), tyto hodnoty
jsou veřejně sdělitelné.
Každý účastník si zvolí svůj exponent e (nesoudělný modulem) – tajný.
Každý účastník vypočte šifrovací klíč.

Složení skupiny
Jiří Vohradský (A)
Josef Hobel (B)
Miroslav Vild (C)
Zdeněk Kleisner (D)

Postup
-

Domluvili jsme se na modulu m = 19 a základu z = 2
Zvolil jsem si exponent e = 2

1) První krok výpočtu vychází ze vzorce |ze|mod 19, v mém případě |22|19 = 4
2) Tento výsledek pošlu účastníkovi B a současně přijmu výsledek 7 od účastníka D,
který opět vložím do vzorce |72|19 = 11
3) Tento výsledek pošlu účastníkovi B a současně přijmu výsledek 1 od účastníka D,
který opět vložím do vzorce |12|19 = 1
4) Tento výsledek opět pošlu účastníkovi B a současně přijmu výsledek 1 od účastníka
D, který opět vložím do vzorce |12|19 = 1
Tento výsledek je již konečný, ostatním účastníkům také vyšel výsledek roven jedné. Vyplývá
z toho, že počet výpočtů je roven počtu účastníků ve skupině.

Analýza počtu kroků
Počet kroků je vždy roven počtu účastníků, v případě, že všem účastníkům vychází
stejný výsledek i při menším počtu kroků, tak je nutné dále pokračovat ve výpočtech až
do konce, tedy do doby než bude počet opakování roven počtu účastníků.

Kontrolní ověření výpočtu
e=e1*e2*e3*e4
e=2*5*3*6=180
Ks=Ze Q=2180 mod=19=1

Zdroje
http://www.algoritmy.net/article/84/Diffie-Hellman

