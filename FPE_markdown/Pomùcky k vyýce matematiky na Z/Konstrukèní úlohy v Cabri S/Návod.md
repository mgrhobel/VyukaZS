---
title: "Návod.doc"
source: "/mnt/f/git/mgr/FPE_navazujici/Pomùcky k vyýce matematiky na Z/Konstrukèní úlohy v Cabri S/Návod.doc"
date: 2005-12-20
type: DOC
---

**Návod k použití souborů**

\

Konstrukční úlohy můžeme v Cabri geometrii zadávat pomocí zde uložených
souborů s ovladači. Jeden z ovladačů i s doplněným zadáním úlohy je na
obrázku. Je možné jej na obrazovce přemisťovat pomocí myši úchopem za
levý horní krajní bod. Podobně úchopem za levý dolní krajní bod lze
měnit „výšku" ovladače, tj. svislé mezery mezi jeho prvky. Úchopem za
pravé koncové body prvků ovladače (přesněji pravé krajní body úseček
nebo koncové body vektorů úhlových prvků ovladače) nastavujeme hodnoty
zadaných prvků útvaru, který máme sestrojit. Čtenář si může podobná
zadání konstrukcí trojúhelníků a některých čtyřúhelníků snadno
připravovat v Cabri sám.

Ve složce „1 ZADÁNÍ" jsou soubory se zadáním úloh, které byly připraveny
pro dílnu na konferenci. Složka „2 MOJE KONSTRUKCE" je prázdná a má
sloužit k ukládání řešených úloh, které si uživatel sám sestaví. Složky
„3 VYŘEŠENÉ V CABRI II" a „4 VYŘEŠENÉ V CABRI II+" obsahují soubory
vyřešených úloh z první složky. Poslední složka „5 OVLADAČE" nabízí
trojprvkové a čtyřprvkové ovladače, přičemž názvy souborů inzerují typ
ovladače. Například *S_s_s.fig* znamená ovladač se třemi délkovými
prvky, *U_u_s_s.fig* ovladač, pomocí nějž můžeme zadávat dva úhly a dvě
délky, apod. Zadání úlohy v Cabri připravíme pomocí vhodného souboru ze
složky 5 tak, že jej otevřeme, pomocí nabídky *Texty* napíšeme zadání a
pomocí nabídky *Názvy* přepíšeme označení jednotlivých prvků ovladače na
symboly, které požaduje text úlohy.

\

Příklady řešení úloh, tvorby souborů a jejich využití:

\

**Úloha** ** **1** (*05_alfa_a_c.fig*): Sestrojte trojúhelník *ABC*,
je-li dáno ![](N%C3%A1vod_html_a2efcbe.gif){#Object1 align="absmiddle"
width="55" height="18"} (Viz obr. 1, kopii interaktivního obrázku, do
nějž žák může přímo rýsovat řešení.)

![](N%C3%A1vod_html_5827ca53.png){#Image1 align="left" hspace="12"
width="178" height="180"}\
\

![](N%C3%A1vod_html_481a9241.png){#Image2 align="left" hspace="12"
width="360" height="166" border="0"}\

Obr. 1: Zadání úlohy v souboru *05_alfa_a_c.fig* Obr. 2: Rozbor úlohy 1

\

*Rozbor*: Při rozboru vycházíme z náčrtku, který lze provést tradičním
způsobem (na tabuli, na papír) nebo přímo v Cabri (obr. 2). Začneme-li
umístěním úsečky *AB* délky *c*, zbývá najít vrchol *C*. Z podmínky
![](N%C3%A1vod_html_489c00e9.gif){#Object2 align="absmiddle" width="83"
height="19"} plyne, že bod *C* leží na ramenu *AX* úhlu *BAX* o
velikosti ![](N%C3%A1vod_html_c1f015a3.gif){#Object3 align="absmiddle"
width="17" height="18"} Z podmínky
![](N%C3%A1vod_html_90de7ac7.gif){#Object4 align="absmiddle" width="55"
height="19"} plyne, že též leží na kružnici
![](N%C3%A1vod_html_529f278c.gif){#Object5 align="absmiddle" width="64"
height="19"} Je tedy v průsečíku obou čar.

\

