---
title: "SMwebmathematica_i[1]..doc"
source: "/mnt/f/git/mgr/FPE_navazujici/1. Semestr/SM/Podklady k pøednákám/SMwebmathematica_i[1]..doc"
date: 2008-08-24
type: DOC
---

**WebMathematica**

**Úvod**

Přirozeným požadavkem v posledních letech začal být přístup k programu
Mathematica pomocí webového prohlížeče. Tomuto požadavku firma Wolfram
vyhověla verzí programu, která se nazývá WebMathematica.

Existují dvě základní platformy -- amatér a profesionál. Základní rozdíl
je obslužných funkcích . Verzi amatér může získat každý, kdo vlastní
program Mathematica na určité úrovni ( jde o tzv. službu Premiér Service
) , verze profesionál je za úplatu.

V našem případě se budeme samozřejmě zabývat verzí amatér . Budeme se
nadále snažit využít znalostí programu Mathematica , které jsme
v předchozím studiu nabyli. Pokud chceme vytvářet aplikace ve
WebMathematica , musíme se kromě vlastní syntaxe příkazů Matematiky
naučit i specifické příkazy značkovacího jazyku pro WebMathematiku a
navíc technologii skriptového jazyku Java, která je použita ve formě
tzv. Java Servetů.

\

Technologie psaní příkazů WebMathematica je založena na základních
přístupech ve značkovacích jazycích typu HTML. Speciálně pro práci
v našem prostředí byly vytvořeny unikátní příkazy ,které například
v daném okamžiku spouští jádro výpočetního prostředí programu, provádějí
výpočet , umožňují načítání dat,přistupují k databázím , zobrazují
grafické výstupy z prostředí Mathematica atd. Podrobný seznam takovýchto
příkazů je uveden na serveru Wolfram na tomto místě:
[<http://documents.wolfram.com/webmathematica/>]{.underline} .

Samotná Mathematica v nové verzi je schopna spolupracovat s mnoha
externími programy a službami operačního systému. Základem pro
programovací činnost je možnost vstupů a výstupů v programovacích
jazycích Java , C , Fortran a Perl. V předchozích verzích bylo za úplatu
mnoho podpůrných programů,které se souhrnně nazývaly Linky -například
Excel Link, který zprostředkoval přenot dat z a do prostředí MS Excel a
Matematiky. Pro vytváření programových souborů v prostředí
WebMathematica je důležitý Link ,který nenazývá J/Link, jde o soubor
nástrojů ,který slouží k integraci příkazů jazyku Javy do prostředí
Mathematica. Kromě těchto možností je velmi důležité, že uživatel může
bez obtíží přistupovat pomocí SQL serveru k databázovému prostředí.
V poslední verzi programu zabezpečila firma Wolfram konverzi dat a
výsledků základních dokumentů programu --notebooků do neuvěřitelného
množství jiných formátů viz další:

\

![](SMwebmathematica_i%5B1%5D._html_df9f4d94.png){#Image1 align="bottom"
width="604" height="313" border="0"}

Klasicky v programu Mathematica zadává uživatel příkazy pomocí
speciálního rozhraní , které se nazývá kernel.Takovéto rozhraní je
označujeme také symbolem front end. Uživatel tedy jen zadává příkazy
v prostředí notebooku a tyto příkazy jsou interpretovány jádrem programu
a zpracovány .Uživateli se pak v jím zvolené formě zobrazí.

V prostředí WebMathematica uživatel pracuje velmi podobně . Rozdíl je
v tom, že musí každou instanci jádra volat a samostatně také ukončovat.
Slovem uživatel zde ovšem rozumíme tvůrce webové stránky ,která má být
interpretována v prostředí WebMtahematika.

Uživatel na straně klienta musí být vybaven klasickým prohlížečem
webových stránek například Explorer , Modzilla, Opera nebo některým
z dalších. Důležité je , že daný prohlížeč má možnost interpretovat
Javascrip příkazy .

Pro vlastní práci ve web Mathematica by měl tvůrce webových stránek
ovládat:

\

1.  Znalost programu Mathematica

2.  Základní znalost tvorby webových stránek nebo aspoň umět pracovat
    s některým editorem těchto stránek

3.  Program web Mathematica a aspoň základní příkazy

\

Jakmile je vytvořena stránka WebMathematica , jsou všechny základní tagy
( značky užívané WM -- dále WebMathematica ) interpretovány pomocí
technologie JSP ( Java Server Pages ) a technologie Servlet.

\

**Java Servlet**

\

Servlety jsou neoddělitelnou součástí platformy J2EE od firmy SUN. Jsou
to programové komponenty běžící na straně servru, napsané v Jave. To
znamená, že vyžadují \"java-enabled-server\" a samozřejmě JVM (Java
Virtual Machine). Se servlety jako mezičlánkem se můžeme nepřímo potkat
při technologii dynamických stránek JavaServer Pages.

