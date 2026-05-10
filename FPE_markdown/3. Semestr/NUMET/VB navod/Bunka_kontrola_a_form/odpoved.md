---
title: "odpoved.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/NUMET/VB navod/Bunka_kontrola_a_form/odpoved.doc"
date: 2004-07-28
type: DOC
---

**Práce s buňkou, adresa buňky a kontrola platnosti proměnné.**

[[www.slezak-petr.cz](http://www.slezak-petr.cz/)]{.underline}
[<info@slezak-petr.cz>]{.underline}

\

Zaprvé o adrese buňky. Jak píšu na svém webu, existuje adresa buňky
relativní,

a adresa absolutní ...

\

Odkaz v buňce „ = A4" je relativní (pokud bude v buňce B4, a pak se B4
zkopíruje do B5, tak v B5 bude odkaz „ = A5")

\

Znakem dolar se blokuje změna adresy pro:

-   řádek „ = A\$4" -- při kopírování po řádcích stále kouká jen do ř.
    „4"

-   sloupec „ = \$A4" - při kopírování po sloupcích stále kouká jen do
    sl. „A"

-   nebo absolutně „ = [\$A\$4]{lang="en-US"}" -- adresa -- odkaz se
    nemění vůbec

\

nejlépe napsat do buňky zkopírovat dolů a do strany a bude to jasné.

Další možností, kdy používáme absolutní odkaz („ = \$A\$4"),

je definovat [název buňky]{.underline} tj. v Excelu menu:

Vložit / Název / Definovat ... také viz web ...

nebo vybrat buňku, a do řádku adresy

(tam kde se ukazuje adresa buňky „ = A4") napsat libovolný název

[bez mezer]{.underline} a pokud možno [bez diakritiky]{.underline} !!! a
potvrdit [Enterem]{.underline} .

Potom třeba buňka E7 bude mít název „Moje_bunka" jako v mém příkladu.

\

Nahrání hodnoty je pak jednoduché:

Nejprve je třeba deklarovat adresu buňky:

# Dim Moje_bunka As Range {#dim-moje_bunka-as-range .western lang="cs-CZ"}

a deklarovat proměnnou pro VBA:

*Dim Hodnota_bunky As Variant* (As String ...)

*Hodnota_bunky= Range(„Moje_bunka")*

Tím má proměnná naplněnou hodnotu.

Pak pomocí dalších událostí pracujeme dál ...

\

Práce s formulářem je čitelná po přepnutí ve VBA do kódu formuláře.

Kontrola platnosti obsahu buňky pak v modulu „Vloz_cislo".

\

\
