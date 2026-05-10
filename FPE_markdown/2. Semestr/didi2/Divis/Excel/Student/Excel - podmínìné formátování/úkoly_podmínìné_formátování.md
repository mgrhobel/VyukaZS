---
title: "úkoly_podmínìné_formátování.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/2. Semestr/didi2/Divis/Excel/Student/Excel - podmínìné formátování/úkoly_podmínìné_formátování.doc"
date: 2005-03-09
type: DOC
---

# Podmíněné formátování {#podmíněné-formátování .western lang="cs-CZ"}

*Tabulka kterou dnes vytvoříme bude sledovat vaše týdenní náklady. Ze
zadaných výdajů (vaše útrata v každém dnu) se budou počítat průměrné
náklady na jeden den a na týden. Vyzkoušíme si tzv. Podmíněné
formátování, které nám umožní upravit formát buněk s výdaji, podle výše
zadané částky.*

Př: při zadání částky do 20 Kč se buňka vybarví zeleně

při zadání částky od 20 do 60 Kč se buňka vybarví oranžově

při zadání částky od 60 Kč se buňka vybarví červeně

*Poznámka: Je-li zadána nulová částka buňka nezmění formát.*

## Postup: {#postup .western lang="cs-CZ"}

-   otevřete nový soubor

-   přejmenujte List 1 na „Týdenní náklady"

-   vytvořte tabulku podle předlohy

    -   n![](%C3%BAkoly_podm%C3%ADn%C3%ACn%C3%A9_form%C3%A1tov%C3%A1n%C3%AD_html_48e93db2.gif){#Object1
        align="left" hspace="12" width="305" height="191"}\
        apište dny v týdnu pod sebe --buňky A2:A8 - ulehčete si práci a
        použijte funkce Excelu „Seznamy"

        -   do buňky A2 napište „Pondělí" a přesuňte kurzor na táhlo v
            pravém
            d![DrawObject1](%C3%BAkoly_podm%C3%ADn%C3%ACn%C3%A9_form%C3%A1tov%C3%A1n%C3%AD_html_b3af90d1.gif){#DrawObject1
            align="left" hspace="12" width="11" height="11"} olním rohu
            buňky A2  kurzor se změní z na 

        -   nyní stiskněte levé tlačítko myši a roztáhněte výběr z A2 až
            do buňky A8  pusťte levé tlačítko myši

    -   upravte formát buněk A2:A8 --font, barva písma, stínování apod.

    -   doplňte zbývající údaje do tabulky --buňky A10, A11 a B1

    -   ohraničte všechny buňky tenkou čarou

    -   ohraničte celou tabulku silnou čarou

    -   spodek buňky B8 bude ohraničen dvojitou čarou

-   do buněk B2:B8 budete zadávat částku, kterou jste v daný den
    utratili. Nastavte pro tyto buňky příslušný formát

-   d![](%C3%BAkoly_podm%C3%ADn%C3%ACn%C3%A9_form%C3%A1tov%C3%A1n%C3%AD_html_ed152d15.gif){#Object2
    align="left" hspace="12" width="151" height="34"} o buňky B10 vložte
    vzorec na výpočet celkových nákladů za týden = součet buněk B2:B8

-   nastavte pro buňku B10 vlastní formát ***0,00\_;\"Kč/týden\"***

význam nuly v zápisu -- není-li na místě nuly žádná číslice, zobrazuje
se zde nula

-   do buňky B11 vložte vzorec na výpočet průměrných nákladů za týden =
    průměr z buněk B2:B8. Průměr vytvoříme vložením funkce Průměr Vložit
     Funkci  Funkce statické  Název funkce „PRŮMĚR". Pak vyberte
    oblast B2:B8

-   nastavte pro buňku B11 vlastní formát ***0,0\_;\"Kč/den\"*** Tento
    formát nám zobrazí výsledný průměr zaokrouhlený na jedno desetinné
    místo.

-   nyní nastavte *podmíněné formátování* pro buňky B2:B8.

    -   Vyberte oblast B2:B8

    -   jděte do menu Formát  Podmíněné formátování...

    -   N![](%C3%BAkoly_podm%C3%ADn%C3%ACn%C3%A9_form%C3%A1tov%C3%A1n%C3%AD_html_cbf57098.gif){#Object3
        align="left" hspace="12" width="454" height="281"}\
        astavte postupně všechny tři podmínky (viz obrázek). Po zadání
        první podmínky klikněte na tlačítko *„Přidat \>\>"*, tím se
        dostanete na zadávání druhé podmínky.

\

-   zadejte data do tabulky

-   [**ZAVOLAT UČITELE**]{.underline}

\
