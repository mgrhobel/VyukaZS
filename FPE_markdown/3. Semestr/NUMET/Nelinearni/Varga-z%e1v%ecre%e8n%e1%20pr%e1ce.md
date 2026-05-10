---
title: "Varga-z%e1v%ecre%e8n%e1%20pr%e1ce.docx"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/NUMET/Nelinearni/Varga-z%e1v%ecre%e8n%e1%20pr%e1ce.docx"
date: 2010-01-06
type: DOCX
---

[]{#_Toc245440725}[]{#_Toc245736552}\

Západočeská univerzita v Plzni

[Fakulta pedagogická]{.smallcaps}

[[Katedra výpočetní a didaktické
techniky]{style="background: #c0c0c0"}]{.smallcaps}

[[]{style="background: #c0c0c0"}]{.smallcaps}

Ivan Varga

*Rozšiřující studium výpočetní techniky pro učitele SŠ*

*léta studia (2006-2009)*

Vedoucí práce: *[Ing.Pavel Kocur, CSc.]{style="background: #c0c0c0"}*

Plzeň [1 listopadu 2026]{style="background: #c0c0c0"}2009

Prohlašuji, že jsem závěrečnou práci vypracoval samostatně s použitím
uvedené literatury a zdrojů informací.

Plzeň [1 listopadu 2026]{style="background: #c0c0c0"}2009

..............................

Anotace

Závěrečná práce je zaměřena na programování numerických metod v excelu
2007. Práce má teoretickou a praktickou část. Teoretická část popisuje
numerické metody používané v řešení nelineárních rovnic, soustavy
lineárních algebraických rovnic, výpočet určitého integrálů. Tato část
je doplněna vývojovými diagramy. Praktická část obsahuje programy
v Excelu 2007.

Annotation

The final work is focused on programming numerical methods in Excel
2007. The theoretical part describes numerical methods used in solving
non-linear equations, systems of linear algebraicaly equations,
numerical computation of definite integral. This part is completed with
program flow diagrams. The practical part contains programs in Excel
2007. A CD containing programs and the theoretical part is included.

#    {#section .western style="page-break-before: always"}

**[Obsah]{style="text-decoration: none"}**

\
\

::: {#Table of Contents1 dir="ltr"}
**[1 Základní pojmy numerických metod 2](#_Toc246343912)**

**[2 Metody řešení nelineárních rovnic 3](#_Toc246343913)**

[2.1 Startovní metody 3](#_Toc246343914)

[2.1.1 Metoda bisekce 4](#_Toc246343916)

[2.1.2 Metoda[ prosté iterace]{lang="en-US"} 7](#_Toc246343917)

[[2.1.3 Metoda tětiv (regula falsi).]{lang="en-US"} 9](#_Toc246343918)

[2.2 Zpřesňující metody 11](#_Toc246343919)

[[2.2.1 Newtonova metoda]{lang="en-US"} 11](#_Toc246343920)

[[2.2.2 Metoda sečen]{lang="en-US"} 11](#_Toc246343921)

**[3 Řešení soustav lineárních algebraických rovnic
12](#_Toc246343922)**

[3.1 Přímé metody řešení soustav lineárních rovnic 13](#_Toc246343923)

[3.1.1 Gaussova eliminační metoda 13](#_Toc246343924)

[3.1.2 Gaussova metoda s výběrem hlavního prvku 16](#_Toc246343925)

[3.1.3 Gaussova-Jordanova eliminační metoda 18](#_Toc246343926)

[3.2 Iterační metody řešení soustav lineárních rovnic
19](#_Toc246343927)

[3.2.1 Jacobiova metoda 20](#_Toc246343928)

[3.2.2 Gaussova-Seidelova metoda 21](#_Toc246343929)

**[4 Numerický výpočet určitého integrálu 24](#_Toc246343930)**

[4.1 Obdélníková metoda 24](#_Toc246343931)

[4.2 Lichoběžníková metoda 27](#_Toc246343932)

[4.3 Simpsonova metoda 29](#_Toc246343933)

[4.4 Rombergova metoda 31](#_Toc246343934)

**[5 Seznam použité literatury 34](#_Toc246343936)**
:::

\

\

# []{#_Toc246343810}[]{#_Toc246343912} 1 Základní pojmy numerických metod {#základní-pojmy-numerických-metod .western}

Reálné problémy lze řešit pomocí experimentů, měřením nebo matematickými
prostředky. K řešení matematickými prostředky je potřebné nejdříve
formulovat matematický model daného problému. Vyřešit danou úlohu můžeme
exaktními metodami, přibližnými metodami a numerickými metodami.

\

![Shape1](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e391c8d4.gif){#Shape1
align="left" width="600" height="381"}\

S.Míka, M.Brandner. Numerické metody I

\

Pro numerické úlohy je podstatný požadavek konečnosti souborů vstupních
a výstupních dat vyjádřených konečným počtem čísel. Numerická metoda
může být realizována na počítači. Numerická matematika je základní
matematickou disciplinou, která konstruuje a analyzuje metody a postupy
pro řešení numerických úloh na počítači. Numerická matematika umožňuje
matematické problémy vyřešit aritmetickými a logickými operacemi, zabývá
se volbou postupu-metodou, která se nejlépe hodí k řešení speciálního
problému.

Numericky řešené úlohy jsou zatíženy chybami dvojího typu. První typ
chyb vzniká v matematické formulaci problému. Rozdíl řešení
idealizovaného problému a řešení reálního problému nazýváme chybou
matematického modelu. Pokud k řešení matematické úlohy použijeme metodu,
která nám neposkytne přesné řešení dané úlohy, pak chybu, které se
dopustíme, nazýváme chybou metody. Druhý typ chyb je způsoben nepřesným
prováděním aritmetických operací v počítači, jde o zaokrouhlovací chyby.

Mezi matematickými úlohami a tím i mezi numerickými úlohami jsou úlohy,
kterých řešení jsou citlivá na změny ve vstupních datech. Malé změny
vstupních dat se projeví velkým rozptylem řešení. Této problematice je
nutné věnovat pozornost při volbě algoritmu pro řešení dané numerické
úlohy. Matematickou úlohu lze chápat jako zobrazení
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_fd3a349e.gif){#Object1
align="bottom"} , které ke každému vstupnímu údaji x z množiny D
vstupních dat přiřadí výsledek z množiny R výstupních dat. Říkáme, že
matematická úloha
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_b3c8023c.gif){#Object2
align="bottom"} je korektní, když ke každému vstupu
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_31ee927e.gif){#Object3
align="bottom"} existuje jediné řešení
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_ca48de56.gif){#Object4
align="bottom"} a toto řešení závisí spojitě na vstupních datech.
Říkáme, že korektní úloha je dobře podmíněná, jestliže malá změna ve
vstupních datech vyvolá malou změnu v řešení. Mezi nekorektní úlohy
patří hlavně nejednoznačně řešitelné úlohy.

O [numerické
metodě](http://cs.wikipedia.org/wiki/Numerick%C3%A1_metoda){target="Numerická metoda"}
říkáme, že je konvergentní, pokud v nějakém smyslu lze touto metodou
získat libovolně přesné řešení dané úlohy. Obvykle se tak děje
snižováním kroku, nebo zvyšováním počtu uzlů, iterací apod.

Když chceme úspěšně řešit numerické úlohy, musíme si vybírat algoritmy,
kterým se říká stabilní. Stabilní algoritmus musí být dobře podmíněný
(málo citlivý na poruchy v datech) a numericky stabilní (málo citlivý na
vliv zaokrouhlovacích chyb během výpočtu na počítači).

Pokud interval
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_8f976223.gif){#Object5
align="bottom"} [ro]{lang="en-US"}zdělíme na konečný počet stejných
dílů, říkáme o rovnoměrném, ekvidistantním dělení intervalu
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_8f976223.gif){#Object6
align="bottom"} [.]{lang="en-US"}

![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_a57e399b.gif){#Object7
align="bottom"} [kde ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_33526568.gif){#Object8
align="bottom"} [ ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e408fc47.gif){#Object9
align="bottom"} [, ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_5ce70bcf.gif){#Object10
align="bottom"}

# []{#_Toc246343913}[]{#_Toc246343811}[]{#_Toc245736553}[]{#_Toc245440726} 2 Metody řešení nelineárních rovnic {#metody-řešení-nelineárních-rovnic .western}

Kořeny nelineární rovnice
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_479872fc.gif){#Object11
align="bottom"} obecně neumíme vyjádřit explicitním vzorcem. K řešení
nelineární rovnice proto používáme iterační metody (iterace -- opakované
použití té samé početní operace). Pro některé metody stačí, když zadáme
interval
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_8f976223.gif){#Object12
align="bottom"} [,kter]{lang="en-US"}ý obsahuje hledaný kořen. Jiné
metody vyžadují, aby počáteční aproximace (aproximace -- přibližná
hodnota) byla k hledanému kořenu blízko, takové metody konvergují mnohem
rychleji.

Když nemáme předběžné informace o poloze kořenů, pak použijeme k výpočtu
takovou iterační metodu, jejíž konvergence nezávisí na volbě počáteční
aproximace. Konverguje pomalu, její aproximace kořene je pak použita
jako počáteční aproximace pro nějakou zpřesňující konvergující metodu.

Metody řešení nelineárních rovnic můžeme rozdělit na dva typy:

a.  startovací metody (vždy konvergentní metody)

b.  zpřesňující metody

## []{#_Toc246343914}[]{#_Toc246343812}[]{#_Toc245736554}[]{#_Toc245440727} 2.1 Startovní metody {#startovní-metody .western}

Určení počáteční aproximace

Počáteční aproximaci kořenů rovnice
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_479872fc.gif){#Object13
align="bottom" vspace="60"} můžeme zjistit z grafu funkce
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_7f289311.gif){#Object14
align="bottom" vspace="60"} pomocí vhodného programu na počítači,
například v programu Excel. Z grafu funkce
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_7f289311.gif){#Object15
align="bottom" vspace="60"} zjistíme průsečíky s osu x. Reálný kořen
leží mezi body, ve kterých má funkce f(x) hodnoty s opačným znaménkem,
když
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_24e4657f.gif){#Object16
align="bottom" vspace="60"} [. Mezi body ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_54c8b775.gif){#Object17
align="bottom" vspace="60"} [ a ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_4dc35d4b.gif){#Object18
align="bottom" vspace="60"} [ leží reálný kořen rovnice ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_479872fc.gif){#Object19
align="bottom" vspace="60"} . Někdy je výhodné rovnici
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_479872fc.gif){#Object20
align="bottom" vspace="60"} psát ve tvaru
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_b196bcc2.gif){#Object21
align="bottom" vspace="60"} , kořeny pak určíme jako x-ové souřadnice
průsečíků grafů funkcí
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_43aee528.gif){#Object22
align="bottom" vspace="60"} a
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_884ad053.gif){#Object23
align="bottom" vspace="60"} .

![Shape2](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_73a2f4bc.gif){#Shape2
align="left" width="600" height="288"}\

### []{#_Toc246343813}[]{#_Toc245736556}[]{#_Toc246343915}[]{#_Toc245440729} ![Shape3](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_163c5c67.gif){#Shape3 align="left" hspace="12" width="600" height="288"}   {#shape3 .western}

###    {#section-1 .western}

###    {#section-2 .western}

### []{#_Toc246343916}[]{#_Toc246343814} 2.1.1 Metoda bisekce {#metoda-bisekce .western}

Je známá jako metoda půlení intervalů. Předpokládáme, že reálná funkce f
je spojitá pro
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_7c3e32ad.gif){#Object24
align="bottom"} . Stačí, když nalezneme dva body
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_413d6811.gif){#Object25
align="bottom"} takové, že
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_2fe0a7df.gif){#Object26
align="bottom"} [. To znamená, že funkce f má v těchto bodech různé
znaménko. Protože je funkce f spojitá, leží mezi body ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_413d6811.gif){#Object27
align="bottom"} alespoň jeden lořen.[ Sestro]{lang="en-US"}jíme
posloupnost intervalů

![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_ad2ea492.gif){#Object28
align="bottom"} , které obsahují kořen.\
Intervaly
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_d2f9bc72.gif){#Object29
align="bottom"} , k = 0,1, určíme takto:\
střed intervalu
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e15535f0.gif){#Object30
align="bottom"} je bod
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_bba45bff.gif){#Object31
align="bottom"} .\
Když
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_c519d09e.gif){#Object32
align="bottom"} , tak
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e9f1d960.gif){#Object33
align="bottom"} je kořen rovnice. Pokud
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_262faf35.gif){#Object34
align="bottom"} , určíme nový interval

![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_4ceb3caf.gif){#Object35
align="bottom" vspace="8"} když
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_f894150.gif){#Object36
align="bottom" vspace="8"} [, nebo interval ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_d9331adf.gif){#Object37
align="bottom" vspace="8"} [ ]{lang="en-US"}když
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_f0d30766.gif){#Object38
align="bottom" vspace="8"} [.\
Hledání kořene končí když ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_c519d09e.gif){#Object39
align="bottom" vspace="8"} [, ]{lang="en-US"}nebo když interval
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e15535f0.gif){#Object40
align="bottom" vspace="8"} je menší než požadovaná přesnost kořene.

