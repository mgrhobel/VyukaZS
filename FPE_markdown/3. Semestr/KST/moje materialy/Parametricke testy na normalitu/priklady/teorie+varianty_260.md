---
title: "teorie+varianty_260.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/moje materialy/Parametricke testy na normalitu/priklady/teorie+varianty_260.doc"
date: 2010-01-20
type: DOC
---

**Otázky ze statistiky**

\

**B**

\

1.  Napište druhy charakteristiky polohy a uveďte 3 příklady

2.  Jaký je rozdíl mezi parametrickým a neparametrickým testem?

3.  Za jakých podmínek můžeme provádět analýzu rozptylu?

4.  Co vyjadřuje hladinu významnosti?

5.  Jaký znáte charakteristiky variability?

6.  Co je to odlehlé pozorování?

7.  Priklad **opravte chyby -**

Proc ttest data=ms;

class hmotnost;

\

\

2.část. **dva příklady.**

-   Soubor ženy/ muži a jejich naměřená hmotnost, dokažte statisticky
    významné rozdíly na hladině alfa=0,01 a 0,05;

-   Máte 3 križovatky a ke každé spoustu naměřených hodnot, projíždějící
    auta nebo tak. Do sas nasázím ***křižovatka; počet***

  ------- -----
  0.898   I
  1.2     I
  0.65    II
  1.5     II
  0.72    III
  atd     III
  ------- -----

\

**proc glm data=soubor;**

**class krizovatka;**

**model pocet=krizovatka;**

**means krizovatka/hovtest tukey cliff;** *(popř. cldiff; alpha=0,01)*

**run;**

měl by vyjít statisticky významný rozdíl ,ezi křižovatkami a to
hvězdičkový výstup ukáže rozdíl např mezi I-II \*\*\* (nepamatuji si
mezi kterou)

\

**A**

-   -   -   Spolehlivost a přípustnost

        -   Co je to charakteristika polohy a 3 příklady. ¨

        -   Rozdíl mezi parametrickým a neparametrickým testem.

        -   Podmínky pro analýzu rozptylu.

        -   Hladina významnosti.\
            \
            Potom prográmek s T - testem (ten byl skoro celej špatně)\
            proc ttest\...

\

V příkladový částí jak závisí výška na pohlaví a závislost teploty
potrubí na hloubce uložení.

\

\

\

\

\

\

\

\

*[testování hypotéz]{.underline}*

### []{#Paired_t-test} Párový t-test {#párový-t-test .western lang="cs-CZ"}