\

**Java Server Pages (JSP)**

Jedná se o technologii, která je nyní součástí standardu Java 2
Enterprise Edition (J2EE), určenou pro tvorbu webových stránek s
dynamickým obsahem. Zpracování dynamického obsahu probíhá na straně
serveru. Technologie JSP přináší několik odlišností a výhod, které bych
se pokusil v několika bodech shrnout:

-   Ze všech konkurenčních řešení je možno JSP považovat za nejlépe
    přenositelné mezi různými platformami, což je zaručeno především
    skutečností, že je JSP od základu postaveno na jazyce Java.
    V současné době je podpora implementována do všech významných
    webových serverů. V případě, že nejsou JSP přímo zahrnuty, je možno
    podporu v serveru dodatečně zajistit pomocí přídavného enginu (např.
    JRun firmy Macromedia).

-   JSP, podobně jako předchozí skriptovací jazyky, slouží ke generování
    dynamického obsahu pro webové stránky. S tím rozdílem, že v případě
    JSP je statický a dynamický obsah důsledně oddělen. Netřeba dodávat,
    že při použití takového postupu je výsledný kód daleko přehlednější
    a vhodnější k případným úpravám.

-   V rámci JSP existují dva základní principy použití zapouzdřených
    funkčností -- jednak architektura JavaBeans, sloužící k práci s
    komponentami, a jednak princip uživatelsky definovaných tagů,
    umožňujících opakované použití funkcí a dalších částí kódu, které
    jsou umístěny v knihovnách tagů, tzv. tag libraries. JSP dále
    podporuje přístup k databázím pomocí JDBC driveru.

-   JSP bychom také mohli považovat za nástupce servletů, vytvořených v
    jazyce Java, ke kterým má JSP velice blízko (JSP je při zpracování
    na serveru převedeno do formy servletu). Při práci se servlety bylo
    však HTML značky potřeba generovat v rámci kódu samotného servletu,
    což nebylo vždy nejlepší řešení. Zpracování JSP stránky probíhá v
    následujících krocích:

1.  Webový server vybavený JSP kontejnerem obdrží požadavek od klienta
    na JSP stránku

2.  Požadovaná JSP stránka je načtena webovým serverem

3.  JSP soubor je zpracován kontejnerem a uveden do podoby servletu -
    HTML tagy jsou převedeny na println příkazy, části JSP převedeny na
    kód v Javě

4.  Je zkompilována třída nově vytvořeného servletu

5.  Kontejner spustí soubor se třídou

6.  Vygenerovaná stránka v podobě HTML je předána klientovi

\

\

Postup práce ve WebMathematica je tedy ten, že nejdříve vytvoříme
webovou stránku pomocí vhodného editoru HTML ,druhým krokem je vložení
vhodných příslušných příkazů WebMathematiky , a posledním krokem je
převedení této upravené stránky na soubor s příponou .jsp .

\

V dalším budeme studovat ukázku jedné takové strany ,která řeší
integrování funkcí :

**Hlavičky stránky s popisky:**

\

\<%@ page language=\"java\" %\>

\<%@ taglib uri=\"/webMathematica-taglib\" prefix=\"msp\" %\>

\<%@ page contentType = \"text/html;charset=windows-1250\" %\>

\

**Hlavičky a tagy HTML:**

\

\<html\>

\<head\>

\<title\>Výpočet integrálu\</title\>

\<meta http-equiv=Content-Type content=\"text/html;
charset=windows-1250\"\>

\</head\>

\

\<body bgcolor=\"White\" text=\"Black\" link=\"#727E9C\"
vlink=\"#004891\"\>

\