![Shape4](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_cdcaf072.gif){#Shape4
align="bottom" hspace="12" width="600" height="348"}

[Tato metoda konverguje pomalu, nikdy však neselže. Lze ji doporučit
hlavně v případě když nemáme dostatečnou předběžnou informaci o poloze
kořene rovnice ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_479872fc.gif){#Object41
align="bottom"} [.]{lang="en-US"}

\

[Vývojový diagram pro metodu bisekce:]{lang="en-US"}

![Shape5](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e4713d9b.gif){#Shape5
align="left" width="521" height="898"}\

[Výpis programu: Microsoft Visual Basic -- makro aplikace Excel. Program
je umístěn v makru sešitu bisekce.xlsm.]{lang="en-US"}

\

### []{#_Toc246343917}[]{#_Toc246343815}[]{#_Toc245736557}[]{#_Toc245440730} 2.1.2 Metoda[ prosté iterace]{lang="en-US"} {#metoda-prosté-iterace .western}

[Rovnici ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_479872fc.gif){#Object42
align="bottom"} [ přepíšeme na tvar ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_12012941.gif){#Object43
align="bottom"} [. Předpoklad: existuje interval ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e8b45aa9.gif){#Object44
align="bottom"} [ patřící definičnimu oboru a oboru spojitosti funkce f
i funkce ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_6d3c284e.gif){#Object45
align="bottom"} [ takový, který obsahuje společný kořen ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_3db6585e.gif){#Object46
align="bottom"} [ obou uvedených rovnic a je pro něj splněna podmínka
]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_75a173f7.gif){#Object47
align="bottom"} [. Pomocí ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_12012941.gif){#Object48
align="bottom"} [ dostaneme posloupnost postupných aproximací
]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_55496fbd.gif){#Object49
align="bottom"} [ kořene ]{lang="en-US"}[]{lang="en-US"}[. Postupujeme
dle následujícího algoritmu:]{lang="en-US"}

