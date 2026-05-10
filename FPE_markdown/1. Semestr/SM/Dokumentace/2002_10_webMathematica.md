---
title: "2002_10_webMathematica.pdf"
source: "/mnt/f/git/mgr/FPE_navazujici/1. Semestr/SM/Dokumentace/2002_10_webMathematica.pdf"
date: 2008-08-25
type: PDF (text-based)
---

webMathematica
Článek pro časopis Automatizace
Ladislav Prskavec
Katedra elektroenergetiky, Fakulta elektrotechniky ČVUT, Technická 2, 166 27 Praha 6
Email: xprskave@fel.cvut.cz, Web: http://prskavec.zde.cz
Abstrakt: Článek pojednává o produktu fy Wolfram Research webMathematica [1]. Ukazuje rozdíly
mezi stávajícím programem Mathematica a novým produktem webMathematica. Mathematica je
široce známý program pro technické a vědecké výpočty, nejnověji je ve verzi 4.2, nová verze přináší
další rozšíření stávající produktu jako např. přináší nové funkce a vylepšenou konektivitu s Javou,
XML, webem a další [2].

1. Úvod
Produkt webMathematica nám umožňuje přenést vytvořené notebooky z programu
Mathematica na web. Lidé, co používají Mathematicu pro svoji práci, poskytnou výsledky svoje
práce ke zveřejnění a prohlížení i lidem, co nemají Mathematicu, vystačí si s webovým prohlížečem
(Internet Explorer 5 a 6, Netscape Navigator 5 a 6).

Obr 1.1 - Příklad 1 v Mathematica 4.2

Obr 1.2 - Příklad 1 ve webMathematice

Na obr.1.1 je vidět Mathematica notebook, ve kterém je tento jednoduchý příklad:
Plot[{x^2, 6*Sin[x]}, {x, -Pi, Pi}, PlotStyle -> {GrayLevel[0],
Hue[0]}, AxesLabel -> {"x", "y"}]
Plot3D[Sin[x y], {x, 0, 4}, {y, 0, 4}, PlotPoints -> 40, Mesh ->
False, FaceGrids -> All, AxesLabel -> {"Length", "Width",
"Height"}];
Příklad 1 - Mathematica Notebook

Na obr. 1.2 je vidět příklad 1, jak ho umí zobrazit webový prohlížeč, když ho vytvoříme pomocí
MSP (Mathematica Server Pages). Obdoba notebooku ve webMathematice je webová stránka
v HTML kombinovaná s Mathlet tagy (vyznačené v kódu červeně) a kódem v Matematice
(vyznačené v kódu zeleně).
<h1 align=center>Example 01 - Plot</h1>
<hr>
<div align=center class=sZakladni>Plot[{x^2, 6*Sin[x]}, {x, -Pi,
Pi}, PlotStyle -> {GrayLevel[0], Hue[0]}, AxesLabel -> {"x",
"y"}]</div>
<div align=center>
<%Mathlet MSPShow[Plot[{x^2, 6*Sin[x]}, {x, -Pi, Pi}, PlotStyle ->
{GrayLevel[0], Hue[0]},
AxesLabel -> {"x", "y"}]] %>
</div><br><br>
<div align=center class=sZakladni>Plot3D[Sin[x y], {x, 0, 4}, {y,
0, 4}, PlotPoints -> 40, Mesh -> False,FaceGrids -> All, AxesLabel
-> {"Length", "Width", "Height"}]]</div>
<div align=center>
<%Mathlet MSPShow[Plot3D[Sin[x y], {x, 0, 4}, {y, 0, 4},
PlotPoints -> 40, Mesh -> False,FaceGrids -> All, AxesLabel ->
{"Length", "Width", "Height"}]] %>
</div>
Příklad 1 - MSP skript

2. Další příklady a možnosti
Pokud bychom používali webMathematicu jen pro reprodukci notebooků tak nám to mnoho
nepřinese. Hlavní výhodou je možnost přidání webových formulářů, to umožňuje modifikování
vstupních veličin pro výpočet realizovaný webMathematicou. Na obr. 2.1 je příklad pro výuku o
Fourierových řadách a tam pomocí formulářů si studenti mohou modifikovat frekvenci, amplitudu
jednotlivých harmonických, měnit počet harmonických a další.