**Tag s odkazem na stránky WM:**

\

\<p\>\<b\>Nápověda\</b\>\</p\>

\<ul\>

\<li\>\<a href =
\"http://documents.wolfram.com/webmathematica/\"\>Dokumentace\</a\>

\</ul\>

\

\

**Tag s nápisem:**

\<td vAlign=top align=left width=\"80%\"\>

\<table cellSpacing=1 cellPadding=1 border=0\>

\<tr\>

\<td bgColor=#004182\>\<center\>\<font face=arial,helvetica.sanserif

color=#ffffff\>\<b\>Výpočet primitivní funkce v
\<b\>R\</b\>\</b\>\</font\>\</center\>\<tr\>\<td\>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

\<tr\>

\<td\>

\<blockquote\>

\<div align = justify\>

\

**Vstupní pole :**

\

\<form action=\"integral.jsp\" method=\"post\"\>\<b\>Zadejte
funkci:\</b\>

\<br\>

\

**První spuštění jádra Matematiky (první užití příkazu msp ):**

\

\<msp:allocateKernel\>

\

**Příkaz evaluace , kterým naplňujeme proměnnou před užitím :**

\

\<msp:evaluate\>

\

**Do proměnné integrand je vložena vstupní hodnota Null ( příkaz ukončen
; ):**

\

integrand = Null;

\

**Užití příkazu If , v podmínce užíváme příkaz MSPValueQ, který umožňuje
vyhodnocovat hodnotu proměnné Promena( všimněte si znaků \$\$), jestliže
je tedy něco do proměnné vloženo, tak se hodnota proměnné integrand
naplní hodnotou promena, evaluace se ukončí :**

\

If\[ MSPValueQ\[ \$\$Promena\],

integrand = MSPToExpression\[ \$\$Promena\]\] ;

\</msp:evaluate\>

\

**Textové pole ,do kterého zadáváme funkci na integraci ( implicitní
hodnota funkce je nastavena na
![](SMwebmathematica_i%5B1%5D._html_2be4c3fa.gif){#Object1
align="absmiddle" width="76" height="21"} ) --je spuštěn příkaz pro
evaluaci ,abychom mohli odchytit hodnotu vloženého výrazu :**

\

\<input type=\"text\" name=\"Promena\" size=\"24\"

value=\"\<msp:evaluate\> MSPValue\[ \$\$Promena, \"x\^2 + 2 x +
4\"\]\</msp:evaluate\>\"\>

\

**Použití prvku seznam (k vybrané funkci můžeme přidat funkce z předem
vybraného seznamu funkcí ):**

\

\<select name=\"Vyber\" onChange=\"Promena.value = Promena.value +
Vyber.value\"\>

\<option value=\"\"\>Funkce\</option\>

\<option value=\"x\^b\"\>x na b\</option\>

\<option value=\"b\^x\"\>b na x\</option\>

\<option value=\"E\^x\"\>e na x\</option\>

\<option value=\"Log\[x\]\"\>přirozený logaritmus x\</option\>

\<option value=\"Log\[b,x\]\"\>logaritmus x o základu b\</option\>

\<option value=\"Sin\[x\]\"\>sinus x\</option\>

\<option value=\"Cos\[x\]\"\>cosinus x\</option\>

\<option value=\"Tan\[x\]\"\>tangens x\</option\>

\<option value=\"ArcSin\[x\]\"\>arcussinus x\</option\>

\<option value=\"ArcCos\[x\]\"\>arcuscosinus x\</option\>

\<option value=\"ArcTan\[x\]\"\>arcustangens x\</option\>

\<option value=\"Sinh\[x\]\"\>sinus hyperbolický x\</option\>

\<option value=\"Cosh\[x\]\"\>cosinus hyperbolický x\</option\>

\<option value=\"Tanh\[x\]\"\>tangens hyperbolický x\</option\>

\<option value=\"ArcSinh\[x\]\"\>arcussinus hyperbolický x\</option\>

\<option value=\"ArcCosh\[x\]\"\>arcuscosinus hyperbolický x\</option\>

\<option value=\"ArcTanh\[x\]\"\>arcustangens hyperbolický x\</option\>

\</select\>

\<br\>

\<br\>

\<br\>

\