1.  [zvolíme číslo ]{lang="en-US"}
    ![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_eedad37.gif){#Object50
    align="bottom"} [ a počáteční aproximaci ]{lang="en-US"}
    ![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_64147f65.gif){#Object51
    align="bottom"} [.]{lang="en-US"}

2.  [další aproximaci určíme z iterační formule ]{lang="en-US"}
    ![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_7b620432.gif){#Object52
    align="bottom"} [ k=1,2,3,]{lang="en-US"}[]{lang="en-US"}

3.  [když je ]{lang="en-US"}
    ![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_278dba88.gif){#Object53
    align="bottom"} [, pokračuje dle bodu 2, jinak výpočet zastavíme a
    ]{lang="en-US"}
    ![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e569c9e0.gif){#Object54
    align="bottom"} [ považujeme za aproximaci kořene ]{lang="en-US"}
    ![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_3db6585e.gif){#Object55
    align="bottom"} [.]{lang="en-US"}

\

[Podmínky konvergence pro metodu prosté iterace jsou:]{lang="en-US"}

1.  [funkce ]{lang="en-US"}[]{lang="en-US"}[ je na intervalu
    ]{lang="en-US"}
    ![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_83c87e11.gif){#Object56
    align="bottom"} [ spojitá]{lang="en-US"}

2.  ![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_b2b1e7d6.gif){#Object57
    align="bottom"}

3.  ![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_a136d372.gif){#Object58
    align="bottom"}

![Shape6](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_f5ff175a.gif){#Shape6
align="left" width="600" height="360"}\

[Výpis programu: Microsoft Visual Basic -- makro aplikace Excel. Program
je umístěn v makru sešitu IteracniMetoda.xlsm.]{lang="en-US"}