Párový t-test není nic jiného než [[jednovýběrový
t-test](http://www.karlin.mff.cuni.cz/~kulich/sas/SASStat.html#One-sample%20t-test)]{.underline}
aplikovaný na rozdíl hodnot dvou korelovaných veličin.

### Dvouvýběrový t-test {#dvouvýběrový-t-test .western lang="cs-CZ"}

Dvouvýběrový t-test k porovnání středních hodnot dvou výběrů se stejným 
rozptylem počítá mj. procedura TTEST. Hodnoty obou výběrů musí být v
datech uloženy v jediné numerické veličině (třeba X), zatímco jiná
veličina se dvěma úrovněmi (třeba S) určuje, do kterého výběru každé
pozorování patří. T-test se provede takto:

PROC TTEST DATA=mojedata;\
  CLASS S;\
  VAR X;\
RUN;

\
\

[<http://www.karlin.mff.cuni.cz/~kulich/sas/SASStat.html>]{.underline}

\

[**Analýza rozptylu**]{.underline} -- testy na průměr *(př. průměrné
přírůstky; 3 měsíce + prům. teplota)*

\

**[proc glm data=soubor;]{style="background: #ffff00"}**

**[ class oblast;]{style="background: #ffff00"}**

**[ model vynos=oblast;]{style="background: #ffff00"}**

**[ means oblast/hovtest tukey
]{style="background: #ffff00"}*****[lines]{style="background: #ffff00"}*****[;
]{style="background: #ffff00"}** *(popř. cldiff; alpha=0,01)*

**[run;]{style="background: #ffff00"}**

\

*pozn.:* *[lines]{.underline}* *= stat. významný rozdíl existuje mezi
řádky, které mají různá písmenka; vyvážený model dá rovnou písmenka
([cldiff]{.underline}* *-- místo písmenek jsou hvězdičky)*

*[tukey]{.underline}* *= označují rozdíl statisticky významný*

*pozn.: pokud máme* ***2 kritéria*** *=\> dvouvýběrový t-test*

***3.. kritéria*** *=\> analýza rozptylu (jen* ***do jednoho sloupce***
*dle znaků!!)*

\

\

\

\

\

\

\

\

[**Párový t-test**]{.underline} *(př. mají lepší výsledky u písemné nebo
ústní zkoušky?; závislé soubory)*

\

**[proc ttest data=soubor;]{style="background: #ffff00"}**

**[ paired P\*U;]{style="background: #ffff00"}** *\*) P=písemná,
U=ústní*

**[run;]{style="background: #ffff00"}**

\

\

[**t-test**]{.underline} (jednovýběrový)

\

**[proc ttest data=soubor;]{style="background: #ffff00"}**

**[ class SEX;]{style="background: #ffff00"}**

**[ var IQ;]{style="background: #ffff00"}**

**[run;]{style="background: #ffff00"}**

\

pozn*.: nepárový t-test* ***v jednom sloupci*** *a rozdělen dle znaků
kvalitativního*

\

\

**Vysvětlivky**

[start]{.underline} :) =\> insight -- enter -- work -- new

=\> Solution / Analysis / Interaktive Data Analysis

**mean** -- průměr

**Std Dev** -- směrodatná odchylka

**Variance** -- variabilita, rozptyl

**LCL, UCL** -- dolní, horní meze

**Coeficient variation** -- variační koeficient

**Cell Percent** -- relativní četnost

**Cum Percent** -- komulativní četnost

**Density** -- hustota

**Test for Normality** -- test pro normální rozdělení

**Trimmed** -- stupně volnosti (počet pozorování) **/ Winsorized** --
t-test **Mean** (prvnky, %)

**DF** - stupně volnosti (n -- 1)

**clm** -- intervaly spolehlivost

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

\

\

\

\

\

\

\

\

**Analyze / Histogram** -- vybereme jakou proměnou chceme analyzovat
(umístíme jí do Y) -- OK

-   histogram rozdělí soubor na několik intervalů a ukáže nám s jakou
    četností se jednotlivé hodnoty souboru v těchto intervalech
    vyskytují (frequency -- četnost, EUR -- vybraná proměnná, na ose X
    jsou intervaly)

\

**Analyze / Boxplot -** detekce odlehlých pozorování; krabicový graf
(diagram)

-   odhad polohy, mediánu

-   posouzení symetrie v okolí kvantilů a u konců rozdělení

-   identifikace odlehlých pozorování

-   odlehlé pozorování se značí „o" a extrémní pozorování „\*"

-   (pokud se „krabice" nepřekrývají -- statisticky výnamný rozdíl
    v průměrech)

\

**Pr\>F**: přepočítaná hladina významnosti

-   pokud je vetší než α (zprav. 0,05) =\> Ho -- neexistuje stat.
    významný rozdíl

-   pokud je menší než α =\> Ha -- existuje stat. významný rozdíl,
    obecná platnost

-   Ho =\> **Pr \> t** \--\> rozptyly se rovnají \--\> Variances --
    Equal = stat. významný rozdíl

-   

\

\

**Statistické charakteristiky**:

1.  [polohy]{.underline} - arit. průměr, modus (nejčastější) , medián
    (prostřední)

2.  [variability]{.underline} - variační rozpětí (max hodnota souboru --
    min hodnota souboru), rozptyl, směrodatná odchylka (o kolik se
    hodnota odchyluje od střední hodnoty), variační koeficient (pro
    porovnání více souborů)

3.  [šikmosti a špičatosti]{.underline}

\

**Hypotézy** -- nulová (porovnáváme průměr nebo rozptyl \... vůči
předpokladu)

\- alternativní -- popírá nulovou hypotézu (oboustranná, jednostranná)

\

**Parametrické testy**:

-   jednovýběrové -- T-test = o shodě průměru, Test hypotézy o hodnotě
    rozptylu

-   dvouvýběrové -- F-test = o shodě dvou rozptylů, Dvouvýběrový T-test
    -- Teste hypotézy o shodě dvou průměrů

-   analýza rozptylu -- porovnávám průměry více jak dvou základních
    souborů

\

**Neparametrické testy.**

-   mají hlavní výhodu v tom, že jsou nezávislé na tvaru rozdělení
    základního souboru, a netýkají se parametrů statistického souboru
    v jejich tradičním smyslu.

-   Další důležitou vlastností je neparametrických testů je jejich větší
    univerzálnost ve srovnání s parametrickými testy, mohou být
    používány jak pro znaky kvantitativní tak pro znaky kvalitativní.

-   Jistou předností je skutečnost že po výpočetní stránce jsou velmi
    jednoduché rychlé a nenáročné.

\

-   Nevýhoda: mají menší sílu se srovnáním s parametrickými testy.

\

\

\

\

\

*[pozn]{.underline}*.: Hypotézy, které se týkají hodnot parametrů
rozdělení, se nazývají parametrické a **testy**, sloužící k jejich
ověřování, se rovněž nazývají **parametrické**. Tvrzení o zákonu
rozdělení základního souboru (bez precizování jeho parametrů) se
nazývají neparametrickými hypotézami a příslušné **testy** označujeme
jako **neparametrické.**

\

\

**Rezidua:**

-   vzdálenost mezi výrovnanou hodnotou a naměřenou di = ei

-   N (0, konst.) =\> normální rozdělení (nulová střední hodnota, konst.
    rozptyl)

-   megafonový efekt (= není konstatní rozptyl)

-   graf reziduí: Graphs/Residual Normal QQ

\

**Analýza rozptylu:**

-   představuje zobecnění dvouvýběrového t-testu na případ více než dvou
    výběrů

-   užívá se jí tehdy, sledujeme-li vliv jednoho nebo několika faktorů
    na zkoumaný kvantitativní statistický znak X

-   končí pouze tehdy jestliže nulová hypotéza nebyla zamítnuta

\

**Hladina významnosti:**

-   pravděpodobnost chyby 1. druhu se nazývá hladina významnosti a značí
    se α (![](teorie+varianty_260_html_c6363368.gif){#Object1
    align="absmiddle" width="128" height="19"}

-   udává výši rizika, s jakým se Ho zamítá, i když platí

\

\

**Spolehlivost:**

-   statistiky (náhodné veličiny, jejichž konkrétní hodnoty jsou
    vypočteny z výsledků příslušného náhodného výběru)

-   ![](teorie+varianty_260_html_65317d20.gif){#Object2 align="bottom"
    width="139" height="22"}

-   α=0,05 -- 95% interval spolehlivosti

-   α=0,01 -- 99% interval spolehlivosti

-   1-α -- koeficient spolehlivosti (spolehlivost)

-   *Spolehlivost -- pravděpodobnost s jakou interval vystihne hledanou
    hodnotu*

-   Interval spolehlivosti pro průměr, rozptyl, případně směrodatnou
    odchylku konstruujeme jestliže pracujeme se znaky kvantitativními.
    V případě znaků kvalitativních jejichž jednotlivé varianty jsou
    vyjádřeny slovně, nikoliv číselně není možné průměr případně rozptyl
    počítat. Hlavní statistickou charakteristikou kvalitativních znaků
    je relativní četnost výskytu sledované varianty kvalitativního
    znaku.

\

**Přípustnost:**

Δ- přípustná chyba (viz. Intervalový odhad)

\

\

\
