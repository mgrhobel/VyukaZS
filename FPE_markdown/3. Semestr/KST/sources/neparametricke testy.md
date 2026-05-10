---
title: "neparametricke testy.html"
source: "/mnt/f/git/mgr/FPE_navazujici/3. Semestr/KST/sources/neparametricke testy.html"
date: 2009-12-27
type: HTML
---

[![dal¹í](neparametricke%20testy_soubory/next_motif.gif){align="BOTTOM"
border="0"}](http://new.euromise.org/czech/tajne/ucebnice/html/html/node12.html){#tex2html370}
[![vý¹](neparametricke%20testy_soubory/up_motif.gif){align="BOTTOM"
border="0"}](http://new.euromise.org/czech/tajne/ucebnice/html/html/statist.html){#tex2html366}
[![pøedchozí](neparametricke%20testy_soubory/previous_motif.gif){align="BOTTOM"
border="0"}](http://new.euromise.org/czech/tajne/ucebnice/html/html/node10.html){#tex2html360}
[![obsah](neparametricke%20testy_soubory/contents_motif.gif){align="BOTTOM"
border="0"}](http://new.euromise.org/czech/tajne/ucebnice/html/html/node1.html){#tex2html368}
[![rejstøík](neparametricke%20testy_soubory/index_motif.gif){align="BOTTOM"
border="0"}](http://new.euromise.org/czech/tajne/ucebnice/html/html/node17.html){#tex2html369}\
**Dal¹í:** [10. Analýza kategoriálních
dat](http://new.euromise.org/czech/tajne/ucebnice/html/html/node12.html){#tex2html371}
**Vý¹:** [Základy statistiky pro biomedicínské
obory](http://new.euromise.org/czech/tajne/ucebnice/html/html/statist.html){#tex2html367}
**Pøedchozí:** [8. Porovnání dvou
skupin](http://new.euromise.org/czech/tajne/ucebnice/html/html/node10.html){#tex2html361}\

[**Kapitola**]{#CHILD_LINKS}

-   [9.1 Základní
    pojmy](http://new.euromise.org/czech/tajne/ucebnice/html/html/node11.html#SECTION001110000000000000000){#tex2html372}
-   [9.2 Kvantilový, mediánový a znaménkový
    test](http://new.euromise.org/czech/tajne/ucebnice/html/html/node11.html#SECTION001120000000000000000){#tex2html373}
-   [9.3 Wilcoxonùv párový
    test](http://new.euromise.org/czech/tajne/ucebnice/html/html/node11.html#SECTION001130000000000000000){#tex2html374}
-   [9.4 Mannùv-Whitneyùv
    test](http://new.euromise.org/czech/tajne/ucebnice/html/html/node11.html#SECTION001140000000000000000){#tex2html375}

------------------------------------------------------------------------

# []{#SECTION001100000000000000000} []{#chapnepar} 9. Neparametrické metody

> *®ádné statistické techniky nevytvoøí \"dobré\" výsledky z dat
> pochybné kvality.*\
>
> ::: {align="RIGHT"}
> M. Buyse
> :::

\

------------------------------------------------------------------------

# [9.1 Základní pojmy]{#SECTION001110000000000000000}

Dosud jsme se zabývali statistickými metodami, které zahrnovaly
pøedpoklady o rozdìlení dat. Existuje je¹tì jiná tøída statistických
metod, které nepøedpokládají konkrétní rozdìlení - nazývají se
neparametrické metody. Nejvíce se u¾ívají k analýze údajù, které
nevyhovují po¾adavkùm na rozdìlení v parametrických metodách, napøíklad
párovém a dvouvýbìrovém *t* testu. Zopakujme, ¾e v pøípadì párového
*t* testu jsme pøedpokládali, ¾e rozdíly jsou normálnì rozdìlené. Nìkdy
je jasné, ¾e rozdìlení nemù¾e být normální, u¾ pouhým pohledem na
normální graf. Zde nám pøi rozhodování, zda mìøení sledují normální
rozdìlení, opìt pomù¾e odborná znalost oboru. Urèování na základì malého
rozsahu výbìru je zpravidla naprosto nespolehlivé. Druhým dùvodem, proè
pou¾ívat neparametrické testy, je fakt, ¾e jsou èasto jedinou dostupnou
metodou pro urèité typy údajù, napøíklad pro ordinální data, poøadí nebo
èetnosti. Na druhou stranu mnohé testy, které jsou pova¾ované za
neparametrické, zahrnují parametry a rozdìlení. To je proto, ¾e se tyto
metody netýkají rozdìlení testových statistik, ale mohou být pou¾ívány
na výbìry pocházející z ¹iroké tøídy rozdìlení urèené pouze velmi
obecnými pøedpoklady, napø. symetrií rozdìlení. Nemusí mít nìjaké
konkrétní rozdìlení, jako napø. normální.

V posledním desetiletí do¹lo v oblasti neparametrických metod ke
znaènému rozvoji, hlavnì díky dostupnosti poèítaèù. Stalo se tak
pøedev¹ím v oblasti exaktních testù a intervalù spolehlivosti. Podrobný
výèet této oblasti viz
\[[15](http://new.euromise.org/czech/tajne/ucebnice/html/html/node16.html#Sprent)\].

V ka¾dém pøípadì, slab¹í pøedpoklady, které neodmyslitelnì patøí
k neparametrickým testùm, zpùsobují, ¾e tyto metody nejsou tak silné,
jako jejich parametrické protìj¹ky. A koneènì, a¾ do poslední doby se
neparametrické metody zamìøovaly hlavnì na testování hypotéz, a kladly
malý dùraz na odhad.

Zavedeme nyní pojem, který se v neparametrických metodách èasto
vyskytuje. Mìjme dána reálná èísla uspoøádaná podle velikosti ![\$x_1,
x_2, \\dots,
x_n\$](neparametricke%20testy_soubory/img469.gif){width="95"
align="MIDDLE" border="0" height="29"}. Jsou-li v¹echna tato èísla
vzájemnì rùzná, je poøadí èísla *x*~*i*~ dáno hodnotou indexu *i*.
[]{#10754}[]{#DEFPo_ad_}*Poøadí* *R*~*i*~ udává poèet èísel ![\$x_1,
x_2, \\dots,
x_n\$](neparametricke%20testy_soubory/img469.gif){width="95"
align="MIDDLE" border="0" height="29"}, která jsou men¹í nebo rovna
èíslu *x*~*i*~. Pøíklad pøiøazení poøadí vzájemnì rùzným hodnotám je
uveden v tabulce
[9.1](http://new.euromise.org/czech/tajne/ucebnice/html/html/node11.html#tab9_1).

\

::: {align="CENTER"}
[]{#10418}

+-----------------------------------------------------------------------+
|   -----------------------                                             |
| ---------------- ---------------------------------------------------- |
| ---------------------------------------------------- --- --- --- ---- |
|   Vzestupnì uspoøádané                                                |
| hodnoty *x*~*i*~   ![\$-2\$](neparametricke%20testy_soubory/img470.gi |
| f){width="25" align="MIDDLE" border="0" height="29"}   0   5   7   18 |
|   Poøadí *R*~*i*~                                                     |
|                     1                                                 |
|                                                         2   3   4   5 |
|   -----------------------                                             |
| ---------------- ---------------------------------------------------- |
| ---------------------------------------------------- --- --- --- ---- |
|                                                                       |
| []{#tab9_1}                                                           |
+-----------------------------------------------------------------------+

: **Tabulka 9.1:** Pøiøazení poøadí vzájemnì rùzným hodnotám
:::

\

Nìkdy se stane, ¾e èísla ![\$x_1, x_2, \\dots,
x_n\$](neparametricke%20testy_soubory/img469.gif){width="95"
align="MIDDLE" border="0" height="29"} nejsou rùzná, ale nìkterá z nich
jsou si rovna a vytváøejí tzv. []{#10762}[]{#DEFShody}*shody*. Èíslùm,
která tvoøí urèitou shodu, se pak pøiøazuje prùmìrné poøadí odpovídající
takové skupince. Pøíklad na pøiøazení poøadí hodnotám, které nejsou
rùzné, je uveden v tabulce
[9.2](http://new.euromise.org/czech/tajne/ucebnice/html/html/node11.html#tab9_2).

\

::: {align="CENTER"}
[]{#10438}

+-----------------------------------------------------------------------+
|   --                                                                  |
| ------------------------------------- ------------------------------- |
| --------------------------------------------------------------------- |
| ---- ---------------------------------------------------------------- |
| ---------------------------------------- --- --- --- ---- ----- ----- |
|                                                                       |
|  Vzestupnì uspoøádané hodnoty *x*~*i*~   ![\$-5\$](neparametricke%20t |
| esty_soubory/img471.gif){width="25" align="MIDDLE" border="0" height= |
| "29"}   ![\$-5\$](neparametricke%20testy_soubory/img471.gif){width="2 |
| 5" align="MIDDLE" border="0" height="29"}   0   0   0   10   21    21 |
|   Oèíslování hodnot *x*~*i*~              1                           |
|                                                                       |
|          2                                                            |
|                                              3   4   5   6    7     8 |
|                                                                       |
| Poøadí *R*~*i*~                         1,5                           |
|                                                                       |
|        1,5                                                            |
|                                            4   4   4   6    7,5   7,5 |
|   --                                                                  |
| ------------------------------------- ------------------------------- |
| --------------------------------------------------------------------- |
| ---- ---------------------------------------------------------------- |
| ---------------------------------------- --- --- --- ---- ----- ----- |
|                                                                       |
| []{#tab9_2}                                                           |
+-----------------------------------------------------------------------+

: **Tabulka 9.2:** Pøiøazení poøadí hodnotám v pøípadì shody
:::

\

Uspoøádat v¹ak lze nejen hodnoty kvantitativního znaku, ale i hodnoty
kvalitativního ordinálního znaku. Proto i tam, kde je vyjádøení
slo¾itìj¹ích vlastností èlenù souboru jedním nebo nìkolika
kvantitativními znaky obtí¾né nebo zcela nemo¾né, lze èasto uspoøádání
provést prostøednictvím vhodného ordinálního znaku, napøíklad pøi
posuzování nìkterých sportovních výkonù, ¹kolní klasifikace, hodnocení
záva¾nosti onemocnìní nebo posuzování sobìstaènosti handicapovaných
osob.

# [9.2 Kvantilový, mediánový a znaménkový test]{#SECTION001120000000000000000}

V  []{#10770}[]{#DEFKvantilov__test}*kvantilovém testu* vycházíme
z nulové hypotézy\

::: {align="CENTER"}
![\\begin{displaymath}H_0\\!\\!:\\ x_q = c,
\\end{displaymath}](neparametricke%20testy_soubory/img472.gif){width="78"
height="29"}
:::

\

¾e ![\$100q\\%\$](neparametricke%20testy_soubory/img473.gif){width="49"
align="MIDDLE" border="0" height="32"} kvantil základního souboru
*x*~*q*~ je roven dané konstantì *c*. Na základì náhodného výbìru
rozsahu *n* zjistíme poèet èlenù *m* v náhodném výbìru, u nich¾ hodnota
znaku *x* je men¹í ne¾ konstanta *c*, tj. *x* \< *c*. Zpravidla se pøed
touto operací v¹echna pozorování rovná hodnotì *c* z výbìru odstraní a
hodnota *n* se pøíslu¹nì zmen¹í.

Statistický test pro ovìøování odchylek od nulové hypotézy je zalo¾en na
velièinì\

::: {align="CENTER"}
  ------------------------------------------------------------------------------------------------------------------------------------------------------ -------
  ![\\begin{displaymath}Z = \\frac{m - nq}{\\sqrt{nq(1 - q)}}, \\end{displaymath}](neparametricke%20testy_soubory/img474.gif){width="116" height="45"}   (9.1)
  ------------------------------------------------------------------------------------------------------------------------------------------------------ -------
:::

\

která má pøi platnosti *H*~0~ standardizované normální rozdìlení.
V pøípadì oboustranné alternativní hypotézy\

::: {align="CENTER"}
![\\begin{displaymath}H_1\\!\\!: \\ x_q \\neq c
\\end{displaymath}](neparametricke%20testy_soubory/img475.gif){width="73"
height="29"}
:::

\

je kritickou hodnotou kvantil ![\$z\_{1 -
\\frac{\\alpha}{2}}\$](neparametricke%20testy_soubory/img304.gif){width="40"
align="MIDDLE" border="0" height="29"} standardizovaného normálního
rozdìlení, který nalezneme v tabulce
[A.1](http://new.euromise.org/czech/tajne/ucebnice/html/html/node15.html#kritNrozd).
Nulovou hypotézu zamítneme, pokud ![\$\\vert Z\\vert\\geq z\_{1 -
\\frac{\\alpha}{2}}\$](neparametricke%20testy_soubory/img476.gif){width="81"
align="MIDDLE" border="0" height="32"}.

Pro jednostrannou alternativu\

::: {align="CENTER"}
![\\begin{displaymath}H_1\\!\\!: \\ x_q \> c
\\end{displaymath}](neparametricke%20testy_soubory/img477.gif){width="73"
height="29"}
:::

\

je kritickou hodnotou kvantil
![\$z\_{\\alpha}\$](neparametricke%20testy_soubory/img478.gif){width="21"
align="MIDDLE" border="0" height="29"}, který opìt nalezneme v tabulce
[A.1](http://new.euromise.org/czech/tajne/ucebnice/html/html/node15.html#kritNrozd).
Nulovou hypotézu zamítneme, pokud ![\$Z\\leq
z\_{\\alpha}\$](neparametricke%20testy_soubory/img353.gif){width="53"
align="MIDDLE" border="0" height="30"}.

Pro jednostrannou alternativu\

::: {align="CENTER"}
![\\begin{displaymath}H_1\\!\\!: \\ x_q \< c
\\end{displaymath}](neparametricke%20testy_soubory/img479.gif){width="73"
height="29"}
:::

\

je kritickou hodnotou kvantil ![\$z\_{1 -
\\alpha}\$](neparametricke%20testy_soubory/img344.gif){width="37"
align="MIDDLE" border="0" height="29"} a nulovou hypotézu zamítneme,
pokud ![\$Z \\geq z\_{1 -
\\alpha}\$](neparametricke%20testy_soubory/img480.gif){width="69"
align="MIDDLE" border="0" height="30"}.

Popsaný test lze pou¾ít, jestli¾e *n* \> 30 a 0,10 \< *q* \< 0,90.
Speciálním pøípadem kvantilového testu je
[]{#10778}[]{#DEFMedi_nov__test}*mediánový test* pøi *q* = 0,50.
Dosazením do obecného vzorce testového kritéria pro kvantilový test
dostáváme, ¾e mediánový test je zalo¾en na velièinì\

::: {align="CENTER"}
  --------------------------------------------------------------------------------------------------------------------------------------------- -------
  ![\\begin{displaymath}Z = \\frac{2m - n}{\\sqrt{n}}. \\end{displaymath}](neparametricke%20testy_soubory/img481.gif){width="88" height="43"}   (9.2)
  --------------------------------------------------------------------------------------------------------------------------------------------- -------
:::

\

Jestli¾e sledovaná velièina má spojité symetrické rozdìlení (napø.
normální rozdìlení), je medián zároveò prùmìrem, tak¾e jde o test
hypotézy o prùmìru náhodné velièiny.

<div>

**Pøíklad 9.1**   Ve skupinì 49 chlapcù ve vìku 9,5-10 let
dispenzarizovaných v roce 1960 po dobu nejménì ètyø let pro jisté
onemocnìní bylo nalezeno 27 chlapcù men¹ích ne¾ 138,5 cm, kde 138,5 cm
je zji¹tìný prùmìr tìlesné vý¹ky v populaci chlapcù stejného vìku pøi
celostátním ¹etøení. Ovìøte na 5% hladinì významnosti, zda u nemocných
dìtí je prùmìrná vý¹ka men¹í ne¾ v odpovídající vìkové skupinì zdravých
dìtí.

*Øe¹ení:* Nulová hypotéza pøedpokládá, ¾e se dispenzarizovaní chlapci
v prùmìru neli¹í vý¹kovì od stejnì starých chlapcù v populaci, tj.\

::: {align="CENTER"}
![\\begin{displaymath}H_0\\!\\!:\\ x\_{0{,}50} = 138{,}5.
\\end{displaymath}](neparametricke%20testy_soubory/img482.gif){width="123"
height="29"}
:::

\

Alternativní hypotéza\

::: {align="CENTER"}
![\\begin{displaymath}H_1\\!\\!: \\ x\_{0{,}50} \< 138{,}5
\\end{displaymath}](neparametricke%20testy_soubory/img483.gif){width="117"
height="29"}
:::

\

vyjadøuje, ¾e dispenzarizovaní chlapci jsou v prùmìru men¹í. Vypoèteme
hodnotu testové statistiky\

::: {align="CENTER"}
![\\begin{displaymath}Z = \\frac{2\\cdot 27-49}{\\sqrt{49}} =
\\frac{5}{7} = 0{,}714.
\\end{displaymath}](neparametricke%20testy_soubory/img484.gif){width="195"
height="43"}
:::

\

Kritická hodnota pro jednostrannou alternativu a hladinu významnosti
![\$\\alpha =
0{,}05\$](neparametricke%20testy_soubory/img299.gif){width="63"
align="MIDDLE" border="0" height="29"} je kvantil ![\$z\_{1 - \\alpha} =
1{,}645\$](neparametricke%20testy_soubory/img346.gif){width="93"
align="MIDDLE" border="0" height="29"} (viz tabulku
[A.1](http://new.euromise.org/czech/tajne/ucebnice/html/html/node15.html#kritNrozd)),
tak¾e na 5% hladinì významnosti nelze nulovou hypotézu zamítnout. Na¹e
pozorování statisticky neprokázalo, ¾e onemocnìní brzdí rùst dìtí.
![\$\\Diamond\$](neparametricke%20testy_soubory/img40.gif){width="17"
align="BOTTOM" border="0" height="16"}

</div>

V pøípadì, ¾e hodnoty sledované velièiny jsou rozdíly párových
pozorování, u¾íváme pro mediánový test název
[]{#10787}[]{#DEFZnam_nkov__test}*znaménkový test*.

<div>

**Pøíklad 9.2**   Pøi kontrole pyrogenity infuzních roztokù se
zji¹»ovala ve skupinì 81 králíkù zmìna tìlesné teploty po injekci. U 47
králíkù se tìlesná teplota zvý¹ila. Ovìøte na 10% hladinì významnosti,
zda vzestup teploty po injekci je statisticky významný.

*Øe¹ení:* U ka¾dého králíka jsme zmìøili dvì hodnoty, pøed injekcí a po
injekci, které jsou párovì závislé. Reakce na podaný roztok je vyjádøena
pomocí diference *x* obou párových hodnot, ve zjednodu¹eném pøípadì
pouze znaménkem této diference. Kdyby byl injekèní roztok zcela
nepyrogenní, teplota zvíøat by kolísala jen nahodile, tak¾e zhruba
v polovinì pøípadù by mìlo být znaménko diference kladné.

Zvolíme tedy nulovou hypotézu

::: {align="CENTER"}
*H*~0~: *x*~0,50~ = 0, tj. roztok je nepyrogenní,
:::

kterou testujeme vùèi jednostranné alternativì\

::: {align="CENTER"}
![\\begin{displaymath}H_1\\!\\!: x\_{0{,}50} \> 0,
\\end{displaymath}](neparametricke%20testy_soubory/img485.gif){width="90"
height="29"}
:::

\

která vyjadøuje pyrogenitu roztoku pomocí zvy¹ování teploty. Dosazením
do vzorce pro výpoèet testové statistiky dostaneme\

::: {align="CENTER"}
![\\begin{displaymath}Z = \\frac{2\\cdot 34 - 81}{\\sqrt{81}} =
-\\frac{13}{9} = -1{,}444.
\\end{displaymath}](neparametricke%20testy_soubory/img486.gif){width="227"
height="43"}
:::

\

Pro hladinu významnosti ![\$\\alpha =
0{,}10\$](neparametricke%20testy_soubory/img487.gif){width="63"
align="MIDDLE" border="0" height="29"} je ![\$z\_{\\alpha} =
-1{,}282\$](neparametricke%20testy_soubory/img488.gif){width="89"
align="MIDDLE" border="0" height="29"}, jak zjistíme z tabulky
[A.1](http://new.euromise.org/czech/tajne/ucebnice/html/html/node15.html#kritNrozd).
Proto¾e ![\$Z = -1{,}444 \<
-1{,}282\$](neparametricke%20testy_soubory/img489.gif){width="153"
align="MIDDLE" border="0" height="30"}, zamítneme nulovou hypotézu a
dojdeme k závìru, ¾e na 10% hladinì významnosti je vzestup teploty
významný a roztok je pyrogenní. Vzhledem k tomu, ¾e pyrogenita je vá¾nou
závadou roztoku, zvolili jsme vy¹¹í, 10% hladinu významnosti, abychom
tak snáze zachytili podezøelé roztoky.
![\$\\Diamond\$](neparametricke%20testy_soubory/img40.gif){width="17"
align="BOTTOM" border="0" height="16"}

</div>

\
***Poznámka:*** Pøi popsané kontrolní zkou¹ce jsme nerespektovali
mo¾nost, ¾e vzestup teploty mù¾e zpùsobit i jiná pøíèina ne¾ pyrogenita
roztoku, napø. stres pøi vpichu jehly, rùzné pokusné podmínky pøi obou
mìøeních teploty apod. Chceme-li vylouèit jiné pøíèiny zvý¹ení teploty,
musíme pou¾ít standardního nepyrogenního roztoku v kontrolní skupinì
pokusných zvíøat. Potom srovnáváme procento zvý¹ení teploty v pokusech
s nepyrogenním placebem v kontrolní skupinì s kontrolovaným pøípravkem
v pokusné skupinì. Pøi men¹ím poètu pozorování (v praxi vìt¹inou pro *n*
\< 20) hledáme kritické hodnoty znaménkového testu ve speciálních
tabulkách. Znaménkový test je pøíkladem párového testu. V klinickém
výzkumu se dá výhodnì vyu¾ít v situaci, kdy zámìrnì vytváøíme páry
vzájemnì podobných jedincù. V ka¾dém takovém homogenním páru náhodnì
vylosujeme kontrolního jedince. Výsledky zji¹tìné u kontrolního a
pokusného jedince vytváøejí párová pozorování. Jedná-li se navíc o slepý
pokus, kdy není experimentátorovi známé, který jedinec je kontrolní,
hodí se znaménkový test i k posuzování slo¾itých vlastností, pokud je
experimentátor doká¾e ve dvojicích vzájemnì porovnat.

\

Nyní pøedstavíme nìkteré neparametrické testy, napøíklad neparametrickou
verzi párového a dvouvýbìrového *t* testu.

# [9.3 Wilcoxonùv párový test]{#SECTION001130000000000000000}

<div>

**Pøíklad 9.3**   []{#prParWil}Tabulka
[9.3](http://new.euromise.org/czech/tajne/ucebnice/html/html/node11.html#tabT4aT8)
udává poèet *T*~4~ a *T*~8~ bunìk/
![\$\\mbox{mm}\^3\$](neparametricke%20testy_soubory/img490.gif){width="38"
align="BOTTOM" border="0" height="18"} ve vzorcích krve 10 pacientù
v remisi Hodginsovy nemoci. Zajímá nás srovnání prùmìrného poètu *T*~4~
a *T*~8~ bunìk.

\

::: {align="CENTER"}
[]{#10704}

+-----------------------------------------------------------------------+
|   -------------------- --------------------                           |
|   Poèet *T*~4~ bunìk   Poèet *T*~8~ bunìk                             |
|   396                  236                                            |
|   568                  786                                            |
|   1212                 311                                            |
|   171                  449                                            |
|   554                  811                                            |
|   1104                 686                                            |
|   257                  412                                            |
|   435                  286                                            |
|   295                  336                                            |
|   397                  936                                            |
|   -------------------- --------------------                           |
|                                                                       |
| []{#tabT4aT8}                                                         |
+-----------------------------------------------------------------------+

: **Tabulka:** Poèty *T*~4~ a *T*~8~ bunìk v 1
![\$\\mbox{mm}\^3\$](neparametricke%20testy_soubory/img490.gif){width="38"
align="BOTTOM" border="0" height="18"} krve u 10 pacientù
:::

\

*Øe¹ení:* Z parametrických metod bychom pou¾ili párový *t* test, nebo»
oba znaky zji¹»ujeme na stejných pacientech, tak¾e se nejedná o dva
nezávislé výbìry. Jedním z pøedpokladù tohoto testu je, ¾e rozdíly
(poèet *T*~8~ bunìk
![\$-\$](neparametricke%20testy_soubory/img425.gif){width="17"
align="MIDDLE" border="0" height="29"} poèet *T*~4~ bunìk)
u jednotlivých pacientù jsou normálnì rozdìlené. Pokud nechceme uèinit
takový pøedpoklad, mohli bychom pou¾ít neparametrický test zvaný
[]{#10797}[]{#DEFWilcoxon_v_p_rov__test}*Wilcoxonùv párový test*.

V párovém *t* testu se nulová a alternativní hypotéza vztahovaly
k *prùmìru* rozdílù. U Wilcoxonova párového testu se hypotézy týkají
*mediánu* rozdílù:

::: {align="CENTER"}
  --------- ----------------------------------
  *H*~0~:   Medián rozdílù je nulový.
  *H*~1~:   Medián rozdílù je rùzný od nuly.
  --------- ----------------------------------
:::

Abychom mohli provést ná¹ statistický test, musíme nejprve vypoèítat
rozdíly pro ka¾dou osobu a poøadí absolutních hodnot rozdílù. Potom
pøipojíme znaménko rozdílu k poøadí. Výsledky ukazuje tabulka
[9.4](http://new.euromise.org/czech/tajne/ucebnice/html/html/node11.html#tabWilcTbunky).

\

::: {align="CENTER"}
[]{#10589}

+-----------------------------------------------------------------------+
|   -------------------- -------------------- -----                     |
| --------------------------------------------------------------------- |
| -------------------------------- ------------------------------------ |
| --------------------------------------------------------------------- |
|   Poèet *T*~4~ bunì                                                   |
| k   Poèet *T*~8~ bunìk   Rozdíl                                       |
|                                                                Poøadí |
|   396                  236                  ![                        |
| \$-160\$](neparametricke%20testy_soubory/img491.gif){width="40" align |
| ="MIDDLE" border="0" height="29"}   ![\$-4\$](neparametricke%20testy_ |
| soubory/img492.gif){width="25" align="MIDDLE" border="0" height="29"} |
|   568                                                                 |
|          786                  218                                     |
|                                                                     5 |
|   1212                 311                  ![\                       |
| $-901\$](neparametricke%20testy_soubory/img493.gif){width="40" align= |
| "MIDDLE" border="0" height="29"}   ![\$-10\$](neparametricke%20testy_ |
| soubory/img494.gif){width="33" align="MIDDLE" border="0" height="29"} |
|   171                                                                 |
|          449                  278                                     |
|                                                                     7 |
|   554                                                                 |
|          811                  257                                     |
|                                                                     6 |
|   1104                 686                  ![                        |
| \$-418\$](neparametricke%20testy_soubory/img495.gif){width="40" align |
| ="MIDDLE" border="0" height="29"}   ![\$-8\$](neparametricke%20testy_ |
| soubory/img496.gif){width="25" align="MIDDLE" border="0" height="29"} |
|   257                                                                 |
|          412                  155                                     |
|                                                                     3 |
|   435                  286                  ![                        |
| \$-149\$](neparametricke%20testy_soubory/img497.gif){width="40" align |
| ="MIDDLE" border="0" height="29"}   ![\$-2\$](neparametricke%20testy_ |
| soubory/img470.gif){width="25" align="MIDDLE" border="0" height="29"} |
|   295                                                                 |
|          336                  41                                      |
|                                                                     1 |
|   397                                                                 |
|          936                  539                                     |
|                                                                     9 |
|   -------------------- -------------------- -----                     |
| --------------------------------------------------------------------- |
| -------------------------------- ------------------------------------ |
| --------------------------------------------------------------------- |
|                                                                       |
| []{#tabWilcTbunky}                                                    |
+-----------------------------------------------------------------------+

: **Tabulka 9.4:** Rozdíly a poøadí rozdílù
:::

\
Pokud je nulová hypotéza pravdivá, tj. mediány se shodují, pak souèet
záporných poøadí by mìl být teoreticky roven souètu kladných poøadí.
Pokud je pravdivá alternativní hypotéza, pak toto neplatí.

V na¹em pøíkladu je souèet kladných poøadí ve výbìru 5 + 7 + 6 + 3 + 1 +
9 = 31 a souèet záporných poøadí je 4 + 10 + 8 + 2 = 24.

Souèty záporných a kladných hodnot jsou vzájemnì svázány, tak¾e staèí
vzít v úvahu jen jeden z nich. Pro na¹e úèely uva¾ujme pouze ni¾¹í
z obou hodnot, v tomto pøípadì 24. Nazvìme ji *S*.

Nyní urèíme hladinu významnosti ![\$\\alpha =
5\~\\%\$](neparametricke%20testy_soubory/img423.gif){width="62"
align="MIDDLE" border="0" height="32"} (oboustranný test) a v tabulce
[A.7](http://new.euromise.org/czech/tajne/ucebnice/html/html/node15.html#kritWilcox)
zjistíme pøíslu¹nou kritickou hodnotu. Pro *n* = 10 je daná kritická
hodnota 8. Pokud je *S* men¹í ne¾ tato hodnota, mù¾eme zamítnout nulovou
hypotézu. Pro ná¹ pøíklad je *S* = 24 \> 8, a proto nemáme dostateèný
dùkaz pro zamítnutí nulové hypotézy. Na základì zkoumaných dat nelze
uèinit závìr, ¾e u pacientù s Hodginovou nemocí je medián skupiny *T*~4~
bunìk odli¹ný od mediánu skupiny *T*~8~ bunìk. U vìt¹ích výbìrù mù¾e být
pou¾ita normální aproximace testové
statistiky *S*.![\$\\Diamond\$](neparametricke%20testy_soubory/img40.gif){width="17"
align="BOTTOM" border="0" height="16"}

</div>

# [9.4 Mannùv-Whitneyùv test]{#SECTION001140000000000000000}

<div>

[**Pøíklad 9.4**]{#prDeprese}   Údaje v tabulce
[9.5](http://new.euromise.org/czech/tajne/ucebnice/html/html/node11.html#tabDeprese)
pøedstavují délku remise ve dnech z prostého náhodného výbìru ze dvou
rùzných skupin pacientù - s endogenní depresí a s neurotickou depresí.
Opìt pøedpokládáme, ¾e pozorování v rámci skupiny jsou nezávislá - ka¾dý
pacient pøedstavuje jednu hodnotu. Zajímá nás, zda existuje rozdíl
v tìchto dvou rozdìleních.

</div>

\

::: {align="CENTER"}
[]{#10610}

+-----------------------------------------------------------------------+
|   ------------------------------ --------------------------------     |
|   Pacienti s endogenní depresí   Pacienti s neurotickou depresí       |
|   109                            546                                  |
|   214                            844                                  |
|   1818                           602                                  |
|   140                            87                                   |
|   179                            794                                  |
|   744                            643                                  |
|   108                            199                                  |
|   101                            91                                   |
|   107                            105                                  |
|   1547                           479                                  |
|   529                            1296                                 |
|   140                            279                                  |
|   ------------------------------ --------------------------------     |
|                                                                       |
| []{#tabDeprese}                                                       |
+-----------------------------------------------------------------------+

: **Tabulka 9.5:** Délka remise ve dnech u pacientù s depresí
:::

\

*Øe¹ení:* Obrázek
[9.1](http://new.euromise.org/czech/tajne/ucebnice/html/html/node11.html#krab45)
ukazuje krabicový graf porovnávající délku remise (ve dnech) pro obì
skupiny.

\

::: {align="CENTER"}
[]{#krab45}[]{#10616}

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ![\\begin{figure} \\centering \\fbox{\\includegraphics\[clip, width=\\sirka\]{eps/g45.eps}}\\end{figure}](neparametricke%20testy_soubory/img498.gif){width="434" height="300"}
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

  : **Obrázek 9.1:** Délka remise pro obì skupiny
:::

\

\

::: {align="CENTER"}
[]{#npp46}[]{#10621}

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ![\\begin{figure} \\centering \\fbox{\\includegraphics\[clip, width=\\sirka\]{eps/g46.eps}}\\end{figure}](neparametricke%20testy_soubory/img499.gif){width="434" height="300"}
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

  : **Obrázek 9.2:** Normální graf pro obì skupiny
:::

\

Obrázek
[9.2](http://new.euromise.org/czech/tajne/ucebnice/html/html/node11.html#npp46)
ukazuje normální graf (normal probability plot) pro obì skupiny. Je
z nìj vidìt, ¾e body na normálních grafech nele¾í na pøímce, ale tvoøí
spí¹e silnì zahnutou køivku. Pøedpoklad normálního rozdìlení pro délku
remise je proto tì¾ko udr¾itelný. K otestování rozdílù ve skupinových
prùmìrech proto nepou¾ijeme dvouvýbìrový *t* test, ale radìji
neparametrický test zvaný
[]{#10806}[]{#DEFMann_v-Whitney_v_test}*Mannùv-Whitneyùv* nebo také
*Wilcoxonùv dvouvýbìrový test*. []{#10817} Nulová a alternativní
hypotéza jsou vyjádøeny následujícím zpùsobem:

::: {align="CENTER"}
  --------- ----------------------------------
  *H*~0~:   Rozdìlení obou skupin je shodné.
  *H*~1~:   Rozdìlení obou skupin se li¹í.
  --------- ----------------------------------
:::

Test pokraèuje kombinováním obou výbìrù, seøazením pozorování od nízkých
hodnot po vysoké a potom stanovením poøadí pro ka¾dé pozorování.
Výsledky jsou uvedeny v tabulce
[9.6](http://new.euromise.org/czech/tajne/ucebnice/html/html/node11.html#tabMannWh).

\

::: {align="CENTER"}
[]{#10657}

+-----------------------------------------------------------------------+
|   -----                                                               |
| -------------- ---------------- -------------------- ---------------- |
|   End                                                                 |
| ogenní deprese   Celkové poøadí   Neurotická deprese   Celkové poøadí |
|   109                 \(7\)            546                  \(16\)    |
|   214                 \(12\)           844                  \(21\)    |
|   1818                \(24\)           602                  \(17\)    |
|   140                 \(8\)            87                   \(1\)     |
|   179                 \(10\)           794                  \(20\)    |
|   744                 \(19\)           643                  \(18\)    |
|   108                 \(6\)            199                  \(11\)    |
|   101                 \(3\)            91                   \(2\)     |
|   107                 \(5\)            105                  \(4\)     |
|   1547                \(23\)           479                  \(14\)    |
|   529                 \(15\)           1296                 \(22\)    |
|   150                 \(9\)            279                  \(13\)    |
|   -----                                                               |
| -------------- ---------------- -------------------- ---------------- |
|                                                                       |
| []{#tabMannWh}                                                        |
+-----------------------------------------------------------------------+

: **Tabulka 9.6:** Poøadí pacientù s depresí
:::

\
Dále spoèteme souèet poøadí pro 12 pacientù s endogenní depresí a pro 12
pacientù s neurotickou depresí.

Endogenní deprese: souèet poøadí *S*~1~ = 141, rozsah výbìru *n*~1~ =
12.

Neurotická deprese: souèet poøadí *S*~2~ = 159, rozsah výbìru *n*~2~ =
12.

Nyní spoèteme testové statistiky *U*~1~ a *U*~2~, kde\

::: {align="CENTER"}
  -------- --- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- -------
  *U*~1~   =   ![\$\\displaystyle S_1 - \\frac{n_1 (n_1 + 1)}{2} = 141 - \\frac{12\\cdot 13}{2} = 63,\$](neparametricke%20testy_soubory/img500.gif){width="265" align="MIDDLE" border="0" height="53"}   (9.3)
  *U*~2~   =   ![\$\\displaystyle S_2 - \\frac{n_2 (n_2 + 1)}{2} = 159 - \\frac{12\\cdot 13}{2} = 81.\$](neparametricke%20testy_soubory/img501.gif){width="265" align="MIDDLE" border="0" height="53"}   (9.4)
  -------- --- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- -------
:::

\

Mezi tìmito dvìma statistikami opìt existuje vzájemný vztah. Staèí nám
proto spoèítat pouze jednu z nich, napø. *U*~1~, a druhou vypoèteme ze
vzorce\

::: {align="CENTER"}
  ---------------------------------------------------------------------------------------------------------------------------------------------------- -------
  ![\\begin{displaymath}U_2 = n_1 n_2 - U_1 = 144 - 63 = 81, \\end{displaymath}](neparametricke%20testy_soubory/img502.gif){width="224" height="28"}   (9.5)
  ---------------------------------------------------------------------------------------------------------------------------------------------------- -------
:::

\

co¾ jsme dostali i vý¹e.

Nyní zvolíme hladinu významnosti ![\$\\alpha =
5\~\\%\$](neparametricke%20testy_soubory/img423.gif){width="62"
align="MIDDLE" border="0" height="32"} a v tabulce
[A.8](http://new.euromise.org/czech/tajne/ucebnice/html/html/node15.html#kritMW5)
nalezneme kritickou hodnotu pro rozsahy výbìrù *n*~1~ a *n*~2~. Nulovou
hypotézu zamítneme, pokud men¹í z èísel *U*~1~ a *U*~2~ je men¹í ne¾
kritická hodnota.

Pro ná¹ pøíklad ![\$(n_1 = 12,\\ n_2 = 12,\\ \\alpha =
0{,}05)\$](neparametricke%20testy_soubory/img503.gif){width="204"
align="MIDDLE" border="0" height="32"} je nalezená kritická hodnota 37
(viz tabulku
[A.8](http://new.euromise.org/czech/tajne/ucebnice/html/html/node15.html#kritMW5)).
Men¹í z èísel *U*~1~ a *U*~2~ je 63. Proto¾e 63 \> 37, nemù¾eme
zamítnout nulovou hypotézu. Nemáme tedy ¾ádný dùvod pro tvrzení, ¾e mezi
støední délkou remise v tìchto dvou skupinách je nìjaký rozdíl.

Tabulky
[A.8](http://new.euromise.org/czech/tajne/ucebnice/html/html/node15.html#kritMW5)
a
[A.9](http://new.euromise.org/czech/tajne/ucebnice/html/html/node15.html#kritMW1)
obsahují kritické hodnoty pro 5% a 1% hladinu významnosti pro rozsah
vìt¹ího výbìru ![\$n_1 \\leq
30\$](neparametricke%20testy_soubory/img504.gif){width="57"
align="MIDDLE" border="0" height="29"} a rozsah men¹ího výbìru ![\$n_2
\\leq 20\$](neparametricke%20testy_soubory/img505.gif){width="57"
align="MIDDLE" border="0" height="29"}. Pro vìt¹í hodnoty *n*~1~ a
*n*~2~ mù¾eme pou¾ít normální aproximaci\

::: {align="CENTER"}
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- -------
  ![\\begin{displaymath}Z = \\frac{U_1 - \\frac{1}{2}n_1 n_2}{\\sqrt{\\frac{1}{12}n_1 n_2 (n_1 + n_2 + 1)}}. \\end{displaymath}](neparametricke%20testy_soubory/img506.gif){width="192" height="59"}   (9.6)
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- -------
:::

\

Pro zvolenou hladinu významnosti
![\$\\alpha\$](neparametricke%20testy_soubory/img341.gif){width="15"
align="BOTTOM" border="0" height="16"} je kritickou hodnotou kvantil
![\$z\_{1 -
\\frac{\\alpha}{2}}\$](neparametricke%20testy_soubory/img304.gif){width="40"
align="MIDDLE" border="0" height="29"} standardizovaného normálního
rozdìlení, který nalezneme v tabulce
[A.1](http://new.euromise.org/czech/tajne/ucebnice/html/html/node15.html#kritNrozd).
![\$\\Diamond\$](neparametricke%20testy_soubory/img40.gif){width="17"
align="BOTTOM" border="0" height="16"}

Uvedené dva testy jsou pøíklady neparametrických testù. Podrobnìj¹í
informace o výbìrech vìt¹ích rozsahù ne¾ 20 (pou¾ití normální
aproximace) a pojednání o shodách lze nalézt napøíklad
v \[[15](http://new.euromise.org/czech/tajne/ucebnice/html/html/node16.html#Sprent)\].
Mnohé z novìj¹ích statistických programù obsahují i èást
s neparametrickými statistickými metodami, kterými se v tomto dílu
sbírky podrobnìji nezabýváme.

Závìrem lze øíci, ¾e neparametrické testy se pou¾ívají na data, u nich¾
lze snadno urèit uspoøádané hodnoty, poøadí nebo èetnosti. Pou¾ívají se
také k analýze dat, která neodpovídají rozdìlení pøedpokládanému
v parametrických metodách, jako je napøíklad párový nebo dvouvýbìrový
*t* test. Aèkoli nepøedpokládají normální rozdìlení, nejsou úplnì bez
pøedpokladù. A koneènì, nìkteré neparametrické metody vy¾adují pouze
minimální informaci. Pøedpokládejme, ¾e chceme testovat, mají-li váhy
pøedmìtù v jistém vzorku urèitý pøedem daný medián *M*. Z provozních
dùvodù pøitom nelze získat pøesná mìøení, ale je mo¾né urèit, zda jsou
pøedmìty tì¾¹í, èi lehèí ne¾ *M*. U tohoto typu údajù mù¾eme s výhodou
pou¾ít právì neparametrický mediánový test.

------------------------------------------------------------------------

[![dal¹í](neparametricke%20testy_soubory/next_motif.gif){align="BOTTOM"
border="0"}](http://new.euromise.org/czech/tajne/ucebnice/html/html/node12.html){#tex2html370}
[![vý¹](neparametricke%20testy_soubory/up_motif.gif){align="BOTTOM"
border="0"}](http://new.euromise.org/czech/tajne/ucebnice/html/html/statist.html){#tex2html366}
[![pøedchozí](neparametricke%20testy_soubory/previous_motif.gif){align="BOTTOM"
border="0"}](http://new.euromise.org/czech/tajne/ucebnice/html/html/node10.html){#tex2html360}
[![obsah](neparametricke%20testy_soubory/contents_motif.gif){align="BOTTOM"
border="0"}](http://new.euromise.org/czech/tajne/ucebnice/html/html/node1.html){#tex2html368}
[![rejstøík](neparametricke%20testy_soubory/index_motif.gif){align="BOTTOM"
border="0"}](http://new.euromise.org/czech/tajne/ucebnice/html/html/node17.html){#tex2html369}\
**Dal¹í:** [10. Analýza kategoriálních
dat](http://new.euromise.org/czech/tajne/ucebnice/html/html/node12.html){#tex2html371}
**Vý¹:** [Základy statistiky pro biomedicínské
obory](http://new.euromise.org/czech/tajne/ucebnice/html/html/statist.html){#tex2html367}
**Pøedchozí:** [8. Porovnání dvou
skupin](http://new.euromise.org/czech/tajne/ucebnice/html/html/node10.html){#tex2html361}

*Tato stránka byla naposledy zmìnìna dne 5. ledna 1999.\
*