[]{#_Toc245736558}[]{#_Toc245440731}
![Shape7](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_3447489a.gif){#Shape7
align="left" width="461" height="721"}\

[Výpis programu: Microsoft Visual Basic -- makro aplikace
Excel.]{lang="en-US"}

[Program je umístěn v makru sešitu IteračniMetoda.xlsm.]{lang="en-US"}

\

### []{#_Toc246343816}[]{#_Toc246343918} [2.1.3 Metoda tětiv (regula falsi).]{lang="en-US"} {#metoda-tětiv-regula-falsi. .western}

\

[Předpoklady:]{lang="en-US"}

-   [funkce f(x) je v intervalu ]{lang="en-US"}
    ![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_8f976223.gif){#Object59
    align="bottom"} [ spojitá]{lang="en-US"}

-   [v koncových bodech intervalu ]{lang="en-US"}
    ![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_8f976223.gif){#Object60
    align="bottom"} [ platí: f(a).f(b)\<0]{lang="en-US"}

-   [rovnice f(x) má v intervalu ]{lang="en-US"}
    ![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_8f976223.gif){#Object61
    align="bottom"} [ jeden kořen]{lang="en-US"}

\

Body A=[\[a, f(a)\], B=\[b, f(b)\] se vede ]{lang="en-US"}úsečka
(tětiva). Průsečík přímky AB s osou x je zpřesnění kořene.

![Shape8](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_dab672cc.gif){#Shape8
align="left" width="600" height="252"} Pro výpočet aproximace kořene se
použije vztah:

![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_529dadf5.gif){#Object62
align="bottom"}

Když f(s)=0 nebo když
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_988a0fb4.gif){#Object63
align="bottom"} výpočet končí. Když
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_9fa8fc20.gif){#Object64
align="bottom"} nebo
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_c5ea32fc.gif){#Object65
align="bottom"} ( je číslo blízké nule) postupujeme takto:

Když f(s).f(b)\<0, přeznačíme s na a s počítáme dle stejného vztahu jako
předtím. Když f(s).f(b)\>0, přeznačíme s na b a počítáme dle stejného
vztahu jako předtím.

Metoda regula falsi je konvergentní pro všechny spojité funkce. Jedná se
o nestacionární metodu. Mnohokrát je stacionární, jeden krajní bod
intervalu je vždy jedním ze dvou bodů užitých v následující iteraci.
Metoda konverguje pomalu, je vhodná když nejsou známy výchozí údaje o
poloze kořenu. Rychlost konvergence metody regula falsi je lineární.

Používáme ji pro získání dobré počáteční aproximace, pak přecházíme na
rychlejší metodu.

[]{#_Toc238539126}
![Shape9](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_1e19790f.gif){#Shape9
align="left" width="459" height="884"}\

\

[Výpis programu: Microsoft Visual Basic -- makro aplikace Excel. Program
je umístěn v makru sešitu MetodaTetiv.xlsm.]{lang="en-US"}

\

\

## []{#_Toc246343919}[]{#_Toc246343817}[]{#_Toc245736560}[]{#_Toc245440733} 2.2 Zpřesňující metody {#zpřesňující-metody .western}

[Po startovací metodě řešení nelineární rovnice se přejde k rychleji
konvergující metodě, která slouží ke zpřesnění počítané aproximace
kořene.]{lang="en-US"}

### []{#_Toc246343920}[]{#_Toc246343818}[]{#_Toc245736561}[]{#_Toc245440734} [2.2.1 Newtonova metoda]{lang="en-US"} {#newtonova-metoda .western}

[]{#_Toc238539129} [Newtonova metoda je známá taky jako metoda tečen.
Vychází z počáteční aproximace ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_9e30a19f.gif){#Object66
align="bottom"} [ a postupně počítá ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_6481e1c5.gif){#Object67
align="bottom"} [, ]{lang="en-US"}[]{lang="en-US"}[\
Známe ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e569c9e0.gif){#Object68
align="bottom"} [ a lepší aproximaci ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e9f1d960.gif){#Object69
align="bottom"} [ určíme tak, že bodem ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_3d5412f4.gif){#Object70
align="bottom"} [ vedeme te]{lang="en-US"}čnu ke křivce\
y = f(x). Průsečík tečny s osou x je
[x]{lang="en-US"}![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_a81a5624.gif){#Object71
align="bottom"} [. Do rovnice tečny ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_19805a17.gif){#Object72
align="bottom"}
[]{lang="en-US"}![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_8552dc38.gif){#Object73
align="bottom"} [\
dosad]{lang="en-US"}íme
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_df63fbac.gif){#Object74
align="bottom"} , vypočteme x a položíme
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_5835171c.gif){#Object75
align="bottom"} [. Tak dostaneme předpis\
]{lang="en-US"}![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_b6ee3016.gif){#Object76
align="bottom"} [.\
]{lang="en-US"}![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e9f1d960.gif){#Object77
align="bottom"} [ je dostatečně velká aproximace kořene, pokud\
]{lang="en-US"}![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_9cddb16b.gif){#Object78
align="bottom"} [, případně ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_771ff4a.gif){#Object79
align="bottom"} [ nebo ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_1aa6b09d.gif){#Object80
align="bottom"} [,\
kde ]{lang="en-US"}[]{lang="en-US"}[ je požadovaná přesnost. Newtonova
metoda konverguje za předpokladu, když počáteční aproximaci zvolíme
dostatečně blízko ke kořenu.Program je umístěn v makru sešitu
MetodaTecen.xlsm]{lang="en-US"}

### []{#_Toc245440735}[]{#_Toc246343921}[]{#_Toc245736562}[]{#_Toc246343819} [2.2.2 Metoda sečen]{lang="en-US"} {#metoda-sečen .western}

[V každém kroku Newtonovy metody počítáme hodnotu ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_a5f28768.gif){#Object81
align="bottom"} [ a derivaci ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_b4fd2843.gif){#Object82
align="bottom"} [. Když je výpočet derivace náročný, nebo jej nemáme,
můžeme derivaci aproximovat podílem\
]{lang="en-US"}![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_1271637e.gif){#Object83
align="bottom"} [\
Tím dostaneme metodu sečen. Zadáme dvě počáteční aproximace
]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_9e30a19f.gif){#Object84
align="bottom"} [, ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_f212c110.gif){#Object85
align="bottom"} [ a počítáme další x dle předpisu\
]{lang="en-US"}![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e7c408f6.gif){#Object86
align="bottom"}

