---
title: "BurianovaV_DP_duben2007_èestné uznání.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/Diplomové práce/Vyuití webMathematica na støední kole/BurianovaV_DP_duben2007_èestné uznání.pdf"
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

Veronika BURIANOVÁ

České Budějovice, duben 2007

Prohlašuji, že jsem diplomovou práci zpracovala samostatně a použitou literaturu jsem
citovala.
V Českých Budějovicích.................... 2007

..........................................
Veronika Burianová

Anotace
Cílem diplomové práce je zpracovat jednotlivé způsoby, jakými lze využívat
produkt webMathematica ve výuce matematiky na středních školách. Široké využití
programu webMathematica je umožněno jeho volnou přístupností pro všechny uživatele
libovolného internetového prohlížeče. Výsledné poznatky budou prezentovány v rámci
internetového portálu vznikajícího jako součást internetových stránek katedry
matematiky. Z tohoto portálu budou pedagogičtí pracovníci i jejich studenti moci čerpat
webové aplikace, které názorně ilustrují podstatu jednotlivých matematických pojmů.

Annotation
The aim of this thesis is to analyze the individual ways how to use the
webMathematica product in teaching mathematics at secondary schools. The extensive
usage of webMathematica programme is provided by its free access for all users of any
internet browser. The final results will be presented within the internet gateway which is
developed as a part of web sites of the Department of Mathematics. From this internet
gateway can teachers and their students gather web applications which illustrate the
principle of particular mathematical terms.

Poděkování:
Děkuji panu RNDr. Tomášovi Mrkvičkovi Ph.D., vedoucímu mé diplomové
práce, za jeho odborné vedení, cenné rady a připomínky, kterými mi pomohl při jejím
vypracování.
Dále bych chtěla poděkovat svému kolegovi Miroslavu Bendovi za jeho cennou
spolupráci při vývoji a porozumění tajům webMathematica, rodině a přátelům za
podporu při studiu.

Obsah
1. Úvod..............................................................................................................................7
1.1 Cíl............................................................................................................................8
1.2 Jak si představujeme využití naší práce ..................................................................8
2. Co je webMathematica?................................................................................................9
2.1 Proč se používá webMathematica na webu ............................................................9
2.1.1 Výpočty ............................................................................................................9
2.1.2 Propojitelnost ...................................................................................................9
2.1.3 Mathematica front end ...................................................................................10
2.1.4 Matematické zápisy a MathML .....................................................................10
3. Proč webové rozhraní?................................................................................................11
3.1 Snadné používání ..................................................................................................11
3.2 Server – základní konfigurace...............................................................................11
3.3 Oblasti využití webMathematica...........................................................................12
4. Mathematica ................................................................................................................13
4.1 Mathematica versus webMathematica ..................................................................16
4.2 Mathematica versus webMathematica – výstup ...................................................17
4.2.1 Výstup v podobě Mathematica notebooku:....................................................17
4.2.2 Výstup v podobě webové stránky - JSP:........................................................18
5. webMathematica – technologie...................................................................................19
5.1 Spojení Mathematica a HTML .............................................................................19
5.2 Technologie...........................................................................................................19
5.3 webMathematica - Schéma technologie................................................................20
6. Praktická část ..............................................................................................................21
6.1 Úvod do HTML ....................................................................................................21
6.2 MSP statická stránka .............................................................................................22
6.2.1 Vytvoření HTML stránky bez Math tagů ......................................................22
6.2.2 Uložení souboru jako *.jsp............................................................................22
6.2.3 Přidání webMath tagů ....................................................................................23
6.2.4 Přidání kódu v Mathematice mezi webMath tagy..........................................23
6.2.5 Přidání specifických příkazů do kódu v Mathematica ...................................24
6.2.6 Otestování v prohlížeči ..................................................................................25
6.3 Tvorba MSP na příkladu .......................................................................................25
6.3.1 Výroba notebooku v Mathematice .................................................................26
6.3.2 Vytvoření HTML stránky s formulářem ........................................................26
6.3.3 Uložení souboru jako JSP do adresáře, kde je nainstalovaná
webMathematica .....................................................................................................27
6.3.4 Přidání webMathematica tagů........................................................................27
6.3.5 Přidání kódu v Mathematica mezi webMathematica tagy a přidání
specifických příkazů do kódu v Mathematica .........................................................28
6.3.6 Otestování stránky v prohlížeči......................................................................30
6.4 Přehled důležitých tagů a příkazů .........................................................................31
6.4.1 HTML tagy ....................................................................................................31
6.4.2 webMathematica tagy ....................................................................................31
6.4.3 Mathematica kód............................................................................................31
6.4.4 MSP specifické příkazy .................................................................................31

7. Témata.........................................................................................................................34
7.1. Zdrojové kódy ......................................................................................................34
7.1.1 Komplexní čísla – početní operace ................................................................34
7.1.2 Komplexní čísla – goniometrický tvar...........................................................37
7.1.3 Komplexní čísla – zobrazení v rovině............................................................41
7.1.4 Analytická geometrie .....................................................................................44
7.2 Internetové stránky................................................................................................56
8. Závěr ...........................................................................................................................59
9. Užitá literatura a www ................................................................................................61

1. Úvod
Diplomová práce – Využití produktu webMathematica ve výuce na střední škole
– byla zadána tak, že ji bylo možné zpracovat týmově. Proto jsme si toto téma vybrali,
a proto také i webové stránky, které jsou hlavní částí této práce, vznikaly ve vzájemné
spolupráci s kolegou Miroslavem Bendou.
Cílem naší diplomové práce je zpracovat jednotlivé způsoby, jakými lze
využívat produkt webMathematica ve výuce matematiky na středních školách. Jeho
využití si představujeme dvěma způsoby. Prvním způsobem je využití produktu
webMathematica při hodinách, kdy má učitel k dispozici pouze jeden počítač, nebo mu
jeden počítač v danou chvíli stačí, a data-projektor. V této situaci lze naši práci použít
jako pomůcku pro doplnění jeho výkladu, pro snadnější pochopení látky,
pro demonstraci různých typů grafů, jako pomoc pro představivost studenta,
a samozřejmě i pro zpestření hodiny. Druhým

způsobem

je

využití v

hodinách,

kdy je možné

výuku

přemístit do počítačových učeben, kde je možnost

práce

počítačů.

Například v matematických cvičeních, kdy je látka již

u

více

probrána a je třeba ji procvičit na co největším množství příkladů. Každý student má
k dispozici svůj počítač, pracuje samostatně a svoji práci si kontroluje pomocí počítače,
přičemž učitel pomáhá a radí.
Jsme si vědomi, že na všech školách není možnost vyučovat matematiku
v učebnách výpočetní techniky, ale věříme, že situace se bude zlepšovat,
a že počítačové výbavy bude na školách přibývat nejen pro využití v hodinách
výpočetní techniky.
V diplomové práci se v prvních kapitolách zabýváme tím, co produkt
webMathematica je, jak funguje, jaké jsou výhody jeho použití. Praktická část obsahuje
samotnou tvorbou webových stránek a tvorbu Mathematica Server Pages (MSP).
Podařilo se nám zpracovat několik témat středoškolské matematiky a přáli
bychom si, aby webové stránky s těmito tématy byly učiteli i studenty do budoucna
využívány. Aby se staly pomocníkem učitelů při výuce, studentům návodem
k porozumění dané látky a zároveň jejich cvičebnicí. Chceme, aby propojovaly svět
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
množství příkladů) do počítačové učebny. A to formou kdy učitel prezentuje na dataprojektoru, nebo každý žák má k dispozici počítač a pracuje samostatně. Kontroluje
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
pro vědecké výpočty narozdíl od jiných webových technologií.

2.1.2 Propojitelnost
Mathematica je

schopna

se

pohotově propojit s externími službami,

které poskytují programovací jazyky jako jsou Java, C, Fortran nebo Perl. Tyto služby
mohou poskytovat datové zdroje pro výpočty a také využívat výsledky z Mathematica.

Zvláště jednoduché je spojení s Java přes J/Link. J/Link je soubor nástrojů
pro integraci Java do Mathematica.

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
.

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

