---
title: "BendaM_DP_duben2007.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomové práce/Vyuití webMathematica na støední kole/BendaM_DP_duben2007.pdf"
date: 2008-08-25
type: PDF (text-based)
---

Jihočeská univerzita v Českých Budějovicích
Pedagogická fakulta
Katedra matematiky

Využití produktu webMathematica ve výuce na
střední škole
Usage of WebMathematica for teaching on the secondary school

DIPLOMOVÁ PRÁCE

Miroslav BENDA
České Budějovice, duben 2007

Prohlašuji, že jsem diplomovou práci zpracoval samostatně a použitou literaturu jsem
citoval.
V Českých Budějovicích.................... 2007

..........................................
Miroslav BENDA

Anotace
Cílem diplomové práce je zpracovat jednotlivé způsoby, jakými lze využívat
produkt WebMtahematica ve výuce matematiky na středních školách . Široké využití
programu WebMathematica je umožněno jeho volnou přístupností pro všechny
uživatele libovolného internetového prohlížeče. Výsledné poznatky budou prezentovány
v rámci internetového portálu, vznikajícího jako součást internetových stránek katedry
matematiky. Z tohoto portálu budou pedagogičtí pracovníci i jejich studenti moci čerpat
webové aplikace, které názorně ilustrují podstatu jednotlivých matematických pojmů.

Annotation
The aim of this thesis is to analyze the individual ways how to use the
WebMathematica product in teaching mathematics at secondary schools. The extensive
usage of WebMathematica programme is provided by its free access for all users of any
internet browser. The final results will be presented within the internet gateway which is
developed as a part of web sites of the Department of Mathematics. From this internet
gateway can teachers and their students gather web applications which illustrate the
principle of particular mathematical terms.

Poděkování:
Děkuji panu RNDr. Tomášovi Mrkvičkovi Ph.D., vedoucímu mé diplomové
práce, za jeho odborné vedení, cenné rady a připomínky, kterými mi pomohl při jejím
vypracování.
Dále bych chtěl poděkovat své kolegyni Veronice Burianové za její cennou
spolupráci při vývoji a porozumění tajům webMathematica, rodině a přátelům za
podporu při studiu.

Obsah
1. Úvod......................................................................................................................... - 1 1.1 Cíl....................................................................................................................... - 8 1.2 Jak si představujeme využití naší práce ............................................................. - 8 2. Co je webMathematica?........................................................................................... - 9 2.1 Proč se používá webMathematica na webu ....................................................... - 9 2.1.1 Výpočty ....................................................................................................... - 9 2.1.2 Propojitelnost .............................................................................................. - 9 2.1.3 Mathematica front end .............................................................................. - 10 2.1.4 Matematické zápisy a MathML ................................................................ - 10 3. Proč webové rozhraní?........................................................................................... - 11 3.1 Snadné používání ............................................................................................. - 11 3.2 Server – základní konfigurace.......................................................................... - 11 3.3 Oblasti využití webMathematica...................................................................... - 12 4. Mathematica........................................................................................................... - 13 4.1 Mathematica versus webMathematica ............................................................. - 16 4.2 Mathematica versus webMathematica – výstup .............................................. - 17 4.2.1 Výstup v podobě Mathematica notebooku: .............................................. - 17 4.2.2 Výstup v podobě webové stránky - JSP:................................................... - 18 5. webMathematica – technologie ............................................................................. - 19 5.1 Spojení Mathematica a HTML ........................................................................ - 19 5.2 Technologie...................................................................................................... - 19 5.3 webMathematica - Schéma technologie........................................................... - 20 6. Praktická část ......................................................................................................... - 21 6.1 Úvod do HTML ............................................................................................... - 21 6.2 MSP statická stránka ........................................................................................ - 22 6.2.1 Vytvoření HTML stránky bez Math tagů ................................................. - 22 6.2.2 Uložení souboru jako *.jsp....................................................................... - 22 6.2.3 Přidání webMath tagů ............................................................................... - 23 6.2.4 Přidání kódu v Mathematice mezi webMath tagy..................................... - 23 6.2.5 Přidání specifických příkazů do kódu v Mathematice .............................. - 24 6.2.6 Otestování v prohlížeči ............................................................................. - 25 6.3 Tvorba MSP na přikladu .................................................................................. - 25 6.3.1 Výroba notebooku v Mathematice ............................................................ - 26 6.3.2 Vytvoření HTML stránky s formulářem ................................................... - 26 6.3.3 Uložení souboru jako JSP do adresáře, kde je nainstalovaná webMathematica
............................................................................................................................ - 27 6.3.4 Přidání webMathematica tagů................................................................... - 27 6.3.5 Přidání kódu v Mathematice mezi webMathematica tagy a přidání
specifických příkazů do kódu v Mathematice.................................................... - 28 6.3.6 Otestování stránky v prohlížeči................................................................. - 30 6.4 Přehled důležitých tagů a příkazů .................................................................... - 31 6.4.1 HTML tagy ............................................................................................... - 31 6.4.2 webMathematica tagy ............................................................................... - 31 6.4.3 Mathematica kód....................................................................................... - 31 6.4.4 MSP specifické příkazy ............................................................................ - 31 7. Témata.................................................................................................................... - 34 -

7.1. Zdrojové kódy ................................................................................................. - 35 7.1.1 Kvadratická rovnice, kvadratická funkce.................................................. - 35 7.1.2 Grafy elementárních funkcí....................................................................... - 58 7.2. Internetové stránky.......................................................................................... - 67 7.2.1 Kvadratická rovnice, kvadratická funkce.................................................. - 67 7.2.2 Grafy elementárních funkcí....................................................................... - 69 8. Závěr ...................................................................................................................... - 71 9. Užitá literatura a www ........................................................................................... - 73 -

1. Úvod
Diplomová práce – Využití produktu webMathematica ve výuce na střední škole
– byla zadána tak, že ji bylo možné zpracovat týmově. Proto jsme si toto téma vybrali,
a proto také i webové stránky, které jsou hlavní částí této práce, vznikaly ve vzájemné
spolupráci s kolegyní Veronikou Burianovou.
Cílem naší diplomové práce je zpracovat jednotlivé způsoby, jakými lze
využívat produkt webMathematica ve výuce matematiky na středních školách. Jeho
využití si představujeme dvěma způsoby. Prvním způsobem je využití produktu
webMathematica při hodinách, kdy má učitel k dispozici pouze jeden počítač, nebo mu
jeden počítač v danou chvíli stačí, a data-projektor. V této situaci lze naši práci použít
jako pomůcku pro doplnění jeho výkladu, pro snadnější pochopení látky, pro
demonstraci různých typů grafů, jako pomoc pro představivost studenta, a samozřejmě
i pro zpestření hodiny. Druhým způsobem je využití v hodinách, kdy je možné
výuku

přemístit do

počítačů.

počítačových

učeben,

kde

je

možnost

práce

u

více

Například v matematických cvičeních, kdy je látka již probrána a je třeba ji

procvičit na co největším množství příkladů. Každý student má k dispozici svůj počítač,
pracuje samostatně a svoji práci si kontroluje pomocí počítače, přičemž učitel pomáhá
a radí.
Jsme si vědomi, že na všech školách není možnost vyučovat matematiku
v učebnách výpočetní techniky, ale věříme, že situace se bude zlepšovat, a že
počítačové výbavy bude na školách přibývat nejen pro využití v hodinách výpočetní
techniky.
V diplomové práci se v prvních kapitolách zabýváme tím, co produkt
webMathematica je, jak funguje, jaké jsou výhody jeho použití. Praktická část obsahuje
samotnou tvorbou webových stránek a tvorbu Mathematica Server Pages (MSP).
Podařilo se nám zpracovat několik témat středoškolské matematiky a přáli
bychom si, aby webové stránky s těmito tématy byly učiteli i studenty do budoucna
využívány. Aby se staly pomocníkem učitelů při výuce, studentům návodem k
porozumění dané látky a zároveň jejich cvičebnicí. Chceme, aby propojovaly svět
matematiky se světem výpočetní techniky.

1.1 Cíl
Cílem naší diplomové práce je zpracovat jednotlivé způsoby, jakými lze
využívat produkt webMathematica ve výuce matematiky na středních školách. Pokusit
se o

široké

využití programu

webMathematica umožněné volnou přístupností

pro všechny uživatele libovolného internetového prohlížeče.
Výsledné poznatky budou prezentovány v rámci internetového portálu,
vznikajícího jako součást internetových stránek katedry matematiky a v diplomových
pracích.

1.2 Jak si představujeme využití naší práce
Na SŠ, ZŠ, kde je možné přemístit výuku některých hodin matematiky
(v matematických cvičeních, kdy je látka probrána a je třeba ji procvičit na co největším
množství příkladů) do počítačové učebny. A to formou, kdy učitel prezentuje na dataprojektoru, nebo každý žák má k dispozici počítač, pracuje samostatně. Kontroluje
a pomáhá učitel i počítač.

2. Co je webMathematica?
WebMathematica je způsob, jakým lze vytvářet interaktivní výpočty na webu
s využitím programu Mathematica a s využitím webových technologií. To znamená,
že tato unikátní technologie umožňuje vytvářet webové stránky, kde jsou využity
výpočetní a vizualizační schopnosti programu Mathematica v celé jeho šíři.
WebMathematica, vybudovaná na bázi nejlepšího světového softwaru v oblasti
technických výpočtů a osvědčené technologie Java Servlet, je plně kompatibilní
s programem Mathematica

a s nejmodernějšími dynamickými webovými systémy.

Používá takových vzorů (šablon), aby vytvořené stránky měly odpovídající
profesionální vzhled.

2.1 Proč se používá webMathematica na webu
WebMathematica pracuje s obrovskou knihovnou Mathematica příkazů. Mezi
možnosti, které Mathematica nabízí webu, patří výpočty, interaktivní programovací
jazyk na vysoké úrovni, propojitelnost, Mathematica front end a zvýšená podpora
pro MathML.

2.1.1 Výpočty
Mathematica obsahuje obrovskou sbírku funkcí pro numerické i symbolické
výpočty i pro zobrazování grafiky – 2D, 3D grafy apod. WebMathematica pak zajistí
funkčnost a dostupnost těchto aplikací na webu. Mathematica je navíc velice vhodná
pro vědecké výpočty na rozdíl od jiných webových technologií.

2.1.2 Propojitelnost
Mathematica

je

schopna

se

pohotově propojit s externími službami,

které poskytují programovací jazyky jako jsou Java, C, Fortran nebo Perl. Tyto služby
mohou poskytovat datové zdroje pro výpočty a také využívat výsledky z Mathematica.

Zvláště jednoduché je spojení s Java přes J/Link. J/Link je soubor nástrojů pro
integraci Java do Mathematica.