[]{#Frame1 dir="ltr"
style="float: left; width: 0.58in; border: none; padding: 0in; background: #ffffff"}

x![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_6a331710.gif){#Object87
align="bottom"}

![Shape11](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_57c4c4eb.gif){#Shape11
align="bottom" width="600" height="216"}

\

\

[Metoda sečen zaručeně konverguje, pokud zvolíme startovací hodnoty
]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_9e30a19f.gif){#Object88
align="bottom"} [ a ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_f212c110.gif){#Object89
align="bottom"} [ dostatečně blízko ke kořenu x. Metoda je použitelná v
případě, když ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_a0f4c5e5.gif){#Object90
align="bottom"} [, kde a je číslo blízké nule.]{lang="en-US"}

![Shape12](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_8f3349ea.gif){#Shape12
align="left" width="472" height="665"}\

\

\

[Program je umístěn v makru sešitu MetodaSečen.xlsm.]{lang="en-US"}

\

# []{#_Toc246343922}[]{#_Toc246343820}[]{#_Toc245736563}[]{#_Toc245440736} 3 Řešení soustav lineárních algebraických rovnic {#řešení-soustav-lineárních-algebraických-rovnic .western}

V praxi se často vyskytují úlohy vedoucí na soustavy lineárních rovnic,
které mají řádově stovky neznámých. Řešení takových úloh klade velké
požadavky na rychlost a kapacitu paměti počítače. Proto se efektivnost
metody či algoritmu posuzuje podle tři hlavních kritérií:

-   jak je algoritmus rychlý, kolik vyžaduje aritmetických operací

-   jaké požadavky klade algoritmus na paměť počítače

-   jaká je přesnost vypočteného řešení

V praxi je obtížné zjistit, zda je soustava vůbec řešitelná. Numerické
metody pro řešení soustavy lineárních rovnic se dělí na přímé metody a
iterační metody. Základním principem přímých metod je eliminace
neznámých. Pro plné matice jsou přímé metody většinou nejefektivnější.
Pro velká n je však jejich použití limitováno kapacitou paměti počítače.
Iterační metody jsou efektivnější pro některé typy řídkých matic a pro
velké soustavy.

Soustavu rovnic\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_eaa8b96b.gif){#Object91
align="bottom"}\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_44c6a4dc.gif){#Object92
align="bottom"} (1)\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_3f2d831b.gif){#Object93
align="bottom"}\
můžeme psát ve tvaru\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_da5c22b0.gif){#Object94
align="bottom"} , i = 1, 2, , n (2)\
nebo v maticovém tvaru\
Ax = b, (3)\
kde\
\
A =
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_bb85f2f0.gif){#Object95
align="bottom"} , x =
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_64da5ee.gif){#Object96
align="bottom"} , b =
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_abf35cf9.gif){#Object97
align="bottom"}\
\
Matici A nazýváme maticí soustavy, b je vektor pravé strany a x vektor
neznámých. Předpokládáme, že matice soustavy je regulární, řešená
soustava má jediné řešení.

## []{#_Toc246343923}[]{#_Toc246343821}[]{#_Toc245736564}[]{#_Toc245440737} 3.1 Přímé metody řešení soustav lineárních rovnic {#přímé-metody-řešení-soustav-lineárních-rovnic .western}

### []{#_Toc246343822}[]{#_Toc246343924}[]{#_Toc245440738}[]{#_Toc245736565} 3.1.1 Gaussova eliminační metoda {#gaussova-eliminační-metoda .western}

Soustava (1) se převede na ekvivalentní soustavu\
Ux = c,\
kde U je tzv. horní trojúhelníková matice, je to matice, která má pod
hlavní diagonálou všechny prvky nulové,\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_ee023759.gif){#Object98
align="bottom"} ,\
\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_9f8d0071.gif){#Object99
align="bottom"}

Z poslední rovnice vypočteme
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_d477198e.gif){#Object100
align="bottom"} , z předposlední
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_a0a086e2.gif){#Object101
align="bottom"} atd. až nakonec z první rovnice vypočteme
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_f212c110.gif){#Object102
align="bottom"} . Tomuto postupu říkáme zpětná substituce. Soustava má
jediné řešení, když součin diagonálních prvků je různý od nuly.\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_7a61ba3b.gif){#Object103
align="bottom"}\
Pokud při realizaci Gaussovy eliminace vycházejí pro prvky matice
redukované soustavy velká čísla je rozdíl přesného a vypočteného
výsledku nepřijatelně velký. Je to vlivem zaokrouhlovacích chyb. Říkáme,
že algoritmus Gaussovy eliminace je numericky nestabilní.

Vývojový diagram pro upravení matice -- nuly pod hlavní diagonálou.

\

![Shape13](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_32ee8b62.gif){#Shape13
align="left" width="514" height="810"}\

\

\