Obr. 2.1 - Příklad 2
V MSP skriptu druhého příkladu je vidět, že přibyly do kódu části, obsahující webový
formulář (modrý text), a dále obsahuje skript jazyk HTML, Mathlet tagy (červený text) a příkazy

Mathematici (zelený text). Protože používáme formuláře, musí se použít syntaxe pomocí příkazu
MSPBlock, která nám umožňuje práci s daty odeslanými z webového formuláře.
<form action="ex03_plot2" method="post">
...
Function:
<input type="text" name="fce" align="left" size="24" value =
"<%Mathlet MSPValue[ $$fce, "{x^2,6*Sin[x],Tan[x]}"] %>">
...
PlotStyle:
<input type="text" name="style" align="left" size="50" value =
"<%Mathlet MSPValue[ $$style, "{RGBColor[0,0,0], RGBColor[1,0,0],
RGBColor[0,0,1]}"] %>">
...
<h3 align=left>Results</h3><div align=center>
<%Mathlet MSPBlock[{$$fce,$$ran,$$xlab,$$ylab,$$style,$$size},
MSPShow[Plot[$$fce, $$ran, PlotStyle -> $$style,ImageSize>$$size,AxesLabel -> {$$xlab,$$ylab} ]] ] %>
</div><br><br><hr>
<input type="submit" name="btnSubmit" value="Evaluate">
</div></form>
Příklad 2 - MSP skript
Na dalších obrázcích jsou další možnosti užití za pomocí webových formulářů, příklad na
obr. 2.2 ukazuje, jak se dá udělat jednoduchý grafický kalkulátor pro kreslení různých 2D funkcí.
Na dalším příkladu (obr. 2.3) je výpočet vlastních čísel matice.

Obr. 2.2
Obr. 2.3
V literatuře na konci článku je uvedena řada odkazů na různé stránky, které využívají
webMathematicu, jak pro vědecké a výukové, tak i pro komerční účely. Možnost vyzkoušet si
webMathematicu má majitel Premier Service automaticky, protože dostane na požádání zdarma
k vyzkoušení webMathematicu Amateur (vlastnosti jsou proti verzi Professional omezeny viz.
informace na stránkách fy Wolfram Research [3]).

3. Technologie MSP
Technologie MSP [4] (Mathematica Server Pages) je založena na Javě a proto funguje na
všech podporovaných platformách. Mám zkušenosti s provozem na Windows 2000/XP za použití
webového serveru Apache (1.3.x), servletového serveru Tomcat (4.0.4) a za použití JDK (j2sdk

1.4.01). Testováno bylo i použití na Linuxu, kde se to po určitých potížích hlavně s Javou a XFree
autorizací podařilo produkt úspěšně zprovoznit.

Obr. 3.1
Na obr. 3.1 je schéma technologie MSP, vše začíná a končí u webového prohlížeče
(browser), který vysílá požadavek (request) na MSP servlet, který zpracuje stránku za použití jádra
(kernel) Mathematici (Mathematica umožňuje běžet na více procesorech a to umožní mít více
kernelů spuštěných a přidělovat je dle požadavků MSP servletu). Po zpracování se zpracovaný
požadavek odešle ke zobrazení webovému prohlížeči (response).

4. Literatura
[1] Wolfram Research – webMathematica web Pages [online] [cit. 15. září 2002] Dostupné na
internetu: <http://www.wolfram.com/products/webmathematica/>.
[2] Wolfram Research – Mathematica, New in 4.2 [online] [cit. 15. září 2002] Dostupné na
internetu: <http://www.wolfram.com/products/mathematica/newin42/>.
[3] Wolfram Research – webMathematica, Amateur x Professional [online] [cit. 15. září 2002]
Dostupné na internetu: <http://www.wolfram.com/products/webmathematica/versions/>.
[4] Wolfram Research – webMathematica, Technology [online] [cit. 15. září 2002] Dostupné na
internetu: <http://www.wolfram.com/products/webmathematica/technology/>.

webMathematica - Internetové příklady
http://www.calc101.com,
http://integrals.wolfram.com,
http://www.hostsrv.com/,
http://faculty.uml.edu/klevasseur/webmathematica/,
http://www.higgins.ucdavis.edu/webmath.php,
http://www.optics.arizona.edu/jcwyant/math.htm,
http://www3.kawase-h.ed.jp/webMathematica/MSP/JLMyProj/Calculation.