*Popis konstrukce v Cabri*: Sestrojíme pomocnou polopřímku, její počátek
označíme *A* (nabídka *Názvy*). Pomocí funkce *Nanést délku* naneseme na
polopřímku délku *c* (tzn. číslo 6,80 cm z údaje na ovladači, je-li
tento nastaven podle obr. 1). Vzniklý bod označíme *B*. Nyní můžeme body
*A*, *B* spojit úsečkou a skrýt pomocnou polopřímku. Bod X získáme
například otočením bodu *B* kolem bodu *C* jako středu otáčení o úhel
![](N%C3%A1vod_html_c1f015a3.gif){#Object6 align="absmiddle" width="17"
height="18"} (Nabídka *Otočení*, klepneme levým tlačítkem myši na bod
*B*, pak na bod *A* a nakonec na číslo, které ukazuje velikost
nastaveného úhlu ovladače. Pro situaci na obr. 1 je to
![](N%C3%A1vod_html_f08ff568.gif){#Object7 align="absmiddle" width="60"
height="21"} Dále vytvoříme polopřímku *AX*. Kdybychom ještě sestrojili
polopřímku ![](N%C3%A1vod_html_1068f71c.gif){#Object8 align="absmiddle"
width="31" height="20"} souměrnou s polopřímkou *AX* podle přímky *AB*,
nevznikla by nová řešení.^[^1^](#sdfootnote1sym){#sdfootnote1anc
.sdfootnoteanc}^ Vznikly by jen trojúhelníky shodné s těmi, které
sestrojíme v rovině *ABX*. Kružnici *m* sestrojíme pomocí funkce
*Kružítko*: Nejprve klikneme na údaj délky *a* ovladače (tzn. 5,00 cm
při nastavení podle obr. 1), pak na střed *B* sestrojované kružnice.
Průsečíky kružnice *m* a polopřímky *AX* označíme *C1* a *C2*. Nakonec
provedeme estetické úpravy: Pomocí nabídky *Trojúhelník* sestrojíme
trojúhelníky *ABC1*, *ABC2*, zvýrazníme je například volbou středně
silné čáry a černou barvou (nabídky *Tloušťka čáry* a *Obarvit*),
pomocné čáry obarvíme světlejší barvou nebo je vyznačíme čárkovaně
(nabídka *Typ čáry*).

\

Názornou ukázku provedení i se zápisem postupu konstrukce můžeme vidět
na obr. 3.^[^2^](#sdfootnote2sym){#sdfootnote2anc .sdfootnoteanc}^ Pokud
si takto vytvořený soubor uložíme (a máme učebnu vybavenou
dataprojektorem), můžeme z něj celou konstrukci při výkladu nebo
opakování učiva frontálně demonstrovat pomocí nabídky *Historie* (v
Cabri II+ je to nabídka *Krokovat konstrukci*).

\

![](N%C3%A1vod_html_4ee5791e.png){#Image3 align="left" hspace="12"
width="604" height="282"}\
\

\

Obr. 3: Provedení konstrukce úlohy 1

\

\

*Metodika provedení diskuse*: Jak uvádí poznámka 2 pod čarou, závisí
počet řešení na počtu průsečíků kružnice *m* a polopřímky *AX*. Názorné
prozkoumání pomocí Cabri můžeme provést takto:

Na ovladači nastavme nejprve ostrý úhel
![](N%C3%A1vod_html_289770e.gif){#Object9 align="absmiddle" width="12"
height="18"} a hodně malou (resp. nulovou) hodnotu *a*, například
![](N%C3%A1vod_html_800083b.gif){#Object10 align="absmiddle" width="116"
height="20"} cm, ![](N%C3%A1vod_html_1eaf5b94.gif){#Object11
align="absmiddle" width="56" height="18"} cm. Kružnice *m* má
s polopřímkou *AX* prázdný průnik, trojúhelník neexistuje.

Jestliže nyní zvětšujeme *a*, přičemž ostatní hodnoty neměníme, objeví
se dva téměř shodné trojúhelníky
![](N%C3%A1vod_html_2923bdd1.gif){#Object12 align="absmiddle" width="87"
height="21"} až pro ![](N%C3%A1vod_html_2e5bf879.gif){#Object13
align="absmiddle" width="59" height="21"} cm. Jediné řešení by mělo
nastat v případě dotyku uvažované kružnice a polopřímky, což se nám asi
nepodaří nastavit. Ručním ovládáním totiž zadané veličiny měníme po
skocích velikosti několika setin milimetru. Dalším zvětšováním délky *a*
se rozdíl tvaru sestrojených trojúhelníků stále více liší. Pro
![](N%C3%A1vod_html_9e8b6067.gif){#Object14 align="absmiddle" width="56"
height="18"} cm již trojúhelník
![](N%C3%A1vod_html_867bdb91.gif){#Object15 align="absmiddle" width="41"
height="21"} téměř splývá s úsečkou *AB*, ale je ještě rozeznatelný. Pro
![](N%C3%A1vod_html_99dd04f6.gif){#Object16 align="absmiddle" width="56"
height="18"} cm se jeví úsečky *AB* a
![](N%C3%A1vod_html_a130e0aa.gif){#Object17 align="absmiddle" width="31"
height="21"} totožné, pro ![](N%C3%A1vod_html_b2749f1c.gif){#Object18
align="absmiddle" width="54" height="18"} cm bod
![](N%C3%A1vod_html_5766c777.gif){#Object19 align="absmiddle" width="19"
height="21"} neexistuje.

Analogicky vyšetříme situace pro
![](N%C3%A1vod_html_974f2716.gif){#Object20 align="absmiddle" width="47"
height="20"} . Diskusi pak shrneme
takto^[^3^](#sdfootnote3sym){#sdfootnote3anc .sdfootnoteanc}^:

\

I. Pro ![](N%C3%A1vod_html_79ec2c2d.gif){#Object21 align="absmiddle"
width="65" height="20"} nemá úloha řešení, je-li poloměr *a* kružnice
*m* menší než vzdálenost d bodu *B* od přímky *AX*. Dále má jediné
řešení, je-li ![](N%C3%A1vod_html_ab13ac82.gif){#Object22
align="absmiddle" width="33" height="18"} a dvě řešení pro
![](N%C3%A1vod_html_44b43d25.gif){#Object23 align="absmiddle" width="56"
height="18"} Je-li ![](N%C3%A1vod_html_1bf085a8.gif){#Object24
align="absmiddle" width="38" height="18"} má úloha jedno řešení.

II\. Pro ![](N%C3%A1vod_html_974f2716.gif){#Object25 align="absmiddle"
width="47" height="20"} má úloha jediné řešení, jestliže
![](N%C3%A1vod_html_33c28d76.gif){#Object26 align="absmiddle" width="30"
height="18"} , a nemá řešení pro
![](N%C3%A1vod_html_f3717168.gif){#Object27 align="absmiddle" width="38"
height="18"}

\

*Poznámka*: Vytvořenou pomůcku můžeme využít pro zdůvodnění věty Ssu o
shodnosti trojúhelníků. Na obr. 3 vidíme dva trojúhelníky
![](N%C3%A1vod_html_68e23377.gif){#Object28 align="absmiddle" width="40"
height="21"} a ![](N%C3%A1vod_html_7a27fdad.gif){#Object29
align="absmiddle" width="47" height="21"} které se shodují ve dvou
stranách a úhlu proti menší z nich, a nelze je přemístit, aby se kryly.
Pokud však nastavíme situaci tak, aby platilo
![](N%C3%A1vod_html_645d3313.gif){#Object30 align="absmiddle" width="35"
height="18"} je trojúhelník *ABC* určen jednoznačně. Trojúhelníky, které
se shodují ve dvou stranách a úhlu proti větší z nich, tedy musí být
shodné.

\

**Úloha 2** (*04_c_va_vb 1.fig*): Sestrojte trojúhelník *ABC*, je-li
dáno ![](N%C3%A1vod_html_1a5c390b.gif){#Object31 align="absmiddle"
width="66" height="21"}

\

*R![](N%C3%A1vod_html_73f087c3.png){#Image4 align="left" hspace="12"
width="221" height="212" border="0"} ozbor*: Začneme-li umístěním úsečky
*AB* délky *c*, zbývá najít vrchol *C*. Označme po řadě *P*, *Q* paty
výšek z vrcholů *A*, *B* (obr. 4). Pak bod *C* je průsečíkem přímek *AQ*
a *BP*. Tím jsme úlohu převedli na nalezení bodů *P*, *Q*. Z podmínky
kolmosti ke stranám *BC* a *AC* plyne, že oba tyto body leží na
Thaletově kružnici *th* s průměrem *AB*. Z podmínky
![](N%C3%A1vod_html_af520934.gif){#Object32 align="absmiddle" width="60"
height="21"} plyne, že P leží na kružnici
![](N%C3%A1vod_html_8abae15.gif){#Object33 align="absmiddle" width="72"
height="22"} analogicky z podmínky
![](N%C3%A1vod_html_34229ad1.gif){#Object34 align="absmiddle" width="61"
height="21"} zjistíme ![](N%C3%A1vod_html_d410d104.gif){#Object35
align="absmiddle" width="98" height="22"} Platí tedy
![](N%C3%A1vod_html_a23df4de.gif){#Object36 align="absmiddle"
width="123" height="22"} a ![](N%C3%A1vod_html_1b8ae75a.gif){#Object37
align="absmiddle" width="124" height="22"} Odtud je již zřejmá
konstrukce, kterou již nebudeme podrobněji rozepisovat, neboť zásady
sestrojení v Cabri jsou stejné, jako u předchozí úlohy.  Obr. 4: Rozbor
úlohy 2

\

\

Kopii výsledného obrázku můžeme i se zápisem postupu konstrukce vidět na
obr. 5. Průsečík přímek ![](N%C3%A1vod_html_ade0241d.gif){#Object38
align="absmiddle" width="32" height="21"} a
![](N%C3%A1vod_html_5259a531.gif){#Object39 align="absmiddle" width="29"
height="21"} vede na trojúhelník souměrný s trojúhelníkem
![](N%C3%A1vod_html_2fd18b1a.gif){#Object40 align="absmiddle" width="40"
height="21"} a nepředstavuje tedy další řešení úlohy. Stejně tak
průsečík přímek ![](N%C3%A1vod_html_7848973b.gif){#Object41
align="absmiddle" width="31" height="21"} a
![](N%C3%A1vod_html_5259a531.gif){#Object42 align="absmiddle" width="29"
height="21"} by představoval řešení shodné s trojúhelníkem
![](N%C3%A1vod_html_aca533e3.gif){#Object43 align="absmiddle" width="47"
height="21"}

\

Počet řešení vyšetřujeme analogicky, jako u předchozí úlohy,
problematická místa konstrukce představují body 4, 5 a 6. Zkoumáme
nejprve vztah délek *c* a ![](N%C3%A1vod_html_d353dc91.gif){#Object44
align="absmiddle" width="22" height="21"} pak *c* a
![](N%C3%A1vod_html_5e6b85ab.gif){#Object45 align="absmiddle" width="22"
height="21"} Nakonec zformulujeme diskusi:

\

I. Je-li ![](N%C3%A1vod_html_78dec88a.gif){#Object46 align="absmiddle"
width="35" height="21"} nebo ![](N%C3%A1vod_html_17a1ee4b.gif){#Object47
align="absmiddle" width="41" height="21"} nemá úloha řešení.

\

II\. Pro ![](N%C3%A1vod_html_32c74f66.gif){#Object48 align="absmiddle"
width="38" height="21"} a ![](N%C3%A1vod_html_86b1b0c9.gif){#Object49
align="absmiddle" width="35" height="21"} dostaneme jediné řešení,
například trojúhelník ![](N%C3%A1vod_html_2fd18b1a.gif){#Object50
align="absmiddle" width="40" height="21"} s pravým úhlem při vrcholu
*B*. Podobně pro ![](N%C3%A1vod_html_298022ca.gif){#Object51
align="absmiddle" width="38" height="21"} a
![](N%C3%A1vod_html_93867f1c.gif){#Object52 align="absmiddle" width="35"
height="21"} je jediným řešením například trojúhelník
![](N%C3%A1vod_html_2fd18b1a.gif){#Object53 align="absmiddle" width="40"
height="21"} s pravým úhlem při vrcholu *A*. Pro
![](N%C3%A1vod_html_bd48ab1a.gif){#Object54 align="absmiddle" width="66"
height="21"} úloha nemá řešení.

\

\

O![](N%C3%A1vod_html_9c84ed12.png){#Image5 align="left" hspace="12"
width="604" height="371"}\
br. 5: Provedení konstrukce úlohy 2

\

III\. Pokud je ![](N%C3%A1vod_html_dca40818.gif){#Object55
align="absmiddle" width="35" height="21"} a
![](N%C3%A1vod_html_a238656d.gif){#Object56 align="absmiddle" width="41"
height="21"} má úloha:

a\) jedno řešení, je-li navíc![](N%C3%A1vod_html_4ca1f255.gif){#Object57
align="absmiddle" width="50" height="21"}

b\) dvě řešení pro ![](N%C3%A1vod_html_2d5fe706.gif){#Object58
align="absmiddle" width="44" height="21"} (obr 5).

\

\

::: {#sdfootnote1}
[1](#sdfootnote1anc){#sdfootnote1sym .sdfootnotesym} Je celkem
rozšířeným zvykem omezovat konstrukci u podobných nepolohových úloh jen
na zvolenou polorovinu. To může vést, jak uvidíme při řešení úlohy 2
k neúplnému výsledku. V úloze 1 však takové nebezpečí nehrozí a
provedení konstrukce jen v jedné polorovině je přehlednější, pomineme-li
okolnost, že se sestrojené trojúhelníky překrývají
:::

::: {#sdfootnote2}
[2](#sdfootnote2anc){#sdfootnote2sym .sdfootnotesym} Hvězdičkou budeme
označovat ty body konstrukce, v nichž není zcela jasné, kolik prvků
v tomto bodě postupu sestrojovaných může vzniknout. V naší ukázce je to
bod 4\*, neboť zde může vzniknout 0, 1 nebo 2 průsečíků.
:::

::: {#sdfootnote3}
[3](#sdfootnote3anc){#sdfootnote3sym .sdfootnotesym} V diskusích počtu
řešení nepolohových úloh není jednotná dohoda. Autoři různých učebnic
uvádí různá pravidla. Zde jsme se řídili dohodou z učebnice Herman J.,
Chrápavá V., Jančovičová E., Šimša J.: *Matematika -- Tercie,
Geometrické konstrukce*, Prometheus, Praha, 1998.

\
:::