[]{#_Toc245736566}[]{#_Toc245440739} Vývojový diagram pro výpočet
kořenů.

![Shape14](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_9714f707.gif){#Shape14
align="left" width="408" height="878"}\

\

Program je uložen v makru sešitu GaussovaMetoda.xlsm.

\

### []{#_Toc246343925}[]{#_Toc246343823} 3.1.2 Gaussova metoda s výběrem hlavního prvku {#gaussova-metoda-s-výběrem-hlavního-prvku .western}

Je vylepšením Gaussovy eliminační metody. S rostoucími čísly v průběhu
Gaussovy eliminace roste i počet chyb. Proto je použit algoritmus výběru
hlavního prvku matice, tzv. pivotu. Pivot se vybírá v daném sloupci,
nebo v daném řádku, nebo v celé matici. V posledním případě mluvíme o
algoritmu úplného výběru hlavního prvku. Procházíme celou matici prvek
po prvku a hledáme prvek s největší absolutní hodnotou. Prvek
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_64e5e62e.gif){#Object104
align="bottom"} s největší absolutní hodnotou musíme dostat na pozici
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_60f41c65.gif){#Object105
align="bottom"} . Nejdříve prohodíme první a i-tý řádek a potom první a
j-tý sloupec. Současně se změní i vektor neznámých. Při eliminaci prvků
matice se prvky matice nemohou nějak dramaticky zvětšovat a neporoste
tedy vliv zaokrouhlovacích chyb. Nemůže se stát, že na pozici
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_60f41c65.gif){#Object106
align="bottom"} bude nula. Obvyklým způsobem eliminujeme prvky prvního
sloupce pod diagonálou a prvky přeznačíme. Pro
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_f1d90242.gif){#Object107
align="bottom"} opět provedeme výběr hlavního prvku, do výběru
nezahrneme 1. sloupec a první řádek. Eliminujeme prvky druhého sloupce.
V uvedeném postupu pokračujeme, až dostaneme trojúhelníkovou matici. Pak
použijeme zpětnou substituci k vyčíslení neznámých. Prohledání a
porovnávání prvků celé matice je proces, který, zejména u soustav o
větším počtu neznámých může vyvolat velké zdržení. Proto bývá často
výhodnější, omezit výběr pivotu pouze na daný sloupec, nebo řádek. Tím
dojde často ke zrychlení výpočtu při srovnatelné přesnosti.

Vývojový diagram pro výběr pivotu omezeného na sloupec.

![Shape15](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_9f519e0c.gif){#Shape15
align="left" width="506" height="900"}\

\

\

Program je uložen v makru sešitu GaussovaHlPrvek.xlsm

\

### []{#_Toc246343926}[]{#_Toc246343824}[]{#_Toc245736567}[]{#_Toc245440740} 3.1.3 Gaussova-Jordanova eliminační metoda {#gaussova-jordanova-eliminační-metoda .western}

Metoda se shoduje s Gaussovou eliminační metodou. Matice se dále
upravuje na jednotkovou matici. Z ní je pak patrné řešení soustavy
rovnic.

Diagramu Gaussové eliminační metody ukazuje jak se dostanou nuly pod
hlavní diagonálu.

Diagram pro nuly pod hlavní diagonálou uveden v Gaussivě eliminační
metodě.

Diagram pro nuly nad hlavní diagonálou.

\

P![Shape17](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_33c02c49.gif){#Shape17
align="left" width="374" height="723"} rogram je uložen v makru sešitu
GaussovaJordanovaMetoda.xlsm

\

## []{#_Toc246343927}[]{#_Toc246343825}[]{#_Toc245736568}[]{#_Toc245440741} 3.2 Iterační metody řešení soustav lineárních rovnic {#iterační-metody-řešení-soustav-lineárních-rovnic .western}

Zvolí se počáteční vektor
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_49fdffbf.gif){#Object108
align="bottom"} , a generuje se posloupnost vektorů
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_5e50e25d.gif){#Object109
align="bottom"} , která konverguje k hledanému řešení u. Společným rysem
všech iteračních metod je, že každý jednotlivý iterační krok
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_1460c9ee.gif){#Object110
align="bottom"} vyžaduje objem výpočtů srovnatelný s násobením matice A
vektorem. Přijatelný objem výpočtů lze dosáhnout i pro velký objem
iterací. Pro extremně rozsáhlé soustavy rovnic jsou vhodně zvolené
iterační metody často jedinou prakticky realizovatelnou metodou řešení.

Většina klasických iteračních metod vychází z rozkladu matice
soustavy![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_10cd0d30.gif){#Object111
align="bottom"} , kde M je regulární matice. Pak je posloupnost
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_b11bebbf.gif){#Object112
align="bottom"} definována předpisem\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_caf1397e.gif){#Object113
align="bottom"} ,\
přičemž počáteční aproximace
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_49fdffbf.gif){#Object114
align="bottom"} je daná.

Řekneme, že iterační metoda konverguje, a píšeme
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_41ab93b7.gif){#Object115
align="bottom"} , když číselná posloupnost\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_208fc4c9.gif){#Object116
align="bottom"} . Označme
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_2cf8672b.gif){#Object117
align="bottom"} chybu v k-té iteraci. Protože
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_56a29aa9.gif){#Object118
align="bottom"} , dostaneme\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_75f04148.gif){#Object119
align="bottom"} nebo-li
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_c148dee.gif){#Object120
align="bottom"} .Označíme-li
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_1fcb3a86.gif){#Object121
align="bottom"} , pak pomocí\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_127b4f9b.gif){#Object122
align="bottom"} dostaneme\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_89015250.gif){#Object123
align="bottom"} .\
Konvergence iterační metody z libovolného startovacího vektoru proto
jistě nastane, když\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_f1969b2e.gif){#Object124
align="bottom"} , kde
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_1fcb3a86.gif){#Object125
align="bottom"} je iterační matice. (1)\
Tato podmínka se neověřuje snadno, proto u konkrétních metod jsou
uvedeny jiné podmínky konvergence.\
Ukončení výpočtu se testuje tak, že uživatel zadá malé kladné číslo
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_b31b683e.gif){#Object126
align="bottom"} jako požadovanou přesnost a v každém kroku metody se
testuje, zda je už splněna jedna z následujících podmínek\
1.
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_93070005.gif){#Object127
align="bottom"}\
2.
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_85c573fa.gif){#Object128
align="bottom"} .\
Je ji podmínka na ukončení iterací splněna, výpočet přerušíme a
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_b8455d8d.gif){#Object129
align="bottom"} považujeme za přibližnou hodnotu řešení u.