2.1.3 Mathematica front end
Uživatelské rozhraní tzv. Mathematica notebooku – front end – pracuje s jádrem
(kernel) Mathematica. Tzn., že uživatel zadává pouze vstupní příkazy, jádro je zpracuje
a uživateli se zobrazí přímo výsledky. WebMathematica pak poskytuje rozhraní
přes web. Ve webovém prostředí je front end velmi používán. Je využíván k psaní
matematických zápisů, pro vytvoření dvou nebo tří dimenzionálních grafů a jejich
zobrazení.

2.1.4 Matematické zápisy a MathML
Mathematica je vhodný systém pro matematické zápisy. Je také vhodný systém
pro práci s MathML. MathML je systém (jazyk), který je vytvořen pro psaní
matematických zápisů a pro to, aby mohl být využíván různými aplikacemi.

3. Proč webové rozhraní?
3.1 Snadné používání
K používání webMathematica uživateli stačí pouze standardní internetový
prohlížeč (browser) – Microsoft Internet Explorer, FireFox, Opera – pro zadávání
výpočtů a zobrazování výsledků. Ovládání je pro uživatele známé, protože uživatelské
rozhraní používá standardní web GUI elementy - tlačítka, textová pole, boxy,
a rozevírací seznamy (rolety), atd. Uživatelé se nemusí učit různé softwarové aplikace
a tím je výrazně redukován výcvikový čas. V mnoha případech nejsou nutné
ani zkušenosti s programem Mathematica (pouze pasivní uživatelé).

3.2 Server – základní konfigurace
Pro užívání webMathematica není třeba nakupovat žádný software, instalovat ho
nebo ho udržovat. Všichni koncoví uživatelé potřebují jen internetový prohlížeč
(browser) a pro náročnější aplikace jako je interaktivní 3D grafika Java runtime
prostředí. Podstatné je, že uživatel nemusí investovat do softwaru, což vede ke značné
úspoře, a navíc má vždy k dispozici nejposlednější verzi. Další výhoda je,
že webMathematica může být zpřístupněna z mnoha různých druhů počítačů.

Obrázek 3.1

3.3 Oblasti využití webMathematica
Oblastí, kde lze využívat produkt webMathematica, je mnoho. Uplatnění má
ve vědě a výzkumu, ve vzdělávání a výuce, v oblastech, kde jsou využívány výpočetní
schopnosti prohlížeče (např. různé interaktivní aplikace, Java utility, atd.). Přednostmi
webMathematica je možnost zveřejnění výsledků a aplikací z těchto různých oblastí
pomocí internetového prohlížeče a možnost využití těchto výsledků v různých
zaměstnáních a aktivitách.

4. Mathematica
Mathematica je integrovaný počítačový systém, který v sobě shrnuje možnosti
programovacího jazyka, softwaru pro analytické zpracování matematických výrazů,
grafického programu, numerických knihoven a v posledních verzích i textového editoru.
Je možno ho používat nejen jako „vědeckou kalkulačku“, ale umožňuje ve svém
vlastním jazyce psát i samostatné programy, které jsou přenositelné mezi všemi
platformami.

Vývoji systému Mathematica se věnuje Stephen Wolfram zakladatel firmy
Wolfram Research. První verze Mathematica se objevila v roce 1988 a její vydání bývá
označováno jako začátek moderního využívání výpočetní techniky pro tzv. „dělání
matematiky na počítači“.

Umožňuje například numerické i symbolické výpočty, práci s přesnými
i přibližnými čísly s nastavitelnou přesností, se skaláry, vektory, maticemi i tenzory
vyšších řádů, s reálnými i komplexními čísly, řešení algebraických, diferenciálních
i diferenčních rovnic, atd. Dále umožňuje výstup v podobě dvourozměrných
i třírozměrných barevných grafů s možností animace i zvukový výstup. Součástí
systému je i bohatá dokumentace včetně definic, nápověd a příkladů.

Formát souborů tzv. notebooků (zápisníků) Mathematica je užitečný
při vytváření dokumentů, které jsou nezávislé na platformě a které může sdílet více
studentů, učitelů či kolegů. Zápisníky se osvědčují při prezentaci seminářů, přednášek
a názorných ukázek. Protože zobrazují tradiční matematický zápis, hodí se dobře
k sestavování sylabů, testů a úloh, které se mohou buď tisknout nebo rozdávat, řešit
a sbírat elektronicky.

Nejpodobnějším softwarovým systémem je Maple od firmy Maplesoft. Systém
Mathematica se však liší logikou jak samotného systému, tak jeho syntaxí a celkovou
konstrukcí a dokumentací.

Pro zpracování této diplomové práce jsme používali program Mathematica 4.1.
V současné době již existuje verze 5.2. Od předchozích verzí se liší svou rychlostí,
ale i přístupem. Tyto nové dovednosti doplňují vylepšení v oblasti automatického
výběru algoritmu Mathematica.

Obrázek 4.1 – Příklad grafického výstupu.

Obrázek 4.2 – Příklad na řešení rovnice.

4.1 Mathematica versus webMathematica
1)

Mathematica i webMathematica jsou založené na stejné technologii,

ale mají rozdílné uživatelské rozhraní a jsou určeny každá pro jinou skupinu uživatelů.

2)

WebMathematica nabízí přístup ke specifickým aplikacím programu

Mathematica prostřednictvím webového prohlížeče (browseru) nebo prostřednictvím
jiných webových klientů.

3)

WebMathematica používá vše z Mathematica.

4)

Stačí pouze malý zácvik k tomu, aby bylo možné standardní rozhraní

efektivně používat. Ve většině případů uživatelé nemusí být v Mathematica zběhlí,
dokonce ani nemusí vědět, jak se Mathematica používá.

5)

Mathematica je vývojové prostředí pro WebMathematica. Například:

Mathematica je vhodná pro práci na kódu, který modeluje určitý fyzikální proces. Tento
kód se následně dá umístit jako součást stránky webMathematica a po spuštění mohou
být výsledky používány při běžné práci.

6)

Produkt webMathematica nám umožňuje přenést vytvořené notebooky

z programu Mathematica na web.

4.2 Mathematica versus webMathematica – výstup

4.2.1 Výstup v podobě Mathematica notebooku:

Obrázek 4.3 – Příklad v Mathematica 4.1.

4.2.2 Výstup v podobě webové stránky - JSP:

Obrázek 2.2 – Příklad pomocí webMathematica 2.

5. webMathematica – technologie
Předpoklady pro práci ve webMathematica
•

Znalost Mathematica

•

Základní znalost tvorby webových stránek

•

Program webMathematica

5.1 Spojení Mathematica a HTML
Jak už jsme se zmínili, webMathematica nabízí přístup k aplikacím
Mathematica a využívá vše z tohoto programu. Když je vznesen požadavek na jedné
ze stránek webMathematica, Mathematica vyhodnotí příkazy a výsledek se zobrazí
na příslušnou stránku. Toto umožňují tzv. Java Server Pages (JSP) – standardní Java
technologie využívající uživatelské tagy.
Po počátečním nastavení je vše, co je potřebné k psaní webMathematica aplikací
základní znalost tvorby HTML a Mathematica.

5.2 Technologie
WebMathematica je založena na dvou standardních Java technologiích – Java
Servlet a JSP.

Java Servlet
Servlety jsou speciální Java programy, které se spouštějí přes webový prohlížeč.
Obvykle se nazývají servlet containers nebo servlet engine. Existuje mnoho různých
typů těchto Java programů. Jsou spouštěny (jsou aktivní) na mnoha operačních
systémech.

Java Server Pages (JSP)
Při použití JSP se podobně jako v ASP nebo v PHP přímo do HTML kódu
zapisují příkazy. Ty jsou nyní zapisovány v jazyce Java. Speciální servlet se stará o to,
aby byla JSP stránka vždy po své modifikaci automaticky přeložena do byte-kódu.

5.3 webMathematica - Schéma technologie

1. webMathematica server si rezervuje Mathematica kernel (jádro)
z bazénu
2. Mathematica kernel je nastaven se vstupními paramatery, provede
kalkulace a vrací výsledky serveru.
3. webMathematica server vrací Mathematica kernel do bazénu.
4. Webový prohlížeč posílá požadavek na webMathematica server.
5. webMathematica server vrací výsledky webovému prohlížeči1