**Opět spuštěna evaluace , abychom zjistili zda jsme do proměnné je
hodnota proměnné integrand změněna ( na počátku procesu je nastavena na
Null ). V případě , že je do ní vložen nějaký výraz , tedy není rovna
Null, provede se integrace proměnné integrand - Integrate\[integrand,x\]
a výsledek se zobrazí pomocí příkazu Format (MSPFormat ) ve standardním
tvaru :**

\

\<msp:evaluate\>

If\[ integrand =!= Null,

MSPFormat\[Integrate\[integrand,x\], StandardForm\]\]

\</msp:evaluate\>

\

**Ukončena práce práce jádra Mathematica :**

\

\</msp:allocateKernel\>

\<br\>

\<br\>

\

**Tlačítko propuštění výpočtu:**

\

\<input type=\"submit\" name=\"btnSubmit\" value=\"Počítej\"\>

\</form\>

\</div\>\</blockquote\>\</table\>

\<br\>\<script LANGUAGE=\"JavaScript\"\>

\

**Java skript , který vypisuje výsledek na obrazovku:**

\

document.write(document.lastModified)

\</script\>\</ body\>\</html\>

\

V dalším si ukážeme další příklady:

-   1.  Zobrazení grafu funkce pomocí příkazu Plot:

\

\<form action=\"Plot.jsp\" method=\"post\"\>\
**Spuštění jádra Mathematica:\
**\<msp:allocateKernel\>\
Enter a function:

**Zadání funkce implicitně je brána funkce
![](SMwebmathematica_i%5B1%5D._html_f86f6368.gif){#Object2
align="absmiddle" width="19" height="21"} :\
**\<input type=\"text\" name=\"fun\" size=\"24\" value =\
   \"\<msp:evaluate\>MSPValue\[ \$\$fun, \"x[\^]{lang="en-US"}2\"\]\
      \</msp:evaluate\>\"\
/\>

**V předchozím užití příkazu evaluace pomocí MSPValue**

\
Zadejte hodnotu horní meze intervalu:

\

**Zadáváme číslo do proměnné x1 , implicitně je dosazena hodnota 10:**

\
\<input type=\"text\" name=\"x1\" size=\"24\" value =\
   \"\<msp:evaluate\>MSPValue\[ \$\$x1, \"10\"\]\
      \</msp:evaluate\>\"\
/\>\
\<br\>\
\<msp:evaluate\>

\

**Poprvé užíváme příkazů MSPBlock, v nichž můžeme provádět více příkazů
najednou,v našem případě zobrazíme graf funkce fun v intervalu (0 , x1)
pomocí příkazu MSPShow :**

\
   MSPBlock\[ {\$\$fun, \$\$x1},\
      MSPShow\[ Plot\[\$\$fun, {x, 0, \$\$x1}\]\]\]\
\</msp:evaluate\>\
\<hr\>

\

**Ukončení práce jádra:\
**\</msp:allocateKernel\>\
**Vytvoření tlačítka pro spuštění skriptu:\
**\<input type=\"submit\" name=\"btnSubmit\" value=\"Vyčíslení\"\>\
\
\</form\>

\

-   2.  Příklad trojrozměrného grafu:

\

\<%@ page language=\"java\" %\>\
\<%@ taglib uri=\"/webMathematica-taglib\" prefix=\"msp\" %\>\
\
\<html\>\
\<head\>\
\<title\>Live 3D graf\</title\>\
\</head\>\
\
\<body text=\"#171717\" bgcolor = \"#ffffff\"\>\
\<msp:allocateKernel\>\
**Spuštění jádra:\
**\<msp:evaluate\>\
\$ImageBackground = \"#ffffff\";\
\$ImageSize = {300, 300};\
\</msp:evaluate\>\
**Zadání proměnných potřebných pro vytvoření grafu:\
**\<h1\>Live 3D graf\</h1\>\
\<form action=\"Plot3DLive.jsp\" method=\"post\"\>\
Plot3D graf\
\<input type=\"text\" name=\"fun\" size=\"22\" value =\
\"\<msp:evaluate\> MSPValue\[ \$\$fun, \"(x + y )\^2\"\]
\</msp:evaluate\>\"\>\
\<br\>