U iteračních metod se zkoumá podmínka konvergence. Pokud jedna z níže
uvedených norem je menší než jedna, pak iterační metoda konverguje.

Řádková norma
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_daa2d729.gif){#Object130
align="bottom"} (maximální řádkový součet)

Sloupcová norma
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_420596dd.gif){#Object131
align="bottom"} (maximální sloupcový součet)

Euklidovská norma
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_bd17b0a1.gif){#Object132
align="bottom"}

\

### []{#_Toc246343928}[]{#_Toc246343826}[]{#_Toc245736569}[]{#_Toc245440742} 3.2.1 Jacobiova metoda {#jacobiova-metoda .western}

Předpokládáme, že A=L+D+U, kde D je diagonální matice, která má stejnou
diagonálu jako A, a kde L resp. U je ryze dolní resp. horní
trojúhelníková část A, tj.\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_79e3b110.gif){#Object133
align="bottom"} ,
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_411db0b0.gif){#Object134
align="bottom"} ,
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_5f09327b.gif){#Object135
align="bottom"} .

Nejjednodušší rozklad A dostaneme pro M=D a
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e259964f.gif){#Object136
align="bottom"} .\
Metoda je pak tvaru\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_82e97fe1.gif){#Object137
align="bottom"} (2)\
a je známa jako Jacobiova metoda. Zapíšeme-li (2) po složkách,
dostaneme\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_a181443b.gif){#Object138
align="bottom"} , i=1,2,,n.\
Tato metoda se v praxi používá málo, protože Gaussova-Seidelova metoda
konverguje i když Jacobiova metoda nekonverguje a Gaussova-Seidelova
metoda konverguje rychleji.

\

\

\

\

     

\

Vývojový diagram pro úpravu matice -- na hlavní diagonálu číslo 1:

\

![Shape18](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_dcef42a0.gif){#Shape18
align="left" width="287" height="630"}\

\

\

Program je uložen v makru sešitu JacobiovaMetoda.xlsm

### []{#_Toc246343929}[]{#_Toc246343827}[]{#_Toc245736570}[]{#_Toc245440743} 3.2.2 Gaussova-Seidelova metoda {#gaussova-seidelova-metoda .western}

Jacobiova metoda používá
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e569c9e0.gif){#Object139
align="bottom"} k výpočtu všech složek
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e9f1d960.gif){#Object140
align="bottom"} . Protože prvky vektoru
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e9f1d960.gif){#Object141
align="bottom"} počítáme postupně jeden za druhým, lze využít ty složky
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_e9f1d960.gif){#Object142
align="bottom"} , které jsou už k dispozici. Dostaneme
Gaussovu-Seidelovu metodu:

![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_d9063565.gif){#Object143
align="bottom"} , i=1,2,,n.

Když metodu vyjádříme v maticovém tvaru, dostaneme\
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_a07d56a7.gif){#Object144
align="bottom"} .\
Gaussova-Seidelova metoda konverguje, když A je ryze diagonálně
dominantní nebo pozitivně definitní.

\

Vývojový diagram pro zjištění symetričnosti matice:

![Shape19](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_a589cfa4.gif){#Shape19
align="left" width="431" height="558"}\

\

\

Vývojový diagram -- pozitivně definitní matice:

\

[]{#Frame2 dir="ltr"
style="float: left; width: 0.19in; border: none; padding: 0in; background: #ffffff"}

[-]{lang="en-US"}

![Shape20](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_44d27e16.gif){#Shape20
align="left" width="441" height="692"}\

\

Program je uložen v makru sešitu souboru GaussovaSeidelovaMetoda.xlsm

\

# []{#_Toc246343930}[]{#_Toc246343828}[]{#_Toc245736571}[]{#_Toc245440744} 4 Numerický výpočet určitého integrálu {#numerický-výpočet-určitého-integrálu .western}

Numerické metody výpočtu integrálu se používají, když je analytický
výpočet velmi pracný nebo když integrál není možné spočítat analytickými
metodami, nebo když je funkce f(x) daná jen tabulkou. Princip
numerických metod pro výpočet integrálu vychází z výsledků o aproximaci
funkcí. Danou funkci f nahradíme její vhodnou aproximací . Pak za
přibližnou aproximaci integrálu I(f) použijeme I(). Pro numerickou
aproximaci určitého integrálu se často používá termín numerická
kvadratura. Vzorce, které udávají aproximace určitých integrálů se
nazývají kvadraturní vzorce. Geometrický význam určitého integrálu je
obsah obrazce vymezený částí osy x, [grafem funkce]{lang="en-US"}
v intervalu [\<a,b\> a přímkami rovnoběžnými s osou y : x=a, x=b.
]{lang="en-US"}Přesnost aproximace při numerickém výpočtu integrálů se
zvyšuje postupným dělením intervalu [\<a,b\> a užíváním stejného vzorce
na jednotlivých dílčích intervalech. Interval \<a,b\> rozdělíme na
konečný počet ekvidistantních intervalů ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_ddc4607d.gif){#Object145
align="bottom"} [, ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_c400c32a.gif){#Object146
align="bottom"} [ a položíme ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_777273db.gif){#Object147
align="bottom"} [, kde ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_2df3adea.gif){#Object148
align="bottom"} [ je aproximací funkce f na intervalu ]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_c78f51a6.gif){#Object149
align="bottom"} [. Když sečteme vzorce pro jednotlivé intervaly
]{lang="en-US"}
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_c78f51a6.gif){#Object150
align="bottom"} [, j=1, 2, ]{lang="en-US"}[]{lang="en-US"}[,m,
dostaneme vzorec pro celý interval \<a,b\>.]{lang="en-US"}

[Níže uvedeným metodám se říká Newtonovy-Cotesovy kvadraturní
vzorce.]{lang="en-US"}