Při práci na této diplomové práci jsme používali program webMathematica 2,
který je v současné době poslední verzí. Instalace tohoto softwaru je na fakultním
serveru Pedagogické fakulty katedry matematiky.
( http://home.pf.jcu.cz/webmathematica/webmath )
1

http://ladislav.prskavec.net/

6. Praktická část
V této části naší diplomové práce se snažíme osvětlit vznik jednoduché stránky
ve webMathematica. Nejprve jako vznik jednoduché webové stránky (*.html)
a poté její transformaci na stránku pro webMathematica (*.jsp).

6.1 Úvod do HTML
HTML je zkratka z anglického Hypertext Markup Language, značkovací jazyk
pro hypertext. Je jedním z jazyků pro vytváření stránek v systému www ( World Wide
Web ), který umožňuje publikaci stránek na internetu.

Jazyk je podmnožinou dříve vyvinutého rozsáhlého univerzálního značkovacího
jazyka SGML ( Standard Generalized Markup Language ). Vývoj HTML byl ovlivněn
vývojem webových browser (prohlížečů), které zpětně ovlivňovaly definici jazyka.

HTML neboli hypertextový jazyk značek (tagů). Je to formát souborů
používaných převážně na Internetu. Do takového souboru můžete vložit odkaz na jiný
soubor, měnit formátování, vkládat obrázky a spoustu dalších věcí. Tyto věci provádíte
pomocí tzv. značek (tagů). Většina těchto tagů je párová. Nejkratší HTML dokument
vypadá takto:
<html>
<head>
<title>Titulek stránky</title>
</head>
<body bgcolor="Barva pozadí" text="Barva textu"
link="Barva odkazů">
...text dokumentu...
</body>
</html>

6.2 MSP statická stránka
V této kapitole se zabýváme tvorbou statických a dynamických stránek MSP
(Mathematica Server Pages).

6.2.1 Vytvoření HTML stránky bez Math tagů
<htlm>

<head>

<title> … </title>
</head>

<body bgcolor="Barva pozadí" text="Barva textu"
link="Barva odkazů">

...text dokumentu...

</body>
</html>

Základní HTML tagy

6.2.2 Uložení souboru jako *.jsp
Po vytvoření základní stránky změníme koncovku z *.html na *.jsp. Uložíme
soubor do adresáře, kde je nainstalovaná webMathematica. V našem případě se jedná
o

http://home.pf.jcu.cz/webMathematica/webmath.

Samostatná

stránka

(*.html)

bez přípony *.jsp je nefunkční i kdyby již obsahovala webMathematica příkazy a tagy.

6.2.3 Přidání webMath tagů
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib"prefix="msp" %>
<!--Hlavička dokumentu, zavedení jazyku Java (Java Server Pages). -->
<html>
<head>

<title> …

</title>

</head>

<msp:allocateKernel>
<!--Alokace kernel (jádro) webMathematica.-->
<body bgcolor= … >
....
</body>
</msp:allocateKernel>
<!- - Párový tag.-->
</html>
Základní HTML tagy.
Přidání webMathematica tagů.

6.2.4 Přidání kódu v Mathematice mezi webMath tagy
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib"
prefix="msp" %>
<html>
<head>
<title> …

</title>

</head>2
2

http://ladislav.prskavec.net/

<msp:allocateKernel>
<body bgcolor= … >
<msp:evaluate> $$x. </msp:evaluate>
<!—Příkaz pro samotné spuštění webMathematica – řeš, vyhodnoť. -->
</body>
</msp:allocateKernel>
</html>
Základní HTML tagy.
Přidání webMathematica tagů.
Vložení Mathematica kódu.

6.2.5 Přidání specifických příkazů do kódu v Mathematice
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib"
prefix="msp" %>
<html>
<head>
<title> …

</title>

</head>
<msp:allocateKernel>
<body bgcolor= … >

<msp:evaluate> MSPBlock[…] </msp:evaluate>

</body>
</msp:allocateKernel>
</html>3

3

http://ladislav.prskavec.net/

Základní HTML tagy.
Přidání webMathematica tagů.
Vložení Mathematica kódu.
Přidání specifických příkazů do kódu v Mathematica.

Jednotlivé specifické příkazy jsou vypsány i s jednotlivými příklady v kapitole
6.4.

6.2.6 Otestování v prohlížeči
Výsledek po uložení na server, kde je webMathematica nainstalována,
zkontrolujeme webovým prohlížečem. Jedná se především o kontrolu funkčnosti
vytvářené aplikace.4

6.3 Tvorba MSP na přikladu
Tvorbu MSP se pokusíme demonstrovat na jednoduchém příkladu. Je to příklad
součtu dvou libovolných čísel.

4

http://ladislav.prskavec.net/

6.3.1 Výroba notebooku v Mathematice

Obrázek 6.1

6.3.2 Vytvoření HTML stránky s formulářem
<html>
<head>
<title>Součet</title>
</head>
<body bgcolor=“white“>
<h2>Součet</h2>
<p>Zadej dvě libovolná čísla.</p>

<form action=“Soucet.jsp“ method=“POST“ >
a: <input name:“a“ size=“3“ value“... “ >
b: <input name:“b“ size=“3“ value“... “ >
<input type=“submit“ name=“btnSubmit“ value=“scitej“>

</form>
</body>

</html>
Základní HTML tagy.

6.3.3 Uložení souboru jako JSP do adresáře, kde je nainstalovaná
webMathematica
Viz. kapitola 6.2.2.

6.3.4 Přidání webMathematica tagů
<%@ page language=“java“ %>
<%@ taglib uri=“/webMathematica-taglib“ prefix=“msp“ %>
<html>
<head>
<title>Součet</title>
</head>
<body bgcolor=“white“>
<h2>Součet</h2>
<p>Zadej dvě libovolná čísla.</p>

<form action=“Soucet.jsp“ method=“POST“ >

<msp:allocateKernel>
<!--Hlavička dokumentu, zavedení jazyku Java (Java Server Pages) -->
a:<input name:“a“ size=“3“ value“ “ >
b:<input name:“b“ size=“3“ value“ “ >
<input type=“submit“ name=“btnSubmit“ value=“scitej“>

</msp:allocateKernel>
<!--Hlavička dokumentu, zavedení jazyku Java (Java Server Pages) -->
</form>
</body>

</html>

Základní HTML tagy.
Přidání webMathematica tagů.

6.3.5 Přidání kódu v Mathematice mezi webMathematica tagy a
přidání specifických příkazů do kódu v Mathematice
<%@ page language=“java“ %>
<%@ taglib uri=“/webMathematica-taglib“ prefix=“msp“ %>

<html>
<head>
<title>Soucet</title>
</head>
<body bgcolor=“white“>
<h2>Soucet</h2>
<p>Zadej dve libovolna cisla:</p>

<form action=“Soucet.jsp“ method=“POST“ >

<msp:allocateKernel>

a:<input

name:“a“

size=“3“

value“

<msp:evaluate>

value“

<msp:evaluate>

MSPValue[$$a]</msp:evaluate> “ >
b:<input

name:“b“

size=“3“

MSPValue[$$b]</msp:evaluate> “ >

<input type=“submit“ name=“btnSubmit“ value=“scitej“>

<msp:evaluate>
MSPBlock[{$$a,$$b},a=$$a;b=$$b;]
</msp:evaluate>

Součet je:
<msp:evaluate>a+b</msp:evaluate>

</msp:allocateKernel>

</form>
</body>
</html>

Základní HTML tagy.
Přidání webMathematica tagů.
Vložení Mathematica kódu.
Přidání specifických příkazů do kódu v Mathematica.

6.3.6 Otestování stránky v prohlížeči

Obrázek 6.2

6.4 Přehled důležitých tagů a příkazů

6.4.1 HTML tagy
Tato diplomová práce nemá za úkol tvorbu HTML stránek jako takovou.
Základní HTML tagy jsou uvedené v kapitole 6.1, nejsou však zdaleka uvedeny
všechny. Úvod do HTML, tudíž zde nebudeme znovu uvádět a jednotlivé tagy
vypisovat.

6.4.2 webMathematica tagy
•

<%@page language=“java“ %>
<%@taglib uri=“/webMathematica-taglib“prefix=“msp“ %>
Hlavička souboru

•

<msp:allocateKernel>
</msp:allocateKernel>
Alokace kernel (jádro) webMathematica

•

<msp:evaluate>
</msp:evaluate>
Z anglického evaluate jasně vyplývá, že se jedná

o příkaz vyhodnoť, což je v tomto případě příkaz pro webMathematica, aby provedla
výpočet, nebo splnila následující příkazy nebo výpočty.

6.4.3 Mathematica kód
Používá se standardní příkazy Mathematica. Stejný syntax, konstrukce a logika
příkazů.

6.4.4 MSP specifické příkazy
- MSP statické příkazy:
•
5

MSPShow[]5

http://ladislav.prskavec.net/

Pro vkládání grafiky do HTML stránky. Tento příkaz použijte pro zobrazení 2D
i 3D grafu.
Příklad:
MSPShow[Plot[Cos[x],{x,0,2 Pi}]]

•

MSPFormat[výraz, formát]
Formátuje výraz ve stylu formát
Příklad:
MSPFormat[x^2+5x-2,TraditionalFormat]

•

MSPLive3D[]
Pro přidání appletu Live3D do HTML stránky. Tento příkaz umožňuje

interaktivní 3D graf.
Příklad:
MSPLive3D[ContourPlot3D[Sin[Sqrt[x^2+y^2+z^2]],{x,
xmin, xmax},{y, ymin,ymax},{z, zmin, zmax}]

•

MSPShowAnimation[{gr1, gr2, gr3, …}]
Vloží do stránky základní animaci vytvořenou jako GIF z listu grafických

objektů.
Příklad:
MSPShowAnimation[Table[Plot[Sin[x+i],{x,0,4*Pi}],
{i,0.,2*Pi-Pi/4,Pi/4}]

- HTML formátování:
•

HTMLTableForm[]
Přeformátuje vstup do HTML tabulky.

•

6

HTMLFormat[výraz]6

http://ladislav.prskavec.net/

Formátuje výrazy do jednoduchého HTML. Není to tak dobré jako grafika
nebo MathML
- MSP dynamické příkazy:
Narozdíl od Mathematica nemusí být MSP neměnné. Toho se docílí použitím
webových formulářů. Jméno každé proměnné se volá $$jmeno.
Příklad:
<input type="text" name="x" value="3">
Formulářový vstup (V Mathematica proměnná: $$x)

•

MSPBlock[{var1,var2,...}, body,defvalue]
•

Kontroluje zda všechny proměnné $$var1, $$var2, … mají hodnoty.

•

Když mají všechny proměnné hodnoty, každý její výskyt v souboru bude

nahrazen danou hodnotou.
•

Když některá z proměnných nemá hodnotu vrátí se defvalue.

•

MSPBlock je také důležité používat kvůli bezpečnosti. Nemůže dojít

v přímému vyhodnocení proměnných.

•

MSPValue[var, default]
Vrací hodnotu proměnné var. Když proměnná nemá hodnotu vrací default.

Neinterpretuje se pokud proměnná je String (Textový řetězec je v informatice znakový
řetězec a zároveň abstraktní datový typ.).

•

MSPValue[var1,var2, …]
Vrací True když všechny proměnné mají hodnoty.

•

MSPToExpression[var]
MSP verze přikladu ToExpression (což je příkaz z Mathematica). Konverze

String na výraz, důležité při ošetření vstupů.7

7

http://ladislav.prskavec.net/

7. Témata
Příklady témat zpracovaných pomocí webMathematica:

•

Kvadratická rovnice, kvadratická funkce
Pro práci s kvadratickou rovnicí je třeba ovládat několik dovedností jako je

spočítání diskriminantu a následně výpočet jednotlivých kořenů. Graf kvadratické
funkce je možno zobrazit za předpokladu, že známe průsečíky s osami x a y
a souřadnici vrcholu paraboly a kořeny.

•

Grafy elementárních funkcí
Jednou z mnoha témat, která se učí při hodinách matematiky na středních

školách je i znalost elementárních funkcí, jednak práce s výrazy jako takovými,
ale i jejich grafické znázornění.

Všechna témata jsou zpracována na webových stránkách, které najdete
na internetové adrese: http://home.pf.jcu.cz/webMathematica/webmath/index.htm . Tyto
stránky jsou hlavní součástí naší diplomové práce a tam můžete jednotlivá témata vidět
a použít.

7.1. Zdrojové kódy
7.1.1 Kvadratická rovnice, kvadratická funkce
• Výpočet diskriminantu
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib" prefix="msp" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtnl1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<head>
<meta http-equiv="content-type" content="text/html;
charset=windows-1250" />
<meta http-equiv="keywords" content="Mathematica,webMathematica"
/>
<meta http-equiv="author" content="all:Mira Benda" />
<meta http-equiv="copyright" content="© Mira Benda" />
<meta http-equiv="authormail" content="mirabenda@volny.cz" />
<meta http-equiv="language" content="czech" />
<meta http-equiv="country" content="cz" />
<meta http-equiv="content-script-type" content="text/javascript"
/>
<meta http-equiv="content-style-type" content="text/css" />
<meta http-equiv="content-language" content="cs" />
<title>WebMathematica</title>
</head>
<body bgcolor="white" text="black" link="blue" vlink="blue"
alink="blue" background="" bgproperties="fixed" leftmargin="150"
topmargin= "100"maginwidth="" marginheight="5">
<basefont face="Verdana" size="2" />
<center><IMG SRC="PIC\webm-black.gif" ALT="webm-black.gif(7 kb)"
WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<br>
<br />
<center><h1>DISKRIMINANT</h1></center>
<form action="diskr.jsp" method="post">
<msp:allocateKernel>
<h2>
&nbsp;&nbsp;&nbsp;a&nbsp;x<sup>2</sup>&nbsp;+&nbsp;b&nbsp;x&nbsp;+&nbs
p;c&nbsp;=&nbsp;0
</h2>
a=<input name="a" size="1"
value="<msp:evaluate>MSPValue[$$a]</msp:evaluate>">&nbsp;
b=<input name="b" size="1"
value="<msp:evaluate>MSPValue[$$b]</msp:evaluate>">&nbsp;
c=<input name="c" size="1"
value="<msp:evaluate>MSPValue[$$c]</msp:evaluate>">

<br>
<br>
<input type="submit" name="btnSubmit"

value ="DISKRIMINANT">

<msp:evaluate>
MSPBlock[{$$a,$$b,$$c},a=$$a;b=$$b;c=$$c;]
</msp:evaluate>
<br>
<hr>
<br/>
D=
<msp:evaluate>
MSPFormat[b^2-(4*a*c),StandardForm]
</msp:evaluate>
</msp:allocateKernel>
</form>
<br>
<br>
<br>
<a href="http://home.pf.jcu.cz/webMathematica/webmath/index2.htm"
title="WebMATHEMATICA">
<center><h6>Zpet na vyber temat</h6></center></a><br />
<br>
<br>
<center><IMG SRC="PIC\webm-black-animated.gif" ALT="webm-blackanimated.gif(30 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<center><td style='font-family: Helvetica; font-size: 10px; width:
100%'>Created by
<a href="http://www.wolfram.com"><span style='font-style:
italic'>Mathematica</span></a></center>
<HR> <center><p align="center"><font face="verdana,tahoma,sans serif"
size="1">webmaster: <a href="http://www.bendamira.wz.cz" title="BENDA
MIREK">Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">email</a> &copy; 2006</center>
<center><script language="javascript">
modate = new Date(document.lastModified);
year = modate.getYear();
if (year < 80)
year += 2000;
else if (year >= 80 && year < 200)
year += 1900;
mon = modate.getMonth()+1;
if (mon < 10)
mon = "0"+mon;
dat = modate.getDate();
if (dat < 10)
dat = "0"+dat;
resu = "Datum poslední aktualizace: "+dat+"."+mon+"."+year;
document.write(resu);
</script></FONT></CENTER>
</body>
</html>

• Výpočet kořenů kvadratické rovnice
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib" prefix="msp" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtnl1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<head>
<meta http-equiv="content-type" content="text/html;
charset=windows-1250" />
<meta http-equiv="keywords" content="Mathematica,webMathematica"
/>
<meta http-equiv="author" content="all:Mira Benda" />
<meta http-equiv="copyright" content="© Mira Benda" />
<meta http-equiv="authormail" content="mirabenda@volny.cz" />
<meta http-equiv="language" content="czech" />
<meta http-equiv="country" content="cz" />
<meta http-equiv="content-script-type" content="text/javascript"
/>
<meta http-equiv="content-style-type" content="text/css" />
<meta http-equiv="content-language" content="cs" />
<title>WebMathematica</title>
</head>
<body bgcolor="white" text="black" link="blue" vlink="blue"
alink="blue" background="" bgproperties="fixed" leftmargin="150"
topmargin= "100"maginwidth="" marginheight="5">
<basefont face="Verdana" size="2" />
<center>
<IMG SRC="PIC\webm-black.gif" ALT="webm-black.gif(7 kb)" WIDTH="468"
HEIGHT="60" BORDER="0">
</center>
<br>
<br />
<center><h1>KORENY</h1></center>
<form action="koreny.jsp" method="post">
<msp:allocateKernel>
<h2>
&nbsp;&nbsp;&nbsp;a&nbsp;x<sup>2</sup>&nbsp;+&nbsp;b&nbsp;x&nbsp;+
&nbsp;c&nbsp;=&nbsp;0
</h2>
a=<input name="a" size="1" value="
<msp:evaluate>
MSPValue[$$a]
</msp:evaluate>">&nbsp;
b=<input name="b" size="1" value="
<msp:evaluate>
MSPValue[$$b]
</msp:evaluate>">&nbsp;
c=<input name="c" size="1" value="
<msp:evaluate>
MSPValue[$$c]

</msp:evaluate>">
<br>
<br>
<input type="submit" name="btnSubmit"

value ="KORENY">

<msp:evaluate>
MSPBlock[{$$a,$$b,$$c},a=$$a;b=$$b;c=$$c;]
</msp:evaluate>
<br>
<hr>
<br/>
x<sub>1</sub>=
<msp:evaluate>
MSPFormat[((-b+Sqrt[(b^2-(4*a*c))])/(2*a)),StandardForm]
</msp:evaluate>
(Numericka hodnota
<msp:evaluate>
MSPFormat[N[((-b+Sqrt[(b^2-(4*a*c))])/(2*a))],StandardForm]
</msp:evaluate>)
<br/>
<br>
<br/>
x<sub>2</sub>=
<msp:evaluate>
MSPFormat[((-b-Sqrt[(b^2-(4*a*c))])/(2*a)),StandardForm]
</msp:evaluate>(Numericka hodnota
<msp:evaluate>
MSPFormat[N[((-b-Sqrt[(b^2-(4*a*c))])/(2*a))],StandardForm]
</msp:evaluate>)
<br/>
</msp:allocateKernel>
</form>
<BR>
<br>
<br>
<a href="http://home.pf.jcu.cz/webMathematica/webmath/index2.htm"
title="WebMATHEMATICA"><center><h6>Zpet na vyber
temat</h6></center></a> <br />
<br>
<br>
<center><IMG SRC="PIC\webm-black-animated.gif" ALT="webm-blackanimated.gif(30 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<center><td style='font-family: Helvetica; font-size: 10px; width:
100%'>Created by
<a href="http://www.wolfram.com"><span style='font-style:
italic'>Mathematica</span></a></center>
<HR> <center><p align="center"><font face="verdana,tahoma,sans serif"
size="1">webmaster: <a href="http://www.bendamira.wz.cz" title="BENDA

MIREK">Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">email</a> &copy; 2006</center>
<center><script language="javascript">
modate = new Date(document.lastModified);
year = modate.getYear();
if (year < 80)
year += 2000;
else if (year >= 80 && year < 200)
year += 1900;
mon = modate.getMonth()+1;
if (mon < 10)
mon = "0"+mon;
dat = modate.getDate();
if (dat < 10)
dat = "0"+dat;
resu = "Datum poslední aktualizace: "+dat+"."+mon+"."+year;
document.write(resu);
</script></FONT></CENTER>
</body>
</html>

• Graf kvadratické rovnice
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib" prefix="msp" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtnl1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<head>
<meta http-equiv="content-type" content="text/html;
charset=windows-1250" />
<meta http-equiv="keywords" content="Mathematica,webMathematica"
/>
<meta http-equiv="author" content="all:Mira Benda" />
<meta http-equiv="copyright" content="© Mira Benda" />
<meta http-equiv="authormail" content="mirabenda@volny.cz" />
<meta http-equiv="language" content="czech" />
<meta http-equiv="country" content="cz" />
<meta http-equiv="content-script-type" content="text/javascript"
/>
<meta http-equiv="content-style-type" content="text/css" />
<meta http-equiv="content-language" content="cs" />
<title>WebMathematica</title>
</head>
<body bgcolor="white" text="black" link="blue" vlink="blue"
alink="blue" background="" bgproperties="fixed" leftmargin="150"
topmargin= "100"maginwidth="" marginheight="5">
<basefont face="Verdana" size="2" />
<center>
<IMG SRC="PIC\webm-black.gif" ALT="webm-black.gif(7 kb)" WIDTH="468"
HEIGHT="60" BORDER="0">
</center>
<br>
<br/>
<center><h1>GRAF KVADRATICKÉ RCE</h1></center>
<form action="grafkva.jsp" method="post">
<msp:allocateKernel>
<h2>
&nbsp;&nbsp;&nbsp;a&nbsp;x<sup>2</sup>&nbsp;+&nbsp;b&nbsp;x&nbsp;+&nbs
p;c&nbsp;=&nbsp;0
</h2>
a=<input name="a" size="1" value="
<msp:evaluate>
MSPValue[$$a]
</msp:evaluate>">&nbsp;
b=<input name="b" size="1" value="
<msp:evaluate>
MSPValue[$$b]
</msp:evaluate>">&nbsp;
c=<input name="c" size="1" value="
<msp:evaluate>
MSPValue[$$c]

</msp:evaluate>">
<br>
<br>
<br>
<b><font color="Red">Koreny rce</font></b><br/>
<br>
<b><font color="Blue">Prusecik s osou y</font></b><br/>
<br>
<b><font color="LightGreen">Vrchol paraboly</font></b><br/>
<br>
<input type="submit" name="btnSubmit"
<hr>

value ="GRAF"><br/><br>

</form>
<msp:evaluate>
MSPBlock[{$$a,$$b,$$c},a=$$a; b=$$b; c=$$c;]
</msp:evaluate>
Souradnice pruseciku s osou y:
[0,<msp:evaluate>MSPFormat[c,StandardForm]</msp:evaluate>]<br/><br>
Souradnice pruseciku s osou x:
[<msp:evaluate>MSPFormat[If[(b^2 - 4*a*c) >= 0,((-b+Sqrt[(b^2(4*a*c))])/(2*a)),Komplexni koren],StandardForm]
</msp:evaluate>,0]<br/><br>
Souradnice pruseciku s osou x:
[<msp:evaluate>MSPFormat[If[(b^2 - 4*a*c) >= 0,((-b-Sqrt[(b^2(4*a*c))])/(2*a)),Komplexni koren],StandardForm]
</msp:evaluate>,0]<br/><br>
Souradnice vrcholu paraboly:
[<msp:evaluate>MSPFormat[-b/(2*a),StandardForm]
</msp:evaluate>,
<msp:evaluate>MSPFormat[c-(b^2/(4*a)),StandardForm]
</msp:evaluate>]<br/><br>
<br>
<br>
<br/>
<center>
<msp:evaluate>
MSPBlock[{$$a,$$b,$$c},
MSPShow[ Plot[a*x^2 + b*x + c,{x,(If[(b^2 - 4*a*c) >= 0,
(((-b+Sqrt[b^2-4*a*c])/(2*a))+3),((-b/2*a)+3)]),(If[(b^2-4*a*c) >= 0,
(((-b - Sqrt[b^2 - 4*a*c])/(2*a))-3), ((-b/2*a)-3)])},
PlotStyle->{RGBColor[0,0,1]}, Epilog -> {PointSize[0.03], Hue[.7],
Point[{0,c}],Hue[5],
Point[{(If[b^2 - 4*a*c >= 0, (-b + Sqrt[b^2 - 4*a*c])/(2*a),
(-b/2*a)]), (If[b^2 - 4*a*c >= 0, 0, (c - (b^2/(4*a)))])}],
Point[{(If[b^2 - 4*a*c >= 0, (-b - Sqrt[b^2 - 4*a*c])/(2*a),
(-b/2*a)]), (If[b^2 - 4*a*c >= 0, 0,(c-(b^2/(4*a)))])}],
Hue[0.3],Point[{(-b/(2*a)),(c-(b^2/(4*a)))}]},
ImageSize->{1000,1000},AspectRatio->Automatic,AxesLabel -> {x, y},
PlotLabel ->StyleForm[TraditionalForm[a*x^2 + b*x + c], "Selection",
FontSlant -> "Bold", FontSize->10]]]]
</msp:evaluate>
</center>

</msp:allocateKernel>
<br>
<br>
<a href="http://home.pf.jcu.cz/webMathematica/webmath/index2.htm"
title="WebMATHEMATICA"><center><h6>Zpet na vyber
temat</h6></center></a> <br />
<br>
<br>
<center><IMG SRC="PIC\webm-black-animated.gif" ALT="webm-blackanimated.gif(30 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<center><td style='font-family: Helvetica; font-size: 10px; width:
100%'>Created by
<a href="http://www.wolfram.com"><span style='font-style:
italic'>Mathematica</span></a></center>
<HR> <center><p align="center"><font face="verdana,tahoma,sans serif"
size="1">webmaster: <a href="http://www.bendamira.wz.cz" title="BENDA
MIREK">Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">email</a> &copy; 2006</center>
<center><script language="javascript">
modate = new Date(document.lastModified);
year = modate.getYear();
if (year < 80)
year += 2000;
else if (year >= 80 && year < 200)
year += 1900;
mon = modate.getMonth()+1;
if (mon < 10)
mon = "0"+mon;
dat = modate.getDate();
if (dat < 10)
dat = "0"+dat;
resu = "Datum poslední aktualizace: "+dat+"."+mon+"."+year;
document.write(resu);
</script></FONT></CENTER>
</body>
</html>

• Kvadratická rovnice – výpočet diskriminantu, kořenů a graf
této rovnice
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib" prefix="msp" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtnl1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<head>
<meta http-equiv="content-type" content="text/html;
charset=windows-1250" />
<meta http-equiv="keywords" content="Mathematica,webMathematica"
/>
<meta http-equiv="author" content="all:Mira Benda" />
<meta http-equiv="copyright" content="© Mira Benda" />
<meta http-equiv="authormail" content="mirabenda@volny.cz" />
<meta http-equiv="language" content="czech" />
<meta http-equiv="country" content="cz" />
<meta http-equiv="content-script-type" content="text/javascript"
/>
<meta http-equiv="content-style-type" content="text/css" />
<meta http-equiv="content-language" content="cs" />
<title>WebMathematica</title>
</head>
<body bgcolor="white" text="black" link="blue" vlink="blue"
alink="blue" background="" bgproperties="fixed" leftmargin="150"
topmargin= "100"maginwidth="" marginheight="5">
<basefont face="Verdana" size="2" />
<center><IMG SRC="PIC\webm-black.gif" ALT="webm-black.gif(7 kb)"
WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<br>
<br />
<center><h1>KVADRATICKA RCE</h1></center><br><br/>
<center><h4>KOMPLET</h4></center>
<form action="kvadraticka.jsp" method="post">
<msp:allocateKernel>
<h2>
&nbsp;&nbsp;&nbsp;a&nbsp;x<sup>2</sup>&nbsp;+&nbsp;b&nbsp;x&nbsp;+&nbs
p;c&nbsp;=&nbsp;0
</h2>
a=<input name="a" size="1" value="<msp:evaluate>
MSPValue[$$a]
</msp:evaluate>">&nbsp;
b=<input name="b" size="1" value="
<msp:evaluate>
MSPValue[$$b]
</msp:evaluate>">&nbsp;
c=<input name="c" size="1" value="
<msp:evaluate>
MSPValue[$$c]
</msp:evaluate>">

<br>
<br>
<input type="submit" name="btnSubmit"

value ="FACHEJ">

<msp:evaluate>
MSPBlock[{$$a,$$b,$$c},a=$$a;b=$$b;c=$$c;]
</msp:evaluate>
<br>
<hr>
<br/>
D=
<msp:evaluate>
MSPFormat[b^2-(4*a*c),StandardForm]
</msp:evaluate>
<br>
<br>
<br/>
x<sub>1</sub>=
<msp:evaluate>
MSPFormat[((-b+Sqrt[(b^2-(4*a*c))])/(2*a)),StandardForm]
</msp:evaluate>
(Numericka hodnota
<msp:evaluate>
MSPFormat[N[((-b+Sqrt[(b^2-(4*a*c))])/(2*a))],StandardForm]
</msp:evaluate>)
<br>
<br/>
x<sub>2</sub>=
<msp:evaluate>
MSPFormat[((-b-Sqrt[(b^2-(4*a*c))])/(2*a)),StandardForm]
</msp:evaluate>
(Numericka hodnota
<msp:evaluate>
MSPFormat[N[((-b+Sqrt[(b^2-(4*a*c))])/(2*a))],StandardForm]
</msp:evaluate>)
<br>
<br>
<br>
Souradnice pruseciku s osou y:
[0,<msp:evaluate>MSPFormat[c,StandardForm]</msp:evaluate>]<br/><br>
Souradnice pruseciku s osou x:
[<msp:evaluate>
MSPFormat[
If[(b^2 - 4*a*c) >= 0,((-b+Sqrt[(b^2-(4*a*c))])/(2*a)),
Komplexni koren],StandardForm]
</msp:evaluate>,0]<br/><br>
Souradnice pruseciku s osou x:
[<msp:evaluate>
MSPFormat[
If[(b^2 - 4*a*c) >= 0,((-b-Sqrt[(b^2-(4*a*c))])/(2*a)),
Komplexni koren],StandardForm]
</msp:evaluate>,0]<br/><br>
Souradnice vrcholu paraboly:

g[<msp:evaluate>
MSPFormat[-b/(2*a),StandardForm]</msp:evaluate>,
<msp:evaluate>
MSPFormat[c-(b^2/(4*a)),StandardForm]</msp:evaluate>]<br/><br>
<br>
<br>
<b><font color="Red">Koreny rce</font></b><br/>
<br>
<b><font color="Blue">Prusecik s osou y</font></b><br/>
<br>
<b><font color="LightGreen">Vrchol paraboly</font></b><br/>
<br/>
<center>
<msp:evaluate>
MSPBlock[{$$a,$$b,$$c},
MSPShow[ Plot[a*x^2 + b*x + c,
{x,(If[(b^2 - 4*a*c) >= 0, (((-b + Sqrt[b^2 - 4*a*c])/(2*a))+3),
((-b/2*a)+3)]),(If[(b^2 - 4*a*c) >= 0,
(((-b - Sqrt[b^2 - 4*a*c])/(2*a))-3), ((-b/2*a)-3)])},
PlotStyle->{RGBColor[0,0,1]}, Epilog -> {PointSize[0.03], Hue[.7],
Point[{0,c}],Hue[5],
Point[{(If[b^2 - 4*a*c >= 0, (-b + Sqrt[b^2 - 4*a*c])/(2*a),
(-b/2*a)]), (If[b^2 - 4*a*c >= 0, 0, (c - (b^2/(4*a)))])}],
Point[{(If[b^2 - 4*a*c >= 0, (-b - Sqrt[b^2 - 4*a*c])/(2*a),
(-b/2*a)]), (If[b^2 - 4*a*c >= 0, 0,
(c-(b^2/(4*a)))])}],Hue[0.3],
Point[{(-b/(2*a)),(c-(b^2/(4*a)))}]},
ImageSize->{1000,1000},AspectRatio->Automatic,
AxesLabel->{x, y},PlotLabel ->StyleForm[
TraditionalForm[a*x^2 + b*x + c], "Selection", FontSlant -> "Bold",
FontSize->10]]]]
</msp:evaluate>
</center>
</msp:allocateKernel>
</form>
<br>
<br>
<br>
<a href="http://home.pf.jcu.cz/webMathematica/webmath/index2.htm"
title="WebMATHEMATICA"><center><h6>Zpet na vyber
temat</h6></center></a> <br />
<br>
<br>
<center><IMG SRC="PIC\webm-black-animated.gif" ALT="webm-blackanimated.gif(30 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<center><td style='font-family: Helvetica; font-size: 10px; width:
100%'>Created by
<a href="http://www.wolfram.com"><span style='font-style:
italic'>Mathematica</span></a></center>
<HR> <center><p align="center"><font face="verdana,tahoma,sans serif"
size="1">webmaster: <a href="http://www.bendamira.wz.cz" title="BENDA

MIREK">Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">email</a> &copy; 2006</center>
<center><script language="javascript">
modate = new Date(document.lastModified);
year = modate.getYear();
if (year < 80)
year += 2000;
else if (year >= 80 && year < 200)
year += 1900;
mon = modate.getMonth()+1;
if (mon < 10)
mon = "0"+mon;
dat = modate.getDate();
if (dat < 10)
dat = "0"+dat;
resu = "Datum poslední aktualizace: "+dat+"."+mon+"."+year;
document.write(resu);
</script></FONT></CENTER>
</body>
</html>

• Postupný výpočet všech předešlých aplikací
V tomto případě je použito rámu, proto jsou jednotlivé kroky (diskriminant,
kořeny kvadratické rovnice a graf) na sobě nezávislé a tato stránka může sloužit jako
pomocný pracovní list pro kontrolu jednotlivých kroků při výpočtu a případný rádce pro
dosažení správného řešení.
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<head>
<meta http-equiv="content-type" content="text/html;
charset=windows-1250" />
<meta http-equiv="keywords" content="Mathematica,webMathematica"
/>
<meta http-equiv="author" content="all:Mira Benda" />
<meta http-equiv="copyright" content="© Mira Benda" />
<meta http-equiv="authormail" content="mirabenda@volny.cz" />
<meta http-equiv="language" content="czech" />
<meta http-equiv="country" content="cz" />
<meta http-equiv="content-script-type" content="text/javascript"
/>
<meta http-equiv="content-style-type" content="text/css" />
<meta http-equiv="content-language" content="cs" />
<title>WebMathematica</title>
</head>
<body bgcolor="white" text="black" link="blue" vlink="blue"
alink="blue" background="" bgproperties="fixed" leftmargin="0"
topmargin= "100" maginwidth="" marginheight="5">
<basefont face="Verdana" size="2" />
<center>
<IMG SRC="PIC\webm-black.gif" ALT="webm-black.gif(7 kb)" WIDTH="468"
HEIGHT="60" BORDER="0">
</center>
<center>
<h1>&nbsp;&nbsp;KVADRATICKA RCE</h1>
</center>
<br><br/>
<iframe
src="http://home.pf.jcu.cz/webMathematica/webmath/kvadraticka/diskr1.j
sp" frameborder="0" scrolling="auto" border="0" width="800"
height="250" bordercolor="red" title="diskriminant" marginwidth="0"
marginheight="0" name="ram">
</iframe>
<iframe
src="http://home.pf.jcu.cz/webMathematica/webmath/kvadraticka/koreny1.
jsp" frameborder="0" scrolling="auto" border="0" width="800"
height="450" bordercolor="red" title="koreny" marginwidth="0"
marginheight="0" name="ram">
</iframe>
<center>

<iframe
src="http://home.pf.jcu.cz/webMathematica/webmath/kvadraticka/grafkva1
.jsp" frameborder="0" scrolling="auto" border="0" width="1150"
height="1550" bordercolor="red" title="graf" marginwidth="0"
marginheight="0" name="ram">
</iframe>
</center>
<br>
<a href="http://home.pf.jcu.cz/webMathematica/webmath/index2.htm"
title="WebMATHEMATICA"><center><h6>Zpet na vyber
temat</h6></center></a> <br />
<br>
<br>
<center><IMG SRC="PIC\webm-black-animated.gif" ALT="webm-blackanimated.gif(30 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<center><td style='font-family: Helvetica; font-size: 10px; width:
100%'>Created by
<a href="http://www.wolfram.com"><span style='font-style:
italic'>Mathematica</span></a></center>
<HR> <center><p align="center"><font face="verdana,tahoma,sans serif"
size="1">webmaster: <a href="http://www.bendamira.wz.cz" title="BENDA
MIREK">Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">email</a> &copy; 2006</center>
<center><script language="javascript">
modate = new Date(document.lastModified);
year = modate.getYear();
if (year < 80)
year += 2000;
else if (year >= 80 && year < 200)
year += 1900;
mon = modate.getMonth()+1;
if (mon < 10)
mon = "0"+mon;
dat = modate.getDate();
if (dat < 10)
dat = "0"+dat;
resu = "Datum poslední aktualizace: "+dat+"."+mon+"."+year;
document.write(resu);
</script></FONT></CENTER>
</body>
</html>

• Změna grafu kvadratické rovnice v závislosti na změně
parametru a (a x2 = 0)
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib" prefix="msp" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtnl1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<head>
<meta http-equiv="content-type" content="text/html;
charset=windows-1250" />
<meta http-equiv="keywords" content="Mathematica,webMathematica"
/>
<meta http-equiv="author" content="all:Mira Benda" />
<meta http-equiv="copyright" content="© Mira Benda" />
<meta http-equiv="authormail" content="mirabenda@volny.cz" />
<meta http-equiv="language" content="czech" />
<meta http-equiv="country" content="cz" />
<meta http-equiv="content-script-type" content="text/javascript"
/>
<meta http-equiv="content-style-type" content="text/css" />
<meta http-equiv="content-language" content="cs" />
<title>WebMathematica</title>
</head>
<body bgcolor="white" text="black" link="blue" vlink="blue"
alink="blue" background="" bgproperties="fixed" leftmargin="150"
topmargin= "100"maginwidth=""
marginheight="5">
<basefont face="Verdana" size="2" />
<center>
<IMG SRC="PIC\webm-black.gif" ALT="webm-black.gif(7 kb)" WIDTH="468"
HEIGHT="60" BORDER="0">
</center>
<br>
<br />
<center><h1>ANIMACE - zmena a</h1></center>
<br>
<br>
<center>
<h2>
a&nbsp;x<sup>2</sup>&nbsp;=&nbsp;0
</h2></center>
<form action="animacea.jsp" method="post">
Zadej rozmezi parametru a<br/><br>
<msp:allocateKernel>
od&nbsp;<input name="a1" size="1" value="
<msp:evaluate>MSPValue[$$a1]</msp:evaluate>">
<br/>
<br>
do&nbsp;<input name="a2" size="1" value="

<msp:evaluate>MSPValue[$$a2]</msp:evaluate>">&nbsp;
<br>
<br>
<center>
Stahovani pro tuto animaci bude chvilku trvat. Doporucuji zadat
rozmezi, ktere ma max 30 kroku (zmen). Krok (zmena) je 0.25 jednotky.
V opacnem pripade pro casovou narocnost nebude animace zobrazena.
</center>
<center>
Tzn. napr. " od: 2 do: 5 " je 3 * 4 = 12 kroku (zmen) ( 1 / 0.25
= 4 )
</center>
<br>
<br>
<br>
<br>
<input type="submit" name="btnSubmit" value ="FACHEJ">
<msp:evaluate>MSPBlock[{$$a1,$$a2},a1=$$a1; a2=$$a2;]</msp:evaluate>
<br>
<hr>
<br/>
<center>
<msp:evaluate>
MSPBlock[{$$a1,$$a2},
MSPShowAnimation[Table[Plot[i*x^2,{x,-5,5},
AspectRatio->Automatic,PlotRange->{-10,10},
ImageSize->{800,600},
AxesLabel->{x,TraditionalForm[i*x^2]}],{i,a1,a2,0.25}]]]
</msp:evaluate>
</center>
</msp:allocateKernel>
<br>
<br>
<a href="http://home.pf.jcu.cz/webMathematica/webmath/index2.htm"
title="WebMATHEMATICA"><center><h6>Zpet na vyber temat
</h6></center></a> <br />
<br>
<br>
<center><IMG SRC="PIC\webm-black-animated.gif" ALT="webm-blackanimated.gif(30 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<center><td style='font-family: Helvetica; font-size: 10px; width:
100%'>Created by
<a href="http://www.wolfram.com"><span style='font-style:
italic'>Mathematica</span></a></center>
<HR> <center><p align="center"><font face="verdana,tahoma,sans serif"
size="1">webmaster: <a href="http://www.bendamira.wz.cz" title="BENDA
MIREK">Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">email</a> &copy; 2006</center>
<center><script language="javascript">
modate = new Date(document.lastModified);
year = modate.getYear();

if (year < 80)
year += 2000;
else if (year >= 80 && year < 200)
year += 1900;
mon = modate.getMonth()+1;
if (mon < 10)
mon = "0"+mon;
dat = modate.getDate();
if (dat < 10)
dat = "0"+dat;
resu = "Datum poslední aktualizace: "+dat+"."+mon+"."+year;
document.write(resu);
</script></FONT></CENTER>
</body>
</html>

• Změna grafu kvadratické rovnice v závislosti na změně
parametru b (x2 + b x = 0)
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib" prefix="msp" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtnl1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<head>
<meta http-equiv="content-type" content="text/html;
charset=windows-1250" />
<meta http-equiv="keywords" content="Mathematica,webMathematica"
/>
<meta http-equiv="author" content="all:Mira Benda" />
<meta http-equiv="copyright" content="© Mira Benda" />
<meta http-equiv="authormail" content="mirabenda@volny.cz" />
<meta http-equiv="language" content="czech" />
<meta http-equiv="country" content="cz" />
<meta http-equiv="content-script-type" content="text/javascript"
/>
<meta http-equiv="content-style-type" content="text/css" />
<meta http-equiv="content-language" content="cs" />
<title>WebMathematica</title>
</head>
<body bgcolor="white" text="black" link="blue" vlink="blue"
alink="blue" background="" bgproperties="fixed" leftmargin="150"
topmargin= "100"maginwidth=""
marginheight="5">
<basefont face="Verdana" size="2" />
<center>
<IMG SRC="PIC\webm-black.gif" ALT="webm-black.gif(7 kb)" WIDTH="468"
HEIGHT="60" BORDER="0">
</center>
<br>
<br />
<center><h1>ANIMACE - zmena b</h1></center>
<br>
<br>
<center><h2>
&nbsp;x<sup>2</sup>&nbsp;+&nbsp;b&nbsp;x&nbsp;=&nbsp;0</h2>
</center>
<form action="animaceb.jsp" method="post">
Zadej rozmezi parametru c<br/><br>
<msp:allocateKernel>
od&nbsp;<input name="b1" size="1" value="<msp:evaluate>
MSPValue[$$b1]</msp:evaluate>">
<br/>
<br>
do&nbsp;<input name="b2" size="1" value="
<msp:evaluate>

MSPValue[$$b2]</msp:evaluate>">&nbsp;
<br>
<br>
<center>
Stahovani pro tuto animaci bude chvilku trvat. Doporucuji zadat
rozmezi, ktere ma max 30 kroku (zmen). Krok (zmena) je 0.25 jednotky.
V opacnem pripade pro casovou narocnost nebude animace zobrazena.
</center>
<center>
Tzn. napr. " od: 2 do: 5 " je 3 * 4 = 12 kroku (zmen) ( 1 / 0.25
= 4 )
</center>
<br>
<br>
<br>
<br>
<input type="submit" name="btnSubmit"

value ="FACHEJ">

<msp:evaluate>MSPBlock[{$$b1,$$b2},b1=$$b1; b2=$$b2;]</msp:evaluate>
<br>
<hr>
<br/>
<center>
<msp:evaluate>
MSPBlock[{$$b1,$$b2},
MSPShowAnimation[Table[Plot[x^2+i*x,{x,-10,10},
AspectRatio->Automatic,PlotRange->{-10,10},
ImageSize->{800,600},AxesLabel->{x,TraditionalForm[x^2+i*x]}],
{i,b1,b2,0.25}]]]
</msp:evaluate>
</center>
</msp:allocateKernel>
<br>
<br>
<a href="http://home.pf.jcu.cz/webMathematica/webmath/index2.htm"
title="WebMATHEMATICA"><center><h6>Zpet na vyber temat</h6>
</center></a> <br />
<br>
<br>
<center><IMG SRC="PIC\webm-black-animated.gif" ALT="webm-blackanimated.gif(30 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<center><td style='font-family: Helvetica; font-size: 10px; width:
100%'>Created by
<a href="http://www.wolfram.com"><span style='font-style:
italic'>Mathematica</span></a></center>
<HR> <center><p align="center"><font face="verdana,tahoma,sans serif"
size="1">webmaster: <a href="http://www.bendamira.wz.cz" title="BENDA

MIREK">Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">email</a> &copy; 2006</center>
<center><script language="javascript">
modate = new Date(document.lastModified);
year = modate.getYear();
if (year < 80)
year += 2000;
else if (year >= 80 && year < 200)
year += 1900;
mon = modate.getMonth()+1;
if (mon < 10)
mon = "0"+mon;
dat = modate.getDate();
if (dat < 10)
dat = "0"+dat;
resu = "Datum poslední aktualizace: "+dat+"."+mon+"."+year;
document.write(resu);
</script></FONT></CENTER>
</body>
</html>

• Změna grafu kvadratické rovnice v závislosti na změně
parametru c (x2 + c = 0)
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib" prefix="msp" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtnl1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<head>
<meta http-equiv="content-type" content="text/html;
charset=windows-1250" />
<meta http-equiv="keywords" content="Mathematica,webMathematica"
/>
<meta http-equiv="author" content="all:Mira Benda" />
<meta http-equiv="copyright" content="© Mira Benda" />
<meta http-equiv="authormail" content="mirabenda@volny.cz" />
<meta http-equiv="language" content="czech" />
<meta http-equiv="country" content="cz" />
<meta http-equiv="content-script-type" content="text/javascript"
/>
<meta http-equiv="content-style-type" content="text/css" />
<meta http-equiv="content-language" content="cs" />
<title>WebMathematica</title>
</head>
<body bgcolor="white" text="black" link="blue" vlink="blue"
alink="blue" background="" bgproperties="fixed" leftmargin="150"
topmargin= "100"maginwidth=""
marginheight="5">
<basefont face="Verdana" size="2" />
<center><IMG SRC="PIC\webm-black.gif" ALT="webm-black.gif(7 kb)"
WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<br>
<br />
<center><h1>ANIMACE - zmena c</h1></center>
<br>
<br>
<center><h2>
&nbsp;x<sup>2</sup>&nbsp;+&nbsp;c&nbsp;=&nbsp;0</h2>
</center>
<form action="animacec.jsp" method="post">
Zadej rozmezi parametru c<br/><br>
<msp:allocateKernel>
od&nbsp;<input name="c1" size="1" value="
<msp:evaluate>MSPValue[$$c1]</msp:evaluate>">
<br/>
<br>
do&nbsp;<input name="c2" size="1" value="<msp:evaluate>
MSPValue[$$c2]</msp:evaluate>">&nbsp;
<br>
<br>

<center>
Stahovani pro tuto animaci bude chvilku trvat. Doporucuji zadat
rozmezi, ktere ma max 30 kroku (zmen). Krok (zmena) je 0.25 jednotky.
V opacnem pripade pro casovou narocnost nebude animace zobrazena.
</center>
<center>
Tzn. napr. " od: 2 do: 5 " je 3 * 4 = 12 kroku (zmen) ( 1 / 0.25
= 4 )
</center>
<br>
<br>
<br>
<br>
<input type="submit" name="btnSubmit"

value ="FACHEJ">

<msp:evaluate>MSPBlock[{$$c1,$$c2},c1=$$c1; c2=$$c2;]</msp:evaluate>
<br>
<hr>
<br/>
<center>
<msp:evaluate>
MSPBlock[{$$c1,$$c2},
MSPShowAnimation[Table[Plot[x^2+i,{x,-5,5},
AspectRatio->Automatic,ImageSize->{800,600},
PlotRange->{-10,10},AxesLabel->{x,TraditionalForm[x^2+i]}],
{i,c1,c2,0.25}]]]
</msp:evaluate>
</center>
</msp:allocateKernel>
<br>
<br>
<a href="http://home.pf.jcu.cz/webMathematica/webmath/index2.htm"
title="WebMATHEMATICA"><center><h6>Zpet na vyber
temat</h6></center></a> <br />
<br>
<br>
<center><IMG SRC="PIC\webm-black-animated.gif" ALT="webm-blackanimated.gif(30 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<center><td style='font-family: Helvetica; font-size: 10px; width:
100%'>Created by
<a href="http://www.wolfram.com"><span style='font-style:
italic'>Mathematica</span></a></center>
<HR> <center><p align="center"><font face="verdana,tahoma,sans serif"
size="1">webmaster: <a href="http://www.bendamira.wz.cz" title="BENDA
MIREK">Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">email</a> &copy; 2006</center>
<center><script language="javascript">
modate = new Date(document.lastModified);
year = modate.getYear();
if (year < 80)
year += 2000;
else if (year >= 80 && year < 200)
year += 1900;

mon = modate.getMonth()+1;
if (mon < 10)
mon = "0"+mon;
dat = modate.getDate();
if (dat < 10)
dat = "0"+dat;
resu = "Datum poslední aktualizace: "+dat+"."+mon+"."+year;
document.write(resu);
</script></FONT></CENTER>
</body>
</html>

7.1.2 Grafy elementárních funkcí
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtnl1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<head>
<meta http-equiv="content-type" content="text/html;
charset=windows-1250" />
<meta http-equiv="keywords" content="Mathematica,webMathematica"
/>
<meta http-equiv="author" content="all:Mira Benda" />
<meta http-equiv="copyright" content="© Mira Benda" />
<meta http-equiv="authormail" content="mirabenda@volny.cz" />
<meta http-equiv="language" content="czech" />
<meta http-equiv="country" content="cz" />
<meta http-equiv="content-script-type" content="text/javascript"
/>
<meta http-equiv="content-style-type" content="text/css" />
<meta http-equiv="content-language" content="cs" />
<title>WebMathematica</title>
</head>
<body bgcolor="white" text="black" link="blue" vlink="blue"
alink="blue" background="" bgproperties="fixed" leftmargin="150"
topmargin= "100"maginwidth="" marginheight="5">
<basefont face="Verdana" size="2" />
<center>
<IMG SRC="PIC\webm-black.gif" ALT="webm-black.gif(7 kb)" WIDTH="468"
HEIGHT="60" BORDER="0">
</center>
<br>
<center><h1>GRAFY ELEMENTARNICH FCI</h1></center>
<form action="graffce.jsp" method="post">
<msp:allocateKernel>
<br>
<h3 align="center">
PREHLED ZAKLADNICH ELEMENTARNICH FCI VE webMATHEMATICA
</h3>
<TABLE border="20" align="center" widht="500" cellspacing="5"
cellpadding="5">
<caption align="bottom">Syntax webMathematica</caption>
<tr>
<td align="center" bordercolor="BLACK" colspan="2">
<b>FUNKCE</b>
</td>
<td>
<td/>
<td align="center" bordercolor="BLACK">Nazev fce
</td>
<td>

<td/>
<td align="center"bordercolor="BLACK" colspan="3" >
<b>SYNTAX webMATHEMATICA</b>
</td>
<td>
<td/>
<td align="center" bordercolor="BLACK">Poznamka
</td>
</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2"><b>
<msp:evaluate>MSPFormat[ax+b,TraditionalForm]</msp:evaluate></b>
</td>
<td>
<td/>
<td bordercolor="BLACK">Linearni fce
</td>
<td>
<td/>
<td align="center"bordercolor="BLACK" colspan="3"><b>a*x+b</b>
</td>
<td>
<td/>
<td align="center">Kde
<msp:evaluate>MSPFormat[a != 0,StandardForm]</msp:evaluate>
</msp:evaluate>
</td>
</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2"><b>
<msp:evaluate>MSPFormat[Abs[x],TraditionalForm]</msp:evaluate></b>
</td>
<td>
<td/>
<td bordercolor="BLACK">Fce s absolutni hodnotou
</td>
<td>
<td/>
<td align="center"bordercolor="BLACK" colspan="3"><b>
Abs[x]</b>
</td>
<td>
<td/>
<td align="center">
</td>
</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2"><b>
<msp:evaluate>
MSPFormat[(ax+b)/(cx+d),TraditionalForm]
</msp:evaluate></b>
</td>
<td>
</td>
<td bordercolor="BLACK">Linearni lomena fce
</td>
<td>
<td/>

<td align="center"bordercolor="BLACK" colspan="3"><b>
(a*x+b)/(c*x+d)</b>
</td>
<td>
<td/>
<td align="center">Kde vyrazy
<msp:evaluate>
MSPFormat[c!=0,TraditionalForm]
</msp:evaluate> a
<msp:evaluate>
MSPFormat[(bc-ad)!=0,TraditionalForm]
</msp:evaluate></td>
</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2"><b>
<msp:evaluate>
MSPFormat[a*x^2+b*x+c,TraditionalForm]
</msp:evaluate></b>
</td>
<td>
<td/>
<td bordercolor="BLACK">Kvadraticka fce
</td>
<td>
<td/>
<td align="center"bordercolor="BLACK" colspan="3">
<b>a*x^2+b*x+c</b>
</td>
<td>
<td/>
<td align="center">Kde
<msp:evaluate>
MSPFormat[a != 0,StandardForm]
</msp:evaluate>
</td>
</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2"><b>
<msp:evaluate>
MSPFormat[x^n,StandardForm]
</msp:evaluate></b>
</td>
<td>
<td/>
<td bordercolor="BLACK">Mocnina fce
</td>
<td>
<td/>
<td align="center"bordercolor="BLACK" colspan="3"><b>x^n</b>
</td>
<td>
<td/>
<td align="center">Kde n patri do N
</td>
</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2"><b>
<msp:evaluate>
MSPFormat[Sqrt[x],StandardForm]

</msp:evaluate></b>
</td>
<td>
<td/>
<td bordercolor="BLACK">Odmocnina
</td>
<td>
<td/>
<td align="center"bordercolor="BLACK" colspan="3"><b>
Sqrt[x]</b>
</td>
<td>
<td/>
<td align="center">Odmocnina je def. na intervalu
<0,<msp:evaluate>
MSPFormat[Infinity,TraditionalForm]
</msp:evaluate>)
</td>
</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2"><b>
<msp:evaluate>
MSPFormat[a^x,StandardForm]</msp:evaluate></b>
</td>
<td>
<td/>
<td bordercolor="BLACK">Exponencialni fce
</td>
<td>
<td/>
<td align="center"bordercolor="BLACK" colspan="3"><b>a^x</b>
</td>
<td>
<td/>
<td align="center">Kde a je ruzne od 1
</td>
</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2"><b>
<msp:evaluate>
MSPFormat[ln[x],TraditionalForm]
</msp:evaluate></b>
</td>
<td>
<td/>
<td bordercolor="BLACK">Pritozeny logaritmus
</td>
<td>
<td/>
<td align="center"bordercolor="BLACK" colspan="3"><b>
Log[x]</b>
</td>
<td>
<td/>
<td align="center">Zaklad je
<msp:evaluate>
MSPFormat[e,StandardForm]
</msp:evaluate> (Eulerovo cislo)
</td>

</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2"><b>
<msp:evaluate>
MSPFormat[Log[x],TraditionalForm]
</msp:evaluate></b>
</td>
<td>
<td/>
<td bordercolor="BLACK">Dekadicky logaritmus
</td>
<td>
<td/>
<td align="center"bordercolor="BLACK" colspan="3"><b>
Log[10,x]</b>
</td>
<td>
<td/>
<td align="center">Zaklad je
<msp:evaluate>
MSPFormat[10,StandardForm]
</msp:evaluate>
</td>
</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2">
<msp:evaluate>
MSPFormat[Sin[x],TraditionalForm]
</msp:evaluate>
</td>
<td>
<td/>
<td bordercolor="BLACK">Funkce sinus
</td>
<td>
<td/>
<td align="center"bordercolor="BLACK" colspan="3">
<b>Sin[x]</b>
</td>
<td>
<td/>
<td align="center">Pro zadani mezi s
<msp:evaluate>
MSPFormat[\[Pi],TraditionalForm]
</msp:evaluate> napis "Pi"
</td>
</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2">
<msp:evaluate>
MSPFormat[Cos[x],TraditionalForm]</msp:evaluate>
</td>
<td>
<td/>
<td bordercolor="BLACK">Funkce kosinus
</td>
<td>
<td/>
<td align="center"bordercolor="BLACK" colspan="3"><b>

Cos[x]</b>
</td>
<td>
<td/>
<td align="center">Pro zadani mezi s <msp:evaluate>
MSPFormat[\[Pi],TraditionalForm]
</msp:evaluate> napis "Pi"
</td>
</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2">
<msp:evaluate>
MSPFormat[tg[x],TraditionalForm]
</msp:evaluate>
</td>
<td>
<td/>
<td bordercolor="BLACK">Funkce tangens
</td>
<td>
<td/>
<td align="center"bordercolor="BLACK" colspan="3"><b>Tan[x]</b>
</td>
<td>
<td/>
<td align="center">Def. na R bez lichych nasobku
<msp:evaluate>
MSPFormat[\[Pi]/2,TraditionalForm]
</msp:evaluate>
</td>
</tr>
<tr>
<td align="center" bordercolor="BLACK" colspan="2">
<msp:evaluate>
MSPFormat[cotg[x],TraditionalForm]
</msp:evaluate>
</td>
<td>
<td/>
<td bordercolor="BLACK">Funkce kotangens
</td>
<td>
<td/>
<td align="center"bordercolor="BLACK" colspan="3"><b>Cot[x]</b>
</td>
<td>
<td/>
<td align="center">Def. na R bez nasobku
<msp:evaluate>
MSPFormat[\[Pi],TraditionalForm]
</msp:evaluate>
</td>
</tr>
<tr>
<td align="center" colspan="5" valign="middle" rowspan="1">
Poznamka k syntaxu WebMathematica
</td>
<td>
<td/>

<td rowspan="15" colspan="6">
<br>
- Za symbol promenne je voleno oznaceni "x".
<br/><br>
- "a,b,c,d" jsou parametry.
<br/><br>
- Osovy kriz je nastaven na stejne jednotky na osach "x" a
"y", proto muze byt nektery graf spatne citelny (maly), v tomto
pripade je treba zadat jine meze.
<br/><br>
- Mathematica chape vyrazy "a*x" a "ax" za totozne, proto je
mozne znak pro nasobeni vynechavat.
<br/><br>
- Pouziva se desetina "." ne ","
<br/><br>
- Pozor na zamenu zavorek [] za ().
<br/><br>
- Pozor na zamenu velkych a malych pismen.
<br/><br>
- U slozitejsich vyrazu je treba kontrolovat sudy pocet
zavorek. (respektive jejich uzavreni - [], pripadne () )
<br/><br>
- Pozor na zadani totoznych hodnot pro meze.
<br/><br>
- U mezi nevadi zadani mezi od "klade" do "zaporne".
<br/><br>
</td>
</tr>
<tr>
<td>
</td>
</tr>
</TABLE>
<br>
<br>
<br>
<br>
FCE:&nbsp;
<input name="fun" size="15" value ="
<msp:evaluate>
MSPValue[$$fun]
</msp:evaluate>"
<br/>
<br>
<br>
Rozmezi osy x:
<br/>
<br>
od:&nbsp;&nbsp;&nbsp;
<input name="x1" size="2" value ="
<msp:evaluate>
MSPValue[$$x1]
</msp:evaluate>"
<br/>
<br>

do:&nbsp;&nbsp;&nbsp;
<input name="x2" size="2" value ="
<msp:evaluate>
MSPValue[$$x2]
</msp:evaluate>"
<br/>
<br>
<br>
<msp:evaluate>
MSPBlock[{$$x1,$$x2},x1=$$x1;x2=$$x2;]
</msp:evaluate>
<input type="submit" name="btnSubmit"

value ="GRAF">

<hr>
<br>
<br>
<br>
<msp:evaluate>
MSPBlock[ {$$fun, $$x1, $$x2},
MSPShow[ Plot[$$fun,{x,$$x1,$$x2},
PlotStyle->{RGBColor[0,0,1]},AxesLabel ->{x,y},AspectRatio->Automatic,
PlotRange->All,ImageSize ->{1000,1000},
PlotLabel ->StyleForm[TraditionalForm[$$fun], "Selection",
FontSlant -> "Italic", FontSize -> 15]]]]
</msp:evaluate>
<br>
</msp:allocateKernel>
</form>
<BR>
<br>
<br>
<a href="http://home.pf.jcu.cz/webMathematica/webmath/index2.htm"
title="WebMATHEMATICA"><center><h6>Zpet na vyber
temat</h6></center></a> <br />
<center><IMG SRC="PIC\webm-black-animated.gif" ALT="webm-blackanimated.gif(30 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<center><td style='font-family: Helvetica; font-size: 10px; width:
100%'>Created by
<a href="http://www.wolfram.com"><span style='font-style:
italic'>Mathematica</span></a></center>
<HR> <center><p align="center"><font face="verdana,tahoma,sans serif"
size="1">webmaster: <a href="http://www.bendamira.wz.cz" title="BENDA
MIREK">Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">email</a> &copy; 2006</center>
<center> <script language="javascript">
modate = new Date(document.lastModified);
year = modate.getYear();
if (year < 80)
year += 2000;
else if (year >= 80 && year < 200)
year += 1900;
mon = modate.getMonth()+1;
if (mon < 10)
mon = "0"+mon;

dat = modate.getDate();
if (dat < 10)
dat = "0"+dat;
resu = "Datum poslední aktualizace: "+dat+"."+mon+"."+year;
document.write(resu);
</script></FONT></CENTER>
</body>
</html>

7.2. Internetové stránky
7.2.1 Kvadratická rovnice, kvadratická funkce
Ukázka některých webových stránek:

Obrázek 7.1 – Graf kvadratické rovnice (význačné body)

Obrázek 7.2 – Graf kvadratické rovnice

7.2.2 Grafy elementárních funkcí

Obrázek 7.3 – Grafy elementárních fcí (tabulka- syntax)

Obrázek 7.4 – Grafy elementárních fcí (graf fce)

8. Závěr
Naším cílem bylo využívat produkt webMathematica takovým způsobem, aby
mohly být výsledky naší práce použitelné ve výuce matematiky na střední škole. Co
všechno obnášela práce na naší diplomové práci, čeho jsme dosáhli, co se nám podařilo
nebo co se nám naopak nepodařilo, bychom chtěli zmínit v této části.
První překážkou bylo malé množství materiálů, ze kterých jsme mohli čerpat
informace, takže samotná tvorba stránek ve webMathematica byla zpočátku velice
náročná a intuitivní. Postupně jsme v naší práci získávali jistotu, pochopili souvislosti
a logiku webMathematica a nyní je výsledkem zpracování několika matematických
témat pomocí webMathematica. Chtěli jsme, aby zpracovaná témata mohl využívat
učitel sám a demonstrovat pomocí nich probíranou látku. Proto jsme zpracovali grafy
elementárních funkcí, zobrazování komplexních čísel v Gaussově rovině nebo grafické
výstupy v části analytické geometrie. Ostatní aplikace jako početní operace
s komplexními čísly, řešení kvadratické rovnice – výpočty diskriminantu, kořenů,
průsečíků s osami nebo výpočty v analytické geometrii, jsou určeny především
studentům, kteří si na nich mohou procvičit danou látku. Otázka, jaká témata zpracovat
nebo rozpracovat nebyla jednoduchá a přinesla nám nejeden problém. Po zvážení jsme
však vybrali ta, o kterých si myslíme, že by studenty mohla zajímat nebo ta, která by
mohla studentů činit potíže, a které jsme byli schopni připravit, otestovat a odladit.
Jak jste si jistě všimli, naše stránky bohužel neobsahují české kódování,
proto jsou všechny slovní zápisy bez české diakritiky. Jistě by se tento problém dal
nějakým způsobem vyřešit, ale my jsme tento problém bohužel nevyřešili. To bude úkol
pro některého z našich pokračovatelů. Popřípadě někoho, kdo ovládá tvorbu webových
stránek lépe než my. Také jsme předpokládali, že zpracujeme více témat, ale vzhledem
k nedostatečnému množství materiálů, což mělo v nemalé míře vliv na to, že jsme
relativně pozdě přišli na postup, jakým tvořit stránky ve webMathematica, a díky
časové náročnosti, se nám jich z původnímu plánu podařilo zpracovat méně.
Podařilo se nám vytvořit webové stránky, na kterých je rozpracováno několik
témat středoškolské matematiky. Rádi bychom, aby se našli další studenti, kteří by
v této práci pokračovali tak, aby hledali nová, pro ně zajímavá témata, a obohacovali
jimi webové stránky. Popřípadě, aby doplňovali námi zpracovaná témata tak, aby se na

webových stránkách postupně objevily všechny okruhy středoškolské matematiky.
Chtěli bychom, aby každý, kdo navštíví tento portál na fakultních stránkách, našel vše,
co by potřeboval pro ilustraci příkladů, k procvičení probírané matematické látky, pro
její lepší pochopení, pro jasnější prezentaci výkladu při hodinách matematiky, a
v neposlední řadě i pro rozšíření vlastních znalostí a představivosti. Šlo nám nejen o to
vytvořit pomůcku platnou při výuce matematiky využívanou především učiteli, ale i o
to, aby možnost praktického ověření probírané látky, vedla k zájmu studenta z jeho
vlastní iniciativy. Myslíme, že webMathematica zpřístupňuje a zjednodušuje cestu
k tomuto poznání.
Vytvořili jsme zajímavou pomůcku, která je dalším krokem pro vylepšení
představivosti studentů a lepšího chápání matematické látky. Doufáme, že u některých
studentů zvýšíme zájem o matematiku jako takovou. A o to nám jde především.

9. Užitá literatura a www
Literatura

[1] WOLFRAM, S.: The MATHEMATICA BOOK 5th ed., USA, Wolfram
Media, 2003

[2] POLÁK, J.: Přehled středoškolské matematiky, Praha, Prométheus, 1995

www

[1] http://www.wolfram.com/

[2] http://www.wolfram.com/products/webmathematica/index.html

[3] http://documents.wolfram.com/webmathematica/

[4] http://www.mathematica.cz/

[5] PRSKAVEC, L.: http://k315.feld.cvut.cz/vyuka/webmathematica
[6] PRSKAVEC, L.: http://ladislav.prskavec.net/

