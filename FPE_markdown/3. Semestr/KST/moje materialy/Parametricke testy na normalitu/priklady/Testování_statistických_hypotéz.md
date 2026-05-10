---
title: "Testování_statistických_hypotéz.htm"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/moje materialy/Parametricke testy na normalitu/priklady/Testování_statistických_hypotéz.htm"
date: 2010-01-20
type: HTML
---

::: {#globalWrapper}
::: {#column-content}
::: {#content}
[]{#top}

::: {#siteNotice}
::: {#centralNotice .expanded .anonnotice}
+-----------------------------------+-----------------------------------+
| ::: notice-text-globalsysops-vote | [                                 |
| Zveme vás k hlasování o návrhu na | \[[Skrýt](#){onclick              |
| zavedení *globálních správců*.    | ="toggleNotice();return false"}\] |
| [Klikněte zde pro více            | ]{.toggle-box-globalsysops-vote}\ |
| informací.](http://meta.          | [ \[[Pomozte nám s                |
| wikimedia.org/wiki/Global_sysops) | překlad                           |
| :::                               | em!](http://meta.wikimedia.org/wi |
|                                   | ki/CentralNotice/Global_sysops)\] |
|                                   | ]{.trans-box}                     |
+-----------------------------------+-----------------------------------+

::: {.siteNoticeSmallAnon .notice-collapsed-wrapper-globalsysops-vote}
:::
:::
:::

# Testování statistických hypotéz {#firstHeading .firstHeading}

::: {#bodyContent}
### Z Wikipedie, otevřené encyklopedie {#siteSub}

::: {#contentSub}
:::

::: {#jump-to-nav}
Skočit na: [Navigace](#column-one), [Hledání](#searchInput)
:::

**Testování
[statistických](http://cs.wikipedia.org/wiki/Statistika "Statistika")
hypotéz** umožňuje posoudit, zda
[experimentálně](http://cs.wikipedia.org/wiki/Pokus "Pokus") získaná
data vyhovují předpokladu, který jsme před provedením testování učinili.
Můžeme například posuzovat, zda platí předpoklad, že určitý lék je
účinnější než jiný; nebo například, zda platí, že úroveň matematických
dovedností žáků 9. tříd je nezávislá na pohlaví a na regionu.

+-----------------------------------------------------------------------+
| ::: {#toctitle}                                                       |
| ## Obsah                                                              |
|                                                                       |
| [\[[skrýt](javascript:toggleToc()){#togglelink                        |
| .internal}\]]{.toctoggle}                                             |
| :::                                                                   |
|                                                                       |
| -   [[1]{.tocnumber} [Statistická                                     |
|     hypotéza]{.toctext}](#Statistick.C3.A1_hypot.C3.A9za)             |
| -   [[2]{.tocnumber} [Statistický                                     |
|     test]{.toctext}](#Statistick.C3.BD_test)                          |
| -   [[3]{.tocnumber} [Testovací                                       |
|     kritérium]{.toctext}](#Testovac.C3.AD_krit.C3.A9rium)             |
| -   [[4]{.tocnumber} [Chyby testu]{.toctext}](#Chyby_testu)           |
| -   [[5]{.tocnumber} [Postup při                                      |
|     testování]{.toctext}](#Postup_p.C5.99i_testov.C3.A1n.C3.AD)       |
| -   [[6]{.tocnumber} [Související                                     |
|     články]{.toctext}](#Souvisej.C3.ADc.C3.AD_.C4.8Dl.C3.A1nky)       |
+-----------------------------------------------------------------------+

## [\[[editovat](http://cs.wikipedia.org/w/index.php?title=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z&action=edit&section=1 "Editace sekce: Statistická hypotéza")\]]{.editsection} [Statistická hypotéza]{#Statistick.C3.A1_hypot.C3.A9za .mw-headline}

Jako statistickou hypotézu chápeme určitý předpoklad o
[rozdělení](http://cs.wikipedia.org/wiki/Rozd%C4%9Blen%C3%AD_pravd%C4%9Bpodobnosti "Rozdělení pravděpodobnosti")
[náhodných
veličin](http://cs.wikipedia.org/wiki/N%C3%A1hodn%C3%A1_veli%C4%8Dina "Náhodná veličina").
Jestliže se tyto předpoklady týkají hodnot parametrů rozdělení náhodné
veličiny, pak hovoříme o *parametrických hypotézách*. V opačném případě
se jedná o *hypotézy neparametrické*.

Jsou-li hypotézou specifikovány všechny parametry rozdělení sledované
veličiny, tzn. rozdělení je určeno jednoznačně, pak říkáme, že hypotéza
je *jednoduchá*. Pokud není některý parametr rozdělení specifikován
jednoznačně, např. je vymezen
[intervalem](http://cs.wikipedia.org/wiki/Interval_%28matematika%29 "Interval (matematika)"),
pak hovoříme o *složené hypotéze*.

## [\[[editovat](http://cs.wikipedia.org/w/index.php?title=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z&action=edit&section=2 "Editace sekce: Statistický test")\]]{.editsection} [Statistický test]{#Statistick.C3.BD_test .mw-headline}

Při [testování](http://cs.wikipedia.org/wiki/Test "Test"){.mw-redirect}
statistických hypotéz vždy porovnáváme dvě hypotézy. Jedna hypotéza,
tzv. **nulová (testovaná)**, je hypotéza, kterou testujeme. Značíme ji
obvykle [*H*~0~]{.texhtml}. Druhou hypotézou je tzv. **alternativní
hypotéza**, kterou obvykle značíme [*H*~1~]{.texhtml}.

Posuzování **nulové hypotézy** [*H*~0~]{.texhtml} je založeno na
následující úvaze:

-   Předpokládáme, že hypotéza [*H*~0~]{.texhtml} platí.
-   Rozhodneme se, kterým [náhodným
    pokusem](http://cs.wikipedia.org/wiki/N%C3%A1hodn%C3%BD_pokus "Náhodný pokus"){.mw-redirect}
    (například založeném na [náhodném
    výběru](http://cs.wikipedia.org/wiki/N%C3%A1hodn%C3%BD_v%C3%BDb%C4%9Br "Náhodný výběr"))
    hypotézu ověříme. Určíme, která [náhodná
    veličina](http://cs.wikipedia.org/wiki/N%C3%A1hodn%C3%A1_veli%C4%8Dina "Náhodná veličina")
    bude výsledkem pokusu.
-   Stanovíme si [hladinu
    spolehlivosti](http://cs.wikipedia.org/w/index.php?title=Hladinu_spolehlivosti&action=edit&redlink=1 "Hladinu spolehlivosti (stránka neexistuje)"){.new}
    [α]{.texhtml} neboli pravděpodobnost (míru rizika) toho, že hypotézu
    [*H*~0~]{.texhtml} neoprávněně zamítneme, ačkoliv platí (viz též
    dále **chyba I. druhu**). [α]{.texhtml} se přitom stanovuje jako
    malé, obvykle 0,05 nebo 0,01.
-   V oboru možných hodnot použité [náhodné
    veličiny](http://cs.wikipedia.org/wiki/N%C3%A1hodn%C3%A1_veli%C4%8Dina "Náhodná veličina")
    určíme takovou část, do níž za platnosti [*H*~0~]{.texhtml} padne
    výsledek veličiny s pravděpodobností [α]{.texhtml}. Tato část oboru
    možných hodnot se nazve kritický obor.
-   Pokud nyní hodnota náhodné veličiny padne do kritického oboru,
    hypotézu zámítáme, neboť nastal jev, který by za platnosti
    [*H*~0~]{.texhtml} měl jen velmi malou pravděpodobnost a jehož
    výskyt tudíž svědčí proti platnosti nulové hypotézy.

Výsledkem testu je rozhodnutí o nulové hypotéze. Přijetí hypotézy
[*H*~0~]{.texhtml} znamená, že ji považujeme za možnou. Zamítnutí
hypotézy [*H*~0~]{.texhtml} je ekvivalentní přijetí hypotézy
[*H*~1~]{.texhtml}. Testování hypotéz je tedy proces, při němž se na
základě náhodného výběru rozhodneme pro testovanou nebo alternativní
hypotézu.

\
Samotný postup testování hypotéz označujeme jako **statistický test**
(**test významnosti**).

\
Testujeme-li neznámý parametr [Θ]{.texhtml} pak testovanou (nulovou)
hypotézu zapisujeme jako

![H_0:\\Theta=\\Theta_0
\\,](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/4f54d1a75e4554728fd5cba9a7d3a0d2.png){.tex}

Alternativní hypotézu pak formulujeme jedním z následujících způsobů

![H_1:\\Theta=\\Theta_1
\\,](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/6282ab48e4fcff3135fa59786b1748ee.png){.tex}

![H_1:\\Theta\>\\Theta_0
\\,](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/3990762a6ea9cbb8b7c498b0d5a34a1a.png){.tex}

![H_1:\\Theta\<\\Theta_0
\\,](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/3d8f42bd9528e3cec98d7f5759e0c4e0.png){.tex}

![H_1:\\Theta\\neq\\Theta_0
\\,](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/f1571cecb4adf2552300ca67d56acc5a.png){.tex}

První formulaci alternativní hypotézy [*H*~1~]{.texhtml} používáme pouze
v případě, kdy rozhodujeme mezi dvěma hodnotami [Θ~0~]{.texhtml} a
[Θ~1~]{.texhtml}. Další dva případy se používají tehdy, chceme-li
dokázat, že odchylka od [Θ]{.texhtml} je pouze v jednom směru.
Alternativní hypotéza formulovaná posledním vztahem pouze popírá
testovanou hypotézu [*H*~0~]{.texhtml}.

## [\[[editovat](http://cs.wikipedia.org/w/index.php?title=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z&action=edit&section=3 "Editace sekce: Testovací kritérium")\]]{.editsection} [Testovací kritérium]{#Testovac.C3.AD_krit.C3.A9rium .mw-headline}

K otestování nulové hypotézy [*H*~0~]{.texhtml} proti alternativní
hypotéze [*H*~1~]{.texhtml} použijeme
[statistiku](http://cs.wikipedia.org/wiki/Statistika_%28v%C3%BDb%C4%9Br%29 "Statistika (výběr)"){.mw-redirect}
[*T*]{.texhtml}, kterou označujeme jako testovací kritérium. Testovací
kritérium je
[funkce](http://cs.wikipedia.org/wiki/Funkce_%28matematika%29 "Funkce (matematika)")
[náhodného
výběru](http://cs.wikipedia.org/wiki/N%C3%A1hodn%C3%BD_v%C3%BDb%C4%9Br "Náhodný výběr"),
která má vztah k nulové hypotéze, a jejíž
[rozdělení](http://cs.wikipedia.org/wiki/Rozd%C4%9Blen%C3%AD_pravd%C4%9Bpodobnosti "Rozdělení pravděpodobnosti")
za předpokladu platnosti nulové hypotézy známe. Obor možných hodnot
testovacího kritéria rozdělíme na dva neslučitelné obory. Jedním z nich
je obor přijetí testované hypotézy
![\\mathbf{V}](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/b0d10a97e7231e562a23ea3e73aa04b4.png){.tex}
a druhým je kritický obor
![\\mathbf{W}](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/1990b12fd270f7d985212dc61cf337af.png){.tex}.
Pokud výběrová hodnota testovacího kritéria padne do oboru přijetí
testované hypotézy, pak přijímáme nulovou hypotézu. Padne-li tato
hodnota do kritického oboru, nulovou hypotézu zamítáme.

Kritický obor oddělují od oboru přijetí tzv. *kritické hodnoty*, což
jsou [kvantily](http://cs.wikipedia.org/wiki/Kvantil "Kvantil")
rozdělení testovacího kritéria při platnosti [*H*~0~]{.texhtml}.

Místo porovnání hodnoty testovacího kritéria s kritickými hodnotami se
pro rozhodování o nulové hypotéze používá též **p-hodnota**, zejména při
použití statistického
[software](http://cs.wikipedia.org/wiki/Software "Software"). Význam
p-hodnoty objasní následující postup.

1.  Nechť testovací kritérium [*T*]{.texhtml} nabylo při testování
    hodnoty [*t*]{.texhtml}.
2.  Obor možných hodnot testovacího kritéria se číslem [*t*]{.texhtml}
    rozdělí na dvě části:
    -   obor
        ![\\mathbf{V\'}](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/7d488a79a249c452f3c449820e22eef8.png){.tex},
        v němž jsou všechny takové hodnoty testovacího kritéria
        [*T*]{.texhtml}, jež svědčí *pro platnost* [*H*~0~]{.texhtml}
        více než nebo stejně jako číslo [*t*]{.texhtml}
    -   obor
        ![\\mathbf{W\'}](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/07167fc4fd8521d930412471326df1eb.png){.tex},
        v němž jsou všechny takové hodnoty testovacího kritéria
        [*T*]{.texhtml}, jež svědčí *proti platnosti* [*H*~0~]{.texhtml}
        více než číslo [*t*]{.texhtml}
3.  P-hodnota je
    [pravděpodobnost](http://cs.wikipedia.org/wiki/Pravd%C4%9Bpodobnost "Pravděpodobnost"),
    že výsledek testovacího kritéria [*T*]{.texhtml} za platnosti
    [*H*~0~]{.texhtml} padne do oboru
    ![\\mathbf{W\'}](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/07167fc4fd8521d930412471326df1eb.png){.tex}.
4.  Je-li p-hodnota menší než předem stanovené [α]{.texhtml}, nulovou
    hypotézu zamítáme.

P-hodnota tedy znamená, zjednodušeně řečeno, jaká je pravděpodobnost, že
by testovací kritérium dosáhlo své hodnoty, případně hodnot ještě více
svědčících proti [*H*~0~]{.texhtml}, pokud by [*H*~0~]{.texhtml} opravdu
platila. Čím menší p-hodnota, tím nepravděpodobnějšího výsledku (za
předpokladu platnosti [*H*~0~]{.texhtml}) bylo dosaženo.

Výhoda p-hodnoty je v tom, že její výpočet nezávisí na konkrétní volbě
[α]{.texhtml}. Není tak nutné znát kritické hodnoty pro různé volby
[α]{.texhtml}, p-hodnota obsahuje dostatečnou informaci sama o sobě.

## [\[[editovat](http://cs.wikipedia.org/w/index.php?title=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z&action=edit&section=4 "Editace sekce: Chyby testu")\]]{.editsection} [Chyby testu]{#Chyby_testu .mw-headline}

Uvedený postup může také vést k chybnému zamítnutí testované hypotézy
(tzv. *chyba I. druhu*) nebo k chybnému přijetí testované hypotézy (tzv.
*chyba II. druhu*).

\
[Pravděpodobnost](http://cs.wikipedia.org/wiki/Pravd%C4%9Bpodobnost "Pravděpodobnost")
chyby I. druhu je označována jako **hladina významnosti testu**.

![\\alpha =
P(T\\in\\mathbf{W}\|H_0)](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/947a458fca1ebe6f1d7faffeca55729f.png){.tex}

Pravděpodobnost, že hodnota testovacího kritéria padne do oboru přijetí
[*H*~0~]{.texhtml}, jestliže platí [*H*~1~]{.texhtml}, tzn.
pravděpodobnost chyby II. druhu, je

![\\beta =
P(T\\in\\mathbf{V}\|H_1)](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/ba193d6a1d362f313753f9b8f9fdcb2d.png){.tex}

Doplněk k [β]{.texhtml} se nazývá **síla testu** (hovoříme také o
**silofunkci**)

![1-\\beta =
P(T\\in\\mathbf{W}\|H_1)](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/4e544e3dd5f8ecb296d69acecaf6ac62.png){.tex}

## [\[[editovat](http://cs.wikipedia.org/w/index.php?title=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z&action=edit&section=5 "Editace sekce: Postup při testování")\]]{.editsection} [Postup při testování]{#Postup_p.C5.99i_testov.C3.A1n.C3.AD .mw-headline}

Při volbě testovacího postupu je naším cílem, aby chyby byly co
nejmenší. Lze dokázat, že za daných podmínek vede snižování
[α]{.texhtml} k růstu [β]{.texhtml} a naopak.

Při testování obvykle postupujeme tak, že nejdříve formulujeme nulovou a
alternativní hypotézu. Poté volíme hladinu významnosti [α]{.texhtml}
(obvykle se volí [α = 0,05]{.texhtml} nebo [α = 0,01]{.texhtml}).
Nalezneme vhodné testovací kritérium a jeho pravděpodobnostní rozdělení
při platnosti [*H*~0~]{.texhtml}. Dále vymezíme kritický obor s ohledem
na formulaci hypotézy [*H*~1~]{.texhtml}. Vypočteme testovací kritérium
[*T*]{.texhtml} a určíme kritické hodnoty testovacího kritéria. Jestliže
![T\\in\\mathbf{W}](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/e49086a4ce3e40d2fdda6573c00f8ac7.png){.tex},
pak hypotézu [*H*~0~]{.texhtml} zamítáme a říkáme, že s pravděpodobností
[1 − α]{.texhtml} platí hypotéza [*H*~1~]{.texhtml}. Pokud
![T\\in\\mathbf{V}](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/dcbebcec5b207acdf65e6ff793a756f2.png){.tex},
pak hypotézu [*H*~1~]{.texhtml} považujeme za neprokázanou. V takové
případě neprovádíme úsudek o platnosti [*H*~0~]{.texhtml}, nechceme-li
se zabývat sílou testu.

## [\[[editovat](http://cs.wikipedia.org/w/index.php?title=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z&action=edit&section=6 "Editace sekce: Související články")\]]{.editsection} [Související články]{#Souvisej.C3.ADc.C3.AD_.C4.8Dl.C3.A1nky .mw-headline}

-   [Odhad](http://cs.wikipedia.org/wiki/Odhad_%28statistika%29 "Odhad (statistika)")

\

  --------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------
  [![Pahýl                                                                                                  *Tento [matematický](http://cs.wikipedia.org/wiki/Matematika "Matematika") článek je [příliš
  -](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/44px-Mathematic_template.png){width="44"   stručný](http://cs.wikipedia.org/wiki/Wikipedie:Pah%C3%BDl "Wikipedie:Pahýl") nebo neobsahuje důležité informace.\
  height="46"}](http://cs.wikipedia.org/wiki/Soubor:Mathematic_template.png "Pahýl -"){.image}              Pomozte Wikipedii tím, že jej vhodně
                                                                                                            [rozšíříte](http://cs.wikipedia.org/w/index.php?title=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z&action=edit){.external
                                                                                                            .text rel="nofollow"}.*

  --------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------

::: printfooter
Citováno z
„<http://cs.wikipedia.org/wiki/Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z>"
:::

::: {#catlinks .catlinks}
::: {#mw-normal-catlinks}
[Kategorie](http://cs.wikipedia.org/wiki/Speci%C3%A1ln%C3%AD:Kategorie "Speciální:Kategorie"):
[[Matematická
statistika](http://cs.wikipedia.org/wiki/Kategorie:Matematick%C3%A1_statistika "Kategorie:Matematická statistika")]{dir="ltr"}
:::

::: {#mw-hidden-catlinks .mw-hidden-cats-hidden}
Skrytá kategorie: [[Matematické
pahýly](http://cs.wikipedia.org/wiki/Kategorie:Matematick%C3%A9_pah%C3%BDly "Kategorie:Matematické pahýly")]{dir="ltr"}
:::
:::

::: visualClear
:::
:::
:::
:::

::: {#column-one}
::: {#p-cactions .portlet}
##### Zobrazení

::: pBody
-   [[Článek](http://cs.wikipedia.org/wiki/Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z "Zobrazit obsahovou stránku [alt-shift-c]"){accesskey="c"}]{#ca-nstab-main}
-   [[Diskuse](http://cs.wikipedia.org/wiki/Diskuse:Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z "Diskuse ke stránce [alt-shift-t]"){accesskey="t"}]{#ca-talk}
-   [[Editovat](http://cs.wikipedia.org/w/index.php?title=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z&action=edit "Tuto stránku můžete editovat. Prosíme použijte tlačítko Ukázat náhled před uložením. [alt-shift-e]"){accesskey="e"}]{#ca-edit}
-   [[Historie](http://cs.wikipedia.org/w/index.php?title=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z&action=history "Starší verze této stránky. [alt-shift-h]"){accesskey="h"}]{#ca-history}
:::
:::

::: {#p-personal .portlet}
##### Osobní nástroje

::: pBody
-   [[Vyzkoušet
    Betu](http://cs.wikipedia.org/w/index.php?title=Speci%C3%A1ln%C3%AD:UsabilityInitiativeOptIn&from=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z "Vyzkoušet nové funkce"){.no-text-transform}]{#pt-optin-try}
-   [[Moje
    diskuse](http://cs.wikipedia.org/wiki/Speci%C3%A1ln%C3%AD:Mytalk)]{#pt-anontalk}
-   [[Přihlášení / vytvoření
    účtu](http://cs.wikipedia.org/w/index.php?title=Speci%C3%A1ln%C3%AD:P%C5%99ihl%C3%A1sit&returnto=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z "Doporučujeme vám přihlásit se, ovšem není to povinné. [alt-shift-o]"){accesskey="o"}]{#pt-login}
:::
:::

::: {#p-logo .portlet}
[](http://cs.wikipedia.org/wiki/Hlavn%C3%AD_strana "Hlavní strana"){style="background-image: url(http://upload.wikimedia.org/wikipedia/cs/b/bc/Wiki.png);"}
:::

::: {#p-search .portlet}
##### Hledání {#hledání lang="cs"}

::: {#searchBody .pBody}
 
:::
:::

::: {#p-navigation .generated-sidebar .portlet}
##### Navigace {#navigace lang="cs"}

::: pBody
-   [[Hlavní
    strana](http://cs.wikipedia.org/wiki/Hlavn%C3%AD_strana "Navštívit Hlavní stranu [alt-shift-z]"){accesskey="z"}]{#n-mainpage}
-   [[Portál
    Wikipedie](http://cs.wikipedia.org/wiki/Wikipedie:Port%C3%A1l_Wikipedie "O projektu, jak můžete pomoci, kde hledat")]{#n-portal}
-   [[Aktuality](http://cs.wikipedia.org/wiki/Port%C3%A1l:Aktuality "Informace o aktuálních událostech")]{#n-currentevents}
-   [[Pod
    lípou](http://cs.wikipedia.org/wiki/Wikipedie:Pod_l%C3%ADpou)]{#n-villagepump}
-   [[Poslední
    změny](http://cs.wikipedia.org/wiki/Speci%C3%A1ln%C3%AD:Posledn%C3%AD_zm%C4%9Bny "Seznam posledních změn na této wiki [alt-shift-r]"){accesskey="r"}]{#n-recentchanges}
-   [[Náhodný
    článek](http://cs.wikipedia.org/wiki/Speci%C3%A1ln%C3%AD:N%C3%A1hodn%C3%A1_str%C3%A1nka "Přejít na náhodně vybranou stránku [alt-shift-x]"){accesskey="x"}]{#n-randompage}
-   [[Nápověda](http://cs.wikipedia.org/wiki/N%C3%A1pov%C4%9Bda:Obsah "Místo, kde najdete pomoc")]{#n-help}
-   [[Podpořte
    Wikipedii](http://wikimediafoundation.org/wiki/Sponzorstv%C3%AD "Podpořte nás")]{#n-sitesupport}
:::
:::

::: {#p-coll-print_export .generated-sidebar .portlet}
##### Tisk/export {#tiskexport lang="cs"}

::: pBody
-   [[Vytvořit
    knihu](http://cs.wikipedia.org/w/index.php?title=Speci%C3%A1ln%C3%AD:Book&bookcmd=book_creator&referer=Testov%C3%A1n%C3%AD+statistick%C3%BDch+hypot%C3%A9z "Vytvoření knihy nebo kolekce stránek"){rel="nofollow"}]{#coll-create_a_book}
-   [[Stáhnout jako
    PDF](http://cs.wikipedia.org/w/index.php?title=Speci%C3%A1ln%C3%AD:Book&bookcmd=render_article&arttitle=Testov%C3%A1n%C3%AD+statistick%C3%BDch+hypot%C3%A9z&oldid=4070863&writer=rl "Stáhnout tuto stránku wiki jako PDF"){rel="nofollow"}]{#coll-download-as-rl}
-   [[Verze k
    tisku](http://cs.wikipedia.org/w/index.php?title=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z&printable=yes "Tato stránka v podobě vhodné k tisku [alt-shift-p]"){accesskey="p"}]{#t-print}
:::
:::

::: {#p-tb .portlet}
##### Nástroje {#nástroje lang="cs"}

::: pBody
-   [[Odkazuje
    sem](http://cs.wikipedia.org/wiki/Speci%C3%A1ln%C3%AD:Co_odkazuje_na/Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z "Seznam všech wikistránek, které sem odkazují [alt-shift-j]"){accesskey="j"}]{#t-whatlinkshere}
-   [[Související
    změny](http://cs.wikipedia.org/wiki/Speci%C3%A1ln%C3%AD:Souvisej%C3%ADc%C3%AD_zm%C4%9Bny/Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z "Nedávné změny stránek, na které je odkazováno [alt-shift-k]"){accesskey="k"}]{#t-recentchangeslinked}
-   [[Speciální
    stránky](http://cs.wikipedia.org/wiki/Speci%C3%A1ln%C3%AD:Speci%C3%A1ln%C3%AD_str%C3%A1nky "Seznam všech speciálních stránek [alt-shift-q]"){accesskey="q"}]{#t-specialpages}
-   [[Trvalý
    odkaz](http://cs.wikipedia.org/w/index.php?title=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z&oldid=4070863 "Trvalý odkaz na současnou verzi této stránky")]{#t-permalink}
-   [[Citovat
    stránku](http://cs.wikipedia.org/w/index.php?title=Speci%C3%A1ln%C3%AD:Cite&page=Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z&id=4070863 "Informace o tom, jak citovat tuto stránku")]{#t-cite}
:::
:::

::: {#p-lang .portlet}
##### V jiných jazycích {#v-jiných-jazycích lang="cs"}

::: pBody
-   [Cymraeg](http://cy.wikipedia.org/wiki/Prawf_rhagdybiaeth)
-   [Dansk](http://da.wikipedia.org/wiki/Hypotesepr%C3%B8vning)
-   [Deutsch](http://de.wikipedia.org/wiki/Statistischer_Test)
-   [English](http://en.wikipedia.org/wiki/Statistical_hypothesis_testing)
-   [Español](http://es.wikipedia.org/wiki/Contraste_de_hip%C3%B3tesis)
-   [فارسی](http://fa.wikipedia.org/wiki/%D8%A2%D8%B2%D9%85%D9%88%D9%86_%D9%81%D8%B1%D8%B6_%D8%A2%D9%85%D8%A7%D8%B1%DB%8C)
-   [Français](http://fr.wikipedia.org/wiki/Test_d%27hypoth%C3%A8se)
-   [עברית](http://he.wikipedia.org/wiki/%D7%91%D7%93%D7%99%D7%A7%D7%AA_%D7%94%D7%A9%D7%A2%D7%A8%D7%95%D7%AA)
-   [Italiano](http://it.wikipedia.org/wiki/Test_di_verifica_d%27ipotesi)
-   [日本語](http://ja.wikipedia.org/wiki/%E4%BB%AE%E8%AA%AC%E6%A4%9C%E5%AE%9A)
-   [ລາວ](http://lo.wikipedia.org/wiki/%E0%BA%81%E0%BA%B2%E0%BA%99%E0%BA%97%E0%BA%BB%E0%BA%94%E0%BA%AA%E0%BA%AD%E0%BA%9A%E0%BA%AA%E0%BA%BB%E0%BA%A1%E0%BA%A1%E0%BA%B8%E0%BA%94%E0%BA%95%E0%BA%B4%E0%BA%96%E0%BA%B2%E0%BA%99%E0%BA%AA%E0%BA%B0%E0%BA%96%E0%BA%B4%E0%BA%95%E0%BA%B4)
-   [Nederlands](http://nl.wikipedia.org/wiki/Statistische_toets)
-   [‪Norsk (bokmål)‬](http://no.wikipedia.org/wiki/Hypotesetest)
-   [Polski](http://pl.wikipedia.org/wiki/Weryfikacja_hipotez_statystycznych)
-   [Português](http://pt.wikipedia.org/wiki/Testes_de_hip%C3%B3teses)
-   [Русский](http://ru.wikipedia.org/wiki/%D0%9F%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0_%D1%81%D1%82%D0%B0%D1%82%D0%B8%D1%81%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D1%85_%D0%B3%D0%B8%D0%BF%D0%BE%D1%82%D0%B5%D0%B7)
-   [Simple
    English](http://simple.wikipedia.org/wiki/Statistical_hypothesis_test)
-   [Svenska](http://sv.wikipedia.org/wiki/Hypotespr%C3%B6vning)
-   [Türkçe](http://tr.wikipedia.org/wiki/Hipotez_testi)
-   [اردو](http://ur.wikipedia.org/wiki/%D8%A7%D8%AD%D8%B5%D8%A7%D8%A6%DB%8C_%D8%A7%D8%AE%D8%AA%D8%A8%D8%A7%D8%B1_%D9%85%D9%81%D8%B1%D9%88%D8%B6%DB%81)
-   [中文](http://zh.wikipedia.org/wiki/%E5%81%87%E8%A8%AD%E6%AA%A2%E5%AE%9A)
:::
:::
:::

::: visualClear
:::

::: {#footer}
::: {#f-poweredbyico}
[![Powered by
MediaWiki](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/poweredby_mediawiki_88x31.png){width="88"
height="31"}](http://www.mediawiki.org/)
:::

::: {#f-copyrightico}
[![Wikimedia
Foundation](Testov%C3%A1n%C3%AD_statistick%C3%BDch_hypot%C3%A9z_soubory/wikimedia-button.png){width="88"
height="31"}](http://wikimediafoundation.org/)
:::

-   [Stránka byla naposledy editována 11. 6. 2009 v 07:46.]{#lastmod}
-   [Text je dostupný pod [licencí Creative Commons Uveďte autora --
    Zachovejte licenci 3.0
    Unported](http://creativecommons.org/licenses/by-sa/3.0/deed.cs),
    případně za dalších podmínek. Podrobnosti naleznete na stránce
    [Podmínky
    užití](http://wikimediafoundation.org/wiki/Podm%C3%ADnky_u%C5%BEit%C3%AD).]{#copyright}
-   [[Ochrana osobních
    údajů](http://wikimediafoundation.org/wiki/Ochrana_osobn%C3%ADch_%C3%BAdaj%C5%AF "wikimedia:Ochrana osobních údajů")]{#privacy}
-   [[O
    Wikipedii](http://cs.wikipedia.org/wiki/Wikipedie "Wikipedie")]{#about}
-   [[Vyloučení
    odpovědnosti](http://cs.wikipedia.org/wiki/Wikipedie:Vylou%C4%8Den%C3%AD_odpov%C4%9Bdnosti "Wikipedie:Vyloučení odpovědnosti")]{#disclaimer}
:::
:::