## []{#_Toc246343931}[]{#_Toc245736572}[]{#_Toc245440745}[]{#_Toc246343829} 4.1 Obdélníková metoda {#obdélníková-metoda .western}

Na interval
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_8f976223.gif){#Object151
align="bottom"} rozdělíme na n subintervalů stejné délky (ekvidistantní
intervaly). Funkci
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_7f289311.gif){#Object152
align="bottom"} nahradíme na každém subintervalu úsečkou rovnoběžnou
s osou x. Sečteme plochy jednotlivých obdélníků a dostaneme přibližnou
hodnotu
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_64e75c6b.gif){#Object153
align="bottom"} .

\

![Shape22](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_44fee1f9.gif){#Shape22
align="bottom" hspace="12" width="600" height="373"}

![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_fdebcc9f.gif){#Object154
align="bottom"}

\

![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_6baba060.gif){#Object155
align="bottom"}

nebo
![Shape23](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_da55794.gif){#Shape23
align="bottom" hspace="12" width="600" height="373"}

\

![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_2799bba8.gif){#Object156
align="bottom"}

\

Program je umístěn v makru sešitu UrčitýIntegrál.xlsm.

Vývojový diagram pro obdélníkovou metodu:

\

\

![Shape24](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_4b11af37.gif){#Shape24
align="left" width="287" height="587"}\

\

\

## []{#_Toc246343932}[]{#_Toc246343830}[]{#_Toc245736573}[]{#_Toc245440746} 4.2 Lichoběžníková metoda {#lichoběžníková-metoda .western}

Na interval
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_8f976223.gif){#Object157
align="bottom"} rozdělíme na n subintervalů stejné délky. V** **každém
subintervalu nahradíme funkci f(x) úsečkou spojující krajní body
příslušného subintervalu.

![Shape25](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_1cf6ad3f.gif){#Shape25
align="bottom" width="600" height="360"}

Součet ploch jednotlivých lichoběžníků je přibližná hodnota
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_64e75c6b.gif){#Object158
align="bottom"} .

![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_41aeda72.gif){#Object159
align="bottom"}

\

Program je umístěn v makru sešitu UrčitýIntegrál.xlsm.

Vývojový diagram pro lichoběžníkovou metodu:

\

![Shape26](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_92eb93e2.gif){#Shape26
align="left" width="359" height="643"}\

## []{#_Toc246343933}[]{#_Toc246343831}[]{#_Toc245736574}[]{#_Toc245440747} 4.3 Simpsonova metoda {#simpsonova-metoda .western style="page-break-before: always"}

Interval [\<a, b\> se ro]{lang="en-US"}zdělí na sudý konečný počet
subintervalů
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_49e736d6.gif){#Object160
align="bottom"} . Původní funkce y=f(x) se nahradí na sousedních
intervalech parabolou (interpolačním polynomem druhého stupně).

![Shape27](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_d927b352.gif){#Shape27
align="bottom" hspace="12" width="600" height="360"}

![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_36c86cbc.gif){#Object161
align="bottom"}

\

Program je umístěn v sešitu UrčitýIntegrál.xlsm.

Vývojový diagram pro Simpsonovu metodu:

\

![Shape28](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_7b3f8e69.gif){#Shape28
align="left" width="461" height="794"}\

\

\

## []{#_Toc246343832}[]{#_Toc246343934}[]{#_Toc245440748}[]{#_Toc245736575} 4.4 Rombergova metoda {#rombergova-metoda .western}

[]{#tady} Výpočet integrálu probíhá dle tohoto schématu:

\

T~00~

T~01~ T~10~

T~02~ T~11~ T~2,0~

~.~ . .

~.\ .\ .~

~.\ .\ .~

T~0m~ T~1,m-1~ T~2,m-2~ ... T~m0~

\

Hodnoty T~0k~ v prvním sloupci schématu se získají lichoběžníkovým
pravidlem s integračním krokem h = (b-a)/2^k^. Další hodnoty schématu se
postupně pro m=1,2, ... zaplňují podle vzorce
![](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_99fd29cd.gif){#Object162
align="bottom"} , k=0,1,...

\

Program je umístěn v makru sešitu UrčitýIntegrál.xlsm.

Vývojový diagram pro Rombergovu metodu:

\

\

![Shape29](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_bd5ec1f3.gif){#Shape29
align="left" width="363" height="704"}\

\

# []{#_Toc245440750}[]{#_Toc245440749}[]{#_Toc245439463}[]{#_Toc245439239}[]{#_Toc245736576}[]{#_Toc246343935}[]{#_Toc246343833} ![Shape30](Varga-z%25e1v%25ecre%25e8n%25e1%2520pr%25e1ce_html_c80406de.gif){#Shape30 align="left" width="348" height="767"} {#shape30 .western style="page-break-before: always"}

# []{#_Toc246343936}[]{#_Toc246343834}[]{#_Toc245736577} 5 Seznam použité literatury {#seznam-použité-literatury .western style="page-break-before: always"}

\

S.Míka, M.Brandner. Numerické metody I

Plzeň : Západočeská univerzita, 2000 1.vyd ISBN 80-7082-619-3

\

P. Přikryl, M.Brandner : Numerické metody II

V Plzni : Západočeská univerzita, 2000 1.vyd ISBN 80-7082-699-1

\

Anthony Ralston : Základy numerické matematiky

Praha : Academia, 1973 1. vyd

\

Karel Rektorys : Přehled užité matematiky I

\

Karel Rektorys : Přehled užité matematiky II

\

Pavel Kocur : Numerické metody

Studijní materiály katedry KVD ZČU

::: {title="footer"}
[]{#Frame4 dir="ltr"
style="position: absolute; top: 0in; left: 0in; width: 0.02in; border: none; padding: 0in; background: #ffffff"}

[37]{style="background: #c0c0c0"}
:::