**Zadání funkce fun, kterou budeme zobrazovat ( implicitně máme funkci
![](SMwebmathematica_i%5B1%5D._html_7ed2e15d.gif){#Object3
align="absmiddle" width="55" height="29"} ):\
**x od:\
\<input type=\"text\" name=\"x0\" size=\"10\" value =\
\"\<msp:evaluate\>MSPValue\[ \$\$x0, \"-2\"\] \</msp:evaluate\>\"\>

**Zadáváme rozsah proměnné x a dále proměnné y (rozsahy načítáme do
proměnných x0-implicitně -2,x1-implicitně
2,y0-implicitně-2,y1-implicitně2):\
**do:\
\<input type=\"text\" name=\"x1\" size=\"10\" value =\
\"\<msp:evaluate\>MSPValue\[ \$\$x1, \"2\"\] \</msp:evaluate\>\"\>\
\<br\>\
y od:\
\<input type=\"text\" name=\"y0\" size=\"10\" value =\
\"\<msp:evaluate\>MSPValue\[ \$\$y0, \"-2\"\] \</msp:evaluate\>\"\>\
do:\
\<input type=\"text\" name=\"y1\" size=\"10\" value =\
\"\<msp:evaluate\>MSPValue\[ \$\$y1, \"2\"\] \</msp:evaluate\>\"\>\
\<br\>\
Počet zobrazovacích bodů grafu:\
\<input type=\"text\" name=\"pts\" size=\"5\" value =\
\"\<msp:evaluate\>MSPValue\[ \$\$pts, \"20\"\] \</msp:evaluate\>\"\>\
\<br\>

**Nyní máme zadané všechny proměnné pro zobrazení grafu :\
**\<msp:evaluate\>\
   MSPBlock\[ {\$\$fun, \$\$x0, \$\$x1, \$\$y0, \$\$y1, \$\$pts},\
         MSPLive3D\[\
            Plot3D\[\$\$fun,\
            {x, \$\$x0, \$\$x1}, {y, \$\$y0, \$\$y1}, PlotPoints -\>
\$\$pts\]\]\]\
\</msp:evaluate\>

**V MSPBlock používáme příkaz MSPLive3D pro zobrazení Plot3D s danými
parametry:\
**\<br\>\<hr\>\
\<input type=\"submit\" name=\"btnSubmit\" value=\"Evaluate\"\>\
\</form\>

**Ukončení práce jádra:\
**\</msp:allocateKernel\>\
\</body\>\
\</html\>

\

-   3.  Práce se soubory -- výstup dat do souboru:

\

\<html\>\
\<head\>\
\<title\>Natažení dat ze souboru\</title\>\
\</head\>\
\<body\>\
\<p\>\
Obsah souboru:\
\</p\>\
\<br\>\
\<pre\>

**V dalším je spouštěn Mathlet -- Servlet , kterým můžeme psát také
rovnou příkazy v MathScriptu:\
**\<%Mathlet\
   file = \"FileName\" /. MSPGetUploadFile\[\];\
   Read\[ file, Record, RecordSeparators-\> {}\]\
%\>\
\</pre\>\
\
\<p\>\
\<a href=\"Natažení souboru\"\>Další soubor?\</a\>\
\</p\>\
\
\</body\>\
\</html\>

\

Popis dvou základních příkazů Mathematica převedených tagů MSP

\

A.  MSPBlock\[{pr1,pr2,...},příkazy , volitelně výstupní *hodnota*\]

\$\$hodnota="6+5";

MSPBlock\[{\$\$hodnota},{Hold\[\$\$hodnota\],\$\$hodnota}\]

Výsledkem tohoto příkazu je

{Hold\[6+5\],11}

B.  MSPFormat\[výraz,volitelně ve stylu *st*, volitelně výstupní
    *tvar*\]

To je jeden ze způsobů jak formátovat výstup ve WM . Příklady :

MSPFormat\[x+y,OutputForm\]

MSPFormat\[Sin\[x\]+Sin\[y\],StandardForm\]

MSPFormat\[Sin\[x\]+Sin\[y\],StandardForm,"Gif"\]

MSPFormat\[Sin\[x\]+Sin\[y\],MathMLForm\]

\

Ostatní příkazy ponechávám k nahlédnutí do základního
[[manuálu](http://www.wolfram.com/products/webmathematica/index.html)]{.underline}
WM.