Mathematica je vývojové prostředí pro WebMathematica Například:

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
Jak už jsme se zmínili, webMathematica nabízí přístup k aplikacím Mathematica
a využívá vše z tohoto programu. Když je vznesen požadavek na jedné ze stránek
webMathematica, Mathematica vyhodnotí příkazy a

výsledek

se

zobrazí

na příslušnou stránku. Toto umožňují tzv. Java Server Pages (JSP) – standardní Java
technologie využívající uživatelské tagy.
Po počátečním nastavení jsou vše, co je potřebné k psaní webMathematica
aplikací, základní znalosti tvorby HTML a Mathematica.

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

1. Webový prohlížeč posílá požadavek na webMathematica server.
2. WebMathematica server si rezervuje Mathematica kernel (jádro)
z bazénu.
3. Mathematica kernel je nastaven, provede kalkulace a vrací výsledky.
4. WebMathematica server vrací Mathematica kernel do bazénu.
5. WebMathematica server vrací výsledky webovému prohlížeči.1

Při práci na této diplomové práci jsme používali program webMathematica 2,
který je v současné době poslední verzí. Instalace tohoto softwaru je na fakultním
serveru Pedagogické fakulty katedry matematiky.
( http://home.pf.jcu.cz/webmathematica/webmath )

1

http://ladislav.prskavec.net/

6. Praktická část
V této části naší diplomové práce se snažíme osvětlit vznik jednoduché stránky
ve webMathematica a to nejprve jako vznik jednoduché webové stránky (*.html)
a pak její transformaci na stránku pro webMathematica (*.jsp).

6.1 Úvod do HTML
HTML je zkratka z anglického Hypertext Markup Language, značkovací jazyk
pro hypertext. Je jedním z jazyků pro vytváření stránek v systému www ( World Wide

Web ), který umožňuje publikaci stránek na

internetu.

Jazyk je podmnožinou dříve vyvinutého rozsáhlého univerzálního značkovacího
jazyka SGML ( Standard Generalized Markup Language ). Vývoj HTML byl ovlivněn
vývojem webových browserů (prohlížečů), které zpětně ovlivňovaly definici jazyka.

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
o http://home.pf.jcu.cz/webMathematica/webmath . Samostatná stránka bez přípony
*.jsp je nefunkční i kdyby již obsahovala webMathematica příkazy a tagy.

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

6.2.5 Přidání specifických příkazů do kódu v Mathematica
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
Jednotlivé specifické příkazy jsou vypsány v kapitole 6.4.

6.2.6 Otestování v prohlížeči
Výsledek po uložení na server, kde je webMathematica nainstalována,
zkontrolujeme webovým prohlížečem. Jedná se především o kontrolu funkčnosti
vytvářené aplikace.4

6.3 Tvorba MSP na příkladu
Tvorbu MSP se pokusíme demonstrovat na jednoduchém příkladu. Příklad bude
na součet dvou libovolných čísel.

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
<h2>Soucet</h2>
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

6.3.5 Přidání kódu v Mathematica mezi webMathematica tagy a
přidání specifických příkazů do kódu v Mathematica
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
Základní HTML tagy jsou uvedené v kapitole 6.1 - Úvod do HTML, tudíž je zde
nebudeme znovu uvádět.

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
</msp:evaluate>5
Z anglického evaluate jasně vyplývá, že se jedná

o příkaz vyhodnoť, což je v tomto případě příkaz pro webMathematica, aby provedla
výpočet, nebo splnila následující příkazy.

6.4.3 Mathematica kód
Používá se standardní příkazy Mathematica. Stejný syntax, konstrukce a logika
příkazů.

6.4.4 MSP specifické příkazy
- MSP statické příkazy:
•

5
6

MSPShow[]6

http://documents.wolfram.com/webmathematica/
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

HTMLFormat[výraz]7
Formátuje výrazy do jednoduchého HTML. Není to tak dobré jako grafika

nebo MathML
7

http://ladislav.prskavec.net/

- MSP dynamické příkazy:
Narozdíl od Mathematica nemusí být MSP neměnné. Toho se docílí použití
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

String na výraz, důležité při ošetření vstupů.8

8

http://ladislav.prskavec.net/

7. Témata
Ke zpracování jsem si vybrala dvě témata - komplexní čísla a analytickou
geometrii v rovině. U prvního tématu jsem se zabývala početními operacemi
s komplexními čísly, převodem algebraického tvaru komplexního čísla na tvar
goniometrický, zobrazováním komplexních čísel a zobrazováním součtu a rozdílu
komplexních čísel v Gaussově rovině. V tématu analytická geometrie jsem zpracovala
určování obecných rovnic přímek zadaných pomocí bodů, určování obecných rovnic
tečen, výšek, os stran v trojúhelníku a určování rovnice kružnice opsané trojúhelníku.

7.1. Zdrojové kódy
7.1.1 Komplexní čísla – početní operace
V tomto zdrojovém kódu jsou obsaženy početní operace se dvěmi komplexními
čísly tzn. součet, rozdíl, součin a podíl dvou komplexních čísel.
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib" prefix="msp" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtnl1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<HEAD >
<TITLE>komplexni cisla</TITLE>
</HEAD>
<BODY bgcolor="white" text="black" link="blue" vlink="blue"
alink="blue" background="" bgproperties="fixed" leftmargin="150"
topmargin= "100"maginwidth="" marginheight="5">
<basefont face="Verdana" size="2" />
<center><IMG SRC="PIC\webm-black.gif" ALT="webm-black.gif
(7 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<br>
<br>
<center><h2>Operace s komplexnimi cisly</h2></center>
<br>
<br>
<form action="komplexnicisla.jsp" method="post">

<msp:allocateKernel>
<font size="+1">Komplexni cislo <b><font
color="Blue">z<sub>1</sub></font></b>:</font>&nbsp;&nbsp;&nbsp;&nbsp;
x<sub>1</sub>
<input name="x1" size="3" value = "
<msp:evaluate>MSPValue[$$x1]</msp:evaluate>">&nbsp;&nbsp;
y<sub>1</sub>
<input name="y1" size="3" value = "
<msp:evaluate>MSPValue[$$y1]</msp:evaluate>">
<br>
<font size="+1">Komplexni cislo <b><font
color="Blue">z<sub>2</sub></font></b>:</font>&nbsp;&nbsp;&nbsp;&nbsp;
x<sub>2</sub>
<input name="x2" size="3" value = "
<msp:evaluate>MSPValue[$$x2]</msp:evaluate>">&nbsp;&nbsp;
y<sub>2</sub>
<input name="y2" size="3" value = "
<msp:evaluate>MSPValue[$$y2]</msp:evaluate>">
<br>
<br>
<input type="submit" name="btnSubmit"
pocitej">&nbsp;&nbsp;&nbsp;&nbsp;

value

<br>
<br>
<br>
<msp:evaluate>
MSPBlock[{$$x1,$$y1,$$x2,$$y2},x1=$$x1;y1=$$y1;x2=$$x2;y2=$$y2;]
</msp:evaluate>
<b><font color="Blue">z<sub>1</sub></font></b> =
<msp:evaluate>MSPFormat[x1+i y1,StandardForm]
</msp:evaluate>&nbsp;&nbsp;&nbsp;&nbsp;
<b><font color="Blue">z<sub>2</sub></font></b> =
<msp:evaluate>MSPFormat[x2+i y2,StandardForm]</msp:evaluate>
<br>
<br>
<br>
<font color="Brown">Soucet</font> techto komplexnich cisel
je:&nbsp;&nbsp;&nbsp;&nbsp;
z<sub><font color="Brown">S</font></sub> =
<msp:evaluate>MSPFormat[x1+x2+i*(y1+y2),StandardForm]</msp:evaluate>
<br>
<br>
<font color="Red">Soucin</font> techto komplexnich cisel
je:&nbsp;&nbsp;&nbsp;&nbsp;
z<sub><font color="Red">Sn</font></sub> = <msp:evaluate>MSPFormat
[(x1*x2-y1*y2)+i*(x1*y2+x2*y1),StandardForm]</msp:evaluate>

<br>
<br>
<font color="Green">Podil</font> techto komplexnich cisel
je:&nbsp;&nbsp;&nbsp;&nbsp;
z<sub><font color="Green">P</font></sub> = <msp:evaluate>MSPFormat
[(x1*x2+y1*y2)/(x2*x2+y2*y2)+i*(x2*y1-x1*y2)/(x2*x2+y2*y2),
StandardForm]</msp:evaluate>
<br>
<br>
<font color="Magenta">Rozdil</font> techto komplexnich cisel
je:&nbsp;&nbsp;&nbsp;&nbsp;
z<sub><font color="Magenta">R</font></sub> = <msp:evaluate>MSPFormat
[x1-x2+i*(y1-y2),StandardForm]</msp:evaluate>
</msp:allocateKernel>
</form>
<br>
<br>
<br>
<a href="http://home.pf.jcu.cz/webMathematica/webmath/index2.htm"
title="WebMATHEMATICA"><center><h6>Zpet na vyber
temat</h6></center></a>
<br />
<center><IMG SRC="PIC\webm-black-animated.gif" ALT="webm-blackanimated.gif(30 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<center><td style='font-family: Helvetica; font-size: 10px; width:
100%'>Created by
<a href="http://www.wolfram.com"><span style='font-style:
italic'>Mathematica</span></a></center>
<HR> <center><p align="center">
<font face="verdana,tahoma,sans serif" size="1">webmaster:
<a href="http://www.bendamira.wz.cz" title="BENDA MIREK">
Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">e-mail</a>
&copy; 2006</center>
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
</script></font></center>
</BODY>
</HTML>

7.1.2 Komplexní čísla – goniometrický tvar
Zde je zpracován převod algebraického tvaru komplexního čísla na tvar
goniometrický. Zdrojový kód obsahuje výpočet absolutní hodnoty komplexního čísla,
výpočet pomocného úhlu, kdy uvažujeme obě složky komplexního čísla kladné,
výpočet skutečné hodnoty úhlu podle toho, v jakém kvadrantu se nachází a sestavení
goniometrického tvaru komplexního čísla.
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib" prefix="msp" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtnl1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<HEAD >
<TITLE>komplexni cisla-goniometricky tvar</TITLE>
</HEAD>
<BODY bgcolor="white" text="black" link="blue" vlink="blue"
alink="blue" background="" bgproperties="fixed" leftmargin="150"
topmargin= "100"maginwidth="" marginheight="5">
<basefont face="Verdana" size="2" />
<center><IMG SRC="PIC\webm-black.gif" ALT="webm-black.gif
(7 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<br>
<br>
<center><h2>Operace s komplexnimi cisly</h2></center>
<br>
<br>
<form action="goniometrickytvar.jsp" method="post">
<msp:allocateKernel>
<b>Zadej komplexni cislo v algebraickem tvaru a preved ho na tvar
goniometricky.</b>
<br>
<br>
<font size="+1">Komplexni cislo <b><font
color="Blue">z</font></b>:</font>&nbsp;&nbsp;&nbsp;&nbsp;
x

<input name="x" size="3" value = "
<msp:evaluate>MSPValue[$$x]</msp:evaluate>">&nbsp;&nbsp;
y
<input name="y" size="3" value = "
<msp:evaluate>MSPValue[$$y]</msp:evaluate>">
<br>
<br>
<input type="submit" name="btnSubmit"

value ="pocitej">

<br>
<br>
<u><b><font color="Red">Pouzijeme rychlejsi postup:</font></b></u>
<br>
<br>
<msp:evaluate>MSPBlock[{$$x,$$y},x=$$x;y=$$y;] </msp:evaluate>
<b><font color="Blue">z</font></b> = <msp:evaluate>MSPFormat
[x+i y,StandardForm]</msp:evaluate>
<br>
<br>
<u><b>1. Absolutni hodnota:</b></u>&nbsp;&nbsp;
<msp:evaluate>MSPFormat[Abs[x+I y],TraditionalForm]</msp:evaluate>
<br>
<br>
Podle znamenek u jednotlivych slozek urcime, v kterem kvadrantu
Gaussovy roviny obraz tohoto cisla lezi.<br/>
Dale uvazujeme cislo, jehoz obe slozky jsou kladne a spocitame jeho
argument:
<msp:evaluate>MSPFormat[\!\(\[CurlyPhi]\_p\),TraditionalForm]
</msp:evaluate>,
<msp:evaluate>MSPFormat[\!\(\[CurlyPhi]\_p\),TraditionalForm]
</msp:evaluate>=<msp:evaluate>MSPFormat[ArcTan[Re/Im],TraditionalForm]
</msp:evaluate>.
<br>
<br>
<br>
<u><b>2.Argument</b>
<msp:evaluate>MSPFormat[\!\(\[CurlyPhi]\_p\),TraditionalForm]
</msp:evaluate></u><b>:</b>&nbsp;&nbsp;
<msp:evaluate>MSPFormat[Round[N[Abs[ArcTan[y/x]] 180/Pi]]
Degree,TraditionalForm]</msp:evaluate>
<br>
<br>
Skutecnou hodnotu uhlu <msp:evaluate>MSPFormat
[\[CurlyPhi],TraditionalForm]</msp:evaluate> dopocitame takto:<br/>

<br>
- lezi-li cislo v 1. kvadrantu, pak
<msp:evaluate>MSPFormat[\[CurlyPhi],TraditionalForm]</msp:evaluate>=
<msp:evaluate>MSPFormat[\!\(\[CurlyPhi]\_p\),TraditionalForm]
</msp:evaluate>
<br>
- lezi-li cislo ve 2. kvadrantu, pak
<msp:evaluate>MSPFormat[\[CurlyPhi],TraditionalForm]</msp:evaluate>=
180 - <msp:evaluate>MSPFormat[\!\(\[CurlyPhi]\_p\),TraditionalForm]
</msp:evaluate>
<br>
- lezi-li cislo ve 3. kvadrantu, pak
<msp:evaluate>MSPFormat[\[CurlyPhi],TraditionalForm]</msp:evaluate>=
180 + <msp:evaluate>MSPFormat[\!\(\[CurlyPhi]\_p\),TraditionalForm]
</msp:evaluate>
<br>
- lezi-li cislo ve 4. kvadrantu, pak
<msp:evaluate>MSPFormat[\[CurlyPhi],TraditionalForm]</msp:evaluate>=
360 - <msp:evaluate>MSPFormat[\!\(\[CurlyPhi]\_p\),TraditionalForm]
</msp:evaluate>
<br>
<br>
<br>
<u><b>3. Goniometricky tvar komplexniho cisla <b><font
color="Blue">z</font></b>:</b></u>&nbsp;&nbsp;
<msp:evaluate>MSPBlock
[{$$x,$$y,$$\[CurlyPhi]},x=$$x;y=$$y;\[CurlyPhi]=$$\[CurlyPhi];]
</msp:evaluate>
<msp:evaluate>MSPFormat
[Which[x>0&&y>0,\[CurlyPhi]=Round[N[Abs[ArcTan[y/x]] 180/Pi]],
x<0&&y<0,\[CurlyPhi]=180+Round[N[Abs[ArcTan[y/x]] 180/Pi]]),
x<0&&y>0,\[CurlyPhi]=180-(Round[N[Abs[ArcTan[y/x]] 180/Pi]]),
x>0&&y<0,\[CurlyPhi]=360-(Round[N[Abs[ArcTan[y/x]] 180/Pi]])]];
</msp:evaluate>
<msp:evaluate>MSPBlock[{$$x,$$y,$$\[CurlyPhi]},x=$$x;y=$$y;\[CurlyPhi]
=$$\[CurlyPhi];]</msp:evaluate>
<msp:evaluate>MSPFormat
[Abs[x+I y] (cos[\[CurlyPhi]]+i sin[\[CurlyPhi]]),TraditionalForm]
</msp:evaluate>
<br>
<br>
<br>

<br>
<u><b>4. Zobrazeni komplexniho cisla <b><font
color="Blue">z</font></b> v Gaussove rovine:</b></u>&nbsp;&nbsp;
<br>
<br>
<br>
<msp:evaluate>MSPShow[Show[{Plot[{y/x x1},{x1,0,x},
AspectRatio->Automatic,ImageSize->{450,400},AxesLabel->{"x","y"}],
Graphics[{PointSize[0.03],Hue[.7],Point[{x,y}]}]}]]</msp:evaluate>
</msp:allocateKernel>
</form>
<br>
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
<HR> <center><p align="center">
<font face="verdana,tahoma,sans serif" size="1">webmaster:
<a href="http://www.bendamira.wz.cz" title="BENDA MIREK">
Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">e-mail</a>
&copy; 2006</center>
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
</script></font></center>
</BODY>
</HTML>

7.1.3 Komplexní čísla – zobrazení v rovině
Tento kód obsahuje grafické znázornění dvou komplexních čísel v rovině
a znázornění jejich součtu a rozdílu.
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib" prefix="msp" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtnl1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<HEAD >
<TITLE>komplexni cisla-znázorneni v rovine</TITLE>
</HEAD>
<BODY bgcolor="white" text="black" link="blue" vlink="blue"
alink="blue" background="" bgproperties="fixed" leftmargin="150"
topmargin= "100"maginwidth="" marginheight="5">
<basefont face="Verdana" size="2" />
<center><IMG SRC="PIC\webm-black.gif" ALT="webm-black.gif
(7 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<br>
<br>
<center><h2>Zobrazeni komplexnich cisel v rovine</h2></center>
<br>
<br>
<form action="zobraz.jsp" method="post">
<msp:allocateKernel>

<font size="+1">Komplexni cislo <b>
<font color="Blue">z<sub>1</sub></font></b>:</font>
&nbsp;&nbsp;&nbsp;&nbsp;
x<sub>1</sub>
<input name="x1" size="3" value = "
<msp:evaluate>MSPValue[$$x1]</msp:evaluate>">&nbsp;&nbsp;
y<sub>1</sub>
<input name="y1" size="3" value = "
<msp:evaluate>MSPValue[$$y1]</msp:evaluate>">&nbsp;&nbsp;
<br>
<br>
<font size="+1">Komplexni cislo <b>
<font color="Blue">z<sub>2</sub></font></b>:</font>
&nbsp;&nbsp;&nbsp;&nbsp;
x<sub>2</sub>
<input name="x2" size="3" value = "
<msp:evaluate>MSPValue[$$x2]</msp:evaluate>">&nbsp;&nbsp;

y<sub>2</sub>
<input name="y2" size="3" value = "
<msp:evaluate>MSPValue[$$y2]</msp:evaluate>">&nbsp;&nbsp;&nbsp;&nbsp;
<input type="submit" name="btnSubmit"

value ="zobraz">

<br>
<br>
<br>
<b>Soucet <b><font color="Red">z<sub>S</sub></font></b> komplexnich
cisel:</b>
<br>
<br>
<msp:evaluate>
MSPBlock[{$$x1,$$y1,$$x2,$$y2},x1=$$x1;y1=$$y1;x2=$$x2;y2=$$y2;]
</msp:evaluate>
<b><font color="Red">z<sub>S</sub></font></b> =
<msp:evaluate>MSPFormat[x1+x2+i*(y1+y2),StandardForm]</msp:evaluate>
<br>
<br>
<br>
<msp:evaluate>MSPShow[Show[{{Plot[{y1/x1 x}, {x,0,x1},
AspectRatio->Automatic,ImageSize->{450,400},AxesLabel->{"x","y"}],
Graphics[{PointSize[0.03],Hue[.7],Point[{x1,y1}]}]},
{Plot[{y2/x2 x},{x,0,x2},AspectRatio->Automatic,
ImageSize->{450,400},AxesLabel->{"x","y"}],
Graphics[{PointSize[0.03],Hue[.7],Point[{x2,y2}]}]},
{Plot[{(y1+y2)/(x1+x2) x},{x,0,x1+x2},
AspectRatio->Automatic,ImageSize->{450,400},AxesLabel->{"x","y"}],
Graphics[{PointSize[0.03],Hue[.0],Point[{x1+x2,y1+y2}]}]},
Graphics[{AbsoluteDashing[{4,10}],Line[{{x1,y1},{x1+x2,y1+y2}}]}],
Graphics[{AbsoluteDashing[{4,10}],Line[{{x2,y2},{x1+x2,y1+y2}}]}]}]]
</msp:evaluate>
<br>
<br>
<br>
<br>
<br>
<br>
<b>Rozdil <b><font color="Red">z<sub>R</sub></font></b> komplexnich
cisel:</b>
<br>
<br>
<b><font color="Red">z<sub>R</sub></font></b> =
<msp:evaluate>MSPFormat[x1-x2+i*(y1-y2),StandardForm]</msp:evaluate>
<br>

<br>
<br>
<msp:evaluate>MSPShow[Show[{{Plot[{y1/x1 x},{x,0,x1},
AspectRatio->Automatic,ImageSize->{450,400},AxesLabel->{"x","y"}],
Graphics[{PointSize[0.03],Hue[.7],Point[{x1,y1}]}]},
{Plot[{y2/x2 x},{x,0,x2},AspectRatio->Automatic,
ImageSize->{450,400},AxesLabel->{"x","y"}],
Graphics[{PointSize[0.03],Hue[.7],Point[{x2,y2}]}]},
{Plot[{(y1-y2)/(x1-x2) x},{x,0,x1-x2},
AspectRatio->Automatic,ImageSize->{450,400},AxesLabel->{"x","y"}],
Graphics[{PointSize[0.03],Hue[.0],Point[{x1-x2,y1-y2}]}]},
Graphics[{AbsoluteDashing[{4,10}],Line[{{x1,y1},{x1-x2,y1-y2}}]}]}]]
</msp:evaluate>
</msp:allocateKernel>
</form>
<a href="http://home.pf.jcu.cz/webMathematica/webmath/index2.htm"
title="WebMATHEMATICA"><center><h6>Zpet na vyber
temat</h6></center></a> <br />
<center><IMG SRC="PIC\webm-black-animated.gif" ALT="webm-blackanimated.gif(30 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<center><td style='font-family: Helvetica; font-size: 10px; width:
100%'>Created by
<a href="http://www.wolfram.com"><span style='font-style:
italic'>Mathematica</span></a></center>
<HR> <center><p align="center">
<font face="verdana,tahoma,sans serif" size="1">webmaster:
<a href="http://www.bendamira.wz.cz" title="BENDA MIREK">
Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">e-mail</a>
&copy; 2006</center>
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
</script></font></center>
</BODY>
</HTML>

7.1.4 Analytická geometrie
Tento zdrojový kód obsahuje šest vstupů pro zadání souřadnic tří různých bodů.
Tyto tři body určují trojúhelník a z jejich souřadnic se pak provede výpočet obecných
rovnic stran trojúhelníku, výpočet obecných rovnic těžnic, výšek a os stran
v trojúhelníku a výpočet rovnice kružnice opsané tomuto trojúhelníku. Dále kód
zahrnuje graf trojúhelníku, grafy těžnic, výšek a kružnice opsané.
<%@ page language="java" %>
<%@ taglib uri="/webMathematica-taglib" prefix="msp" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtnl1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="cs" lang="cs">
<HEAD >
<TITLE>Analyticka geomterie</TITLE>
</HEAD>
<BODY
bgcolor="white"
text="black"
link="blue"
vlink="blue"
alink="blue"
background=""
bgproperties="fixed"
leftmargin="150"
topmargin= "100"maginwidth="" marginheight="5">
<basefont face="Verdana" size="2" />
<center><IMG
SRC="PIC\webm-black.gif"
ALT="webm-black.gif(7
WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<br>
<br>
<center><h2>Analytická geometrie</h2></center>
<br>
<br>
Zadej souradnice bodu <b>A</b>,<b> B</b>,<b> C</b>:
<form action="analytickageom.jsp" method="post">
<msp:allocateKernel>
<b>A</b>:&nbsp;&nbsp;
a<sub>1</sub>
<input name="a1" size="3" value = "
<msp:evaluate>MSPValue[$$a1,"0"]</msp:evaluate>">&nbsp;&nbsp;
a<sub>2</sub>
<input name="a2" size="3" value = "
<msp:evaluate>MSPValue[$$a2,"0"]</msp:evaluate>">
<br>
<br>
<b>B</b>:&nbsp;&nbsp;
b<sub>1</sub>
<input name="b1" size="3" value = "
<msp:evaluate>MSPValue[$$b1,"0"]</msp:evaluate>">&nbsp;&nbsp;

kb)"

b<sub>2</sub>
<input name="b2" size="3" value = "
<msp:evaluate>MSPValue[$$b2,"0"]</msp:evaluate>">
<br>
<br>
<b>C</b>:&nbsp;&nbsp;
c<sub>1</sub>
<input name="c1" size="3" value = "
<msp:evaluate>MSPValue[$$c1,"0"]</msp:evaluate>">&nbsp;&nbsp;
c<sub>2</sub>
<input name="c2" size="3" value = "
<msp:evaluate>MSPValue[$$c2,"0"]</msp:evaluate>">
<br>
<br>
a) Vypocitej obecne rovnice stran v trojuhelniku ABC.<br/>
b) Urcete obecne rovnice teznic v trojuhelniku ABC.<br/>
c) Urcete obecne rovnice výšek v trojuhelniku ABC.<br/>
d) Urcete obecne rovnice os stran v trojuhelniku ABC
kruznice opsane trojuhelniku ABC.<br/>

a

rovnici

<br>
<br>
<input type="submit" name="btnSubmit"

value ="pocitej">

<br>
<br>
<msp:evaluate>
MSPBlock[{$$a1,$$a2,$$b1,$$b2},a1=$$a1;a2=$$a2;b1=$$b1;b2=$$b2;]
</msp:evaluate>
a)<br/>
Rovnice strany <b><font color="Red">c</font></b>:&nbsp;&nbsp;
y<sub><font color="Red">c</font></sub>=
<msp:evaluate>
MSPFormat[If[a1!=b1,(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/(b1-a1),
nelze spocitat timto zpusobem -> rovnice strany -> x== a1],
TraditionalForm]</msp:evaluate>
<br>
<br>
<br>
<br>
<msp:evaluate>
MSPBlock[{$$a1,$$a2,$$c1,$$c2},a1=$$a1;a2=$$a2;c1=$$c1;c2=$$c2;]
</msp:evaluate>
Rovnice strany<b><font color="Blue"> b</font></b>:&nbsp;&nbsp;
y<sub><font color="Blue"> b</font></sub>=
<msp:evaluate>
MSPFormat[If[a1!=c1,(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1),
nelze spocitat timto zpusobem -> rovnice strany -> x== a1],
TraditionalForm]</msp:evaluate>

<br>
<br>
<msp:evaluate>
MSPBlock[{$$b1,$$b2,$$c1,$$c2},b1=$$b1;b2=$$b2;c1=$$c1;c2=$$c2;]
</msp:evaluate>
Rovnice strany <b><font color="Green">a</font></b>:&nbsp;&nbsp;
y<sub><font color="Green">a</font></sub>=
<msp:evaluate>
MSPFormat[If[b1!=c1,(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1),
nelze spocitat timto zpusobem -> rovnice strany -> x== b1],
TraditionalForm]</msp:evaluate>
<br>
<br>
<br>
<br>
<b><u>Trojuhelnik ABC:</u></b>
<br>
<br>
<br>
<br>
<msp:evaluate>MSPShow[Which[a1==b1,Show
[{Plot[{(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1)},{x,c1,a1},
PlotStyle->{RGBColor[0, 0, 1]}],
Plot[{(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1)},{x,b1,c1},
PlotStyle->{RGBColor[0, 1, 0]}]},
Graphics[{RGBColor[1,0,0],Line[{{a1,a2},{b1,b2}}]}],
AspectRatio->Automatic,ImageSize->{500,450},AxesLabel->{"x","y"}],
a1==c1,Show
[{Plot[{(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/(b1-a1)},{x,a1,b1},
PlotStyle->{RGBColor[1,0,0]}],
Plot[{(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1)},{x,b1,c1},
PlotStyle->{RGBColor[0,1,0]}]},
Graphics[{RGBColor[0,0,1],Line[{{a1,a2},{c1,c2}}]}],
AspectRatio->Automatic,ImageSize->{500,450},AxesLabel->{"x","y"}],
b1==c1,Show
[{Plot[{(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/(b1-a1)},{x,a1,b1},
PlotStyle->{RGBColor[1,0,0]}],
Plot[{(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1)},{x,c1,a1},
PlotStyle->{RGBColor[0,0,1]}]},
Graphics[{RGBColor[0,1,0],Line[{{b1,b2},{c1,c2}}]}],
AspectRatio->Automatic,ImageSize->{500,450},AxesLabel->{"x","y"}],
a1!=b1!=c1,Show
[{Plot[{(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/(b1-a1)},{x,a1,b1},
PlotStyle->{RGBColor[1,0,0]}],

Plot[{(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1)},{x,c1,a1},
PlotStyle->{RGBColor[0,0,1]}],
Plot[{(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1)},{x,b1,c1},
PlotStyle->{RGBColor[0,1,0]}]},AspectRatio->Automatic,
ImageSize->{500,450},AxesLabel->{"x","y"}]]]
</msp:evaluate>
<br>
<br>
<br>
<br>
<br>
<msp:evaluate>
MSPBlock[{$$a1,$$a2,$$b1,$$b2,$$c1,$$c2},a1=$$a1;a2=$$a2;b1=$$b1;b2=$$
b2;c1=$$c1;c2=$$c2;]
</msp:evaluate>
b)<br/>
Rovnice teznice na stranu
<b><font color="Red">c</font></b>:&nbsp;&nbsp;
t<sub><font color="Red">c</font></sub>=
<msp:evaluate>MSPFormat
[If[c1!=(a1+b1)/2,(c2-(a2+b2)/2)/(c1-(a1+b1)/2)*x+((c1-(a1+b1)/2)*c2(c2-(a2+b2)/2)*c1)/(c1-(a1+b1)/2),nelze spocitat timto zpusobem],
TraditionalForm]</msp:evaluate>
<br>
<br>
Rovnice teznice na stranu
<b><font color="Blue">b</font></b>:&nbsp;&nbsp;
t<sub><font color="Blue">b</font></sub>=
<msp:evaluate>MSPFormat
[If[b1!=(a1+c1)/2,(b2-(a2+c2)/2)/(b1-(a1+c1)/2)*x+((b1-(a1+c1)/2)*b2(b2-(a2+c2)/2)*b1)/(b1-(a1+c1)/2),nelze spocitat timto zpusobem],
TraditionalForm]</msp:evaluate>
<br>
<br>
Rovnice teznice na stranu
<b><font color="Green">b</font></b>:&nbsp;&nbsp;
t<sub><font color="Green">a</font></sub>=
<msp:evaluate>MSPFormat
[If[a1!=(b1+c1)/2,(a2-(b2+c2)/2)/(a1-(b1+c1)/2)*x+((a1-(b1+c1)/2)*a2(a2-(b2+c2)/2)*a1)/(a1-(b1+c1)/2),nelze spocitat timto zpusobem],
TraditionalForm]</msp:evaluate>
<br>
<br>
<br>
<br>
<b><u>Trojuhelnik ABC s teznicemi:</u></b>
<br>
<br>

<br>
<br>
<msp:evaluate>MSPShow[Which[a1==b1,Show
[{Plot[{(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1)},{x,c1,a1},
PlotStyle->{RGBColor[0,0,1]}],
Plot[{(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1)},{x,b1,c1},
PlotStyle->{RGBColor[0,1,0]}]},
Graphics[{RGBColor[1,0,0],Line[{{a1,a2},{b1,b2}}]}],
Graphics[{RGBColor[1,0,0],Line[{{(a1+b1)/2,(a2+b2)/2},{c1,c2}}]}],
Graphics[{RGBColor[0,0,1],Line[{{(a1+c1)/2,(a2+c2)/2},{b1,b2}}]}],
Graphics[{RGBColor[0,1,0],Line[{{(c1+b1)/2,(c2+b2)/2},{a1, a2}}]}],
AspectRatio->Automatic,ImageSize->{500,450},AxesLabel->{"x","y"}],
a1==c1,Show
[{Plot[{(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/(b1-a1)},{x,a1,b1},
PlotStyle->{RGBColor[1,0,0]}],
Plot[{(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1)},{x,b1,c1},
PlotStyle->{RGBColor[0,1,0]}]},
Graphics[{RGBColor[0,0,1],Line[{{a1,a2},{c1,c2}}]}],
Graphics[{RGBColor[0,0,1],Line[{{(a1+c1)/2,(a2+c2)/2},{b1,b2}}]}],
Graphics[{RGBColor[1,0,0],Line[{{(a1+b1)/2,(a2+b2)/2},{c1,c2}}]}],
Graphics[{RGBColor[0,1,0],Line[{{(c1+b1)/2,(c2+b2)/2},{a1,a2}}]}],
AspectRatio->Automatic,ImageSize->{500,450},AxesLabel->{"x","y"}],
b1==c1,Show
[{Plot[{(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/(b1-a1)},{x,a1,b1},
PlotStyle->{RGBColor[1,0,0]}],
Plot[{(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1)},{x,c1,a1},
PlotStyle->{RGBColor[0,0,1]}]},
Graphics[{RGBColor[0,1,0],Line[{{b1,b2},{c1,c2}}]}],
Graphics[{RGBColor[1,0,0],Line[{{(a1+b1)/2,(a2+b2)/2},{c1,c2}}]}],
Graphics[{RGBColor[0,0,1],Line[{{(a1+c1)/2,(a2+c2)/2},{b1, b2}}]}],
Graphics[{RGBColor[0,1,0],Line[{{(c1+b1)/2,(c2+b2)/2},{a1, a2}}]}],
AspectRatio->Automatic,ImageSize->{500,450},AxesLabel->{"x","y"}],
a1!=b1!=c1,Show[{Plot[{(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/
(b1-a1)},{x,a1,b1},PlotStyle->{RGBColor[1,0,0]}],
Plot[{(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1)},{x,c1,a1},
PlotStyle->{RGBColor[0,0,1]}],
Plot[{(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1)},{x,b1,c1},
PlotStyle->{RGBColor[0,1,0]}]},
Graphics[{RGBColor[1,0,0],Line[{{(a1+b1)/2,(a2+b2)/2},{c1,c2}}]}],
Graphics[{RGBColor[0,0,1],Line[{{(a1+c1)/2,(a2+c2)/2},{b1,b2}}]}],
Graphics[{RGBColor[0,1,0],Line[{{(c1+b1)/2,(c2+b2)/2},{a1,a2}}]}],
AspectRatio->Automatic,ImageSize->{500,450},AxesLabel->{"x","y"}]]]
</msp:evaluate>
<br>
<br>

<br>
<br>
<br>
<msp:evaluate>MSPBlock
[{$$a1,$$a2,$$b1,$$b2,$$c1,$$c2},a1=$$a1;a2=$$a2;b1=$$b1;b2=$$b2;c1=$$
c1;c2=$$c2;]
</msp:evaluate>
c)<br/>
Rovnice vysky na stranu <b><font color="Red">c</font></b>:&nbsp;&nbsp;
v<sub><font color="Red">c</font></sub>=
<msp:evaluate>
MSPFormat[If[a2!=b2,-(b1-a1)/(b2-a2)*x+((b1-a1)*c1+(b2-a2)*c2)/
(b2-a2),nelze spocitat timto zpusobem -> jmenovatel==0],
TraditionalForm]
</msp:evaluate>
<br>
<br>
Rovnice vysky na stranu <b><font olor="Blue">b</font></b>:&nbsp;&nbsp;
v<sub><font color="Blue">b</font></sub>=
<msp:evaluate>
MSPFormat[If[a2!=c2,-(a1-c1)/(a2-c2)*x+((a1-c1)*b1+(a2-c2)*b2)/
(a2-c2),nelze spocitat timto zpusobem -> jmenovatel==0],
TraditionalForm]</msp:evaluate>
<br>
<br>
Rovnice vysky na stranu <b><font
color="Green">a</font></b>:&nbsp;&nbsp;
v<sub><font color="Green">a</font></sub>=
<msp:evaluate>
MSPFormat[If[c2!=b2,-(c1-b1)/(c2-b2)*x+((c1-b1)*a1+(c2-b2)*a2)/(c2b2),nelze spocitat timto zpusobem -> jmenovatel==0],
TraditionalForm]</msp:evaluate>
<br>
<br>
<br>
<br>
<b><u>Trojuhelnik ABC s výškami:</u></b>
<br>
<br>
<br>
<br>
<msp:evaluate>
MSPShow[Which[a1==b1,Show
[{Plot[{(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1)},{x,c1,a1},
PlotStyle->{RGBColor[0,0,1]}],
Plot[{(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1)},{1x,b1,c1},
PlotStyle->{RGBColor[0,1,0]}],

Plot[{-(b1-a1)/(b2-a2)*x+((b1-a1)*c1+(b2-a2)*c2)/(b2-a2)},{x,((b1a1)^2*c1+(b1-a1)*(b2-a2)*c2+(b2-a2)^2*a1-(b1-a1)*(b2-a2)*a2)/((b2a2)^2+(b1-a1)^2),c1},
PlotStyle->{RGBColor[1,0,0]}],
Plot[{-(a1-c1)/(a2-c2)*x+((a1-c1)*b1+(a2-c2)*b2)/(a2-c2)},{x,((a1c1)^2*b1+(a1-c1)*(a2-c2)*b2+(a2-c2)^2*c1-(a1-c1)*(a2-c2)*c2)/((a2c2)^2+(a1-c1)^2),b1},PlotStyle->{RGBColor[0,0,1]}],
Plot[{-(c1-b1)/(c2-b2)*x+((c1-b1)*a1+(c2-b2)*a2)/(c2-b2)},{x,((c1b1)^2*a1+(c1-b1)*(c2-b2)*a2+(c2-b2)^2*b1-(c1-b1)*(c2-b2)*b2)/((c2b2)^2+(c1-b1)^2),a1},PlotStyle->{RGBColor[0,1,0]}]},
Graphics[{RGBColor[1,0,0],Line[{{a1,a2},{b1,b2}}]}],
AspectRatio->Automatic,ImageSize->{500,450},AxesLabel->{"x","y"}],
a1==c1,
Show
[{Plot[{(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/(b1-a1)},{x,a1,b1},
PlotStyle->{RGBColor[1,0,0]}],
Plot[{(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1)},{x,b1,c1},
PlotStyle->{RGBColor[0,1,0]}],
Plot[{-(b1-a1)/(b2-a2)*x+((b1-a1)*c1+(b2-a2)*c2)/(b2-a2)},{x,((b1a1)^2*c1+(b1-a1)*(b2-a2)*c2+(b2-a2)^2*a1-(b1-a1)*(b2-a2)*a2)/((b2a2)^2+(b1-a1)^2),c1},PlotStyle->{RGBColor[1,0,0]}],
Plot[{-(a1-c1)/(a2-c2)*x+((a1-c1)*b1+(a2-c2)*b2)/(a2-c2)},{x,((a1c1)^2*b1+(a1-c1)*(a2-c2)*b2+(a2-c2)^2*c1-(a1-c1)*(a2-c2)*c2)/((a2c2)^2+(a1-c1)^2),b1},PlotStyle->{RGBColor[0,0,1]}],
Plot[{-(c1-b1)/(c2-b2)*x+((c1-b1)*a1+(c2-b2)*a2)/(c2-b2)},{x,((c1b1)^2*a1+(c1-b1)*(c2-b2)*a2+(c2-b2)^2*b1-(c1-b1)*(c2-b2)*b2)/((c2b2)^2+(c1-b1)^2),a1}, PlotStyle->{RGBColor[0,1,0]}]},
Graphics[{RGBColor[0,0,1],Line[{{a1,a2},{c1,c2}}]}],
AspectRatio->Automatic,ImageSize->{500,450},AxesLabel->{"x","y"}],
b1==c1,
Show
[{Plot[{(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/(b1-a1)},{x,a1,b1},
PlotStyle->{RGBColor[1,0,0]}],
Plot[{(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1)},{x,c1,a1},
PlotStyle->{RGBColor[0,0,1]}],
Plot[{-(b1-a1)/(b2-a2)*x+((b1-a1)*c1+(b2-a2)*c2)/(b2-a2)},{x,((b1a1)^2*c1+(b1-a1)*(b2-a2)*c2+(b2-a2)^2*a1-(b1-a1)*(b2-a2)*a2)/((b2a2)^2+(b1-a1)^2),c1},PlotStyle->{RGBColor[1,0,0]}],
Plot[{-(a1-c1)/(a2-c2)*x+((a1-c1)*b1+(a2-c2)*b2)/(a2-c2)},{x,((a1c1)^2*b1+(a1-c1)*(a2-c2)*b2+(a2-c2)^2*c1-(a1-c1)*(a2-c2)*c2)/((a2c2)^2+(a1-c1)^2),b1},PlotStyle->{RGBColor[0,0,1]}],
Plot[{-(c1-b1)/(c2-b2)*x+((c1-b1)*a1+(c2- b2)*a2)/(c2-b2)},{x,((c1b1)^2*a1+(c1-b1)*(c2-b2)*a2+(c2-b2)^2*b1-(c1-b1)*(c2-b2)*b2)/((c2b2)^2+(c1-b1)^2),a1},PlotStyle->{RGBColor[0,1,0]}]},

Graphics[{RGBColor[0,1,0],Line[{{b1,b2},{c1,c2}}]}],
AspectRatio->Automatic,ImageSize->{500,450},AxesLabel->{"x","y"}],
a1!=b1!=c1,
Show
[{Plot[{(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/(b1-a1)},{x,a1,b1},
PlotStyle->{RGBColor[1,0,0]}],
Plot[{(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1)},{x,b1,c1},
PlotStyle->{RGBColor[0,1,0]}],
Plot[{(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1)},{x,c1,a1},
PlotStyle->{RGBColor[0,0,1]}],
Plot[{-(b1-a1)/(b2-a2)*x+((b1-a1)*c1+(b2-a2)*c2)/(b2-a2)},{x,((b1a1)^2*c1+(b1-a1)*(b2-a2)*c2+(b2-a2)^2*a1-(b1-a1)*(b2-a2)*a2)/((b2a2)^2+(b1-a1)^2),c1},PlotStyle->{RGBColor[1,0,0]}],
Plot[{-(a1-c1)/(a2-c2)*x+((a1-c1)*b1+(a2-c2)*b2)/(a2-c2)},{x,((a1c1)^2*b1+(a1-c1)*(a2-c2)*b2+(a2-c2)^2*c1-(a1-c1)*(a2-c2)*c2)/((a2c2)^2+(a1-c1)^2),b1},PlotStyle->{RGBColor[0,0,1]}],
Plot[{-(c1-b1)/(c2-b2)*x+((c1-b1)*a1+(c2-b2)*a2)/(c2-b2)},{x,((c1b1)^2*a1+(c1-b1)*(c2-b2)*a2+(c2-b2)^2*b1-(c1-b1)*(c2-b2)*b2)/((c2b2)^2+(c1-b1)^2),a1},PlotStyle->{RGBColor[0,1,0]}]},
AspectRatio->Automatic,ImageSize->{500,450},AxesLabel->{"x","y"}]]]
</msp:evaluate>
<br>
<br>
(Je-li trojuhelnik tupouhly, nezobrazi se v grafu prusecik vysek.
Prusecik vysek lezi mimo trojuhlenik.)
<br>
<br>
<msp:evaluate>MSPBlock
[{$$a1,$$a2,$$b1,$$b2,$$c1,$$c2},a1=$$a1;a2=$$a2;b1=$$b1;b2=$$b2;c1=$$
c1;c2=$$c2;]
</msp:evaluate>
d)<br>
Rovnice osy strany <b><font color="Red">c</font></b>:&nbsp;&nbsp;
o<sub><font color="Red">c</font></sub>=
<msp:evaluate>MSPFormat
[If[a2!=b2,-(b1-a1)/(b2-a2)*x+(b1^2-a1^2+b2^2-a2^2)/(2*(b2-a2)),nelze
spocitat timto zpusobem -> jmenovatel==0],
TraditionalForm]</msp:evaluate>
<br>
<br>
Rovnice osy strany <b><font color="Blue">b</font></b>:&nbsp;&nbsp;
o<sub><font color="Blue">b</font></sub>=
<msp:evaluate>MSPFormat
[If[a2!=c2,-(a1-c1)/(a2-c2)*x+((a1^2-c1^2)+(a2^2-c2^2))/(2*(a2c2)),nelze spocitat timto zpusobem -> jmenovatel==0],
TraditionalForm]</msp:evaluate>

<br>
<br>
Rovnice osy strany <b><font color="Green">b</font></b>:&nbsp;&nbsp;
o<sub><font color="Green">a</font></sub>=
<msp:evaluate>MSPFormat
[If[c2!=b2,-(c1-b1)/(c2-b2)*x+((c1^2-b1^2)+(c2^2-b2^2))/(2*(c2b2)),nelze spocitat timto zpusobem -> jmenovatel==0],
TraditionalForm]</msp:evaluate>
<br>
<br>
<br>
<u>Kruznice opsana</u><br/>
<br>
Nejprve urcime souradnice pruseciku os, nebot prusecik os je zaroven
stredem kruznice opsane trojuhelniku.
<br>
<br>
Souradnice stredu [m,n]:<br/>
<br>
<b><font color="Magenta">m</font></b> =
<msp:evaluate>MSPFormat[((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2c1^2+a2^2-c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))),
TraditionalForm]</msp:evaluate>
<br>
<br>
<b><font color="Magenta">n</font></b> =
<msp:evaluate>MSPFormat[(((a1-b1)*((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2a2)*(a1^2-c1^2+a2^2-c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))/(b2a2)+(b1^2-a1^2+b2^2-a2^2)/(2*(b2-a2))),TraditionalForm]
</msp:evaluate>
<br>
<br>
Polomer <b><font color="Magenta">r</font></b> =
<msp:evaluate>MSPFormat[Sqrt[((a1-((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2a2)*(a1^2-c1^2+a2^2-c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2c2))))^2+(a2-(((a1-b1)*((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2c1^2+a2^2-c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))/(b2-a2)+(b1^2a1^2+b2^2-a2^2)/(2*(b2-a2))))^2)],TraditionalForm]
</msp:evaluate>
<br>
<br>
<u>Rovnice kruznice opsane trojuhelniku ABC:</u>
<br>
<br>

<br>
<b><font color="Magenta">k:</font></b>&nbsp;&nbsp;
<msp:evaluate>MSPFormat[
(x-((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))^2+(y-(((a1-b1)*((a2c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2-c2^2))/(2*((c1a1)*(b2-a2)-(a1-b1)*(a2-c2))))/(b2-a2)+(b1^2-a1^2+b2^2-a2^2)/(2*(b2a2))))^2,TraditionalForm]
</msp:evaluate>
=
<msp:evaluate>MSPFormat[((a1-((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2a2)*(a1^2-c1^2+a2^2-c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2c2))))^2+(a2-(((a1-b1)*((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2c1^2+a2^2-c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))/(b2-a2)+(b1^2a1^2+b2^2-a2^2)/(2*(b2-a2))))^2),TraditionalForm]
</msp:evaluate>
<br>
<br>
<br>
<b><u>Kruznice opsana trojuhelniku ABC:</u></b>
<br>
<br>
<br>
<br>
<msp:evaluate>
MSPShow[Which[a1==b1,Show
[{Plot[{(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1)},{x,c1,a1},
PlotStyle->{RGBColor[0,0,1]}],
Plot[{(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1)},{x,b1,c1},
PlotStyle->{RGBColor[0,1,0]}]},
Graphics[{RGBColor[1,0,0],Line[{{a1,a2},{b1,b2}}]}],
Graphics[{Hue[-.15],
Circle[{((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))),
(((a1-b1)*((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))/(b2-a2)+(b1^2-a1^2+b2^2a2^2)/(2*(b2-a2)))},
Sqrt[((a1-((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))^2+(a2-(((a1-b1)*((a2c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2-c2^2))/
(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))/(b2-a2)+(b1^2-a1^2+b2^2a2^2)/(2*(b2-a2))))^2)]]}],
AspectRatio->Automatic,ImageSize->{700,650},AxesLabel->{"x","y"}],
a1==c1,Show
[{Plot[{(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/(b1-a1)},{x,a1,b1},
PlotStyle->{RGBColor[1,0,0]}],
Plot[{(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1)},{x,b1,c1},
PlotStyle->{RGBColor[0,1,0]}]},
Graphics[{RGBColor[0,0,1],Line[{{a1,a2},{c1,c2}}]}],
Graphics[{Hue[-.15],

Circle[{((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))),
(((a1-b1)*((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))/(b2-a2)+(b1^2-a1^2+b2^2a2^2)/(2*(b2-a2)))},
Sqrt[((a1-((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))^2+(a2-(((a1-b1)*((a2c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2-c2^2))/
(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))/(b2-a2)+(b1^2-a1^2+b2^2a2^2)/(2*(b2-a2))))^2)]]}],
AspectRatio->Automatic,ImageSize->{700,650},AxesLabel->{"x","y"}],
b1==c1,Show
[{Plot[{(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/(b1-a1)},{x,a1,b1},
PlotStyle->{RGBColor[1,0,0]}],
Plot[{(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1)},{x,c1,a1},
PlotStyle->{RGBColor[0,0,1]}]},
Graphics[{RGBColor[0,1,0],Line[{{b1,b2},{c1,c2}}]}],
Graphics[{Hue[-.15],
Circle[{((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))),
(((a1-b1)*((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))/(b2-a2)+(b1^2-a1^2+b2^2a2^2)/(2*(b2-a2)))},
Sqrt[((a1-((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))^2+(a2-(((a1-b1)*((a2c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2-c2^2))/
(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))/(b2-a2)+(b1^2-a1^2+b2^2a2^2)/(2*(b2-a2))))^2)]]}],
AspectRatio->Automatic,ImageSize->{700,650},AxesLabel->{"x","y"}],
a1!=b1!=c1,Show
[{Plot[{(b2-a2)/(b1-a1)*x+((b1-a1)*a2-(b2-a2)*a1)/(b1-a1)},{x,a1,b1},
PlotStyle->{RGBColor[1,0,0]}],
Plot[{(c2-b2)/(c1-b1)*x+((c1-b1)*b2-(c2-b2)*b1)/(c1-b1)},{x,b1,c1},
PlotStyle->{RGBColor[0,1,0]}],
Plot[{(a2-c2)/(a1-c1)*x+((a1-c1)*c2-(a2-c2)*c1)/(a1-c1)},{x,c1,a1},
PlotStyle->{RGBColor[0,0,1]}]},
Graphics[{Hue[-.15],
Circle[{((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))),
(((a1-b1)*((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))/(b2-a2)+(b1^2-a1^2+b2^2a2^2)/(2*(b2-a2)))},
Sqrt[((a1-((a2-c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2c2^2))/(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))^2+(a2-(((a1-b1)*((a2c2)*(b1^2-a1^2+b2^2-a2^2)-(b2-a2)*(a1^2-c1^2+a2^2-c2^2))/
(2*((c1-a1)*(b2-a2)-(a1-b1)*(a2-c2))))/(b2-a2)+(b1^2-a1^2+b2^2a2^2)/(2*(b2-a2))))^2)]]}],
AspectRatio->Automatic,ImageSize->{700,650},AxesLabel->{"x","y"}]]]
</msp:evaluate>
<br>
<br>

<br>
</msp:allocateKernel>
</form>
<br>
<br>
<a href="http://home.pf.jcu.cz/webMathematica/webmath/index2.htm"
title="WebMATHEMATICA"><center><h6>Zpet na vyber
temat</h6></center></a> <br />
<br>
<center><IMG SRC="PIC\webm-black-animated.gif" ALT="webm-blackanimated.gif(30 kb)" WIDTH="468" HEIGHT="60" BORDER="0"> </center>
<center><td style='font-family: Helvetica; font-size: 10px; width:
100%'>Created by
<a href="http://www.wolfram.com"><span style='font-style: italic'>
Mathematica</span></a></center>
<HR> <center><p align="center">
<font face="verdana,tahoma,sans serif" size="1">webmaster: <a
href="http://www.bendamira.wz.cz" title="BENDA MIREK">
Benda Mirek</a> 2006 <a href="mailto:mirabenda@volny.cz">e-mail</a>
&copy; 2006</center>
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
</script></font></center>
</BODY>
</HTML>

7.2 Internetové stránky
Všechna témata jsou zpracována na webových stránkách, které najdete
na internetové adrese: http://home.pf.jcu.cz/webMathematica/webmath/index.htm . Tyto
stránky jsou hlavní součástí naší diplomové práce.
Ukázka webových stránek:

Obrázek 7.2.1 – Zobrazení součtu komplexních čísel v rovině

Obrázek 7.2.2 – Výpočet obecných rovnic stran trojúhelníku.

Obrázek 7.2.3 – Výpočet obecných rovnic těžnic a graf.

8. Závěr
Naším cílem bylo využívat produkt webMathematica takovým způsobem,
aby mohly být výsledky naší práce použitelné ve výuce matematiky na střední škole.
Co všechno obnášela práce na naší diplomové práci, čeho jsme dosáhli, co se nám
podařilo nebo co se nám naopak nepodařilo, bychom chtěli zmínit v této části.
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
pro některého z našich pokračovatelů. Popřípadě pro někoho, kdo ovládá tvorbu
webových stránek lepe než my. Také jsme předpokládali, že zpracujeme více témat,
ale vzhledem k nedostatečnému množství materiálů, což mělo v nemalé míře vliv na to,
že jsme relativně pozdě přišli na postup, jakým tvořit stránky ve webMathematica,
a díky časové náročnosti, se nám jich z původnímu plánu podařilo zpracovat méně.
Podařilo se nám vytvořit webové stránky, na kterých je rozpracováno několik
témat středoškolské matematiky. Rádi bychom, aby se našli další studenti, kteří by
v této práci pokračovali tak, aby hledali nová, pro ně zajímavá témata, a obohacovali
jimi webové stránky. Popřípadě, aby doplňovali námi zpracovaná témata tak, aby se

na webových stránkách postupně objevily všechny okruhy středoškolské matematiky.
Chtěli bychom, aby každý, kdo navštíví tento portál na fakultních stránkách, našel vše,
co by potřeboval pro ilustraci příkladů, k procvičení probírané matematické látky,
pro její lepší pochopení, pro jasnější prezentaci výkladu při hodinách matematiky,
a v neposlední řadě i pro rozšíření vlastních znalostí a představivosti. Šlo nám nejen o to
vytvořit pomůcku platnou při výuce matematiky využívanou především učiteli,
ale i o to, aby možnost praktického ověření probírané látky, vedla k zájmu studenta
z jeho vlastní iniciativy. Myslíme, že webMathematica zpřístupňuje a zjednodušuje
cestu k tomuto poznání.
Vytvořili jsme zajímavou pomůcku, která je dalším krokem pro vylepšení
představivosti studentů a lepšího chápání matematické látky. Doufáme, že u některých
studentů zvýšíme zájem o matematiku jako takovou. A o to nám jde především.

9. Užitá literatura a www
Literatura

[1] WOLFRAM, S.: The MATHEMATICA BOOK 5th ed., (Wolfram Media,
2003)
[2] POLÁK, J.: Přehled středoškolské matematiky, Praha, Prométheus, 1995

www

[1] http://www.wolfram.com/

[2] http://www.wolfram.com/products/webmathematica/index.html

[3] http://documents.wolfram.com/webmathematica/

[4] http://www.mathematica.cz/

[5] http://k315.feld.cvut.cz/vyuka/webmathematica

[6] http://ladislav.prskavec.net/

